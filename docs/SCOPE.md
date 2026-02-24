# MVP Scope — Visual Beta Cards for Climbing　(Vouno)

This scope defines what ships in MVP. If it’s not here or not logged in the Decision Log, it doesn’t ship.

## MUST (MVP)

- Pick a photo from device gallery.
- Tap to place holds on the photo.
- Edit holds: move, delete, and simple color/type toggle.
- Save a card locally with photo + hold markers.
- List saved cards.
- View card detail.
- Share/export a card as an image.
- Safe, reversible defaults (e.g., undo last hold, confirm delete).
- Data stays local unless explicit share/export.
- Deletion removes local data (no recovery guarantees).

## SHOULD (MVP if low-cost)

- Minimal onboarding/help screen explaining tap-to-mark + share.
- Basic card metadata: title + optional notes.
- Simple ordering/search (e.g., most recent, title).
- Lightweight accessibility: larger tap targets, clear contrast.
- Local-only storage (no cloud sync).

## NOT‑NOW (Post‑MVP)

- GPS/location tagging.
- 3D scanning or models.
- Social network features (profiles, feeds, likes, comments).
- Cloud sync or multi-device accounts.
- In-app video capture or editing.
- Collaborative/shared editing.
- Advanced analytics on user media.
- Background uploads or processing.

## Scope Creep Alarms

If any of these happen, pause and log a Decision Log entry before proceeding:

- “We should add accounts so users don’t lose data.”
- “Let’s add a feed or sharing community.”
- “We can auto-detect holds with ML.”
- “We should add GPS/location to remember where it was.”
- “This needs cloud sync / backend.”
- “We need video support.”
- “We’re adding more than one task per screen.”

## Decision Log Reminder

Any change to scope, tech, or product behavior must be logged with date, decision, rationale, and scope impact.
