# Sobolev Embeddings on Bounded Domains

[![Slidev](https://img.shields.io/badge/Slidev-v51.8.1-2d7748?style=flat-square&logo=vue.js)](https://sli.dev/)
[![Vue](https://img.shields.io/badge/Vue-3.5.16-4fc08d?style=flat-square&logo=vue.js)](https://vuejs.org/)
[![Theme](https://img.shields.io/badge/Theme-Seriph-blue?style=flat-square)](https://github.com/slidevjs/slidev-theme-seriph)
[![GitHub Pages](https://img.shields.io/badge/GitHub%20Pages-Deployed-brightgreen?style=flat-square&logo=github)](https://adamamer20.github.io/sobolev_slides/)
[![License](https://img.shields.io/badge/License-MIT-green?style=flat-square)](LICENSE)

A comprehensive mathematical presentation on Sobolev embeddings for bounded domains, covering fundamental theorems in partial differential equations theory and their applications to nonlinear PDE problems.

## 📋 Mathematical Content Overview

This presentation provides rigorous proofs and applications of key embedding theorems:

### Core Theorems
- **Theorem 2: Bounded Domain Embedding**
  - Extension and mollification techniques for $W^{1,p}(U) \hookrightarrow L^{p^*}(U)$
  - Full $W^{1,p}$-norm bounds for functions on bounded domains
  - Critical Sobolev exponent $p^* = \frac{np}{n-p}$ analysis

- **Theorem 3: Zero-Trace Embedding**  
  - Enhanced bounds for $W_0^{1,p}(U)$ functions
  - Gradient-only norm requirements: $\|u\|_{L^q(U)} \leq C \|Du\|_{L^p(U)}$
  - Extended range $1 \leq q \leq p^*$ via Lyapunov's inequality

### PDE Application
- **Global Existence for Semilinear Heat Equation**
  - Energy method analysis for $u_t = \Delta u + u^3$
  - Critical threshold behavior via $H_0^1$ energy estimates
  - Sobolev embedding applications in nonlinear PDE theory

### Recommended References
- Evans, L.C. - *Partial Differential Equations*
- Brezis, H. - *Functional Analysis, Sobolev Spaces and Partial Differential Equations*
- Adams, R.A. & Fournier, J.J.F. - *Sobolev Spaces*


## 🌐 Live Demo

🚀 **[View Live Presentation](https://adamamer20.github.io/sobolev_slides/)** *(Replace 'adamamer20' with actual GitHub username)*

## 🚀 Quick Start

### Installation & Development

```bash
# Clone the repository
git clone https://github.com/adamamer20/sobolev_slides.git
cd sobolev_slides

# Install dependencies (using pnpm)
pnpm install

# Start development server
pnpm dev

# Open in browser
# Visit http://localhost:3030
```

### Alternative Package Managers

```bash
# Using npm
npm install && npm run dev

# Using yarn  
yarn install && yarn dev
```

## 📦 Deployment Options

### GitHub Pages (Automated)
The repository is configured with GitHub Actions for automatic deployment:

- **Automatic deployment**: Push to `main` branch triggers deployment
- **Manual deployment**: Use "Actions" tab → "Deploy Slidev to GitHub Pages" → "Run workflow"
- **Live URL**: `https://adamamer20.github.io/sobolev_slides/` (replace with your username)

```bash
# Manual build (optional)
pnpm run build
# Built files will be in dist/ directory
```

**Setup Instructions**:
1. Enable GitHub Pages in repository settings
2. Set source to "GitHub Actions"
3. Push to main branch or run workflow manually

### Netlify
Automatic deployment is configured via [`netlify.toml`](netlify.toml):
```bash
# Simply push to main branch
git push origin main
# Netlify will automatically build and deploy
```

### Vercel
Deployment configuration in [`vercel.json`](vercel.json):
```bash
# Connect repository to Vercel
# Automatic deployment on push to main
# Or use Vercel CLI:
vercel --prod
```

## 📁 Project Structure

```
sobolev_slides/
├── slides.md              # Main presentation content (390 lines)
├── package.json           # Dependencies and scripts
├── netlify.toml           # Netlify deployment config
├── vercel.json            # Vercel deployment config
├── components/            # Vue components
│   └── Counter.vue        # Interactive counter component
├── pages/                 # Additional slide pages
│   └── imported-slides.md # Supplementary content
└── snippets/              # Code snippets
    └── external.ts        # TypeScript examples
```

## ⚙️ Technical Details

### Slidev Configuration
- **Version**: 51.8.1 (Latest stable)
- **Theme**: Seriph (Professional academic theme)
- **Vue Version**: 3.5.16
- **GitHub Pages**: Optimized with base URL `/sobolev_slides/`
- **Features Used**:
  - LaTeX mathematical notation
  - Smooth slide transitions (`slide-left`)
  - Markdown-it with custom directives (`mdc: true`)
  - Persistent drawings disabled for clean exports
  - Automated GitHub Actions deployment

### Mathematical Rendering
- Full LaTeX support via KaTeX
- Display math: `$$ ... $$`
- Inline math: `$ ... $`
- Custom mathematical environments supported

### Export Options
```bash
# Export to PDF
pnpm run export

# Export with custom options
slidev export --format pdf --timeout 30000
```

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🙏 Acknowledgments

### Technical Acknowledgments
- Built with [Slidev](https://sli.dev/) - A presentation framework for developers
- Mathematical rendering powered by [KaTeX](https://katex.org/)
- Theme based on [Slidev Seriph](https://github.com/slidevjs/slidev-theme-seriph)
