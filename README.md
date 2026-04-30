# Hint public roadmap

The single-file HTML artifact that powers the public roadmap at `hint.com/roadmap`.

## What's here

- `roadmap.html` — the entire page (HTML + CSS + JS inline).
- `videos/` — demo video assets referenced by the page (e.g. the Marketplace spotlight video).

## Editing

Open `roadmap.html` and look for the comment block near the top:

```
HINT ROADMAP — EDIT THESE PLACEHOLDERS BEFORE PUBLISHING
```

That block lists every `{{TOKEN}}` you need to find/replace before each release (Canny URL, Sales URL, "what's new" copy, demo video links, etc.). The "What's new" ribbon and the "+ N more features…" teaser both fall back gracefully if a placeholder isn't replaced.

## Publishing

The file is designed to drop into a HubSpot custom HTML module on the `/roadmap` page. No build step, no external assets except a Google Fonts link and the videos in `videos/`. If hosting from HubSpot, upload the videos to HubSpot File Manager and update the `<video src="...">` paths accordingly.

## Local preview

```sh
npx serve .
# then open http://localhost:3000/roadmap.html
```

## Quarterly refresh checklist

1. Update `{{LAST_UPDATED}}`.
2. Bump `{{WHATS_NEW_VERSION}}` (so dismissed users re-see the ribbon) and rewrite `{{WHATS_NEW_TEXT}}`.
3. Move shipped features from "in progress" → "shipped" status in the JS `features` dict.
4. Refresh the 8 highlights per quarter.
5. Update `{{Q1_MORE_COUNT}}` / `{{Q2_MORE_COUNT}}`.
6. Update the Active Betas list.
7. Spot-check the spotlight video (replace if a more recent launch warrants it).
