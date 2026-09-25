# 黄色い閃光 — Minato Namikaze Interactive Experience

An immersive, scroll-driven web experience dedicated to the Fourth Hokage, Minato Namikaze — the **Yellow Flash** of the Hidden Leaf.

## 🌟 Overview

This is a vanilla JavaScript, zero-build interactive narrative that unfolds across six acts as you scroll. Each act explores a different facet of Minato's legend through custom canvas animations, particle systems, and frame-by-frame scrubbable sequences.

> 「一瞬でいい。その一瞬に、全部を賭ける。」
> — *All it takes is a single instant. In that instant, you stake everything.*

## ✨ Acts

| Act | Title | Interaction |
|-----|-------|-------------|
| **I** | **覚醒** — Awakening | Scroll-scrub 71 frames: closed eyes → sage mode → yellow flash |
| **II** | **塵** — Particles | Cursor sweeps through Minato; 46k particles scatter & reassemble |
| **III** | **雷** — Hiraishin | Ambient lightning bolts crackle across the viewport |
| **IV** | **残像** — Afterimage | Full-bleed 71-frame dash: standing still → standing behind you |
| **V** | **螺旋丸** — Rasengan | Mouse X tracks the sphere left→right across 33 frames |
| **VI** | **遺** — Legacy | Ghost cursor reveals the night of the Nine-Tails; thunder strikes viewport-wide |

## 🛠 Tech Stack

- **Vanilla ES Modules** — no bundler, no build step
- **Three.js (r169)** via importmap CDN — particle system
- **Canvas 2D** — frame scrubbing, lightning, chakra motes, ghost trail
- **IntersectionObserver** — text reveal, decrypt, count-up animations
- **CSS Custom Properties** — theme, motion, layout
- **Google Fonts** — Shippori Mincho, Zen Kaku Gothic New, Anton, Space Grotesk, JetBrains Mono

## 🚀 Run Locally

```bash
# Python 3
python -m http.server 8000

# Node.js
npx serve .

# PHP
php -S localhost:8000
```

Then open **http://localhost:8000**

> ⚠️ **Must use a local server** — ES modules are blocked by CORS on `file://` protocol.

## 📁 Project Structure

```
Minato/
├── index.html          # Main HTML + importmap for Three.js
├── minato.css          # All styles (CSS custom properties, animations)
├── minato.js           # Main orchestration (6 acts, render loop)
├── particle-object.js  # Three.js particle system (portrait → particles)
├── ghost-cursor.js     # Canvas 2D ghost cursor trail effect
├── art/
│   ├── particle-minato.png   # Alpha-cutout for particle system
│   ├── legacy.jpg            # Legacy section background
│   └── hero.jpg              # Fallback (not included — hidden by default)
└── frames/
    ├── gaze/           # 71 frames: eyes closed → sage → flash
    ├── rasengan/       # 33 frames: rasengan traveling L→R
    └── flash/          # 71 frames: hiraishin dash L→R (frame_001.png..071.png)
```

## 🎮 Controls

| Action | Effect |
|--------|--------|
| **Scroll** | Drives Act I (gaze), Act IV (dash), progress indicators |
| **Mouse X in Act V** | Scrubs rasengan frames left ↔ right |
| **Mouse move Act VI** | Reveals ghost cursor + torch mask |
| **Click anywhere** | Gold spark burst |
| **Nav links** | Smooth scroll + hiraishin flash wipe |
| **Reduced motion** | Respects `prefers-reduced-motion` |

## 🎨 Customization

Key CSS variables (in `minato.css`):

```css
:root {
  --bg: #050812;        /* Deep night */
  --fg: #f5efe6;        /* Warm parchment */
  --gold: #ffc736;      /* Hiraishin yellow */
  --cyan: #4fd8ff;      /* Sage/chakra blue */
  --accent: #ff3d3d;    /* Nine-tails red */
  --font-jp: 'Shippori Mincho', serif;
  --font-ui: 'Zen Kaku Gothic New', sans-serif;
  --font-display: 'Anton', sans-serif;
}
```

## 📸 Credits

- **Character**: Minato Namikaze — *Naruto* by Masashi Kishimoto
- **Fonts**: Google Fonts (Shippori Mincho, Zen Kaku Gothic New, Anton, Space Grotesk, JetBrains Mono)
- **Three.js**: [threejs.org](https://threejs.org/) (MIT License)
- **Inspiration**: reactbits.dev split/reveal/decrypt/count patterns (ported to vanilla)

---

**Built with chakra and patience.** 🍥
