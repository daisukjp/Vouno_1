# Constitution — Visual Beta Cards for Climbing (Vouno)

## Purpose

Build a minimal mobile app that lets a user pick a photo, tap-mark holds, save a beta card, list/detail cards, and share/export an image. No extra features beyond the MVP.

## MVP Scope

- Photo import from device.
- Tap to mark holds on photo.
- Save card with metadata (title, date, notes).
- List and detail views for saved cards.
- Export/share a composited image.

## Non-Goals (Explicitly Out of Scope)

- GPS tracking or location-based features.
- 3D scanning or 3D model capture.
- Social network features (feeds, follows, comments, likes).
- Cloud sync as a hard requirement for MVP.

## UX Principles

- One task per screen whenever possible.
- Fewer taps over more options.
- Defaults must be safe and reversible.
- No blocking flow without a clear user benefit.

## Data Ownership and Media Rules

- User-generated media belongs to the user.
- All media stays local unless the user explicitly shares or exports.
- No background uploads or hidden analytics of user media.
- Deletion removes local data with no recovery guarantees.

## Decision Log Rule

- Every product or technical change must be recorded in a Decision Log.
- Each entry must include: date, decision, rationale, and scope impact.
- No change is “too small” to log.

## Enforcement

- If a feature is not in the MVP Scope, it does not ship.
- If a change is not logged, it does not ship.
