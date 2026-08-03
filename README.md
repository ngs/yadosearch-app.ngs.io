# yadosearch-app.ngs.io

Promotional site for [宿さがし (YadoSearch)](https://apps.apple.com/jp/app/id347959354), the inn search app built in [ngs/yadosearch](https://github.com/ngs/yadosearch).

Built with [Hugo](https://gohugo.io) and deployed to GitHub Pages on every push to `master` (see `.github/workflows/deploy.yml`).

## Structure

```
content/<lang>/_index.md          # landing page (front matter drives the hero)
content/<lang>/privacy/index.md   # privacy policy — linked from App Store Connect
i18n/<lang>.yaml                  # navigation and footer
layouts/                          # baseof / index / single + header and footer partials
static/img/icon.svg               # the app icon, composed from Resources/AppIcon.icon
hugo.toml                         # ja (default) and en
```

Japanese is the default language and sits at the root; English is under `/en/`. That matches the app, whose interface is Japanese only.

`marketing_url` in `fastlane/metadata/<locale>/` points at the language root here, and `privacy_url` at `/privacy/` under it.

## Development

```bash
hugo server            # http://localhost:1313
hugo --gc --minify     # build into public/
```

## Screenshots

There are none yet, and the layout does not reference any. The App Store badge is also left out while the store record is unavailable — see the app repository's README for why.

## The icon

`static/img/icon.svg` is composed from `Resources/AppIcon.icon/Assets/` in the app repository: the two glyph layers on a rounded rect filled with the icon's own accent colour. Regenerate it from there rather than editing it by hand.
