# Decision Log

Project: Visual Beta Cards for Climbing (mobile, minimal) (Vouno)
Scope: MVP only (pick photo → tap-mark holds → save → list/detail → share/export image)  
Non‑goals: GPS/location, 3D scanning/models, social network features  
Rule: If a change isn’t in MVP scope or isn’t logged here, it doesn’t ship.

---

## What Must Be Recorded

Log a decision when it changes any of the following:

- Product scope: adds/removes flows, screens, or MVP features.
- Dependencies: add/remove/major upgrade of libraries, SDKs, or services.
- Data model: new entities, schema changes, migrations, or storage format shifts.
- Media handling: image sizes, compression, export format, annotations, or rendering.
- UX patterns: navigation changes, gestures, state handling, undo/redo, confirmations.
- Privacy/data ownership: where data is stored, shared, or exported.
- Performance/limits: file size caps, offline behavior, caching strategy.
- Platform specifics: iOS/Android differences or permissions requirements.
- Monetization or analytics: any tracking or paid features (even if rejected).
- De‑scoping or deferral: anything explicitly pushed out of MVP.

If unsure, log it.

---

## Decision Template

### YYYY‑MM‑DD — [Short Decision Title]

**Decision**

- **Rationale**

- **Alternatives Considered**

- **Impact (Scope / UX / Tech / Risk)**

- **Follow‑ups**

- ***

## Entries

### 2026‑02‑24 — Initialize Decision Log

**Decision**

- Establish a formal Decision Log for all product/technical changes.

**Rationale**

- Enforces MVP discipline and makes scope changes explicit.

**Alternatives Considered**

- No formal log; informal notes.

**Impact (Scope / UX / Tech / Risk)**

- Scope: tight control
- UX: none
- Tech: minimal overhead
- Risk: low

**Follow‑ups**

- Ensure every change references a logged decision.
