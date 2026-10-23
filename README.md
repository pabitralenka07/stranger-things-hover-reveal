<div align="center">

# ⚡ Stranger Things: Upside Down Reveal Effect

An interactive, dark-fantasy web experience inspired by Netflix's **Stranger Things**. Built with **React 19**, **Vite**, and **Framer Motion**, this project features a smooth cursor-following portal effect that peels back the surface of Hawkins to reveal the terrifying *Upside Down* dimension.

[![React](https://img.shields.io/badge/React-19.2.0-61DAFB?style=for-the-badge&logo=react&logoColor=black)](https://react.dev/)
[![Vite](https://img.shields.io/badge/Vite-7.2.4-646CFF?style=for-the-badge&logo=vite&logoColor=white)](https://vitejs.dev/)
[![Framer Motion](https://img.shields.io/badge/Framer_Motion-12.23-0055FF?style=for-the-badge&logo=framer&logoColor=white)](https://www.framer.com/motion/)
[![CSS3](https://img.shields.io/badge/CSS3-Masking_&_Gradients-1572B6?style=for-the-badge&logo=css3&logoColor=white)](https://developer.mozilla.org/en-US/docs/Web/CSS/mask-image)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg?style=for-the-badge)](https://opensource.org/licenses/MIT)

</div>

---

## 🌟 Overview

When you navigate through the tranquil night streets of Hawkins, Indiana, moving your cursor opens an organic, smoky rift into the **Upside Down**—exposing red lightning, floating spores, and the colossal silhouette of the **Mind Flayer**.

### ✨ Highlights

- 🌀 **Fluid Interactive Mask Reveal**: Dynamic multi-layered radial gradient masking that seamlessly tracks cursor velocity using lerped animation (`requestAnimationFrame`).
- 🎬 **Retro 80s Hawkins Aesthetic**: Authentic eerie typography, glowing crimson neon text shadows, and high-impact cinematic visuals.
- 🎭 **Orchestrated Motion**: Staggered entrance sequences powered by **Framer Motion** for headlines, narrative teasers, and action buttons.
- 💎 **Glassmorphic Navigation Bar**: Translucent backdrop-filtered frosted header with glowing crimson hover underlines.
- ⚡ **Next-Gen Performance**: Instant HMR and lightning-fast asset delivery powered by **Vite**.

---

## 🔬 How the Portal Effect Works

The reveal effect combines **JavaScript physics interpolation** with **CSS Masking**:

1. **Smooth Mouse Follower (LERP)**:
   Instead of snapping directly to cursor coordinates, an animation loop eases the position toward the pointer at 5% delta per frame:
   ```javascript
   x += (mouseX - x) * 0.05;
   y += (mouseY - y) * 0.05;
   ```
2. **CSS Custom Properties**:
   The calculated `x` and `y` offsets are dynamically assigned to CSS variables `--x` and `--y` on the reveal container.
3. **Compound Radial Gradient Masking**:
   The `.fire-reveal` layer uses multiple offset `radial-gradient` circles inside `-webkit-mask-image` to generate an organic, fluid portal cutout rather than a rigid circle:
   ```css
   mask-image:
     radial-gradient(circle 400px at var(--x) var(--y), rgba(255,255,255,1) 0%, transparent 70%),
     radial-gradient(circle 450px at calc(var(--x) + 50px) calc(var(--y) - 40px), rgba(255,255,255,0.8) 0%, transparent 70%),
     radial-gradient(circle 200px at calc(var(--x) - 50px) calc(var(--y) + 30px), rgba(255,255,255,0.6) 0%, transparent 70%);
   ```

---

## 📁 Project Structure

```text
stranger-things-hover-reveal/
├── public/
│   └── images/
│       ├── will1.webp        # Hawkins night background (base state)
│       └── v1.png            # The Upside Down dimension (reveal state)
├── src/
│   ├── assets/               # Static assets & icons
│   ├── components/
│   │   ├── Hero.jsx          # Interactive hero section with mouse tracking logic
│   │   ├── Hero.css          # CSS mask-image radial gradient & styling
│   │   ├── Navbar.jsx        # Glassmorphism header component
│   │   └── Navbar.css        # Frosted glass styling & hover effects
│   ├── App.jsx               # Root application component
│   ├── App.css               # Global application styles
│   ├── index.css             # Base resets
│   └── main.jsx              # React application entry point
├── index.html                # HTML template
├── package.json              # Project dependencies & scripts
└── vite.config.js            # Vite configuration
```

---

## 🚀 Getting Started

### Prerequisites

- [Node.js](https://nodejs.org/) (version `20.19.0+` or `22.12.0+` recommended)
- [npm](https://www.npmjs.com/) or [yarn](https://yarnpkg.com/) / [pnpm](https://pnpm.io/)

### Installation

1. **Clone the repository:**
   ```bash
   git clone https://github.com/<your-username>/stranger-things-hover-reveal.git
   cd stranger-things-hover-reveal
   ```

2. **Install dependencies:**
   ```bash
   npm install
   ```

3. **Start the local development server:**
   ```bash
   npm run dev
   ```

4. **Open in browser:**
   Navigate to [http://localhost:5173](http://localhost:5173) to explore the live portal!

---

## 🛠️ Available Scripts

| Command | Description |
| :--- | :--- |
| `npm run dev` | Starts Vite dev server with instant Hot Module Replacement (HMR) |
| `npm run build` | Compiles optimized production bundle into `dist/` |
| `npm run preview` | Locally previews the production build |
| `npm run lint` | Runs ESLint to check for code quality and syntax issues |

---

## 🎨 Tech Stack

- **Core Framework:** [React 19](https://react.dev/)
- **Build Tool:** [Vite 7](https://vitejs.dev/)
- **Animation Engine:** [Framer Motion](https://www.framer.com/motion/)
- **Styling:** Vanilla CSS3 (CSS Variables, Flexbox, Transitions, Keyframes)
- **Effects:** CSS Masking (`mask-image`, `-webkit-mask-image`, `radial-gradient`)

---

## 🤝 Contributing

Contributions, issues, and feature requests are welcome!
Feel free to check the [issues page](https://github.com/<your-username>/stranger-things-hover-reveal/issues).

1. Fork the Project
2. Create your Feature Branch (`git checkout -b feature/AmazingFeature`)
3. Commit your Changes (`git commit -m 'feat: add some AmazingFeature'`)
4. Push to the Branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

---

## 📜 License

Distributed under the **MIT License**. See `LICENSE` for more information.

---

<div align="center">
  <sub>Made with ❤️ and inspired by Netflix's Stranger Things. Enter the Upside Down if you dare.</sub>
</div>

