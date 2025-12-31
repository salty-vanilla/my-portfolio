# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a **minimal, monochrome portfolio website** for a **Computer Science Researcher & Software Engineer**. It showcases research (publications) and software projects (Web/Cloud) with equal weight.

**Core Philosophy**: Research × Software × Web × Cloud. The UI is not the main focus—content and clarity are.

**Based on**: Bloomfolio template (Astro 5.x + Tailwind CSS 4.x + DaisyUI)
**Design Approach**: Minimalistic design philosophy (whitespace, hierarchy, subtraction)

> **Key Documents**:
> - `DEVELOPMENT.md` - Overall development strategy
> - `.github/instructions/design-rules.instructions.md` - Design & styling rules
> - `.github/instructions/content-structure.instructions.md` - Content guidelines

## Development Commands

```bash
# Install dependencies
pnpm install

# Start development server (localhost:4321)
pnpm run dev

# Build for production (outputs to ./dist/)
pnpm run build

# Preview production build locally
pnpm run preview

# Run Astro CLI commands
pnpm run astro -- <command>

# Type checking
pnpm run astro check
```

## Architecture

### Framework & Build Setup

- **Astro 5.x**: Static site generator with component islands architecture
- **Tailwind CSS 4.x**: Integrated via Vite plugin (`@tailwindcss/vite`)
- **DaisyUI**: Loaded as Tailwind plugin in `src/styles/global.css`
- **TypeScript**: Strict mode enabled via `astro/tsconfigs/strict`

### Styling System

The styling architecture uses Tailwind CSS 4.x with the new CSS-first configuration:

1. Global styles are defined in `src/styles/global.css` using `@import "tailwindcss"` and `@plugin "daisyui"`
2. The Tailwind Vite plugin is configured in `astro.config.mjs`
3. DaisyUI components are available project-wide through the plugin system
4. Component-scoped styles can be added in `<style>` tags within `.astro` files

### Project Structure

```
src/
├── assets/          # Static assets (images, SVGs)
├── components/      # Reusable Astro components
├── layouts/         # Layout templates (wraps page content)
├── pages/           # File-based routing (each file = route)
└── styles/          # Global CSS (Tailwind + DaisyUI imports)
```

### Component Architecture

- **Layouts** (`src/layouts/`): Base HTML structure, imports global CSS, defines `<slot />` for page content
- **Pages** (`src/pages/`): Map directly to routes, import layouts and components
- **Components** (`src/components/`): Reusable UI elements with isolated scopes

### Key Patterns

1. **Layout Usage**: Pages should import and wrap content in `Layout.astro`:
   ```astro
   ---
   import Layout from "../layouts/Layout.astro";
   ---
   <Layout>
     <!-- Page content -->
   </Layout>
   ```

2. **Global CSS Import**: Only import `global.css` in the main layout to avoid duplicate Tailwind imports

3. **Styling Priority**: Use Tailwind utility classes first, minimal DaisyUI (layout only), avoid colorful components

4. **TypeScript**: Astro's strict TypeScript config is enabled - expect type checking on component props and imports

## Design Rules (CRITICAL)

### Color Palette
- **Almost monochrome only**: gray-50 to gray-900, white, black
- **No accent colors** (blue-500, green-600, etc.)
- **Reference site**: [Nagi](https://nagi-6tu.pages.dev/)

### Spacing & Layout
- **Generous whitespace**: `py-16 md:py-24 lg:py-32` between sections
- **Breathing room**: Lower information density
- **Max width**: `max-w-4xl lg:max-w-5xl`

### Typography
- Headings: `text-4xl md:text-5xl`, `font-bold`
- Body: `text-base md:text-lg`, `font-normal`
- Line height: `leading-relaxed`

### Shadows & Borders
- Shadows: `shadow-sm` or none (never `shadow-lg`)
- Borders: `border-gray-200` or `border-gray-300`
- Rounded: `rounded-lg` or `rounded-xl`

### DaisyUI Usage
- ✅ Layout utilities only (`container`, `prose`)
- ❌ Colorful components (`btn-primary`, `alert-success`, `badge-accent`)

> **See**: `.github/instructions/design-rules.instructions.md` for complete rules

## Site Structure

### Homepage (`/`)
1. Hero - Computer Science Researcher & Software Engineer
2. Highlights - Research / Software / Cloud
3. Featured Projects (3 items)
4. Research (own publications only)
5. Skills
6. Writing (Zenn links)
7. Links

### Other Pages
- `/projects` - All projects
- `/research` - All research/publications
- `/cv` - Resume (PDF + web version)
- `/about` - About me
- `/links` - External links

## Content Structure (CRITICAL)

### Projects & Research Format

**Problem / Approach / Impact** structure (NOT tech stack badges):

```markdown
---
title: "Project Name"
description: "One-line description"
date: 2024-01-15
url: "https://..."
github: "https://github.com/..."
---

## Problem
What problem does this solve?

## Approach
How did you approach it?

## Impact
What was the result/impact?
```

### Research Content
- **Own research only** (no paper summaries or surveys)
- Same Problem/Approach/Impact structure
- Include: venue, authors, pdf, arxiv, code

### Prohibited
- ❌ Technology badges
- ❌ "Technologies Used" sections
- ❌ Others' paper summaries/surveys (→ separate site)

> **See**: `.github/instructions/content-structure.instructions.md` for complete rules

## Hero Section Content

```
Title: Computer Science Researcher & Software Engineer
Subtitle: Computer Vision / Industrial Anomaly Detection / Web & Cloud Systems
Description: 研究成果を、Webとクラウド基盤で運用可能なプロダクトに落とし込みます。

CTAs:
- Primary: View Projects
- Secondary: View CV
- Link: Research & Publications
- Link: Paper Archive (external site)
```

## Development Workflow

### Before Implementing
1. Read `DEVELOPMENT.md` for overall strategy
2. Check `.github/instructions/design-rules.instructions.md` for styling
3. Check `.github/instructions/content-structure.instructions.md` for content format

### MCP Tools for Documentation

When building components or implementing features, **always use the available MCP tools** to search documentation:

1. **Astro Documentation**: Use `mcp__astro-docs__search_astro_docs` to search official Astro framework documentation
   - Use for: routing, components, content collections, layouts, data fetching, SSR/SSG patterns

2. **DaisyUI Documentation**: Use `mcp__context7__resolve-library-id` and `mcp__context7__get-library-docs` to search DaisyUI component documentation
   - Use for: UI components, theming, component props, styling patterns
   - First resolve the library ID, then fetch the documentation with specific topics

**Important**: Always consult these documentation sources before implementing features to ensure best practices and correct API usage.
