# Design System (MVP)

## Goal
Define minimal, consistent design principles and tokens for the MVP UI that feel clean, calm, and legible on mobile.

## Decisions / Rules
- Spacing uses a 4pt base with a small token set to keep layouts predictable.
- Typography uses a single sans stack and a short type scale to reduce visual noise.
- Light/Dark themes share identical token names; only values change.
- One accent color is allowed per screen; it is the only saturated hue in UI chrome.
- Backgrounds are soft, eye-friendly (not pure white/black) to reduce glare.

## Markdown document (copy-paste ready)

### Design Principles
- Calm, minimal, single-task screens.
- High legibility: avoid low-contrast text on tinted backgrounds.
- Visual hierarchy comes from size/weight/spacing, not extra colors.
- One accent color rule: at most one accent hue per screen (for primary action, selected state, or key highlight). All other colors are neutral.

### Spacing
- Base unit: `4`
- Token set:
  - `space.1 = 4`
  - `space.2 = 8`
  - `space.3 = 12`
  - `space.4 = 16`
  - `space.5 = 20`
  - `space.6 = 24`
  - `space.7 = 32`
  - `space.8 = 40`
  - `space.9 = 48`
- Rules:
  - Screen padding: `space.5` (20)
  - Section spacing: `space.7` (32)
  - Control height: 44-48 using `space.6` + `space.3`

### Typography
- Font family: `System` (Expo default system font)
- Scale (sp/pt):
  - `type.display = 28/34, weight 600`
  - `type.title = 22/28, weight 600`
  - `type.subtitle = 18/24, weight 600`
  - `type.body = 16/24, weight 400`
  - `type.caption = 13/18, weight 400`
- Rules:
  - Max 2 weights per screen.
  - Body line height >= 1.5 for long notes.

### Color Tokens
All tokens exist in both themes with the same names.

#### Light Theme
- `color.bg = #F6F7F8` (main background)
- `color.bg.subtle = #FFFFFF` (cards/surfaces)
- `color.bg.elevated = #FFFFFF` (modal surfaces)
- `color.text.primary = #15181B`
- `color.text.secondary = #5C646B`
- `color.text.tertiary = #8A9299`
- `color.border = #E3E6E9`
- `color.shadow = #0000001A`
- `color.accent = #3B82F6` (single accent)
- `color.success = #16A34A`
- `color.warning = #F59E0B`
- `color.danger = #EF4444`

#### Dark Theme
- `color.bg = #0F1214`
- `color.bg.subtle = #151A1E`
- `color.bg.elevated = #1A2024`
- `color.text.primary = #E7EAED`
- `color.text.secondary = #A6B0B7`
- `color.text.tertiary = #7F8A93`
- `color.border = #242A2F`
- `color.shadow = #00000066`
- `color.accent = #60A5FA` (single accent)
- `color.success = #22C55E`
- `color.warning = #FBBF24`
- `color.danger = #F87171`

### One Accent Color Rule (enforced)
- `color.accent` is used for exactly one of: primary CTA, selected toggle, or active mark color.
- If a screen needs mark colors (beta marks), use neutral shades or a single accent tint; do not introduce extra saturated hues.

### Component Defaults (MVP)
- Buttons:
  - Primary: `color.accent` background, `color.bg.subtle` text.
  - Secondary: transparent, `color.accent` text, `color.border` outline.
- Cards:
  - Background: `color.bg.subtle`.
  - Radius: `12`.
  - Padding: `space.5`.
- Inputs:
  - Height: 44-48.
  - Border: `color.border`.
  - Text: `color.text.primary`.

## Pitfalls / edge cases
- Pure white/black backgrounds reduce comfort; stick to the tokens.
- Multiple accents on one screen break hierarchy and feel noisy.
- Low-contrast text on tinted surfaces is easy to miss in bright gyms.
- Dark theme shadows can look muddy; prefer subtle borders instead.

## Done criteria checklist
- [ ] Spacing uses the defined 4pt scale only.
- [ ] Typography uses the defined scale and weights.
- [ ] Light/Dark token names match exactly.
- [ ] Only one accent hue appears per screen.
- [ ] Backgrounds use the eye-friendly tokens.
