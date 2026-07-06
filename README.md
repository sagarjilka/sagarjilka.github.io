# sagarjilka.com

Source for **sagarjilka.com** (personal site) and **sagarjilka.com/smartpaper/** (the SmartPaper landing page), served via **GitHub Pages**.

Both pages are single self-contained HTML files — no build step, no framework, no `npm install`. Animations use **GSAP** and **three.js** loaded from CDNs at runtime.

## Structure

```
/
├── index.html              # sagarjilka.com — personal / consultant site (three.js hero + GSAP)
├── icon.png                # favicon / avatar
├── CNAME                   # custom domain: sagarjilka.com
├── README.md
└── smartpaper/
    ├── index.html          # sagarjilka.com/smartpaper/ — landing page + interactive question demo
    ├── confirmed.html      # email-confirmation success page (linked from the app)
    ├── delete-account.html # account-deletion request page (App Store requirement)
    └── dashboard.html      # teacher dashboard (radar/spider demo)
```

> The privacy policy lives in a **separate repo** (`smartpaper-privacy`) and is served at `sagarjilka.com/smartpaper-privacy/`.

## How it's deployed

1. **GitHub Pages** is enabled on this repo (Settings → Pages → Deploy from `main`, root).
2. The `CNAME` file points the site at the custom domain **sagarjilka.com** (configure the A/CNAME DNS records at your registrar to GitHub Pages — see [GitHub's custom-domain docs](https://docs.github.com/pages/configuring-a-custom-domain-for-your-github-pages-site)).
3. Any push to `main` publishes within a minute or two.

## Run / edit locally

No tooling required — just open the file:

```bash
open index.html            # personal site
open smartpaper/index.html # SmartPaper landing
```

…or serve the folder to test relative paths exactly as production:

```bash
python3 -m http.server 8080   # then visit http://localhost:8080
```

## Fork & deploy your own copy

1. Fork this repo (or copy `index.html` + `smartpaper/` into a repo named `<you>.github.io`).
2. Delete/replace `CNAME` with your own domain (or remove it to use `<you>.github.io`).
3. Settings → Pages → Deploy from `main`. Done.

## Design notes

- **Personal site** — dark, editorial. A live **three.js neural-particle field** in the hero (falls back gracefully to the CSS gradient if WebGL is unavailable), GSAP `ScrollTrigger` reveals, a scrubbed timeline, and count-up stats. Palette: near-black ink with an indigo→cyan aurora accent. Fonts: Inter + Fraunces + JetBrains Mono.
- **SmartPaper landing** — bright and warm, using the app's own "Paper & Aurora" palette (violet `#6354D6` → teal `#18B69E`). The centrepiece is a **playable, in-browser question demo**: the visitor colours a fraction, taps a number line, and matches words to pictures, then an animated **line graph** and **radar/spider chart** draw themselves — mirroring the app's real Bayesian score and topic-strength analytics. Fonts: Fredoka + Space Grotesk (same as the app).

All copy is original. External libraries are pinned CDN versions (GSAP 3.12.5, three.js r128).
