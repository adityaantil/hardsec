# HardSec 2026: event website

Website for **HardSec 2026**, a two-day hardware-security training and hackathon
for engineering students across India, organized by the IEEE CASS Student Branch
Chapter at IIIT Allahabad and supported by IEEE CASS (UP Section, India).

Plain static site: no build step, no framework. Live at
https://adityaantil.github.io/hardsec-2026/

## Files (all in one folder, no subfolders)

| File | Purpose |
| --- | --- |
| `index.html` | the page and all its content |
| `fonts.css` | self-hosted font faces |
| `base.css` | colours, typography, buttons, layout helpers |
| `components.css` | prize bar, header + hamburger menu, FAQ, copy button |
| `sections.css` | every page section |
| `config.js` | the only file to edit to open registration |
| `main.js` | menu, scroll-spy, countdown, team "Show more", etc. |
| `registration.js` | registration button + optional participants table |
| `*.woff2` | fonts (Unbounded, Instrument Sans, JetBrains Mono) |
| `*.jpg`, `*.png`, `favicon.svg` | photos, logo, social preview image |
| `.nojekyll` | tells GitHub Pages to serve files as they are |

File names are case-sensitive on GitHub: keep them exactly as they are.

## Everyday edits

Open `index.html` and search for these markers:
`EDIT-DATE` (event dates; also `event.start` in `config.js`), `EDIT-CONTACT`,
`SECTION: TRACKS`, `SECTION: TEAM` (first 5 members show, the rest sit under
"Show more"), `SECTION: FACULTY`, `SECTION: PARTNERS`.
Colours and fonts are defined at the top of `base.css`.

## Opening registration (Google Form)

Edit only `config.js`:

```js
registration: {
  open: true,
  formUrl: 'https://forms.gle/your-form-id',
  embedUrl: '',   // optional: Google Forms "Embed HTML" URL to show the form inside the page
}
```

All "Opening soon" buttons then switch to "Register now" and open your form.

### Showing registered participants (optional)

1. Link the form to a Google Sheet. In the sheet: **File > Share > Publish to web**,
   choose the responses tab and **CSV**, publish, copy the link.
2. In `config.js` set `participants.csvUrl` to that link and
   `participants.columns` to the headers to show, for example `['Name', 'College']`.

**Privacy:** a published sheet exposes every column to anyone with the link.
Keep e-mail and phone out: publish a separate tab with only name and college,
and get participants' consent before listing names.

## Licence

Code: MIT (see `LICENSE`). The IEEE logo and the photographs/posters belong to
their owners and are not covered. Fonts: SIL OFL 1.1 (`FONT-LICENSES.txt`).
