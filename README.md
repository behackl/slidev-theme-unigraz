# @behackl/slidev-theme-unigraz

A [Slidev](https://github.com/slidevjs/slidev) theme with a University of Graz-inspired visual style, intended for talks and lectures with mathematical or technical content.

The theme provides custom layouts, a small set of reusable components, and default styling for headings, code blocks, lists, admonitions, and decorative elements.

## Install

```sh
pnpm add @behackl/slidev-theme-unigraz
```

and reference the theme in the frontmatter of your `slides.md` (quoted, since YAML values may not start with `@`):

```yaml
---
theme: '@behackl/slidev-theme-unigraz'
---
```

To work on the theme while using it in a talk, link a local checkout into the talk project:

```sh
pnpm link ~/code/slidev-theme-unigraz
```

Learn more about [how to use a Slidev theme](https://sli.dev/themes/use).

## Layouts

This theme provides the following custom layouts:

- `cover` — title slide layout with presenter name, affiliation, optional extra content, and optional circular cover media.
- `default` — regular content slide layout.
- `intro` — centered introductory section slide.
- `end` — centered closing / thank-you slide.

The theme also inherits Slidev's base layouts via `@slidev/client/styles/layouts-base.css`, so standard layouts such as `image-right` or `two-cols-header` remain available.

## Components

### `<admonition>`

A callout box for warnings, notes, danger messages, and themed remarks.

```md
::admonition{kind="warning" title="Warning" icon="mdi:warning"}
Pay attention to this point.
::
```

Supported built-in `kind` values are:

- `warning`
- `danger`
- `info`
- `kfu`
- `base` / default

The `icon` prop is optional. If omitted, a default icon is chosen from the admonition kind.

### `<block>`

A highlighted content block with an optional title, useful for theorems, propositions, examples, or definitions.

```md
<block title="Proposition">

Every interesting theorem deserves a nice box.

</block>
```

### `<decor>`

A background decoration container, typically used with Iconify icons.

```md
<decor class="top-15 right-40">
  <mdi-compass />
</decor>
```

### `<cover-circle-media>`

Displays an image or video clipped into the circular title-slide decoration. This is mainly used by the `cover` layout through frontmatter props:

```yaml
---
layout: cover
coverMedia: assets/title/example.jpg
coverMediaAlt: Example image
coverMediaOpacity: 0.9
---
```

The component detects common video extensions automatically (`.mp4`, `.webm`, `.ogg`, `.mov`), or you can set `coverMediaType: video` explicitly.

Instead of an image or video, the circle can also show arbitrary content (e.g. a live
animation component) via the `circle` slot of the `cover` layout. The content fills the
450×450 box in the bottom right corner; only the quarter disc inside the ring is visible.

```md
<template #circle>
  <MyAnimation />
</template>
```

### Branding components

The theme includes SVG-based branding helpers:

- `<logo-unigraz>` — University of Graz logo mark.
- `<circle-unigraz>` — circular University of Graz-style decorative ring.
- `<badge-math-unigraz>` — mathematics-themed University of Graz badge.

## Development

- `pnpm install`
- `pnpm dev` to start the theme preview (`example/slides.md`)
- edit `example/slides.md` and the theme files to see changes
- `pnpm export` to generate a preview PDF
- `pnpm screenshot` to generate preview PNGs

## Releasing

Releases are published to npm from GitHub Actions (`.github/workflows/publish.yml`)
whenever a `v*` tag is pushed:

```sh
pnpm version patch   # or minor / major; bumps package.json, commits, and tags
git push --follow-tags
```

Use `pnpm pack` to check the package contents locally before releasing.

## License

MIT for the code. The University of Graz name and logo are trademarks of the University of Graz and are not covered by this license.
