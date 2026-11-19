# Shanu & Pranav — Wedding Invite

A single-page wedding invitation hosted on GitHub Pages.

**Live:** https://dubeypranav4.github.io/wedding_invite/

## Features
- Animated mandala motif + floating fireflies
- Bilingual **EN / हिं** toggle (remembers choice; `?lang=hi` also works)
- Light / dark mode toggle
- Multi-function schedule (Haldi & Mehendi, Wedding) with per-event **Directions** and **Add to Calendar**
- Live countdown to the wedding
- Lazy-loaded video invite (hides itself until the file exists)
- WhatsApp / social link previews via Open Graph tags

## Guest links (Haldi visibility)
This is a static page, so visibility is controlled by a URL code — **not real security**,
just a way to keep the two invites separate.

| Audience | Link |
|----------|------|
| Everyone (Wedding only) | `https://dubeypranav4.github.io/wedding_invite/` |
| Close family (Haldi + Wedding) | `https://dubeypranav4.github.io/wedding_invite/?h=parivaar` |

Change the code in `index.html` → `const HALDI_CODE = "parivaar";`

## Editing details
All text and event data live near the top of the `<script>` in `index.html`:
- `CONFIG.events` — dates, times, map destinations, calendar locations
- `STRINGS.en` / `STRINGS.hi` — all visible text, per language

## Assets to add
Drop these into `assets/` (filenames matter):
- `video_invite.mp4` — the video invite (player stays hidden until this exists)
- `og-preview.jpg` — 1200×630 image for WhatsApp/social previews

## Run locally
This is a static page, so any simple HTTP server works. Open a terminal in this
folder and run **one** of these, then visit the URL it prints:

```bash
# Python 3 (pre-installed on macOS) — serves at http://localhost:8000
python3 -m http.server 8000

# or Node (if you have it)
npx serve .

# or PHP
php -S localhost:8000
```

Then open:
- Wedding only (default):  http://localhost:8000/
- Haldi + Wedding (family): http://localhost:8000/?h=parivaar
- Force Hindi:             http://localhost:8000/?lang=hi

Stop the server with `Ctrl+C`.

> Don't just double-click `index.html` (a `file://` URL) — the lazy video and some
> browser features behave differently. Use a local server as above.

## Hosting
GitHub Pages → Settings → Pages → Deploy from branch `main` / root.
