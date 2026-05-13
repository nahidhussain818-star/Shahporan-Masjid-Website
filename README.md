# Shahporan Masjid — Website Upgrade

A single-file, modern static rebuild of the Shahporan Masjid website. Everything
lives inside `index.html` (HTML + Tailwind via CDN + vanilla JS). No build step,
no framework, no dependencies to install.

## What's included

Every section from the original site, plus four new features you asked for:

- **Live next-prayer countdown** in the top bar
- **Events & announcements** section (editable list)
- **Hijri date** alongside Gregorian in the top bar
- **Dark mode toggle** (remembers the user's choice)

All existing pages have been consolidated as anchored sections on one scrollable
page: Home, About, Prayer Times, Madrasah, Weekly Circles, Activities, Events,
About Islam, Downloads, Donate, Contact, Newsletter, Footer.

## Hosting

Just upload `index.html` anywhere. Recommended free options:

- **Netlify** — drag-and-drop the file at app.netlify.com/drop
- **Vercel** — `vercel deploy` after putting the file in a folder
- **GitHub Pages** — push to a repo, enable Pages in settings
- **Cloudflare Pages** — connect a repo or upload directly
- Or any cheap shared host (Hostinger, Namecheap, etc.) — just FTP the file

To keep the existing domain `shahporanmasjid.uk`, point its A/CNAME record at
your new host once you're ready to switch over.

## Wiring up MasjidBox (proper)

MasjidBox does **not** offer a public JSON API ([their support article](https://support.masjidbox.com/does-masjidbox-have-a-public-api-for-prayer-times-sfnfd)),
so prayer-time data comes from two sources:

1. **The MasjidBox iframe** — embedded directly in the Prayer Times section.
   Always shows the masjid's exact official times.
2. **The per-prayer cards + countdown** — these need numeric data, so they
   use the Aladhan API as a fallback, **OR** values you paste in manually.

The fallback is now configured for **UK + Hanafi**:
- Coordinates: 51.5292°N, -0.0686°E (Hackney)
- Method: 3 (Muslim World League)
- Asr: Hanafi (later)

If those still don't match the masjid's printed times, you have two options:

### Option A — paste the official MasjidBox widget

1. Log into your MasjidBox admin → **Settings → Embed / Widget**
2. Copy the embed snippet (usually `<script>` + `<masjidbox-widget>`)
3. In `index.html` find `★ MASJIDBOX WIDGET PLACEHOLDER ★`
4. Replace the `<iframe>` below it with that snippet

The full monthly timetable will then render natively in MasjidBox's own UI.

### Option B — manually set the cards/countdown times (most accurate)

Open `index.html`, search for `MASJID_MANUAL_TIMES` and set it to the day's
times from MasjidBox / your printed timetable:

```js
window.MASJID_MANUAL_TIMES = {
  Fajr:'04:23', Sunrise:'05:50', Dhuhr:'13:05', Asr:'17:45',
  Maghrib:'20:15', Isha:'21:45',
  jamaah: { Fajr:'05:00', Dhuhr:'13:30', Asr:'18:00', Maghrib:'20:20', Isha:'22:00' }
};
```

Or set a full month at once via `window.MASJID_MONTHLY_TIMES` (keyed by
`YYYY-MM-DD`). The site will pick today's entry automatically.

### Tuning the API method

If you want to try a different calculation than MWL, change `PRAYER_API.method`
in `index.html`. UK options that some masjids use:

| Method | Name | When |
| :--- | :--- | :--- |
| 3 | Muslim World League (default) | General UK use |
| 15 | Moonsighting Committee Worldwide | Some UK Hanafi masjids |
| 8 | Gulf Region | Some Gulf-aligned masjids |
| 5 | Egyptian General Authority | Older convention |

## Editing the site

Open `index.html` in any text editor. The most common edits:

| What to change                | Where                                           |
| ------------------------------ | ----------------------------------------------- |
| Jumu'ah times                  | Hero card — search "1:20 PM" and "2:10 PM"     |
| Events list                    | `window.MASJID_EVENTS` array near bottom of JS |
| Downloads list                 | `window.MASJID_DOWNLOADS` array                |
| Jamā'ah offsets                | `JAMAAH_OFFSETS` object in JS                  |
| Phone / email / address        | Contact section                                |
| Bank details                   | Donate section + Footer                        |
| Colours                        | `tailwind.config` block in `<head>`            |

## Forms

- **Contact form** — currently opens the user's email client (mailto). To use a
  hosted backend, swap to [Formspree](https://formspree.io),
  [Web3Forms](https://web3forms.com), or Netlify Forms by changing the form's
  `action` and `method` attributes.
- **Newsletter** — currently a client-side stub. Connect Mailchimp / Buttondown
  / Brevo by replacing the submit handler at the bottom of the JS.

## Accessibility & SEO

- Semantic HTML5 (`header`, `nav`, `section`, `footer`)
- Proper alt text, ARIA labels on icon buttons
- Mobile-friendly with a slide-down menu
- Meta description + theme-color set
- Smooth scroll-spy nav highlighting
- Respects user's OS-level dark-mode preference on first visit

## File

The complete site is `index.html` — open it directly in a browser to preview.
