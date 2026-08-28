# CeyBlox Event Creator — Development Feed

This repository is the public **News / Updates / Patch Notes** feed used by CeyBlox Event Creator during development and testing.

## Important history note

`up_0001` is **not** the first day CeyBlox Event Creator development started. The numbered public feed was intentionally reset/cleaned during development so the GitHub history could begin from a simple testable structure. Earlier work existed before this feed.

The first visible item is therefore named **Development Feed Test 07** on purpose. The `id` number only controls feed order; it does not represent the total number of private/internal development builds or the age of the project.

The dates in this repository are a curated development/testing history. They are useful for testing News Center navigation and keeping a readable public progress log, not as a complete engineering changelog.

## Folder format

Each update has its own numeric folder:

```text
up_0001/
up_0002/
up_0003/
...
```

Every folder must contain `update.json`. Large entries can split News, Updates and Patch Notes into separate JSON files.

IDs do not need to be continuous. Missing/deleted IDs are safe.

## Image size

Recommended main News/Update image:

- **1600 × 700 px**
- aspect ratio **16:7**
- JPG or WebP recommended
- keep important subjects/text away from the extreme edges because the Dashboard preview uses `object-fit: cover`
- avoid putting long paragraphs inside the image; keep the readable information in JSON text

Related/smaller images can use **1280 × 720 px (16:9)**.

The included development artwork is illustrative. It should not be described as an exact in-game screenshot unless it really came from the game/editor.

## Updating an existing image

GitHub/raw CDN image caching can take a little time after replacing a file with the exact same filename. During development, the cleanest approach is to use a new filename when an image changes, for example:

```text
library-preview-v1.webp
library-preview-v2.webp
```

Then update the JSON image path. This avoids most stale-image confusion while keeping old feed entries intact.

## Visibility

```json
"visible": true
```

shows an update. `false` keeps it in GitHub but hides it from the normal CeyBlox feed/version check.

## Safe public content

This repository is only for public metadata, news text and public images. Do not put source code, private GitHub tokens, license secrets, paid files, customer data or internal credentials here.

## Simple publishing workflow

1. Create the next `up_####` folder.
2. Give `update.json` a unique numeric `id`.
3. Add News/Updates/Patch Notes and images.
4. Keep `visible:false` while preparing if needed.
5. Commit and push.
6. Change to `visible:true` when ready.
7. Press CeyBlox Refresh to test it.
