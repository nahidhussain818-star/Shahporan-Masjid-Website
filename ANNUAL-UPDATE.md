# Annual prayer-times refresh — what to do each year

The Shahporan Masjid website has prayer times for one year baked in. Each year, when
the masjid publishes the next year's timetable, the website needs a short refresh.

## What you'll need

- The new year's prayer timetable from the masjid committee, as a Google Sheet
  (same layout as 2026: ALL 24 HR tab with date column + Fajr/Sunrise/Zuhr/Asr (Mithl 2)/
   Maghrib/Isha begins & jamā'ah columns)
- The site folder on your computer
- ~15 minutes

## Steps

1. **Save the year's sheet to your computer.** In the Google Sheet:
   - Click the `ALL 24 HR` tab (or whichever tab has the full year of data)
   - File → Download → Web Page (.html, zipped) — or CSV, or XLSX

2. **Open a chat with Claude** and paste this:

   > "Hi Claude — I need to update the Shahporan Masjid website with next year's prayer
   > times. The masjid gave me a [Google Sheet / HTML file / CSV] with the new timetable.
   > Please convert it into `content/prayer-times.json` and regenerate
   > `prayer-calendar.html` with the embedded data."

   Then attach the file (or share the sheet link).

3. **Claude will:**
   - Parse the file
   - Write a new `content/prayer-times.json` with all 365 (or 366 in leap years) days
   - Regenerate `prayer-calendar.html` with the new year's data embedded
   - Verify a couple of days against the original to make sure it's correct

4. **Apply and push:**
   - Open GitHub Desktop
   - You'll see `content/prayer-times.json` and `prayer-calendar.html` as modified
   - Commit message: `Update prayer times to [YEAR]`
   - Commit to main → Push origin
   - Netlify rebuilds in about a minute

5. **Verify on the live site** — refresh the homepage, check today's times match
   the masjid's printed timetable.

## Notes

- **Asr uses Mithl 2 (Hanafi).** If the masjid ever switches to Shafi'i, that
  column changes — let Claude know.
- **The CMS at `/admin/`** is still available for one-off day adjustments mid-year
  (e.g. Ramadan timing tweaks). Add or edit a single day there without re-running
  the whole annual refresh.
- **The masjid never has to do anything for this** — it's entirely a developer
  (you + Claude) task. The committee just keeps publishing the yearly sheet as
  they normally would.

## If Claude isn't around

The conversion is also documented in your learning roadmap (`learning-roadmap.html`).
By Phase 4-5 of that roadmap, you'll have the Python and JS skills to do this
yourself in ~30 minutes:

1. Parse the HTML/CSV table (Python `html.parser` or `csv` module)
2. Map rows to `{date, fajr, sunrise, dhuhr, asr, maghrib, isha, jamaah_*}` objects
3. Write to `content/prayer-times.json` as `{"days": [...]}`
4. Re-inject into `prayer-calendar.html` (find the `let allDays = [...]` line)

The conversion script Claude used for the 2026 data:

```python
from html.parser import HTMLParser
import json

class T(HTMLParser):
    def __init__(self):
        super().__init__()
        self.rows = []
        self.in_tr = False; self.in_td = False
        self.cur_row = []; self.cur_cell = ''
    def handle_starttag(self, tag, attrs):
        if tag == 'tr':
            self.in_tr = True; self.cur_row = []
        elif self.in_tr and tag in ('td','th'):
            self.in_td = True; self.cur_cell = ''
    def handle_endtag(self, tag):
        if tag == 'tr' and self.in_tr:
            self.in_tr = False; self.rows.append(self.cur_row)
        elif tag in ('td','th') and self.in_td:
            self.in_td = False; self.cur_row.append(self.cur_cell.strip())
    def handle_data(self, data):
        if self.in_td: self.cur_cell += data

MONTHS = {'Jan':1,'Feb':2,'Mar':3,'Apr':4,'May':5,'Jun':6,
          'Jul':7,'Aug':8,'Sep':9,'Oct':10,'Nov':11,'Dec':12}

YEAR = 2027   # ← update this each year

def parse_date(s):
    parts = s.strip().split()
    if len(parts) != 2: return None
    try:
        day = int(parts[0]); month = MONTHS.get(parts[1])
        return f"{YEAR}-{month:02d}-{day:02d}" if month else None
    except: return None

def parse_time(s):
    s = (s or '').strip()
    if not s or ':' not in s: return ''
    h, m = s.split(':')[:2]
    return f"{int(h):02d}:{int(m):02d}"

p = T()
with open('NEW-YEAR-TIMETABLE.html') as f: p.feed(f.read())

days = []
for r in p.rows:
    if len(r) < 15: continue
    date = parse_date(r[1])
    if not date: continue
    days.append({
        "date": date,
        "fajr":    parse_time(r[3]),
        "sunrise": parse_time(r[5]),
        "dhuhr":   parse_time(r[6]),
        "asr":     parse_time(r[9]),
        "maghrib": parse_time(r[11]),
        "isha":    parse_time(r[13]),
        "jamaah_fajr":    parse_time(r[4]),
        "jamaah_dhuhr":   parse_time(r[7]),
        "jamaah_asr":     parse_time(r[10]),
        "jamaah_maghrib": parse_time(r[12]),
        "jamaah_isha":    parse_time(r[14])
    })

json.dump({"month_label": f"Full year {YEAR}", "days": days},
          open('content/prayer-times.json','w'),
          indent=2, ensure_ascii=False)

print(f"Done — {len(days)} days written")
```

May Allah accept this work for everyone who maintains it. Bismillah.
