# Velvet Glass — Glassmorphism Sidebar

> A premium glassmorphism sidebar built with pure CSS `backdrop-filter`, Tailwind CSS, and Remix Icons. Part of the **DevIgnitor CSS Tricks** series.

---

![Velvet Glass — Main Preview](./images/velvet-glass-1.png)

---

## What is Velvet Glass?

**Velvet Glass** is a fully self-contained, production-quality sidebar UI component that demonstrates the power of CSS `backdrop-filter` in a real-world layout. The glass doesn't fake depth — it earns it. A living background of softly spawning and fading colored circles gives the frosted glass surface genuine visual work to do, so the blur effect reads as real material rather than a stylesheet trick.

The name came from the feel: not cold or clinical, but warm, soft, and tactile — like light filtered through frosted silk.

Built as part of the [DevIgnitor Sidebar](https://devignitor.com) series — a growing library of interactive CSS demos for developers who learn by seeing.

---

![Velvet Glass — Dark Mode](./images/velvet-glass-2.png)

---

## Features

- **True neutral glass** — sidebar uses zero color tint; it reads as pure frosted material in both themes
- **Floating bubble background** — colorful circles spawn at random positions, fade in over ~0.6s, hold, then fade out; new ones appear every 500–600ms
- **Dark / Light theme toggle** — full token swap via CSS custom properties; glass values, bubble opacity, dot grid, and base gradients all adapt
- **Collapse / expand sidebar** — smooth `cubic-bezier` width transition from `256px` → `64px`; labels, badges, and section titles fade out; icon-only mode with hover tooltips
- **Edge toggle button** — circular pill button sitting exactly on the right border of the sidebar (`right: -14px`), vertically centered; turns red on hover with glow
- **Active nav state** — red left border strip, glow effect, accent-colored icon, subtle background highlight
- **CSS Tools accordion** — expand/collapse sub-menu with smooth `max-height` transition and rotating chevron
- **Ripple effect** — on every nav item click
- **Notification badge** — with animated CSS-only ping ring
- **User card footer** — avatar gradient, online status dot, three action buttons
- **Live CSS annotation** — bottom-right chip shows the exact `backdrop-filter` values currently active, updates on theme switch
- **Red Hat Text font** — 300–700 weight range across all UI; DM Mono for code labels, badges, and mono annotations

---

## CSS Properties Demonstrated

| Property | Where Used |
|---|---|
| `backdrop-filter: blur(32px) saturate(160%)` | Sidebar, all glass panels, stat cards |
| `-webkit-backdrop-filter` | Safari fallback on all glass elements |
| `background: rgba(255,255,255,0.038)` | Sidebar glass fill — dark mode |
| `background: rgba(255,255,255,0.52)` | Sidebar glass fill — light mode |
| `border: 1px solid rgba(255,255,255,0.085)` | Glass border — dark mode |
| `border: 1px solid rgba(255,255,255,0.72)` | Glass border — light mode |
| `transition: width 0.38s cubic-bezier(0.4,0,0.2,1)` | Sidebar collapse animation |
| `animation: bubble-life` | Floating background circles |
| `@keyframes` | Logo pulse, badge ping, bubble fade, bar chart entry |

---

## Color Palette

All colors are applied as CSS custom properties and adapt between dark and light themes.

### Brand

| Name | Hex | Usage |
|---|---|---|
| DevIgnitor Red | `#e63329` | Active states, badges, accent glow, logo mark |
| Red Glow | `rgba(230,51,41,0.28)` | Box shadows and ambient glow |
| Red Soft | `rgba(230,51,41,0.10)` | Active background fills |

### Glass Surfaces — Dark Mode

| Token | Value | Usage |
|---|---|---|
| `--glass-bg` | `rgba(255,255,255,0.038)` | Sidebar and panel fills |
| `--glass-border` | `rgba(255,255,255,0.085)` | Element borders |
| `--glass-top` | `rgba(255,255,255,0.16)` | Top-edge sheen (1px highlight line) |
| `--glass-hover` | `rgba(255,255,255,0.06)` | Nav item hover state |
| `--glass-active` | `rgba(230,51,41,0.09)` | Active nav item fill |
| `--bg` | `#0c0c14` | Page background |

### Glass Surfaces — Light Mode

| Token | Value | Usage |
|---|---|---|
| `--glass-bg` | `rgba(255,255,255,0.52)` | Sidebar and panel fills |
| `--glass-border` | `rgba(255,255,255,0.72)` | Element borders |
| `--glass-top` | `rgba(255,255,255,0.98)` | Top-edge sheen |
| `--glass-hover` | `rgba(255,255,255,0.65)` | Nav item hover state |
| `--bg` | `#eceaf6` | Page background (soft lavender-white) |

### Text Scale

| Token | Dark Value | Light Value | Usage |
|---|---|---|---|
| `--text-1` | `rgba(255,255,255,0.90)` | `rgba(14,12,28,0.90)` | Primary labels |
| `--text-2` | `rgba(255,255,255,0.42)` | `rgba(14,12,28,0.46)` | Secondary / muted |
| `--text-3` | `rgba(255,255,255,0.20)` | `rgba(14,12,28,0.22)` | Tertiary / hints |
| `--divider` | `rgba(255,255,255,0.065)` | `rgba(0,0,0,0.07)` | Separator lines |

### Bubble & UI Colors

| Color | Hex | Usage |
|---|---|---|
| Violet | `#7c5cfc` | Bubbles, chart bar, skill bar |
| Sky | `#0ea5c9` | Bubbles, chart bar, activity dot |
| Emerald | `#22c55e` | Bubbles, online status, stat card |
| Purple | `#a855f7` | Bubbles, chart bar |
| Amber | `#f59e0b` | Bubbles, activity dot |
| Pink | `#ec4899` | Bubbles only |
| Orange | `#f97316` | Bubbles only |
| Avatar gradient start | `#5b3fd4` | User avatar |

---

## Tech Stack

| Layer | Technology |
|---|---|
| Styling utility | Tailwind CSS (CDN) |
| Icons | Remix Icons 4.2 |
| Font | Red Hat Text (Google Fonts) |
| Mono font | DM Mono (Google Fonts) |
| JavaScript | Vanilla — no framework, no build step |
| Dependencies | Zero npm packages |

---

## File Structure

```
01. Velvet Glass - Glassmorphism Sidebar/
├── velvet-glass-sidebar.html   ← everything in one file
└── README.md
```

Everything — HTML, `<style>`, and `<script>` — lives in a single `.html` file. Open it in any browser. No server, no build step, no `node_modules`.

---

## How to Use in Your Own Project

### 1. Copy the glass CSS variables

Paste these into your `:root` and `html.light` blocks. These are the only values you need to control the entire glass aesthetic:

```css
:root {
  /* Dark mode glass */
  --glass-bg:     rgba(255, 255, 255, 0.038);
  --glass-border: rgba(255, 255, 255, 0.085);
  --glass-top:    rgba(255, 255, 255, 0.16);
  --glass-hover:  rgba(255, 255, 255, 0.06);
}

html.light {
  /* Light mode glass */
  --glass-bg:     rgba(255, 255, 255, 0.52);
  --glass-border: rgba(255, 255, 255, 0.72);
  --glass-top:    rgba(255, 255, 255, 0.98);
  --glass-hover:  rgba(255, 255, 255, 0.65);
}
```

### 2. Apply glass to any element

```css
.glass-card {
  background: var(--glass-bg);
  border: 1px solid var(--glass-border);

  /* The core — blur what's behind the element */
  backdrop-filter: blur(32px) saturate(160%);
  -webkit-backdrop-filter: blur(32px) saturate(160%); /* Safari */

  /* Optional: top sheen for depth */
  position: relative;
}
.glass-card::before {
  content: '';
  position: absolute;
  top: 0; left: 0; right: 0;
  height: 1px;
  background: var(--glass-top);
}
```

### 3. Add the floating bubbles background

Drop this HTML before your content and paste the JS function below into your script:

```html
<!-- In your HTML -->
<div id="bubbles" style="position:fixed;inset:0;pointer-events:none;z-index:0;overflow:hidden;"></div>
```

```js
// In your JS
const COLORS = [
  'rgba(124,92,252,VAL)',
  'rgba(14,165,201,VAL)',
  'rgba(34,197,94,VAL)',
  'rgba(168,85,247,VAL)',
  'rgba(245,158,11,VAL)',
];

function spawnBubble() {
  const raw   = COLORS[Math.floor(Math.random() * COLORS.length)];
  const op    = (0.10 + Math.random() * 0.14).toFixed(2);
  const color = raw.replace('VAL', op);
  const size  = 18 + Math.random() * 52;
  const dur   = 2800 + Math.random() * 2400;

  const el = document.createElement('div');
  el.style.cssText = `
    position: absolute;
    border-radius: 50%;
    width: ${size}px;
    height: ${size}px;
    left: ${Math.random() * 100}%;
    top:  ${Math.random() * 100}%;
    background: ${color};
    filter: blur(${4 + Math.random() * 8}px);
    animation: bubble-life ${dur}ms linear forwards;
  `;
  document.getElementById('bubbles').appendChild(el);
  setTimeout(() => el.remove(), dur + 100);
}

// Seed + loop
for (let i = 0; i < 12; i++) setTimeout(spawnBubble, i * 180);
setInterval(() => { spawnBubble(); if (Math.random() > 0.6) spawnBubble(); }, 600);
```

```css
/* Required keyframe */
@keyframes bubble-life {
  0%         { opacity: 0; transform: scale(0.4); }
  20%        { opacity: 1; transform: scale(1);   }
  80%        { opacity: 1; transform: scale(1);   }
  100%       { opacity: 0; transform: scale(0.85);}
}
```

### 4. Sidebar collapse logic

```js
let collapsed = false;

function toggleSidebar() {
  collapsed = !collapsed;
  document.getElementById('sidebar').style.width = collapsed ? '64px' : '256px';
  // Or use a CSS class:
  document.getElementById('sidebar').classList.toggle('collapsed', collapsed);
}
```

```css
#sidebar {
  width: 256px;
  transition: width 0.38s cubic-bezier(0.4, 0, 0.2, 1);
  overflow: hidden;
}
#sidebar.collapsed { width: 64px; }

/* Hide labels when collapsed */
#sidebar.collapsed .nav-label { opacity: 0; max-width: 0; }
```

### 5. Theme switching

```js
function toggleTheme() {
  document.documentElement.classList.toggle('dark');
  document.documentElement.classList.toggle('light');
}
```

Your CSS variables in `:root` (dark) and `html.light` handle everything automatically — no JS color manipulation needed.

---

## Important: backdrop-filter Requires a Background

`backdrop-filter` only works when the element has a non-fully-transparent background. A completely transparent background (`opacity: 0` background) will silently disable the blur. The minimum working setup is:

```css
/* ✅ Works */
backdrop-filter: blur(20px);
background: rgba(255, 255, 255, 0.01); /* even near-zero opacity is enough */

/* ❌ Does not work */
backdrop-filter: blur(20px);
background: transparent;
```

Also make sure the element is not `overflow: hidden` on a parent that clips the blur sampling area.

---

## Browser Support

| Browser | Support |
|---|---|
| Chrome / Edge | ✅ Full |
| Firefox | ✅ Full (v103+) |
| Safari | ✅ With `-webkit-` prefix |
| Mobile Chrome | ✅ Full |
| Mobile Safari | ✅ With prefix |

---

## Part of the Devignitor Sidebar Series

This component is one file in a growing collection of zero-dependency, screen-recording-ready CSS demos. Each file teaches one concept through a live interactive preview.

| # | Trick | File |
|---|---|---|
| 01 | `scroll-margin-top` | `trick-01-scroll-margin-top.html` |
| 02 | `accent-color` | `trick-02-accent-color.html` |
| 03 | `clamp()` | `trick-03-clamp.html` |
| 04 | `aspect-ratio` | `trick-04-aspect-ratio.html` |
| 05 | `backdrop-filter` | `trick-05-backdrop-filter.html` |
| 06 | Velvet Glass Sidebar | `velvet-glass-sidebar.html` |

More tricks added regularly. Star the repo to follow along.

---

## License

MIT — free to use, modify, and ship in your own projects. Credit appreciated but not required.

---

> Built by [DevIgnitor](https://devignitor.com) — tools, tutorials, and CSS tricks for developers who build real things.
