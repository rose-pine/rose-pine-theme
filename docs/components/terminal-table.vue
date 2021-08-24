<script setup>
// TODO: This is taken directly from @rose-pine/palette
// esm packages are not supported in vitepress
const colorsByRole = {
  base: {
    dark: "#191724",
    moon: "#232136",
    dawn: "#faf4ed",
  },
  surface: {
    dark: "#1f1d2e",
    moon: "#2a273f",
    dawn: "#fffaf3",
  },
  overlay: {
    dark: "#26233a",
    moon: "#393552",
    dawn: "#f2e9de",
  },
  inactive: {
    dark: "#555169",
    moon: "#59546d",
    dawn: "#9893a5",
  },
  subtle: {
    dark: "#6e6a86",
    moon: "#817c9c",
    dawn: "#6e6a86",
  },
  text: {
    dark: "#e0def4",
    moon: "#e0def4",
    dawn: "#575279",
  },
  love: {
    dark: "#eb6f92",
    moon: "#eb6f92",
    dawn: "#b4637a",
  },
  gold: {
    dark: "#f6c177",
    moon: "#f6c177",
    dawn: "#ea9d34",
  },
  rose: {
    dark: "#ebbcba",
    moon: "#ea9a97",
    dawn: "#d7827e",
  },
  pine: {
    dark: "#31748f",
    moon: "#3e8fb0",
    dawn: "#286983",
  },
  foam: {
    dark: "#9ccfd8",
    moon: "#9ccfd8",
    dawn: "#56949f",
  },
  iris: {
    dark: "#c4a7e7",
    moon: "#c4a7e7",
    dawn: "#907aa9",
  },
  highlight: {
    dark: "#2a2837",
    moon: "#312f44",
    dawn: "#eee9e6",
  },
  highlightInactive: {
    dark: "#211f2d",
    moon: "#2a283d",
    dawn: "#f2ede9",
  },
  highlightOverlay: {
    dark: "#3a384a",
    moon: "#3f3c53",
    dawn: "#e4dfde",
  },
};

const props = defineProps({
  type: {
    type: String,
    default: "colors",
  },
});

const colors = [
  { usage: "black", role: "overlay" },
  { usage: "bright black", role: "subtle" },
  { usage: "red, bright red", role: "love" },
  { usage: "green, bright green", role: "pine" },
  { usage: "yellow, bright yellow", role: "gold" },
  { usage: "blue, bright blue", role: "foam" },
  { usage: "magenta, bright magenta", role: "iris" },
  { usage: "cyan, bright cyan", role: "rose" },
  { usage: "white, bright white", role: "text" },
];

const ui = [
  { usage: "foreground", role: "text" },
  { usage: "background", role: "base" },
  { usage: "selection foreground", role: "text" },
  { usage: "selection background", role: "highlight" },
  { usage: "links", role: "iris" },
  { usage: "cursor", role: "inactive" },
  { usage: "cursor text", role: "text" },
  { usage: "active tab foreground", role: "text" },
  { usage: "active tab background", role: "overlay" },
  { usage: "inactive tab foreground", role: "subtle" },
  { usage: "inactive tab background", role: "base" },
];

let items = [];

if (props.type == "colors") {
  items = colors;
} else {
  items = ui;
}
</script>

<template>
  <table>
    <thead>
      <tr>
        <th>Usage</th>
        <th>Role</th>
        <th>Dark</th>
        <th>Moon</th>
        <th>Dawn</th>
      </tr>
    </thead>
    <tbody>
      <tr v-for="item in items" :key="item.usage">
        <td>{{ item.usage }}</td>
        <td>{{ item.role }}</td>
        <td>
          <code>{{ colorsByRole[item.role].dark }}</code>
        </td>
        <td>
          <code>{{ colorsByRole[item.role].moon }}</code>
        </td>
        <td>
          <code>{{ colorsByRole[item.role].dawn }}</code>
        </td>
      </tr>
    </tbody>
  </table>
</template>
