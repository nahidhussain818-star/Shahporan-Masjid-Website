# From Zero → Building Websites Like a Pro

A complete, free, self-paced roadmap that takes you from never having coded a line to confidently rebuilding the Shahporan Masjid site yourself — and going beyond.

**Estimated time:** ~5–7 months at 1–2 focused hours/day. Longer is fine. Skipping is not — every phase builds on the last.

---

## How to use this document

1. Work through the phases **in order**. Resist the urge to jump ahead.
2. Each phase has three parts:
   - **Concepts** — a checklist of things you must understand. Tick them off as you genuinely grasp each one (not just read about it).
   - **Resources** — free courses, docs, and videos. You don't need all of them. Pick one main course and use the rest as reference.
   - **Project + Self-test** — the only way to know you've learned it is to build something with it.
3. **Don't move on until the project works without you copy-pasting from a tutorial.** This is the single most important rule. Tutorial code feels like learning; building from scratch *is* learning.
4. Keep a notebook (paper or digital). Write down anything that confuses you, then come back to those notes a week later — if it now makes sense, you've actually learned it.

---

## Phase 0 — Setup & Mindset (Week 1)

Before you write any code, get your environment right and understand what you're working with.

### Concepts

- [ ] How the web works at a high level: client/server, HTTP request/response, URL → DNS → server → HTML → browser renders
- [ ] What a "front-end" vs "back-end" vs "full-stack" developer does
- [ ] What HTML, CSS, and JavaScript each do (structure / style / behaviour)
- [ ] What a "framework" is and why people use them
- [ ] What "open source" means

### Tools to install

- [ ] **VS Code** — the editor (free): https://code.visualstudio.com
- [ ] **Google Chrome or Firefox** — and learn to open **DevTools** (right-click → Inspect)
- [ ] **Git** — version control: https://git-scm.com (we'll use it properly in Phase 4)
- [ ] **A GitHub account** — https://github.com (free)
- [ ] **Node.js** (LTS version) — https://nodejs.org (you won't use it heavily yet, but it's needed later)

### VS Code extensions worth installing

- [ ] Live Server (auto-reloads your HTML in the browser as you save)
- [ ] Prettier (auto-formats your code)
- [ ] Tailwind CSS IntelliSense (much later — but install now)

### Resources

- **How the Internet Works** (video, 13 min) — https://www.youtube.com/watch?v=7_LPdttKXPc
- **MDN: How the Web Works** — https://developer.mozilla.org/en-US/docs/Learn_web_development/Getting_started/Web_standards/How_the_web_works
- **The Odin Project — Foundations: Introduction** — https://www.theodinproject.com/paths/foundations/courses/foundations

### Self-test

You can explain in your own words, out loud, what happens between typing `google.com` and seeing the page load. If you can't, watch the video again.

---

## Phase 1 — HTML: The Skeleton (Weeks 2–3)

HTML is the structure of every web page. Once you internalise it, it never changes much.

### Concepts

- [ ] Document structure: `<!doctype html>`, `<html>`, `<head>`, `<body>`
- [ ] The role of `<head>`: `<title>`, `<meta>` tags, linking CSS and JS
- [ ] Block vs inline elements
- [ ] Headings `<h1>`–`<h6>` and why hierarchy matters
- [ ] Paragraphs, links, images, lists (`<ul>`, `<ol>`, `<li>`)
- [ ] Semantic tags: `<header>`, `<nav>`, `<main>`, `<section>`, `<article>`, `<aside>`, `<footer>`
- [ ] Attributes: `id`, `class`, `href`, `src`, `alt`, `target`, `rel`
- [ ] Forms: `<form>`, `<input>` (all types — text, email, password, checkbox, radio, file), `<textarea>`, `<button>`, `<label>`, `<select>`
- [ ] Tables (rarely used for layout now, but useful for data): `<table>`, `<tr>`, `<td>`, `<th>`
- [ ] Embedding: `<iframe>`, `<video>`, `<audio>`
- [ ] Accessibility basics: alt text, label-for-input pairing, ARIA labels, keyboard navigation
- [ ] Validating HTML: https://validator.w3.org

### Resources (pick one main course)

- **MDN — Introduction to HTML** (the gold standard reference) — https://developer.mozilla.org/en-US/docs/Learn_web_development/Core/Structuring_content
- **freeCodeCamp — Responsive Web Design** (first few sections) — https://www.freecodecamp.org/learn/2022/responsive-web-design/
- **The Odin Project — HTML Foundations** — https://www.theodinproject.com/lessons/foundations-introduction-to-html-and-css

### Project + self-test

- [ ] **Build a personal homepage** — just HTML, no styling yet. Include: header with your name, nav menu (4 sections), an "About me" section, a list of hobbies, a contact form (it doesn't need to work), and a footer. Use semantic tags. Make it pass the W3C validator with zero errors.
- [ ] **Without looking anything up**, write the skeleton of an HTML page from memory. Include doctype, language attribute, charset, viewport, title, and a body with semantic structure.

---

## Phase 2 — CSS: The Look (Weeks 4–7)

CSS is where most beginners struggle. Don't rush this phase. The masjid site lives or dies by good CSS.

### Concepts — fundamentals

- [ ] How to link a CSS file (`<link rel="stylesheet">`)
- [ ] Selectors: element, class, ID, descendant, child, sibling
- [ ] Specificity & the cascade (why your style isn't being applied)
- [ ] The box model: content, padding, border, margin
- [ ] `box-sizing: border-box` — and why you should set it on `*`
- [ ] Units: `px`, `%`, `em`, `rem`, `vh`, `vw`, `fr`
- [ ] Colours: hex, rgb, hsl, rgba, named, `currentColor`
- [ ] Typography: `font-family`, `font-size`, `font-weight`, `line-height`, `letter-spacing`
- [ ] Web fonts via Google Fonts
- [ ] Pseudo-classes: `:hover`, `:focus`, `:active`, `:first-child`, `:nth-child()`, `:not()`
- [ ] Pseudo-elements: `::before`, `::after`

### Concepts — layout (the hardest part)

- [ ] `display`: `block`, `inline`, `inline-block`, `none`
- [ ] `position`: `static`, `relative`, `absolute`, `fixed`, `sticky`
- [ ] `z-index` and stacking contexts
- [ ] **Flexbox** (master this — used everywhere in the masjid site)
  - `flex-direction`, `justify-content`, `align-items`, `gap`, `flex-wrap`, `flex-grow`, `flex-shrink`, `flex-basis`
- [ ] **CSS Grid** (also used heavily)
  - `grid-template-columns`, `grid-template-rows`, `gap`, `grid-column`, `grid-row`, `grid-area`
- [ ] When to use Flexbox vs Grid (rule of thumb: Flexbox for 1D, Grid for 2D)

### Concepts — modern CSS

- [ ] **Responsive design** with media queries (`@media (min-width: 768px) { ... }`)
- [ ] Mobile-first vs desktop-first approach (mobile-first wins)
- [ ] CSS Custom Properties (variables): `--main-color: #0e5c3b;` and `var(--main-color)`
- [ ] Transitions: `transition: all 0.3s ease`
- [ ] Animations: `@keyframes` and `animation`
- [ ] Transforms: `translate`, `rotate`, `scale`
- [ ] Shadows: `box-shadow`, `text-shadow`
- [ ] Gradients: `linear-gradient`, `radial-gradient`
- [ ] Backgrounds: `background-image`, `background-size`, `background-position`, multi-layer backgrounds
- [ ] `filter` and `backdrop-filter` (frosted glass effect)

### Resources

- **MDN — CSS first steps** — https://developer.mozilla.org/en-US/docs/Learn_web_development/Core/Styling_basics
- **CSS Tricks — A Complete Guide to Flexbox** (bookmark forever) — https://css-tricks.com/snippets/css/a-guide-to-flexbox/
- **CSS Tricks — A Complete Guide to Grid** — https://css-tricks.com/snippets/css/complete-guide-grid/
- **Kevin Powell on YouTube** (the best CSS teacher alive, free) — https://www.youtube.com/@KevinPowell
- **Flexbox Froggy** (game — learn Flexbox in 30 minutes) — https://flexboxfroggy.com
- **Grid Garden** (game for CSS Grid) — https://cssgridgarden.com
- **freeCodeCamp Responsive Web Design** (finish the whole course) — https://www.freecodecamp.org/learn/2022/responsive-web-design/

### Projects + self-tests

- [ ] **Restyle your Phase 1 homepage.** Make it look genuinely professional. Use Flexbox or Grid for layout. Make it responsive (looks good on phone and desktop).
- [ ] **Build a card component** with a hover effect, shadow, transition, and a subtle border. (Like the prayer cards on the masjid site.)
- [ ] **Recreate a simple webpage** you admire. Screenshot a real site → recreate it in HTML/CSS without looking at their code. (Frontend Mentor has free challenges with designs: https://www.frontendmentor.io)
- [ ] **From memory**, write the CSS to centre a div horizontally and vertically on the page using Flexbox.

---

## Phase 3 — JavaScript: The Brain (Weeks 8–18)

This is the biggest phase. JS is what makes the prayer countdown tick, the dark-mode toggle work, the events list render, and the API data load. Don't rush.

### Concepts — fundamentals

- [ ] Where JS runs: in a `<script>` tag or `.js` file
- [ ] `console.log()` and the browser's DevTools console
- [ ] Variables: `let`, `const`, (avoid `var`)
- [ ] Data types: `string`, `number`, `boolean`, `null`, `undefined`, `object`, `array`
- [ ] Operators: arithmetic, comparison (`===` vs `==`), logical (`&&`, `||`, `!`), ternary
- [ ] String methods: `.length`, `.split()`, `.slice()`, `.replace()`, `.includes()`, template literals (`` `hello ${name}` ``)
- [ ] Conditionals: `if / else if / else`, `switch`
- [ ] Loops: `for`, `while`, `for...of`, `forEach`
- [ ] Functions: declarations, expressions, **arrow functions** (`() => {}`)
- [ ] Scope: global vs function vs block
- [ ] Arrays: `.push`, `.pop`, `.shift`, `.unshift`, `.map`, `.filter`, `.reduce`, `.find`, `.includes`, `.sort`
- [ ] Objects: keys, values, dot vs bracket notation, destructuring
- [ ] The spread operator (`...`)
- [ ] Truthy vs falsy values

### Concepts — DOM manipulation

This is what lets your code interact with the page.

- [ ] `document.querySelector()` and `querySelectorAll()`
- [ ] `getElementById()` (older but still common)
- [ ] Reading and changing element content: `.textContent`, `.innerHTML`
- [ ] Reading and changing attributes: `.getAttribute()`, `.setAttribute()`, `.classList.add/remove/toggle/contains`
- [ ] Reading and changing styles: `.style.color = 'red'`
- [ ] Creating and inserting elements: `document.createElement()`, `.appendChild()`, `.innerHTML +=`
- [ ] **Events**: `.addEventListener('click', handler)` — and the full list (click, submit, input, change, keydown, scroll)
- [ ] The event object: `event.target`, `event.preventDefault()`

### Concepts — async & APIs (critical for the masjid site)

- [ ] What "async" actually means and why JS is single-threaded
- [ ] Callbacks (the old way — understand them, but prefer the next two)
- [ ] **Promises**: `.then()`, `.catch()`
- [ ] **`async` / `await`** (modern, much cleaner)
- [ ] **The Fetch API**: `fetch('https://api...').then(r => r.json())`
- [ ] What JSON is and how to read/write it
- [ ] Reading data from a public API (the masjid site does this with Aladhan)
- [ ] Error handling with `try / catch`
- [ ] CORS (when fetch fails for "weird" reasons, this is usually why)

### Concepts — modern browser APIs

These are all used in the masjid site:

- [ ] `localStorage` (used for dark-mode preference)
- [ ] `setInterval` and `setTimeout` (used for the countdown)
- [ ] `IntersectionObserver` (used for scroll-reveal animations)
- [ ] `Intl.DateTimeFormat` (used for the Hijri date)
- [ ] Form handling: `FormData`, `submit` events, `e.preventDefault()`

### Concepts — code quality

- [ ] Code organisation: short functions, descriptive names
- [ ] When to comment vs let code self-document
- [ ] Reading other people's code (you'll do this constantly)

### Resources (pick ONE main, use the rest for reference)

- **JavaScript.info** (best free written course on the language, period) — https://javascript.info
- **freeCodeCamp — JavaScript Algorithms and Data Structures** — https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/
- **The Odin Project — JavaScript** — https://www.theodinproject.com/paths/foundations/courses/foundations#javascript-basics
- **Wes Bos — JavaScript30** (30 free vanilla-JS projects) — https://javascript30.com
- **MDN — JavaScript Guide** — https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide
- **Net Ninja YouTube — Modern JavaScript** — https://www.youtube.com/playlist?list=PL4cUxeGkcC9haFPT7J25Q9GRB_ZkFrQAc
- **Practice: Codewars** — https://www.codewars.com (start at 8 kyu)
- **Practice: Exercism** — https://exercism.org/tracks/javascript

### Projects + self-tests

Build these in order. Each one teaches something specific.

- [ ] **Counter** — a button that increments/decrements a number. (DOM, events.)
- [ ] **To-do list** — add, remove, mark complete. Save to localStorage so it survives reload. (Arrays, events, localStorage.)
- [ ] **Tip calculator** — input bill, % tip → output total per person. (Form handling, numbers.)
- [ ] **Weather app** — user types a city, you `fetch()` weather from a free API (try https://open-meteo.com — no API key needed). (Fetch, async/await, JSON.)
- [ ] **Quote generator** — fetch a random quote from https://api.quotable.io on a button click. (Fetch.)
- [ ] **Image carousel** — left/right arrows to flip through images. (DOM, events.)
- [ ] **Stopwatch / countdown timer** — start, stop, reset. (setInterval, setTimeout — this is exactly the prayer countdown.)
- [ ] **Dark-mode toggle** — toggle a class on `<html>`, remember choice in localStorage. (This is straight from the masjid site.)

### Final self-test

Without looking at the masjid site code: write a JS function that takes today's date, fetches prayer times from `https://api.aladhan.com/v1/timings/...` for London, and console.logs them. If you can do that from scratch, you've nailed Phase 3.

---

## Phase 4 — Git & GitHub (Week 19)

Short but essential. You need this before deploying.

### Concepts

- [ ] What version control is and why it matters
- [ ] `git init`, `git status`, `git add`, `git commit`
- [ ] `git log`, `git diff`
- [ ] Branches: `git branch`, `git checkout`, `git merge`
- [ ] Remotes: `git remote add origin ...`, `git push`, `git pull`
- [ ] Cloning: `git clone`
- [ ] `.gitignore`
- [ ] Pushing to GitHub
- [ ] Pull requests
- [ ] Reading a commit history
- [ ] Fixing the "oh no I committed something I shouldn't have" situation

### Resources

- **The Odin Project — Foundations: Git Basics** — https://www.theodinproject.com/lessons/foundations-git-basics
- **GitHub's interactive Git tutorial** — https://learngitbranching.js.org (excellent, gamified)
- **MDN — Git** — https://developer.mozilla.org/en-US/docs/Learn/Tools_and_testing/GitHub
- **Cheat sheet (bookmark)** — https://education.github.com/git-cheat-sheet-education.pdf

### Project

- [ ] Take **every project you've built so far** and push each one to its own GitHub repository with a README.

---

## Phase 5 — Tailwind CSS (Weeks 20–21)

The masjid site uses Tailwind extensively. You should only start Tailwind **after** you understand vanilla CSS. Otherwise it'll feel like magic and you won't know how to fix things when they break.

### Concepts

- [ ] What "utility-first CSS" means and why people argue about it
- [ ] Loading Tailwind via the CDN (no build step) vs proper install
- [ ] Layout utilities: `flex`, `grid`, `gap-*`, `items-*`, `justify-*`
- [ ] Spacing utilities: `p-*`, `m-*`, `px-*`, `space-x-*`
- [ ] Typography: `text-*`, `font-*`, `leading-*`, `tracking-*`
- [ ] Colours and the design system: `bg-*`, `text-*`, opacity (`/50`, `/80`)
- [ ] Responsive prefixes: `md:flex`, `lg:grid-cols-3`
- [ ] Hover/focus states: `hover:bg-blue-700`
- [ ] Dark mode: `dark:bg-gray-900`
- [ ] Customising the config (`tailwind.config`) — adding colours, fonts
- [ ] Extracting components when classes get too long
- [ ] Mixing Tailwind with regular CSS (the masjid site does this)

### Resources

- **The Tailwind docs themselves** (genuinely some of the best docs ever written) — https://tailwindcss.com/docs
- **Net Ninja — Tailwind Tutorial** — https://www.youtube.com/playlist?list=PL4cUxeGkcC9gpXORlEHjc5bgnIi5HEGhw
- **Tailwind Play** (playground) — https://play.tailwindcss.com

### Project

- [ ] **Convert one of your earlier projects** from vanilla CSS to Tailwind. Notice how much shorter the code gets — and where it gets harder.

---

## Phase 6 — APIs & Working with Data (Week 22)

You already touched this in Phase 3. Now go deeper.

### Concepts

- [ ] REST API basics: GET, POST, PUT, DELETE
- [ ] Reading API docs (Aladhan, Open-Meteo, GitHub, etc.)
- [ ] Query parameters vs path parameters
- [ ] API keys: when needed, how to keep them out of public repos
- [ ] Rate limiting
- [ ] Caching responses (so you don't hammer the server)
- [ ] Handling errors gracefully

### Free APIs to play with

- [ ] **Open-Meteo** (weather, no key) — https://open-meteo.com
- [ ] **Aladhan** (prayer times — what the masjid site uses) — https://aladhan.com/prayer-times-api
- [ ] **PokeAPI** (silly but fun) — https://pokeapi.co
- [ ] **GitHub API** — https://docs.github.com/en/rest

### Project

- [ ] **Mini prayer-time card** — for any UK city the user types in, fetch the times and display the next one with a countdown. This is 80% of what the masjid site does. If you can build this, you can build the masjid site.

---

## Phase 7 — Hosting, Domains & Deployment (Week 23)

### Concepts

- [ ] Static hosting vs server hosting
- [ ] What a "build step" is
- [ ] DNS: A records, CNAME records, nameservers
- [ ] HTTPS / SSL certificates (free with Let's Encrypt)
- [ ] How to point a domain at a host

### Free hosts (pick one to start)

- [ ] **Netlify** — drag-and-drop or Git-connected. The easiest. https://www.netlify.com
- [ ] **Vercel** — similar to Netlify, great for Next.js later. https://vercel.com
- [ ] **GitHub Pages** — built into GitHub, perfect for portfolios. https://pages.github.com
- [ ] **Cloudflare Pages** — fast and free. https://pages.cloudflare.com

### Resources

- **Netlify Drop** — https://app.netlify.com/drop (literally drag a folder)
- **Setting up a custom domain** — https://docs.netlify.com/domains-https/custom-domains/

### Project

- [ ] **Deploy every project you've built** to Netlify or GitHub Pages. Share the links somewhere (maybe with me, your mum, the masjid committee — anyone).
- [ ] **Buy a cheap domain** (around £8/year on Namecheap, Cloudflare Registrar, or Porkbun) and point it at one of your projects. This single skill is what makes it feel real.

---

## Phase 8 — CAPSTONE: Rebuild the Masjid Site (Weeks 24–28)

This is your test. Build the site **from scratch**, looking at my version only when you're genuinely stuck — and even then, understand the code before copying anything.

### Stages

- [ ] Start with a blank `index.html` and a `<title>`
- [ ] Build the structure with semantic HTML — every section, no styling
- [ ] Add Tailwind via CDN and style the header + nav
- [ ] Build the hero section (try to recreate the layout I used)
- [ ] Build the prayer times grid — start with hardcoded times, then add the Aladhan fetch
- [ ] Add the next-prayer countdown banner using `setInterval`
- [ ] Add the dark-mode toggle with localStorage
- [ ] Add the Hijri date with `Intl.DateTimeFormat`
- [ ] Build the Activities / Events / Downloads sections (you'll need JS templating)
- [ ] Build the contact form
- [ ] Add the MasjidBox iframe
- [ ] Add the footer
- [ ] Deploy to Netlify
- [ ] Add a custom domain (or use the Netlify subdomain)

### Self-test

Look at your version side-by-side with mine. Where are mine better? Where might yours be better? Pick **one thing** to improve in your version that mine doesn't have.

---

## Phase 9 — Going Further

You're now beyond beginner. From here, branch out based on what excites you.

### Path A — Modern frontend (most common next step)

The masjid site is "vanilla". Modern dev usually means using a framework.

- [ ] **React** — the most popular framework. Start with the official tutorial: https://react.dev/learn
- [ ] **Next.js** — React + routing + server-side rendering + production tooling: https://nextjs.org/learn
- [ ] **TypeScript** — JavaScript with types. Painful at first, addictive once you get it: https://www.typescriptlang.org/docs/handbook/intro.html
- [ ] **Component libraries**: shadcn/ui (https://ui.shadcn.com), Radix UI, Headless UI

Resources:
- **The Odin Project — Full Stack JavaScript path** — https://www.theodinproject.com/paths/full-stack-javascript
- **Scrimba — Learn React for free** — https://scrimba.com/learn/learnreact

### Path B — Backend with Node.js

The masjid contact form just opens an email client. A real backend would actually send the email, store messages, manage users, etc.

- [ ] Node.js basics — running JS outside the browser
- [ ] `npm` and `package.json`
- [ ] **Express.js** — minimal web framework
- [ ] **REST API design** — building your own APIs
- [ ] **Databases**: start with SQLite, then PostgreSQL
- [ ] **Authentication**: sessions, JWTs, OAuth
- [ ] **Deployment**: Render, Railway, Fly.io (all have free tiers)

Resources:
- **The Odin Project — Node.js course** — https://www.theodinproject.com/paths/full-stack-javascript/courses/nodejs
- **Express docs** — https://expressjs.com

### Path C — Python (you asked about this)

Python is *not* used for frontend web, but it's the best second language because it teaches you to think programmatically and is dominant in scripting, data, AI, and automation.

- [ ] **Python basics** — syntax, types, control flow, functions, lists, dicts
- [ ] **Standard library** — `os`, `sys`, `json`, `requests`
- [ ] **File handling, CSV, working with APIs**
- [ ] **Automation** — scripts that do useful stuff (the joy of Python)
- [ ] **Web with Python**: **Flask** (small, easy) or **Django** (huge, batteries-included)
- [ ] **Data**: `pandas`, `numpy`, `matplotlib`
- [ ] **AI/ML**: only once you've done all the above

Resources:
- **Automate the Boring Stuff with Python** (FREE online) — https://automatetheboringstuff.com (the single best intro to Python for non-CS people)
- **CS50P — Harvard's Intro to Python** (free, world-class) — https://cs50.harvard.edu/python/
- **Real Python** — https://realpython.com
- **Flask quickstart** — https://flask.palletsprojects.com/en/3.0.x/quickstart/

### Path D — Java

Java is heavyweight, used in big enterprise and Android. Probably **skip Java unless** you specifically want a corporate dev job or to build Android apps. Python or Go are friendlier next languages. If you do want Java:

- **Codecademy — Learn Java** — https://www.codecademy.com/learn/learn-java
- **MOOC.fi — Java Programming I & II** (free, university-grade) — https://java-programming.mooc.fi

### Path E — Computer Science fundamentals

After 6 months of building, do this. It will make everything click.

- [ ] **CS50x — Harvard's introduction to computer science** (FREE, the most respected intro CS course on Earth) — https://cs50.harvard.edu/x/
- [ ] Data structures & algorithms — through the lens of LeetCode (easy problems only, no need to grind)

---

## Master resource list

A short, opinionated list. Don't drown in too many.

### Documentation (use forever)
- **MDN Web Docs** — https://developer.mozilla.org
- **CSS Tricks** — https://css-tricks.com
- **Tailwind docs** — https://tailwindcss.com/docs
- **React docs** — https://react.dev

### Full courses (free)
- **The Odin Project** — https://www.theodinproject.com (most thorough free curriculum)
- **freeCodeCamp** — https://www.freecodecamp.org (largest free coding platform)
- **CS50** (Harvard) — https://cs50.harvard.edu
- **JavaScript.info** — https://javascript.info
- **Scrimba** — https://scrimba.com (interactive, some free content)

### YouTube channels (free)
- **Kevin Powell** — CSS — https://www.youtube.com/@KevinPowell
- **Web Dev Simplified** — JS, React — https://www.youtube.com/@WebDevSimplified
- **Net Ninja** — broad — https://www.youtube.com/@NetNinja
- **Traversy Media** — broad — https://www.youtube.com/@TraversyMedia
- **Fireship** — short, sharp, modern — https://www.youtube.com/@Fireship
- **Theo - t3.gg** — modern frontend, opinionated — https://www.youtube.com/@t3dotgg

### Practice (free)
- **Frontend Mentor** — design challenges with HTML/CSS — https://www.frontendmentor.io
- **JavaScript30** — 30 vanilla JS projects — https://javascript30.com
- **Codewars** — algorithm puzzles — https://www.codewars.com
- **Exercism** — practice with a mentor — https://exercism.org
- **Advent of Code** — annual puzzle challenge — https://adventofcode.com

### Communities (free)
- **r/learnprogramming** — https://www.reddit.com/r/learnprogramming
- **r/webdev** — https://www.reddit.com/r/webdev
- **The Odin Project Discord** — invite link on their site
- **Stack Overflow** — for specific questions — https://stackoverflow.com

---

## How to stay sane

1. **Build, build, build.** You learn by doing, not by watching. Aim for 70% building, 30% reading/watching.
2. **Get comfortable being stuck.** Every developer Googles things daily. The skill isn't memorising — it's knowing what to search for and how to read docs.
3. **Don't switch courses constantly.** "Tutorial hell" is real. Finish one course before starting another.
4. **Ship small things often.** Deploy something every week, even if it's tiny. Public accountability matters.
5. **Use your masjid project as a goal post.** Every new concept you learn — ask "could this improve the masjid site?" That's how learning becomes useful.
6. **Take breaks.** Coding is a marathon. Rested brains learn faster.
7. **Teach back.** After a week, try to explain what you learned to a non-coder. If you can't, you don't understand it yet.

---

## Progress tracker

Tick these as you complete each phase:

- [ ] Phase 0 — Setup
- [ ] Phase 1 — HTML
- [ ] Phase 2 — CSS
- [ ] Phase 3 — JavaScript
- [ ] Phase 4 — Git & GitHub
- [ ] Phase 5 — Tailwind
- [ ] Phase 6 — APIs
- [ ] Phase 7 — Deployment
- [ ] Phase 8 — Capstone: Masjid site rebuild
- [ ] Phase 9 — Going further (pick a path)

When you tick that final box, you'll genuinely be a junior front-end developer. Not "I did a course" — actually able to build and ship.

May Allah make it easy for you. Bismillah.
