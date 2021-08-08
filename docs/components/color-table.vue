<script setup>
import { hexToRgba, hexToHsla } from "colors-convert";

// TODO: This is taken directly from @rose-pine/palette
// esm packages are not supported in vitepress
const colorsByVariant = {
  dark: {
    base: "#191724",
    surface: "#1f1d2e",
    overlay: "#26233a",
    inactive: "#555169",
    subtle: "#6e6a86",
    text: "#e0def4",
    love: "#eb6f92",
    gold: "#f6c177",
    rose: "#ebbcba",
    pine: "#31748f",
    foam: "#9ccfd8",
    iris: "#c4a7e7",
    highlight: "#2a2837",
    highlightInactive: "#211f2d",
    highlightOverlay: "#3a384a",
  },

  moon: {
    base: "#232136",
    surface: "#2a273f",
    overlay: "#393552",
    inactive: "#59546d",
    subtle: "#817c9c",
    text: "#e0def4",
    love: "#eb6f92",
    gold: "#f6c177",
    rose: "#ea9a97",
    pine: "#3e8fb0",
    foam: "#9ccfd8",
    iris: "#c4a7e7",
    highlight: "#312f44",
    highlightInactive: "#2a283d",
    highlightOverlay: "#3f3c53",
  },

  dawn: {
    base: "#faf4ed",
    surface: "#fffaf3",
    overlay: "#f2e9de",
    inactive: "#9893a5",
    subtle: "#6e6a86",
    text: "#575279",
    love: "#b4637a",
    gold: "#ea9d34",
    rose: "#d7827e",
    pine: "#286983",
    foam: "#56949f",
    iris: "#907aa9",
    highlight: "#eee9e6",
    highlightInactive: "#f2ede9",
    highlightOverlay: "#e4dfde",
  },
};

const props = defineProps({
  variant: {
    type: String,
    default: "dark",
  },
});

const colors = [];

Object.keys(colorsByVariant[props.variant]).map((role) => {
  const hex = colorsByVariant[props.variant][role];

  let rgba = hexToRgba(hex);
  rgba = `${rgba.r} ${rgba.g} ${rgba.b}`;

  let hsla = hexToHsla(hex);
  hsla = `${hsla.h} ${hsla.s} ${hsla.l}`;

  colors.push({ role, hex, rgba, hsla });
});
</script>

<template>
  <table>
    <thead>
      <tr>
        <th colspan="2">Role</th>
        <th>Hex</th>
        <th>RGB</th>
        <th>HSL</th>
      </tr>
    </thead>
    <tbody>
      <tr v-for="color in colors" :key="color.hex">
        <td style="background: var(--c-white)">
          <div class="dot" :style="{ background: color.hex }"></div>
        </td>
        <td>{{ color.role }}</td>
        <td>
          <code>{{ color.hex }}</code>
        </td>
        <td>
          <code>{{ color.rgba }}</code>
        </td>
        <td>
          <code>{{ color.hsla }}</code>
        </td>
      </tr>
    </tbody>
  </table>
</template>

<style scoped>
.dot {
  width: 24px;
  height: 24px;
  border-radius: 9999px;
}
</style>
