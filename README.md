# anatla.com

Holding page for Anatla. Plain HTML + CSS, no build step. Hosted on GitHub Pages from the `main` branch; the `CNAME` file pins the custom domain.

## Editing

- `index.html` – the page copy. The "Register your interest" link is the `mailto:` in the last paragraph; swap it for the form URL when the Brevo/MailerLite decision is made.
- `style.css` – layout and colours. Brand colours: woad `#5876d5`, peach `#fc7e49`, sienna `#c04729`, ink `#000`.
- `assets/logo.svg` – vector logo extracted from `Anatla_Logo_colour.pdf`. Uses `currentColor`, so recolour it with CSS.
- `assets/og.png` – social share image (the designer's holding-page artwork).

## Fonts

The design uses **ABC Arizona Flare** (Dinamo). The Dinamo quote (Sep 2026, EUR 198) is a desktop/print licence, which does not cover serving the font on the web. Until a web licence is bought (or the headings are rendered to SVG outlines under the desktop licence), the site self-hosts Spectral (SIL Open Font Licence, from Google Fonts) as a stand-in. Swap it by replacing the `@font-face` blocks and the `--serif` variable in `style.css`.

## Deploy

Push to `main`. GitHub Pages publishes the repo root directly; no Actions workflow needed.

Adding pages later: drop another `.html` file next to `index.html` and link to it. If the site grows past a handful of pages, move to Hugo.

## DNS (Cloudflare)

| Type  | Name | Value                 | Proxy    |
|-------|------|-----------------------|----------|
| A     | @    | 185.199.108.153       | DNS only |
| A     | @    | 185.199.109.153       | DNS only |
| A     | @    | 185.199.110.153       | DNS only |
| A     | @    | 185.199.111.153       | DNS only |
| CNAME | www  | anatla-labs.github.io      | DNS only |

Leave the records unproxied (grey cloud) so GitHub can issue the HTTPS certificate. Then in the repo's Pages settings tick "Enforce HTTPS".
