# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a **mobile-first** starter template for building native iOS apps using web technologies. Desktop layouts are secondary and not the focus.

**Key Technologies:**
- Nuxt 4 (Vue.js framework with SSG mode)
- Nuxt UI v4 (component library with dark mode)
- Capacitor 7 (native iOS runtime, no Ionic)
- TypeScript throughout
- pnpm as package manager

## Critical Architecture Details

### Build Output for Capacitor

The project uses `nuxt generate` (not `nuxt build`) to create a **static site** in `.output/public/`. This is critical because:
- Capacitor's `webDir` points to `.output/public`
- The iOS app loads the static HTML/JS/CSS from this directory
- Server-side rendering (SSR) is NOT used - it's a static site generation (SSG) setup

### Mobile-First Layout Pattern

The default layout (`app/layouts/default.vue`) uses a **bottom tab bar navigation** pattern:
- Header at top with app name and color mode toggle
- Main content area (scrollable)
- Bottom navigation bar (tab bar style) with Home/Settings

Do NOT use sidebar navigation or desktop-first patterns. When adding new pages, they should work in mobile viewport (375px width).

### CSS and Styling

- Global CSS import in `nuxt.config.ts`: `css: ['~/assets/css/main.css']`
- The `main.css` file imports Tailwind and Nuxt UI: `@import "tailwindcss"` and `@import "@nuxt/ui"`
- Nuxt UI components are auto-imported (no manual imports needed)
- Use Nuxt UI color system: `primary`, `secondary`, `success`, `warning`, `error`, `info`, `neutral`

### Component Availability

Check available Nuxt UI components in `.nuxt/components.d.ts` before using them. Not all expected components exist (e.g., `UToggle` doesn't exist, use `USwitch` instead).

## Development Commands

```bash
# Install dependencies
pnpm install

# Start dev server (http://localhost:3000)
pnpm dev

# Lint code
pnpm lint

# Build static site for production
pnpm build

# Sync web assets to iOS app
pnpm cap:sync

# Open iOS project in Xcode
pnpm cap:open:ios

# Build and sync in one command
pnpm ios:build
```

## iOS Development Workflow

1. Make changes to Vue/Nuxt code
2. Test in browser with `pnpm dev`
3. When ready for iOS: `pnpm ios:build`
4. Open Xcode: `pnpm cap:open:ios`
5. Run on simulator or device from Xcode

**Important:** Always run `pnpm build` before `cap sync` to regenerate the static site.

## Configuration Files

- `capacitor.config.ts` - Capacitor app ID and web directory configuration
- `nuxt.config.ts` - Modules: `@nuxt/eslint`, `@nuxt/ui`, `nuxt-mcp`
- `eslint.config.mjs` - Extends from `.nuxt/eslint.config.mjs`
- `app/app.config.ts` - Nuxt UI theme customization (currently empty)

## Common Patterns

### Adding a New Page

1. Create file in `app/pages/` (e.g., `app/pages/profile.vue`)
2. Add navigation link to `app/layouts/default.vue` bottom tab bar
3. Use Nuxt UI components (`UCard`, `UButton`, `UInput`, etc.)
4. Ensure it works in mobile viewport

### Clearing Build Cache

If you encounter hydration mismatches or stale build issues:
```bash
rm -rf .nuxt .output
```
The dev server will auto-regenerate on next start.

## Notes

- No testing framework is included by design (add as needed for your use case)
- The app uses `nuxt-mcp` module for MCP server integration
- TypeScript is configured with Nuxt's auto-generated types in `.nuxt/`
- Dark mode is enabled by default via Nuxt UI's color mode system
