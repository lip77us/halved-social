# halved-social

Approved Halved social media, published here so the scheduler (Metricool) can
fetch each file by public URL through jsDelivr:

    https://cdn.jsdelivr.net/gh/lip77us/halved-social@main/<path>

Files are only added once the post has been approved on the Review Board.

## Layout

- `video/` — explainers, `<name>-<YYYY-MM-DD>.mp4`
- `image/` — covers, rules cards, carousels, polls, `<name>-<YYYY-MM-DD>.png|jpg`
- `manifest.json` — one entry per board draft: the draft's own `media/…` name
  mapped to its jsDelivr URL here, plus a `batches` log of each push
- `history/` — the manifests from when this media lived on the
  `golf-app@social-media` branch (Oct 30 and Nov 6), kept for reference

## Adding a batch

1. Copy each approved file into `video/` or `image/`, adding the push date to
   the name (`hot-seat-explainer.mp4` → `video/hot-seat-explainer-2026-11-21.mp4`).
2. Add the draft to `manifest.json` under `drafts`, keyed by its board id, and
   add a line to `batches` with the date, who pushed and the draft ids.
3. Commit and push to `main`. Never rename or delete a file that a scheduled
   post already uses.

jsDelivr caches `@main` for up to 12 hours. A new file is fetchable right away;
a changed file may serve the old copy until the cache expires.

## History

Until 2026-11-21 this media lived on the `social-media` branch of
`lip77us/golf-app`. That branch is left as it is so links already scheduled
keep working, and nothing new is added there.
