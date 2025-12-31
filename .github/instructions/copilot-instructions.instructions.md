# GitHub Copilot Instructions

This file provides guidance to GitHub Copilot when working with code in this repository.

## Project Overview

Bloomfolio is an Astro-based portfolio template using Tailwind CSS 4.x and DaisyUI for styling. The project follows Astro's standard project structure with file-based routing.

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

## Coding Patterns & Best Practices

### Layout Usage
Pages should import and wrap content in `Layout.astro`:
```astro
---
import Layout from "../layouts/Layout.astro";
---
<Layout>
  <!-- Page content -->
</Layout>
```

### Global CSS Import
Only import `global.css` in the main layout to avoid duplicate Tailwind imports.

### Styling Priority
1. Use Tailwind utility classes first
2. Then DaisyUI components
3. Component-scoped `<style>` tags for custom styling only when necessary

### TypeScript
Astro's strict TypeScript config is enabled - expect type checking on component props and imports.

## Template Structure

Bloomfolio is designed as a portfolio website template with the following sections:

### Hero Section
- Title, Description, Avatar

### About Section
- Title, Description

### Work Section (Content Collection)
- Company Name, Position, Position Description
- Period (e.g., May 2012 - Feb 2020)

### Education Section (Content Collection)
- University Name, Course Name, Description
- Period, Link to college website

### Projects Section (Content Collection)
- Image, Title, Period, Description
- Skills, Link Demo, Link Source

### Hackathon Section (Content Collection)
- Period, Title, Location, Description
- Link Source

### Contact Section
- Contact information

### Blog Page (Content Collection)
- Image, Title, Publish Date, Content

## Content Collections

This project uses Astro's Content Collections feature for managing content:

- Content is stored in `src/content/` directory
- Collections are defined in `src/content.config.ts`
- Use `getCollection()` and `getEntry()` to query content
- Each collection has a schema for type safety

## Component Development Guidelines

When creating or modifying components:

1. **Use TypeScript**: Define prop types using Astro's Props type
2. **Component Isolation**: Keep components focused on a single responsibility
3. **Responsive Design**: Use Tailwind's responsive prefixes (sm:, md:, lg:, xl:)
4. **DaisyUI Components**: Prefer DaisyUI components over custom implementations when available
5. **Accessibility**: Include appropriate ARIA labels and semantic HTML

## File Naming Conventions

- **Components**: PascalCase (e.g., `ProjectCard.astro`)
- **Layouts**: PascalCase (e.g., `BlogLayout.astro`)
- **Pages**: kebab-case for routes (e.g., `blog/[...slug].astro`)
- **Content**: kebab-case (e.g., `my-first-post.md`)

## Common Tasks

### Adding a New Component
1. Create `.astro` file in `src/components/`
2. Define TypeScript props interface if needed
3. Use Tailwind/DaisyUI for styling
4. Import and use in pages or other components

### Adding a New Page
1. Create `.astro` file in `src/pages/`
2. File path determines the route
3. Import and use `Layout.astro`
4. Add page-specific components

### Adding New Content
1. Add markdown/MDX file to appropriate `src/content/` subdirectory
2. Follow the schema defined in `src/content.config.ts`
3. Use frontmatter for metadata
4. Query using `getCollection()` in components/pages
