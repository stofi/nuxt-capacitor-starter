# Nuxt Capacitor Starter

A mobile-first starter template for building iOS apps with modern web technologies.

## Tech Stack

- **Nuxt 4.2.1** - Vue.js framework with TypeScript
- **Nuxt UI v4** - Beautiful, accessible components with dark mode
- **Capacitor 7.4.4** - Native iOS runtime (without Ionic)
- **ESLint** - Code linting with Nuxt module
- **pnpm** - Fast, disk space efficient package manager
- **OXC-inspired** - Originally planned OXC, switched to ESLint for Vue template support

## Features

- 📱 Mobile-first layout with bottom tab navigation
- 🌙 Dark mode support with toggle
- 🎨 Nuxt UI components pre-configured
- 📦 Simple placeholder pages (Home, Settings)
- 🔧 TypeScript configured and ready
- ✅ ESLint for code quality
- 🚀 Ready to build to iOS device

## Setup

Install dependencies with pnpm:

```bash
pnpm install
```

## Development

Start the development server on `http://localhost:3000`:

```bash
pnpm dev
```

## Building for iOS

1. **Build the web app:**
   ```bash
   pnpm build
   ```

2. **Sync with Capacitor:**
   ```bash
   pnpm cap:sync
   ```

3. **Open in Xcode:**
   ```bash
   pnpm cap:open:ios
   ```

4. **Or build and sync in one command:**
   ```bash
   pnpm ios:build
   ```

## Project Structure

```
nuxt-capacitor-starter/
├── app/
│   ├── assets/css/        # Global styles
│   ├── layouts/           # Layout components (mobile tab bar)
│   ├── pages/             # Route pages (index, settings)
│   └── app.vue            # Root component
├── ios/                   # Capacitor iOS project
├── public/                # Static assets
├── capacitor.config.ts    # Capacitor configuration
└── nuxt.config.ts         # Nuxt configuration
```

## Available Scripts

- `pnpm dev` - Start development server
- `pnpm build` - Generate static site for production
- `pnpm lint` - Lint code with ESLint
- `pnpm cap:sync` - Sync web assets with Capacitor
- `pnpm cap:open:ios` - Open iOS project in Xcode
- `pnpm ios:build` - Build and sync in one command

## Requirements

- Node.js 18+
- pnpm 10+
- Xcode 16.0+ (for iOS development)
- macOS (for iOS builds)

## Notes

- This is a **mobile-first** template - desktop layouts are secondary
- Uses `nuxt generate` to create static output for Capacitor
- The `.output/public` directory is synced to the iOS app
- No testing framework included by design (add as needed)

## Learn More

- [Nuxt Documentation](https://nuxt.com/docs)
- [Nuxt UI Documentation](https://ui.nuxt.com)
- [Capacitor Documentation](https://capacitorjs.com/docs)
