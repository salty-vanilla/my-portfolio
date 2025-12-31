# Portfolio - Computer Science Researcher & Software Engineer

A minimal, monochrome portfolio website showcasing research and software projects with equal weight.

**Purpose**: Job hunting portfolio demonstrating expertise in **Computer Science Research** and **Software Engineering** (Web/Cloud).

**Based on**: [Bloomfolio](https://github.com/lauroguedes/bloomfolio) template
**Design Philosophy**: Minimalistic approach with focus on content over decoration

---

## 📋 Documentation Structure

| Document | Purpose | Audience |
|----------|---------|----------|
| `DEVELOPMENT.md` | Overall development strategy & philosophy | All contributors |
| `.github/instructions/design-rules.instructions.md` | Design & styling rules (monochrome, minimal) | Copilot, developers |
| `.github/instructions/content-structure.instructions.md` | Content format (Problem/Approach/Impact) | Content writers, Copilot |
| `CLAUDE.md` | Quick reference for Claude Code | Claude AI |
| `src/content/projects/README.md` | Projects content guide | Content writers |
| `src/content/research/README.md` | Research content guide | Content writers |

---

## 🎨 Design Principles

- **Monochrome**: Gray-scale only (no accent colors)
- **Minimal**: Generous whitespace, low information density
- **Calm**: Shadows minimal or none, subtle borders
- **Content-first**: UI is not the main focus

**Reference**: [Nagi](https://nagi-6tu.pages.dev/)

---

## 🏗️ Site Structure

### Pages
- `/` - Hero, Highlights, Featured Projects, Research, Skills, Writing, Links
- `/projects` - All projects
- `/research` - All research/publications
- `/cv` - Resume (PDF + web)
- `/about` - About me
- `/links` - External links

### Content Format
All projects and research follow **Problem / Approach / Impact** structure (no tech stack badges).

---

## ⚡ Tech Stack

- **Astro 5.x** - Static site generator
- **Tailwind CSS 4.x** - Styling
- **DaisyUI 5.x** - UI components (minimal usage)
- **TypeScript** - Type safety
- **Markdown/MDX** - Content management

---

## 🚀 Quick Start

### Prerequisites

- Node.js 18+ or 20+
- pnpm (recommended), npm, or yarn

### Installation

```bash
# Clone the repository
git clone https://github.com/salty-vanilla/my-portfolio.git

# Navigate to the project directory
cd my-portfolio

# Install dependencies
pnpm install

# Start the development server
pnpm run dev
```

Visit `http://localhost:4321` to see your portfolio!

## 📋 Commands

All commands are run from the root of the project:

| Command | Action |
| :--- | :--- |
| `pnpm install` | Install dependencies |
| `pnpm run dev` | Start dev server at `localhost:4321` |
| `pnpm run build` | Build production site to `./dist/` |
| `pnpm run preview` | Preview production build locally |
| `pnpm run astro check` | Run TypeScript and Astro checks |
| `pnpm run astro ...` | Run Astro CLI commands |

## ⚙️ Configuration

## ⚙️ Configuration

Main configuration is in `src/config.ts`. See `DEVELOPMENT.md` for detailed customization guidelines.

### Key Configuration Areas

- **Basic Info**: Name, title, description, avatar
- **Social Links**: GitHub, LinkedIn, Zenn, etc.
- **Section Visibility**: Control which sections appear
- **Theme**: Monochrome design (custom styling overrides default themes)

---

## 📝 Content Guidelines

### Projects & Research Format

All content follows **Problem / Approach / Impact** structure:

```markdown
---
title: "Project Name"
description: "One-line description"
date: 2024-01-15
---

## Problem
What problem does this solve?

## Approach
How did you approach it?

## Impact
What was the result/impact?
```

### Prohibited
- ❌ Technology stack badges
- ❌ "Technologies Used" sections
- ❌ Others' paper summaries (only your own research)

**Details**: See `.github/instructions/content-structure.instructions.md`

---

## 🎨 Design Guidelines

When implementing components:
- Use **gray-scale only** (no accent colors)
- **Generous whitespace** between sections
- **Minimal shadows** (`shadow-sm` or none)
- **Subtle borders** (`border-gray-200/300`)
- Avoid DaisyUI colorful components

**Details**: See `.github/instructions/design-rules.instructions.md`

---

## 📂 Project Structure

```
my-portfolio/
├── public/              # Static assets
├── src/
│   ├── assets/         # Images and media
│   ├── components/     # Reusable components
│   │   ├── Hero.astro
│   │   ├── Projects.astro
│   │   ├── ProjectCard.astro
│   │   └── ...
│   ├── content/        # Content collections
│   │   ├── projects/   # Project entries (Problem/Approach/Impact)
│   │   ├── research/   # Research/publications (own work only)
│   │   ├── work/       # Work experience
│   │   ├── education/  # Education history
│   │   ├── about/      # About section
│   │   └── blog/       # Blog posts (linked from Zenn)
│   ├── layouts/        # Layout templates
│   │   ├── Layout.astro
│   │   ├── BlogLayout.astro
│   │   └── ProjectLayout.astro
│   ├── pages/          # File-based routing
│   │   ├── index.astro
│   │   ├── projects/
│   │   ├── research/
│   │   ├── cv/
│   │   └── ...
│   ├── styles/         # Global CSS
│   │   └── global.css
│   ├── config.ts       # Site configuration
│   └── content.config.ts
├── .github/
│   └── instructions/   # Copilot/Claude instructions
│       ├── design-rules.instructions.md
│       └── content-structure.instructions.md
├── DEVELOPMENT.md      # Development strategy
├── CLAUDE.md          # Claude Code reference
└── README.md          # This file
```

---

## 📋 Commands

All commands are run from the root of the project:

| Command | Action |
| :--- | :--- |
| `pnpm install` | Install dependencies |
| `pnpm run dev` | Start dev server at `localhost:4321` |
| `pnpm run build` | Build production site to `./dist/` |
| `pnpm run preview` | Preview production build locally |
| `pnpm run astro check` | Run TypeScript and Astro checks |

---

## 🧭 External Content Strategy

| Content Type | Location | Notes |
|--------------|----------|-------|
| Technical blog | [Zenn](https://zenn.dev/) | Portfolio links to articles |
| Paper summaries/surveys | Separate paper archive site | Not in this portfolio |
| Own research | This portfolio | Research section |

---

## 🚢 Deployment

This project can be deployed to:
- **GitHub Pages**
- **Vercel**
- Any static hosting service

Build command: `pnpm run build`  
Output directory: `./dist/`

---

## 📚 Additional Documentation

- `DEVELOPMENT.md` - Complete development philosophy and strategy
- `CLAUDE.md` - Quick reference for Claude Code
- `.github/instructions/design-rules.instructions.md` - Design implementation rules
- `.github/instructions/content-structure.instructions.md` - Content format guidelines
- `src/content/projects/README.md` - Projects content guide
- `src/content/research/README.md` - Research content guide

---

## 📄 License

MIT License - see `LICENSE` file for details.

---

## 🙏 Credits

Based on [Bloomfolio](https://github.com/lauroguedes/bloomfolio) by Lauro Guedes.  
Design philosophy inspired by [Minimalistic Portfolio](https://github.com/shonebinu/portfolio/).

---

**Built with**: Astro 5 × Tailwind CSS 4 × TypeScript  
**Philosophy**: Minimal, Monochrome, Content-First
│   │   └── YouTube.astro
│   ├── content/        # Content collections
│   │   ├── about/     # About section (1 file)
│   │   ├── blog/      # Blog posts (.md or .mdx)
│   │   ├── education/ # Education history
│   │   ├── hackathons/# Hackathon entries
│   │   ├── projects/  # Portfolio projects
│   │   └── work/      # Work experience
│   ├── layouts/       # Page layouts
│   │   ├── Layout.astro
│   │   ├── BlogLayout.astro
│   │   └── ProjectLayout.astro
│   ├── pages/         # File-based routing
│   │   ├── index.astro
│   │   ├── blog/
│   │   │   ├── index.astro
│   │   │   └── [...slug].astro
│   │   └── projects/
│   │       ├── index.astro
│   │       └── [...slug].astro
│   ├── styles/
│   │   └── global.css # Tailwind + DaisyUI
│   ├── config.ts      # Site configuration
│   └── content.config.ts # Content schemas
├── astro.config.mjs   # Astro configuration
├── package.json
├── tsconfig.json
└── README.md
```

## 📝 Content Management

### Creating Content

All content is stored in `src/content/` organized by type. Each content type has a specific schema.

#### Blog Posts

Create a new file in `src/content/blog/`:

```markdown
---
title: "Your Post Title"
description: "Brief description for SEO"
image: "./featured-image.png"
publishDate: "2024-01-25"
tags: ["Tag1", "Tag2"]
---

Your content here...
```

Supports both `.md` and `.mdx` files. Use `.mdx` for rich media embeds (Spotify, YouTube, Twitter).

#### Projects

Create a new file in `src/content/projects/`:

```markdown
---
title: "Project Name"
description: "Brief description"
image: "./screenshot.png"
startDate: "2023-01-15"
endDate: "2023-06-30"  # Optional (omit for ongoing)
skills: ["React", "Node.js", "MongoDB"]
demoLink: "https://demo.example.com"  # Optional
sourceLink: "https://github.com/..."  # Optional
---

Detailed project description...
```

#### Work Experience

Create a new file in `src/content/work/`:

```markdown
---
title: "Company Name"
subtitle: "Job Title"
startDate: "2020-01-15"
endDate: "2023-06-30"  # Optional (omit for current position)
logo: "https://company-logo-url.com"  # Optional
link: "https://company-website.com"   # Optional
---

Job description and achievements...
```

For complete documentation on content creation, see the [Content Collections Guide](/blog/guides/content-collections-guide) and [Markdown Guide](/blog/guides/markdown-guide).

## 🎨 Customization

### Changing Themes

Edit `src/config.ts`:

```typescript
enableThemeSelector: true  // Dropdown with 6 themes
// OR
enableThemeSelector: false  // Simple light/dark toggle
```

### Adding Custom Styles

Add custom CSS in component `<style>` tags or extend `src/styles/global.css`:

```css
@import "tailwindcss";
@plugin "daisyui";

/* Your custom styles here */
```

### Creating New Sections

1. Create a new component in `src/components/`
2. Import and add to `src/pages/index.astro`
3. Optionally add a toggle in `src/config.ts`

## 🚀 Deployment

### Build for Production

```bash
pnpm run build
```

Output is generated in `dist/` directory.

### Deploy to Vercel

[![Deploy with Vercel](https://vercel.com/button)](https://vercel.com/new/clone?repository-url=https://github.com/lauroguedes/bloomfolio)

1. Connect your GitHub repository
2. Vercel auto-detects Astro
3. Deploy!

### Deploy to Netlify

1. Connect your repository
2. Build command: `pnpm run build`
3. Publish directory: `dist`

### Deploy to Cloudflare Pages

1. Connect your repository
2. Build command: `pnpm run build`
3. Build output directory: `dist`

### Other Platforms

Bloomfolio works with any static hosting platform that supports Node.js builds:
- GitHub Pages
- AWS S3 + CloudFront
- Firebase Hosting
- Render
- Railway

## 🛠️ Tech Stack

- **[Astro 5](https://astro.build)** - Static site generator
- **[Tailwind CSS 4](https://tailwindcss.com)** - Utility-first CSS framework
- **[DaisyUI 5](https://daisyui.com)** - Component library for Tailwind
- **[TypeScript](https://www.typescriptlang.org/)** - Type safety
- **[MDX](https://mdxjs.com/)** - Enhanced Markdown
- **[Lucide Icons](https://lucide.dev/)** - Icon library

## 📚 Documentation

- **[Complete Guide](https://bloomfolio-astro.vercel.app/blog/guides/bloomfolio-complete-guide)** - Comprehensive setup and customization guide
- **[Content Collections Guide](https://bloomfolio-astro.vercel.app/blog/guides/content-collections-guide)** - Learn about Astro Content Collections
- **[Markdown Guide](https://bloomfolio-astro.vercel.app/blog/guides/markdown-guide)** - Master Markdown and MDX syntax
- **[Astro Docs](https://docs.astro.build)** - Official Astro documentation
- **[Tailwind CSS Docs](https://tailwindcss.com/docs)** - Tailwind CSS documentation
- **[DaisyUI Docs](https://daisyui.com/docs)** - DaisyUI component documentation

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🙏 Acknowledgments

- Built with [Astro](https://astro.build)
- Styled with [Tailwind CSS](https://tailwindcss.com) and [DaisyUI](https://daisyui.com)
- Icons from [Lucide](https://lucide.dev)
- Inspired by modern portfolio designs and the developer community

## 💬 Support

- 📖 [Documentation](https://bloomfolio-astro.vercel.app/blog/guides/bloomfolio-complete-guide)
- 🐛 [Report Issues](https://github.com/lauroguedes/bloomfolio/issues)
- 💬 [Discussions](https://github.com/lauroguedes/bloomfolio/discussions)

---
Please if you find this project helpful, consider giving it a ⭐ on GitHub!

Crafted by an Artisan ⛏️ [Lauro Guedes](https://lauroguedes.dev)
