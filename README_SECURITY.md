# Security, privacy & copyright — what changed

This update hardens the site without touching its design. Below: what was done
in the code, and the few steps only you can do (account/hosting side).

## Done in the code
1. **Self-hosted fonts** — Google Fonts CDN removed; Inter + Space Grotesk now
   load from `assets/fonts/` (no visitor IP sent to Google → GDPR-friendly).
   The Greek subset of Inter is included; Greek headings keep falling back to a
   system font exactly as before (Space Grotesk has no Greek glyphs).
2. **Privacy Policy** — new page at `#/privacy` (bilingual EN/GR), linked in the
   footer. It reflects that the site uses no tracking cookies (only a local
   language preference).
3. **Consent checkbox** — both forms now require agreement before sending, with
   a link to the Privacy Policy. Required under GDPR for consent-based contact.
4. **Anti-spam honeypot** — a hidden field silently drops automated bot
   submissions on both forms.
5. **Copyright** — `LICENSE` file (all rights reserved), copyright/author
   `<meta>` tags, and the existing footer © notice.
6. **Image protection** — drag-to-save and image selection disabled (light
   deterrent). Project photos have been given embedded copyright metadata
   (EXIF) — see the tagged copies provided.

## Steps only you can do
- **Public vs private repo.** Your code is currently visible to anyone if the
  repo is public. To hide it, make the GitHub repo **private** and deploy via
  **Netlify** (free with private repos; GitHub Pages needs Pro for private).
- **Fill in real contact details** in the `CONFIG` block near the top of
  `index.html` — the phone `+357 22 000000` is still a placeholder.
- **Add a form backend** (optional): set `formEndpoint` in `CONFIG` to a
  Formspree or Web3Forms URL, and enable their built-in spam filter / reCAPTCHA.
- **Replace the images** in your `images/` folder with the copyright-tagged
  copies provided (they look identical; metadata is embedded losslessly).

## Note on limits
On a public business website, the phone/email are meant to be reachable, so
they can't be strongly "hidden" — the honeypot + JS-built links reduce bot
scraping, which is the realistic goal. Image protection deters casual copying
but cannot make photos technically impossible to save.
