# UI / frontend patterns

Evidence: [M] measured · [S] first-hand or several independent sources ·
[F] single source / practitioner opinion.

Why they happen [S]: with no direction the model picks from the most common
designs in its training data (Anthropic calls this "distributional
convergence"). Tailwind UI's `bg-indigo-500` default, amplified through
training data, is the purple problem. Banning a default makes a new one
appear, so every fix needs a chosen direction, not just a removal.

## Accessibility [M] (fix first)
- Content outside landmark regions; no single `<main>` (A11YN: most common)
- Low text/background contrast
- Links and buttons without readable names; "Click here"
- Missing alt text, or `alt="image"` (present but meaningless)
- Form controls without labels; ARIA misused
- Contrast failures on ghost or white buttons over images

## Missing states [S]
- No empty, loading, or error states ("optimises for the demo")
- `window.alert()` for errors; no inline validation
- No designed focus, hover, active, or disabled states
- Light-only or dark-only by accident

## Color [S]
- Indigo/purple-to-blue gradient in the hero, the loudest tell
- Gradient as decoration on backgrounds, CTAs, and text with no meaning
- Purple on white; timid palettes with every color at equal weight
- [F] Next default after purple is banned: beige/cream + brass/ochre +
  espresso for any "premium" brand
- [F] Warm and cool grays mixed

## Typography [S]
- Inter everywhere (also Roboto, Open Sans, Lato, Arial, system stack) as an
  unchosen default. Inter is fine when *chosen* for a reason.
- [F] Next default serifs: Fraunces, Instrument Serif
- [F] One serif word dropped into a sans headline; 4-line hero headlines

## Layout [S]
- Three equal rounded cards in a row: icon, heading, one-line description
- Standard page order: centered hero -> features -> testimonials -> CTA -> footer
- Same padding, radius, and card height everywhere, so nothing is emphasized
- Cards nested in cards
- Everything shown at once, nothing held back until needed
- [F] Zig-zag image/text rows repeated 3+ times; bento grids with filler cells;
  big-headline-left / small-paragraph-right section headers; logo wall
  inside the hero

## Components and surfaces
- [S] White card + 1px gray border + soft shadow; rounded corners on everything
- [S] shadcn/ui left in its default state
- [F] Glassmorphism and backdrop blur everywhere; untinted black shadows
- [F] Fake product screenshots built from `<div>` rectangles
- [F] Egg / generic-user avatars; circular spinners where skeletons fit

## Icons
- [M] ✨ sparkles for AI features. Ambiguous; 17% of users read it as
  favorite/save (NN/g). Label it or use a specific metaphor.
- [S] Default thin-line Lucide icons, interchangeable
- [F] Obvious metaphors: rocket = launch, shield = security, bolt = fast
- [F] Emoji as icons; mixed icon sets; hand-drawn SVG icons

## Motion
- [S] None, or the same fade-up on every element
- [F] Default ease-in-out; animating top/left/width/height;
  `addEventListener('scroll')`; `h-screen` jumping on iOS (use `100dvh`)

## Copy and content in the UI
- [S] Empty headlines: "Build faster. Ship smarter.", "Scale without limits",
  "Your all-in-one platform", "Elevate your workflow"
- [S] Buzzwords: seamless, unleash, next-gen, game-changer, supercharge
- [F] Placeholder people and brands: John Doe, Jane Smith, Sarah Chen, Acme,
  Nexus, Cloudly; too-neat stats (99.99%, 10x); lorem ipsum
- [F] "Step 1 / 2 / 3" labels, numbered eyebrows (`01 · Features`), decorative
  mono-caps strips (`DESIGN · BUILD · SHIP`), "Scroll to explore" cues,
  BETA/v2.0 badges with no launch behind them

## Code tells [F]
- `w-[calc(33%-1rem)]` flex math where grid would do; `z-[9999]`
- `useState` for continuous mouse or scroll values
- Blur or grain on scrolling containers (constant GPU repaints)
- Two design systems or icon sets mixed
