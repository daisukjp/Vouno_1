# DATA MODEL (MVP)

Decision Log

- Date: 2026-02-24
- Decision: Use two local entities `beta_post` and `beta_mark` with normalized mark coordinates and local-only media URIs.
- Rationale: Minimal schema supports the core flow (photo -> tap marks -> save -> list/detail -> share) without adding non-goal features.
- Scope impact: No cloud fields, no GPS, no social features, no 3D data.

## Overview

The MVP stores all data locally. A `beta_post` represents a single photo and its metadata. A `beta_mark` represents a tap-marked hold on that photo. Marks are stored as normalized coordinates so they render correctly at any image size.

## Entity: beta_post

Fields

- `id`: string (UUID v4)
- `photo_uri`: string (local file URI from image picker)
- `photo_width`: number (pixels, integer)
- `photo_height`: number (pixels, integer)
- `title`: string (optional, default empty)
- `notes`: string (optional, default empty)
- `created_at`: string (ISO 8601 UTC)
- `updated_at`: string (ISO 8601 UTC)
- `export_uri`: string (optional, last exported image file URI)
- `exported_at`: string (optional, ISO 8601 UTC)

Notes

- `photo_width` and `photo_height` capture the original asset dimensions.
- `export_uri` is for the last share/export result; do not store remote URLs in MVP.

## Entity: beta_mark

Fields

- `id`: string (UUID v4)
- `post_id`: string (FK to `beta_post.id`)
- `x`: number (0..1, normalized horizontal position)
- `y`: number (0..1, normalized vertical position)
- `radius`: number (0..1, normalized size, default 0.03)
- `color`: string (optional, default `#FF6A00`)
- `label`: string (optional, short text or number)
- `created_at`: string (ISO 8601 UTC)

Notes

- `x`, `y`, and `radius` are normalized against the original photo dimensions.
- `radius` can be used for display size and hit-target size.

## Relationships

- One `beta_post` has many `beta_mark`.
- Each `beta_mark` belongs to exactly one `beta_post`.

## Minimal TypeScript Shape

```ts
export type BetaPost = {
  id: string;
  photo_uri: string;
  photo_width: number;
  photo_height: number;
  title?: string;
  notes?: string;
  created_at: string;
  updated_at: string;
  export_uri?: string;
  exported_at?: string;
};

export type BetaMark = {
  id: string;
  post_id: string;
  x: number;
  y: number;
  radius?: number;
  color?: string;
  label?: string;
  created_at: string;
};
```
