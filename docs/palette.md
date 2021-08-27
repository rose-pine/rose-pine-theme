---
head:
  - - link
    - rel: shortcut icon
      type: image/png
      href: /assets/logo.png
  - - meta
    - name: theme-color
      content: "#c4a7e7"
  - - meta
    - name: description
      content: All natural pine, faux fur and a bit of soho vibes for the classy minimalist
  - - meta
    - property: og:image
      content: https://rose-pine-images.vercel.app/.png?theme=default
  - - meta
    - property: twitter:image
      content: /assets/logo.png
  - - meta
    - name: twitter:card
      content: summary_large_image
---

<script setup>
import ColorTable from './components/color-table.vue'
import TerminalTable from './components/terminal-table.vue'
</script>

# Palette

## Variants

### Rosé Pine

<ColorTable variant='dark' />

### Rosé Pine Moon

<ColorTable variant='moon' />

### Rosé Pine Dawn

<ColorTable variant='dawn' />

## Terminals

::: tip Examples

- [Kitty](https://github.com/rose-pine/kitty)
- [Hyper](https://github.com/rose-pine/hyper)

:::

### Colors

<TerminalTable type="colors" />

### Interface

<TerminalTable type="ui" />

## Utilities

### [@rose-pine/palette](https://github.com/rose-pine/palette)

> Color palette tool
