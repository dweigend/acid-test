# 🌈 The Algorithmic Acid Test - Interactive Presentation

> _Transform 2025 Conference • KIND Lab • David Weigend_

An interactive [Slidev](https://github.com/slidevjs/slidev) presentation exploring how AI dissolves the boundaries of design research, featuring psychedelic terminal aesthetics and consciousness-expanding content.

## 🚀 Quick Start

```bash
pnpm install
pnpm dev
```

Visit **http://localhost:3030** to experience the interactive presentation.

> **🎬 Live Demo**: [Available during Transform 2025](https://kind-lab.de/transform2025/schedule/25/)

## 🎨 Psychedelic Terminal Theme

This presentation features a unique **consciousness-expanding** aesthetic that bridges 1960s psychedelia with modern terminal aesthetics:

- **🌈 Psychedelic Colors**: Vibrant terminal green, electric blues, consciousness-expanding purples
- **⚡ Beat Generation Vibes**: Typography and layouts inspired by underground comix and poster art
- **🖥️ Terminal Aesthetics**: Monospace fonts, `>` arrow bullets, command-line inspired navigation
- **🎭 Interactive Elements**: Vue components that dissolve the boundary between presentation and experience

### Theme Colors

- **Primary**: Terminal green (`#a4e400`) - headings and highlights
- **Accent colors**: Blue, purple, orange, cyan, yellow
- **Background**: Dark terminal (`#1a1a1a`) with lighter variants for code blocks

### Customization

The theme is defined in `styles/index.css` and uses CSS custom properties:

```css
:root {
  --terminal-bg: #1a1a1a;
  --terminal-green: #a4e400;
  --terminal-blue: #61afef;
  /* ... */
}
```

## 📁 Project Structure

```
├── slides.md              # Main presentation content
├── styles/
│   └── index.css          # Custom terminal theme (auto-loaded)
├── components/            # Vue components
│   └── Counter.vue        # Interactive counter example
├── snippets/              # Code examples
└── public/               # Static assets
```

## 🛠️ Development

- **Edit content**: Modify `slides.md` with Markdown and frontmatter
- **Custom styling**: Update `styles/index.css` for theme changes
- **Components**: Add Vue components in `components/` directory
- **Hot reload**: Changes reflect immediately in browser

## 📦 Export & Deployment

```bash
pnpm export    # Export to PDF, PPTX, PNG, or SPA
pnpm build     # Build for production deployment
pnpm preview   # Preview production build
```

**Deployment Ready For:**

- 🌐 **Netlify**: Zero-config deployment (see `netlify.toml`)
- ▲ **Vercel**: Optimized build configuration (see `vercel.json`)
- 📄 **GitHub Pages**: Static site generation available
- 💻 **Local Hosting**: Full offline presentation capability

## 🎯 Conference Context

This presentation was created for **[Transform 2025](https://kind-lab.de/transform2025/)** - a conference exploring the future of human-AI creative collaboration at KIND Lab.

**Key Themes:**

- 🧠 **Consciousness Expansion**: How AI extends human creative capabilities
- 🎨 **Design Research**: Empirical studies on AI-assisted creativity
- 📚 **Beat Generation**: Historical parallels between 1960s counterculture and AI revolution
- ⚡ **Boundary Dissolution**: The intersection of human and machine creativity

## 📚 Learn More

- **[Complete Project](../README.md)**: Full repository with AI content generation
- **[Content Creator](../content-creator/README.md)**: AI-powered presentation pipeline
- [Slidev Documentation](https://sli.dev/)
- [Transform 2025 Conference](https://kind-lab.de/transform2025/schedule/25/)

---

_Part of the **Algorithmic Acid Test** project by [David Weigend](https://weigend.studio) • Transform 2025 • KIND Lab_
