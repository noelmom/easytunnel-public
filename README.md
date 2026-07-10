# EasyTunnel — Landing Page

Marketing / SEO landing page for **EasyTunnel**, an iPhone-first SSH client with local
port forwarding, a terminal, SFTP, and a code editor.

- Live site: https://easytunnel.app
- App source: https://github.com/noelmom/easytunnel
- Status: submitted to the App Store (v1.0, id 6789007010) — pending review

## Hosting

Static site (plain HTML/CSS) on **Cloudflare Pages** (project `easytunnel`, custom domain
`easytunnel.app`). Deploys are direct-upload via Wrangler — pushing to GitHub does **not**
auto-deploy.

```sh
# from the repo root, with Cloudflare creds in the environment
npx wrangler pages deploy . --project-name easytunnel
```

## Launch flip (when Apple approves)

The "Coming soon" and "Download on the App Store" badges are both in `index.html`, toggled by a
single flag. To go live:

1. Change `<html data-launch="soon">` → `data-launch="live"` in `index.html`.
2. Deploy (command above).

Both badges then become live links to https://apps.apple.com/app/id6789007010.

## Files
- `index.html` — the page
- `privacy.html` — privacy policy (served at `/privacy`)
- `styles.css` — styling (brand palette)
- `assets/demo/` — hero video (desktop + mobile) and posters
- `assets/icon.png` — app icon
- `assets/og-image.png` — 1200×630 social/preview image
