<img src="https://github.com/monsoonnyc/ugly-wireframe-kit/blob/master/ugly-wireframe-kit.png" with="600px"/>

# Ugly Wireframe Kit

A rigorous, intentionally **lo-fi** hand-drawn wireframe design system. Grayscale, [Chalkboard](#typography) type, and a wobbly 1.5px line on every edge. Lo-fi on purpose — it keeps reviews about **structure and flow**, not pixels.

Built so a coding agent (or a human) can drop in a few files, write semantic HTML, and get a believable wireframe in seconds.

👉 **[Open the storybook](https://monsoonnyc.github.io/ugly-wireframe-kit/)** &nbsp;·&nbsp; or open `index.html` locally.

---

## Quick start

Copy four files into your project, then load them:

```html
<!-- 1. tokens + components -->
<link rel="stylesheet" href="wireframe.css">

<!-- 2. the hand-drawn icon set -->
<script src="wireframe-icons.js"></script>

<!-- 3. paste the contents of wireframe-filters.svg
        once, right after <body> (the wobble filters) -->
```

Then write semantic HTML inside a `.wf` wrapper:

```html
<div class="wf">
  <button class="wf-btn wf-btn--primary"><span>Save</span></button>
  <i class="wf-icon" data-icon="check"></i>
</div>
```

That's it. The fourth file, `wireframe-tokens.json`, is the machine-readable token export for tooling.

---

## What's in the box

| File | Purpose |
| --- | --- |
| `wireframe.css` | All design tokens (CSS variables) + every component class + the hand-drawn engine |
| `wireframe-icons.js` | 25 authentic hand-drawn icons; hydrates `<i class="wf-icon" data-icon="…">` |
| `wireframe-filters.svg` | The SVG displacement filters that make edges wobble (paste once per page) |
| `wireframe-tokens.json` | Full token set as JSON for design tooling / pipelines |
| `index.html` | The standalone storybook — every token, component, and pattern |

---

## How the hand-drawn look works

Every "drawn" surface keeps its **text crisp** and wobbles only its **edges**. Each component's border/fill is painted on a `::before` pseudo-element that gets an SVG displacement filter (`#wf-rough-1/2/3`). Because the filter touches only the pseudo-element, real content on top stays perfectly legible.

- Add `.wf-edge` to make any element's border hand-drawn.
- Rotate the three filter variants (`.wf-edge--r2`, `.wf-edge--r3`) so repeated elements don't look identical.
- The filters are intentionally cheap (single-octave noise); avoid applying them to very large elements.

---

## Tokens

All tokens are CSS custom properties — override them to re-skin the whole system.

- **Color** — `--wf-ink` (near-black navy `rgb(6,22,33)`), `--wf-muted`, `--wf-line-muted`, `--wf-fill-soft`, `--wf-paper`, `--wf-danger`, `--wf-link`
- **Type** — one family (Chalkboard → Comic Neue fallback); sizes `--wf-h1/h2/h3/body/small`
- **Spacing** — 8-step ramp on a 4px base (`--wf-space-1` … `--wf-space-8`)
- **Stroke / radius** — `--wf-stroke` (1.5px), `--wf-stroke-bold` (2.5px); corners stay sharp (the wobble is the softness)
- **Shadow** — sketchy offset drops (`--wf-shadow`, `--wf-shadow-pop`)
- **Motion** — `--wf-dur-fast/base/slow`, `--wf-ease`
- **Z-index** — predictable layering scale (`--wf-z-overlay/modal/toast/tooltip`)
- **Breakpoints** — mobile 375 · tablet 768 · desktop 1280

## Components

Buttons · links · tags/chips · text fields · checkbox · radio · toggle · slider · segmented controls · lists & menus · tabs · accordion · search · banners · toasts · cards · modals · confirmation dialog · directional tooltips · avatars · pagination dots · progress · steppers · tables · top nav · side nav · shapes & placeholders · browser frame · phone frame.

## Patterns

Desktop app screen · mobile screen · empty state · onboarding popover · settings/form screen · login & sign-up.

## Icons

`<i class="wf-icon" data-icon="NAME"></i>` — paints with `currentColor`, sizes with `font-size`.

`placeholder` `avatar` `plus` `x` `close` `ellipses` `warning` `info` `check` `square` `trash` `search` `reload` `menu` `caret-left` `caret-right` `caret-up` `caret-down` `arrow-left` `arrow-right` `star` `star-filled` `steps` `steps-filled` `spinner`

---

## Typography

The kit is set in **Chalkboard**, an Apple system font. It is not web-embeddable, so the font stack falls back to **[Comic Neue](https://fonts.google.com/specimen/Comic+Neue)** (a free, near-identical rounded hand face) everywhere else. Both are intentionally informal to reinforce the "this is a wireframe, not a finished design" message.

## Browser support

Modern evergreen browsers. The hand-drawn effect relies on SVG `feTurbulence` / `feDisplacementMap`, supported in all current Chrome, Edge, Firefox, and Safari. In environments without SVG filter support the system degrades gracefully to clean straight-edged wireframes.

## Credits

Derived from the original *Ugly Wireframe Kit* — a Sketch wireframe library first created in **2019**. The original `.sketch` file and its readme are preserved in [`/archive`](./archive). This is the **v2** rebuild (2026): a complete reimagining as a hand-drawn, framework-agnostic CSS system, with the line character and icons kept faithful to the source.

## License

[MIT](./LICENSE)
