# Night Neutral

A dark, gray Firefox 157 (Nova) theme so the browser recedes behind websites. No purple, no pastels.

AMO listing: [Night Neutral](https://addons.mozilla.org/firefox/addon/night-neutral/).

Pair it with [Night Better](https://github.com/JoelLisenby/firefox-night-better) for the proxy toggle and chrome CSS helpers. Chrome-only and theme+chrome installs are in the [better-firefox gist](https://gist.github.com/JoelLisenby/e8bb1dfa7fb2fef3377617b86e3de14b).

## What it paints

Frame, toolbar, sidebar, and new tab are `#000000`. The selected tab is `#2a2a2a`. The address bar is `#0a0a0a`. Hover and active buttons lift a little off black. Bookmark and panel menus use `#1a1a1a` with highlight `#3a3a3a`.

Theme keys come from the official [theme manifest](https://developer.mozilla.org/en-US/docs/Mozilla/Add-ons/WebExtensions/manifest.json/theme). Nova notes from [Mozilla’s add-ons blog](https://blog.mozilla.org/addons/2026/09/29/nova-is-here-what-changes-for-your-firefox-theme/).

Leave `browser.nova.enabled` on. The theme API has no corner-radius property. Nova’s rounding, tab padding, and the purple top-bar gradient stay unless you also copy `userChrome.css` from Night Better (or the better-firefox gist) into your profile.

## Install (AMO)

Install [Night Neutral](https://addons.mozilla.org/firefox/addon/night-neutral/) from addons.mozilla.org. Optionally add [Night Better](https://addons.mozilla.org/firefox/addon/night-better/) and the profile chrome CSS.

## Install (temporary, this session)

1. `about:debugging` → This Firefox → Load Temporary Add-on.
2. Choose `manifest.json` in this folder.

Temporary themes go away when Firefox restarts. Firefox Release only keeps add-ons Mozilla has signed.

## Develop / publish

Load this folder from `about:debugging` while iterating. Do not run `./sign.sh` until a version is ready to keep; AMO reviews listed uploads.

When publishing, bump `version` in `manifest.json` (listed cannot reuse an unlisted number), put AMO JWT credentials in `.amo-credentials` (gitignored) or the environment, then `./sign.sh`. Theme listings use a Creative Commons license slug.

```
export WEB_EXT_API_KEY='user:########:##'
export WEB_EXT_API_SECRET='...'
./sign.sh
```

Unsigned zip: `./pack.sh` writes `dist/night-neutral.xpi`.

## License

[CC BY 4.0](LICENSE)
