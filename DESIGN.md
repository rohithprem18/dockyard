---
name: DockYard
description: Calm, fast inventory operations software for SMB warehouse teams.
colors:
  background: "#f1eefa"
  surface: "#ffffff"
  surface-muted: "#ece8f8"
  border: "#e1dcf1"
  border-strong: "#cec6e6"
  foreground: "#22201f"
  muted-foreground: "#6b6663"
  primary: "#7c55fb"
  brand-pink: "#f871d8"
  brand-blue: "#47bfff"
  success: "#1baf7a"
  warning: "#c98400"
  danger: "#e34948"
  info: "#2a78d6"
typography:
  body:
    fontFamily: "Figtree, ui-sans-serif, system-ui, sans-serif"
    fontSize: "16px"
    fontWeight: 400
    lineHeight: "24px"
  h1:
    fontFamily: "Figtree, ui-sans-serif, system-ui, sans-serif"
    fontSize: "36px"
    fontWeight: 600
    lineHeight: "44px"
  landing-display:
    fontFamily: "Figtree, ui-sans-serif, system-ui, sans-serif"
    fontSize: "clamp(40px, 6vw, 64px)"
    fontWeight: 700
    lineHeight: 1.08
rounded:
  sm: "8px"
  md: "10px"
  lg: "16px"
  pill: "9999px"
  landing-frame: "20px"
spacing:
  1: "4px"
  2: "8px"
  3: "12px"
  4: "16px"
  6: "24px"
  8: "32px"
  12: "48px"
  16: "64px"
components:
  button-primary:
    backgroundColor: "{colors.primary}"
    textColor: "#ffffff"
    rounded: "{rounded.pill}"
    padding: "0 16px"
  nav-pill-active:
    backgroundColor: "{colors.foreground}"
    textColor: "{colors.background}"
    rounded: "{rounded.pill}"
    padding: "0 16px"
  card:
    backgroundColor: "{colors.surface}"
    textColor: "{colors.foreground}"
    rounded: "{rounded.lg}"
    padding: "24px"
---

# Design System: DockYard

## Overview

**Creative North Star: "The Warehouse Floor, Lit Like a Studio"**

DockYard is a warm, confident, purple-and-pink-accented operating system for
inventory — the opposite of the gray enterprise-admin default. One brand runs
end to end now: the same Figtree type, the same warm-lavender neutral, the
same purple primary and pink accent appear on the public landing page and
inside the authenticated app. What changes by surface isn't the palette, it's
the *intensity* — the landing page's hero and final CTA get the full-strength
gradient field; the working app keeps color disciplined to meaning (status,
movement type, positive/negative delta) against a calm, light, warm-neutral
canvas, so a dense product table stays easy to scan all day.

Key characteristics:
- One brand, two intensities: full-saturation purple/pink gradient fields on the landing page's hero and final CTA; disciplined, meaning-only color everywhere else.
- Pill-shaped interactive elements throughout (buttons, nav items, badges, filters) — a rounder, warmer geometry than the previous slate-toned system.
- A top pill-nav bar (not a sidebar) is the app's primary navigation, active route rendered as a solid near-black pill.
- The landing page's proof is literally the product: real components, real hooks, real seed data, framed rather than faked.

## Colors

### Primary
- **Dock Purple** (`#7c55fb`): primary buttons, active/focus states, links, brand mark, progress-bar fill, the landing hero/final-CTA gradient's dominant hue.
- **Signal Pink** (`#f871d8`) and **Signal Blue** (`#47bfff`): the landing gradient field's second and third hues, rounding out the hero/final-CTA's tri-color mesh. Neither is used as an app UI color; both stay marketing-surface accents.

### Neutral
- **Warm Paper** (`#f1eefa`): app background — a lavender-tinted off-white, not slate.
- **Surface** (`#ffffff`): card and panel fill.
- **Surface Muted** (`#ece8f8`): icon chips, skeletons, table header row, inset rows.
- **Border** (`#e1dcf1`) / **Border Strong** (`#cec6e6`): the only line weights in the system, 1px.
- **Ink** (`#22201f`) / **Muted Ink** (`#6b6663`): primary and secondary text — a warm near-black, not cool gray, and also the fill for the active nav pill.

### Semantic (meaning-only, never decorative)
- **Success** `#1baf7a` — in stock, stock-in movement, positive delta.
- **Warning** `#c98400` — low stock.
- **Danger** `#e34948` — out of stock, stock-out movement, negative delta.
- **Info** `#2a78d6` — adjustment movement.

These four match `lib/chart-colors.ts`'s validated categorical/diverging hues, so a status badge and a chart segment that mean the same thing look the same.

### Named Rules
**The Meaning-Only Rule.** Inside `/app/*`, a non-neutral color may only appear because it encodes status, movement type, a positive/negative delta, or is brand purple used for primary actions, active nav state, links, and low-opacity icon-chip tints (`bg-primary/10`) on stat-style cards.

**The Gradient-Stays-Public Rule.** Signal Pink and Signal Blue appear only inside `.landing-hero-field` (the landing page's hero and final CTA). Neither ever appears inside the authenticated app.

## Typography

**Font:** Figtree (self-hosted via `@fontsource/figtree`, weights 400/500/600/700/800), falling back to `ui-sans-serif, system-ui, sans-serif`.

**Character:** A warmer, rounder grotesque than the system stacks it replaces — friendly without losing the density an operations table needs.

### Hierarchy (app)
- **H1** (600, 36px/44px): page titles.
- **H2** (600, 30px/38px): section headers, stat values.
- **H3** (600, 24px/32px): card titles in dense contexts.
- **Body** (400, 16px/24px): default text, form inputs.
- **Small** (400–500, 14px/20px): table cells, secondary labels, nav items.
- **Caption** (400–500, 12px/16px): metadata, timestamps, uppercase stat-card labels.

### Hierarchy (landing, additive — does not replace the app ramp)
- **Landing Display** (700, 40–64px, 1.08 line-height): hero and final-CTA headlines only.
- **Landing Subhead** (400, 16–18px): one supporting line under a display headline, never more.

### Named Rules
**The Five-Size Rule (app).** `/app/*` never introduces a sixth type size. The landing page is the one place permitted a bigger display step, because it is a different surface with a different job, not an exception inside the app.

## Layout

8px spacing rhythm throughout (`4·8·12·16·24·32·48·64`). The app has no sidebar: a single full-width column under a fixed top nav, content capped at `1400px`. The landing page uses a `1200px` content measure with wider, marketing-scale vertical rhythm. Dashboard proof and bento tiles reflow to a single column below `lg` (1024px).

## Elevation & Depth

Resting state is flat: cards carry a near-imperceptible ambient shadow (`0 1px 2px rgba(15,23,42,0.04)`) — just enough to separate surface from background. Depth becomes a *response*, not a default: `Card`'s `hoverable` prop lifts an individual, distinct object (a stat card that links somewhere, a warehouse card, a landing bento tile) by `-translate-y-0.5` into a real elevated shadow (`0 16px 32px -16px rgba(34,20,50,0.18)`) on hover — never applied to container cards (table wrappers, list cards) that aren't themselves the interactive unit. The landing page's `DashboardPreview` frame is the one static exception, carrying its elevated shadow permanently because it reads as a window floating over the gradient field, not a flat card.

### Shadow Vocabulary
- **Ambient** (`0 1px 2px rgba(15,23,42,0.04)`): default card/table elevation everywhere in the app.
- **Lifted** (`0 16px 32px -16px rgba(34,20,50,0.18)`, with `-translate-y-0.5`): hover state for `hoverable` cards only.
- **Floating** (`0 30px 80px -20px rgba(11,7,16,0.7)`): the landing hero's framed product proof only.

### Motion
- **Route entrance:** page content fades/slides up 6px over 320ms (`app-enter`, keyed to the route so it replays on navigation) — gives the top-nav's route switch a beat of life without a full-page spinner.
- **Loading:** `Skeleton` sweeps a soft shimmer highlight left-to-right (1.6s loop) rather than a flat pulse.
- **Data changes:** progress-bar fills (`WarehouseCard`, `WarehouseSummaryCard`, `TopMovingProductsCard`) transition width over 700ms so a refetch settles instead of snapping.
- **Buttons:** `active:scale-[0.97]` on press, for tactile feedback on every button variant.
- **Respect `prefers-reduced-motion`:** route entrance and shimmer both disable under the media query.

## Shapes

**The system is pill-first.** Buttons, badges, nav items, and the landing CTAs are all `rounded-full`. Cards and panels use `--radius-lg` (16px); inputs and dropdowns use `--radius-md` (10px); small chips use `--radius-sm` (8px). The landing page's `DashboardPreview` browser-chrome frame uses a one-off 20px radius because it stands in for a physical window. Borders are always 1px, always the border token, never colored except full-opacity status badges (which rely on their fill, not a border).

## Components

### Navigation
- **App top nav:** fixed-height (64px) bar — brand mark (left), horizontally-scrollable pill nav group, search/notification icon buttons + avatar (right). Active route = solid `foreground`-colored pill with `background`-colored text and icon. Below the `sm` breakpoint, nav items collapse to icon-only circular pills (label hidden) so six destinations still fit a phone-width bar without silently disappearing, the way the old sidebar did below `md`.
- **Landing nav:** fixed, transparent over the hero field, solidifies to `bg-surface` + border past `scrollY > 40` — a legibility response, not decoration.

### Buttons
- **Shape:** fully pilled (`rounded-full`) everywhere, app and landing alike.
- **Primary:** `bg-primary text-white`, `h-9 px-4` (app) / `h-12 px-6` (landing CTA, white pill + primary-colored text).
- **Hover/Focus:** opacity-based hover (`hover:opacity-90`); `:focus-visible` gets a 2px ring in the primary-tinted `--ring`.
- **Icon buttons:** `size-9`, fully circular.

### Badges
- **Style:** fully pilled, `whitespace-nowrap` (fixed during this pass — badge text was wrapping in narrow table columns), optional leading dot, semantic-tinted `-bg` fill for status/movement variants.

### Cards / Containers
- **Corner style:** 16px (`--radius-lg`).
- **Background:** `--surface` on `--background`.
- **Border:** 1px `--border`.
- **Internal padding:** 24px header/content, tightened to 16px inside dense bento tiles on the landing page.
- **Interactive variant:** `StatCard` accepts an `href` and becomes a `Card asChild` wrapping a `Link` — `hoverable` lift, a trailing arrow icon that slides in on hover, `group`-scoped. Only used where the destination is real (Dashboard → Products/Analytics); never added just for visual effect.

### Empty States
- **Treatment:** soft primary-tinted icon badge (`bg-primary/10`, ring, icon in `text-primary`) inside a subtle gradient panel (`from-surface-muted/70 to-transparent`) — no dashed border. Title at `text-body font-semibold`, one description line, primary action when the emptiness is fixable by the user (never shown for a "no results" filter state, only for a genuinely empty collection).
- **Copy contract:** state why it's empty, what happens next, one primary action — never a bare "No data."

### Loading States
- **Treatment:** shimmer-swept `Skeleton` blocks shaped like the content they replace (row height for table rows, card height for stat cards) — never a full-page spinner.

### Dashboard Preview (signature component)
A non-interactive (`aria-hidden`, `pointer-events-none`), truthful reproduction: the real `StatCard`, `RecentTransactionsCard`, and a decorative mirror of the real top nav, wired to the same live query hooks as `/app`, inside a macOS-style browser-chrome frame. It exists specifically so the landing page never has to fabricate a screenshot, and it is kept in sync with the real nav shell (rebuilt in this pass when the app moved from a sidebar to a top nav).

## Do's and Don'ts

### Do:
- **Do** keep every non-neutral color inside the app tied to a status or delta meaning, except brand purple on primary actions.
- **Do** reuse real feature components/hooks for any landing-page "proof" content instead of drawing a lookalike.
- **Do** keep Signal Pink/Blue to the landing page's two gradient bookends.
- **Do** collapse nav items to icon-only rather than letting them overflow or vanish below `sm`.
- **Do** reserve `hoverable`/lift treatment for genuinely distinct, individually-meaningful objects (a stat card, a warehouse card, a bento tile) — never a container.
- **Do** give a clickable `StatCard` a real destination; the hover affordance must be true.

### Don't:
- **Don't** bring Signal Pink/Blue into `/app/*`.
- **Don't** add a kicker/eyebrow label above a heading anywhere in the product.
- **Don't** invent stat-card deltas that aren't derived from real stored/computed data.
- **Don't** hide row actions behind hover-only opacity — the product rules ban hidden actions; every "…" menu stays visible at rest.
- **Don't** add a sixth type size to the app ramp; give the landing page its own additive scale instead.
- **Don't** ship an interactive pill/badge without `whitespace-nowrap` — this system's density means narrow columns are common.
