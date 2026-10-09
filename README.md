# raemote.github.io

The website for [Raemote](https://github.com/raemote/raemote_cli) — served at
**<https://raemote.github.io>**.

- What it is: your self-hosted apps (Jellyfin, Home Assistant, dashboards, dev
  servers) on your phone, over an end-to-end encrypted connection. One install,
  one QR scan, no account, no VPN, no port forwarding.
- A guide in English and Chinese: [`get-started.html`](get-started.html),
  [`zh/`](zh/).

## Layout

```
index.html            landing page (English)
get-started.html      setup guide (English)
zh/index.html         landing page (中文)
zh/get-started.html   setup guide (中文)
assets/site.css       the only stylesheet — light and dark, no webfonts
assets/logo.svg       vector mark (also the app's icon artwork)
assets/*.svg          diagrams, themed via prefers-color-scheme inside the SVG
assets/favicon.png    raster icon (sized down from raemote_cli/Raemote_ICON.png)
assets/og.png         social preview image
```

Hand-written HTML and CSS on purpose: no framework, no build step, no
JavaScript except a few lines that reveal the copy buttons (they stay hidden
without scripting). The pages load no third-party resources.

## Working on it

```sh
python3 -m http.server 8080      # then open http://127.0.0.1:8080/
```

Publishing is branch-based GitHub Pages (Settings → Pages → Deploy from a
branch, `main` / root), so a push to `main` is the whole deploy.

## Keeping it honest

The site describes what the software actually does today. When you change the
product, update the pages in the same commit:

- install one-liner and the Gitee mirror (`raemote_cli/install.sh`)
- pairing, device management, discovery (`raemote_cli/README.md`)
- the iOS feature list and the Safari "Not Secure Connection Warning" note
  (`raemote_ios/Raemote Connector/README.md`)
- the HTTPS-only limitation in the "What Raemote does not do" section

Screenshots and a short demo video are still missing; the pages are built to
degrade gracefully without them.

## Mirrors

- GitHub (hosted): <https://github.com/raemote/raemote.github.io>
- Gitee (source mirror, for networks where GitHub is unreliable):
  <https://gitee.com/pppkin/raemote_site>

## License

AGPL-3.0-or-later, matching the server and the iOS app. See [LICENSE](LICENSE).
