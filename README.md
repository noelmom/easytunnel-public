# EasyTunnel — Landing Page

Marketing / SEO landing page for **EasyTunnel**, an iPhone-first SSH client with local
port forwarding, a terminal, SFTP, and a code editor.

- Live site: https://easytunnel.app
- App source: https://github.com/noelmom/easytunnel
- Status: **live on the App Store** (v1.0, id 6789007010) — approved 2026-07-15

## Hosting

Static site (plain HTML/CSS) on **Cloudflare Pages** (project `easytunnel`, custom domain
`easytunnel.app`). Deploys are direct-upload via Wrangler — pushing to GitHub does **not**
auto-deploy.

```sh
# from the repo root, with Cloudflare creds in the environment
npx wrangler pages deploy . --project-name easytunnel
```

## Launch flag (flipped live 2026-07-15)

The "Coming soon" and "Download on the App Store" badges are both in `index.html`, toggled by a
single flag: `<html data-launch="live">`. It was flipped from `"soon"` and deployed when the app
was approved; both badges are now live links to https://apps.apple.com/app/id6789007010. To
revert (e.g. if the app is ever pulled), set it back to `"soon"` and redeploy.

## Files
- `index.html` — the page
- `privacy.html` — privacy policy (served at `/privacy`)
- `styles.css` — styling (brand palette)
- `assets/demo/` — hero video (desktop + mobile) and posters
- `assets/icon.png` — app icon
- `assets/og-image.png` — 1200×630 social/preview image
