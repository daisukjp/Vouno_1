# ROADMAP — Visual Beta Cards (MVP)
Date range: 2026-02-24 to 2026-03-09 (14 days)

## Scope Summary
- Build the MVP flow: pick photo -> tap-mark holds -> save -> list/detail -> share/export image.
- Local-only storage; no cloud sync.
- Data model only: `beta_post` + `beta_mark` with normalized coordinates.
- Single task per screen; no GPS, no 3D scanning, no social network features.

## Decision Log
- 2026-02-24: Use Expo SQLite for `beta_post` and `beta_mark` with cascade delete.
  Rationale: relational data with one-to-many marks; reliable local persistence.
  Scope impact: add DB schema + migrations + simple repository layer.
- 2026-02-24: Render marks using `react-native-svg` overlay and record taps as normalized coordinates.
  Rationale: clean rendering and simple coordinate transforms across device sizes.
  Scope impact: add SVG overlay + coordinate mapping utilities.
- 2026-02-24: Export share image via `react-native-view-shot` + `expo-sharing` + `expo-file-system`.
  Rationale: minimal implementation to capture composed image with marks.
  Scope impact: add capture/export pipeline and error handling.

## Daily Milestones
### Day 1 — Tue 2026-02-24
Goal: Project scaffolding and navigation skeleton.
Done criteria:
- Expo app boots on iOS/Android simulator.
- Basic navigation stack with placeholder screens for List, Create, Detail, Share.
- `docs/ROADMAP.md` and decision log up to date.

### Day 2 — Wed 2026-02-25
Goal: Data layer and schema.
Done criteria:
- SQLite schema for `beta_post` and `beta_mark` implemented with migrations.
- Repository functions for create/read/update/delete posts and marks.
- Cascade delete verified for `beta_post` -> `beta_mark`.

### Day 3 — Thu 2026-02-26
Goal: Photo picking and post creation shell.
Done criteria:
- Photo picker flow using `expo-image-picker`.
- Image dimensions captured and stored on `beta_post`.
- New post saved with title/notes (minimal UI).

### Day 4 — Fri 2026-02-27
Goal: Marking UI v1 (tap to add).
Done criteria:
- Image displayed with `react-native-svg` overlay.
- Tap adds a mark at normalized x/y with default radius/color.
- Marks stored to DB and reload correctly.

### Day 5 — Sat 2026-02-28
Goal: Mark editing basics.
Done criteria:
- Undo last mark or delete selected mark.
- Mark color picker or quick palette (single accent color per screen).
- Mark label optional input (single field).

### Day 6 — Sun 2026-03-01
Goal: List screen.
Done criteria:
- List of `beta_post` with thumbnail, title, and updated date.
- Tap navigates to Detail screen.
- Empty state copy aligned with MVP scope.

### Day 7 — Mon 2026-03-02
Goal: Detail screen.
Done criteria:
- Detail displays image with marks overlay.
- Title/notes displayed read-only.
- Delete post action removes marks via cascade.

### Day 8 — Tue 2026-03-03
Goal: Share/export pipeline.
Done criteria:
- Capture composed image (photo + marks) to file.
- Share sheet opens via `expo-sharing`.
- Export timestamp stored on `beta_post`.

### Day 9 — Wed 2026-03-04
Goal: UX polish for core flow.
Done criteria:
- Single task per screen enforced (no mixed actions).
- 4pt spacing scale and system font applied.
- Light/dark tokens applied with soft background.

### Day 10 — Thu 2026-03-05
Goal: Error handling and permissions.
Done criteria:
- Photo permission prompts with fail-safe UI.
- Share failure states handled with clear copy.
- Image load failure fallback UI.

### Day 11 — Fri 2026-03-06
Goal: Data integrity and edge cases.
Done criteria:
- Normalized coordinates remain correct across orientation/size.
- Deletion removes local data and files.
- Export image name collisions handled.

### Day 12 — Sat 2026-03-07
Goal: Performance and accessibility pass.
Done criteria:
- Mark overlay remains responsive with 200+ marks.
- Basic accessibility labels on core buttons.
- No blocking operations on UI thread for export.

### Day 13 — Sun 2026-03-08
Goal: QA pass and bug fixes.
Done criteria:
- Smoke tests for create, mark, save, list, detail, share.
- Fix top 3 UX/bug issues found.
- No scope creep added.

### Day 14 — Mon 2026-03-09
Goal: Release-ready MVP build.
Done criteria:
- MVP checklist complete.
- Decision log updated for any new choices.
- Readme quick-start and known limitations written.

## MVP Done Definition
- User can create a card from a photo, add marks, save, view list/detail, and export image.
- Data is stored locally only; deletion removes associated marks.
- No GPS, no 3D scanning, no social network features.
