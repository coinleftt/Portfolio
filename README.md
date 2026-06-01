# Coinleft — Portfolio

A minimalist, terminal-inspired portfolio website for **Coinleft LFT**, an indie hacker building open-source projects.

🔗 **Live:** [codejapoe.xyz](https://codejapoe.xyz/)

```
[ok] Loading web module
[ok] Loading projects
[ok] Loading system files
[ok] System ready
```

## Overview

A single-page static site styled like a terminal. It opens with a boot-sequence
animation, then reveals a series of bordered "panels" — each labelled like a shell
path (`~/francium`, `~/devlog`, `~/projects`, `~/todo`, `~/contact`) — that walk through
a featured app, work history, projects, and an ongoing to-do list.

## Features

- 🖥️ **Terminal aesthetic** — boot sequence, command-style section headers (`$ cat features.txt`), and a blinking cursor.
- 🧱 **system24-style panels** — every section is boxed with a 2px border and a title tab that breaks through the top edge.
- 🌗 **Dark / light themes** — Tokyo Night *Night* and *Day* palettes, toggled with `$ theme --light`. Preference is remembered for the session.
- 📱 **Live app preview** — an iPhone mockup of the Francium app with its own dark/light switch and a soft fade into the page.
- ✨ **Scroll reveals & micro-animations** — panels fade in on scroll; subtle hover states on borders and buttons.
- 📐 **Responsive** — full-width panels on mobile, centered cards with whitespace on desktop.

## Tech stack

No frameworks, no build step — just the platform.

| Layer       | Choice                                        |
| ----------- | --------------------------------------------- |
| Markup      | Plain HTML5                                   |
| Styling     | CSS custom properties (inline + `style.css`)  |
| Behavior    | Vanilla JavaScript                            |
| Typography  | [JetBrains Mono](https://www.jetbrains.com/lp/mono/) |
| Palette     | [Tokyo Night](https://github.com/enkia/tokyo-night-vscode-theme) |

## Project structure

```
.
├── index.html              # The whole page: markup, inline <style>, and <script>
├── static/
│   ├── style.css           # Tokyo Night color tokens (Night + Day variants)
│   ├── fonts.css           # JetBrains Mono @font-face declarations
│   ├── icon-light.png      # Site icon / favicon
│   ├── phone-dark.png      # App mockup (dark)
│   └── phone-light.png     # App mockup (light)
└── README.md
```

## Running locally

It's a static site, so any local server works. From the project root:

```bash
# Python
python3 -m http.server 8000

# or Node
npx serve .
```

Then open <http://localhost:8000>.

> **Tip:** open `index.html` *through a server* (not via `file://`) so the relative
> `./static/...` paths resolve correctly — otherwise the stylesheet and images won't load.

## Theming

Colors live as CSS variables in [`static/style.css`](static/style.css). The `:root` block
defines the dark (Night) palette; the `[data-theme="light"]` block overrides them for the
light (Day) palette. Adjust those tokens to re-skin the whole site:

```css
:root {
  --bg:      #1a1b26;
  --text:    #a9b1d6;
  --accent:  #7aa2f7;
  /* … */
}
```

## Credits

Original design adapted from [init.Habits](https://inithabits.com/), reworked with a
system24-style boxed-panel layout. Built and maintained by Coinleft —
[GitHub](https://github.com/coinleftt) · [X](https://x.com/coinleftt) · [LinkedIn](https://www.linkedin.com/in/coinleft/).
