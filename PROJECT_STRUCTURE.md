# Project Structure

This document provides a detailed overview of the ThreadMill Education project structure, explaining the purpose of each directory and key files.

## 📁 Directory Overview

```
ThreadMill/
├── .git/                           # Git version control
├── app/                            # Next.js App Router directory
│   ├── actions/                   # Server Actions (API logic)
│   ├── globals.css                # Global styles and CSS variables
│   ├── layout.tsx                 # Root layout component
│   └── page.tsx                   # Home page component
├── components/                     # React components
│   ├── ui/                        # Reusable UI primitives (Radix UI)
│   └── *.tsx                      # Feature-specific components
├── hooks/                          # Custom React hooks
├── lib/                           # Utility functions and helpers
├── public/                        # Static assets (images, icons)
├── styles/                        # Additional stylesheets
├── .gitignore                     # Git ignore rules
├── CHANGELOG.md                   # Version history
├── CODE_OF_CONDUCT.md            # Community guidelines
├── CONTRIBUTING.md                # Contribution guidelines
├── LICENSE                        # MIT License
├── PROJECT_STRUCTURE.md           # This file
├── README.md                      # Project documentation
├── SECURITY.md                    # Security policy
├── components.json                # shadcn/ui configuration
├── next.config.mjs               # Next.js configuration
├── package.json                   # Dependencies and scripts
├── pnpm-lock.yaml                # Lock file for pnpm
├── postcss.config.mjs            # PostCSS configuration
├── tsconfig.json                 # TypeScript configuration
└── tailwind.config.ts            # Tailwind CSS configuration (if exists)
```

## 📂 Detailed Directory Breakdown

### `/app` - Next.js App Router

The `app` directory uses Next.js 13+ App Router architecture.

```
app/
├── actions/                        # Server-side actions
│   └── generate-learning-path.ts  # AI learning path generation
├── globals.css                     # Global CSS and Tailwind directives
├── layout.tsx                      # Root layout with metadata
└── page.tsx                        # Main landing page
```

#### `app/actions/`
Contains Next.js Server Actions - server-side functions that can be called from client components.

- **`generate-learning-path.ts`**
  - Purpose: Generate personalized learning paths using Google Gemini AI
  - Features: AI integration, error handling, fallback to mock data
  - Exports: `generateLearningPath(subject, level)`

#### `app/globals.css`
Global stylesheet with:
- Tailwind CSS directives (`@tailwind base`, `@tailwind components`, `@tailwind utilities`)
- CSS custom properties for theming
- Base styles for HTML elements
- Dark mode variables

#### `app/layout.tsx`
Root layout component:
- Metadata configuration (title, description, icons)
- Font loading (Space Grotesk, Inter)
- Viewport configuration
- Vercel Analytics integration
- Theme provider wrapper

#### `app/page.tsx`
Main landing page:
- Composes all major sections
- Defines scroll anchor IDs
- Manages component layout

### `/components` - React Components

All React components are organized here.

```
components/
├── ui/                              # Shadcn/Radix UI primitives
│   ├── button.tsx                  # Button component
│   ├── card.tsx                    # Card component
│   ├── dialog.tsx                  # Dialog/Modal component
│   ├── input.tsx                   # Input component
│   ├── label.tsx                   # Label component
│   ├── select.tsx                  # Select dropdown
│   ├── separator.tsx               # Separator line
│   ├── slider.tsx                  # Slider component
│   ├── tabs.tsx                    # Tabs component
│   └── ...                         # Other UI primitives
├── achievement-arcade.tsx           # Badge collection display
├── ai-demo-section.tsx             # Interactive AI demo
├── cta-section.tsx                 # Call-to-action section
├── dashboard-mockup.tsx            # Analytics dashboard
├── diagonal-background.tsx         # Animated background
├── diagonal-hero.tsx               # Hero section
├── features-section.tsx            # Features showcase
├── interactive-treadmill.tsx       # Treadmill animation
├── konami-confetti.tsx             # Easter egg confetti
├── launch-cta.tsx                  # Launch call-to-action
├── mobile-experience.tsx           # Mobile preview
├── navigation.tsx                  # Navigation menu
├── page-loader.tsx                 # Loading component
├── scroll-progress.tsx             # Scroll indicator
├── section-reveal.tsx              # Scroll reveal animation
├── testimonials-section.tsx        # User testimonials
├── theme-provider.tsx              # Theme context provider
├── theme-toggle.tsx                # Dark/Light mode toggle
├── thread-map.tsx                  # Learning path visualization
└── transformation-section.tsx      # Transformation showcase
```

#### Component Categories

**UI Primitives** (`components/ui/`)
- Base components from Radix UI with custom styling
- Reusable across the application
- Follow shadcn/ui patterns
- Fully accessible (ARIA compliant)

**Feature Components** (root of `components/`)
- Domain-specific components
- Compose multiple UI primitives
- Handle business logic
- Client-side interactivity

### Key Components Explained

#### `achievement-arcade.tsx`
**Purpose**: Display gamification badges
- 6 badge tiers (Bronze to Legendary)
- Interactive modal for each badge
- Animated badge cards
- Hover effects and glow

#### `ai-demo-section.tsx`
**Purpose**: Interactive AI learning path generator
- Form for subject and level selection
- Real-time AI path generation
- Loading states
- Error handling
- Display learning path, first lesson, and recommendations

#### `thread-map.tsx`
**Purpose**: Visual learning path with nodes
- 12+ interconnected topic nodes
- Three states: completed, active, locked
- SVG connections between nodes
- Animated on scroll
- Progress tracking visualization

#### `dashboard-mockup.tsx`
**Purpose**: Real-time analytics dashboard
- Learning speed meter
- Difficulty adaptation display
- Topics mastered progress
- XP earned tracking
- Recent activity feed
- AI suggestions panel

#### `diagonal-hero.tsx`
**Purpose**: Landing hero section
- Animated gradient background
- Staggered text animations
- CTA buttons
- Interactive treadmill component

### `/hooks` - Custom React Hooks

Custom hooks for shared logic across components.

```
hooks/
└── use-*.ts                        # Custom hooks (if any)
```

### `/lib` - Utility Functions

Helper functions and utilities.

```
lib/
└── utils.ts                        # Utility functions (cn, etc.)
```

Common utilities:
- `cn()`: Tailwind class name merger
- Type definitions
- Constants
- Helper functions

### `/public` - Static Assets

Publicly accessible static files.

```
public/
├── academic-woman-portrait.jpg
├── apple-icon.png
├── icon-dark-32x32.png
├── icon-light-32x32.png
├── icon.svg
├── placeholder-logo.png
├── placeholder-logo.svg
└── ...                             # Other images and assets
```

**File Types**:
- Icons (PNG, SVG)
- Images (JPG, PNG)
- Placeholder assets
- Favicon files

**Naming Convention**:
- Descriptive kebab-case names
- Include size in filename for icons
- Dark/light variants specified

### `/styles` - Additional Stylesheets

Additional CSS files beyond `globals.css`.

```
styles/
└── *.css                           # Additional stylesheets
```

## 🔧 Configuration Files

### `package.json`
**Purpose**: Project metadata and dependencies

```json
{
  "name": "threadmill",
  "version": "0.1.0",
  "scripts": {
    "dev": "next dev",
    "build": "next build",
    "start": "next start",
    "lint": "eslint ."
  }
}
```

**Key Scripts**:
- `dev`: Start development server (http://localhost:3000)
- `build`: Create production build
- `start`: Start production server
- `lint`: Run ESLint

### `next.config.mjs`
**Purpose**: Next.js configuration

```javascript
const nextConfig = {
  typescript: {
    ignoreBuildErrors: true,  // For rapid development
  },
  images: {
    unoptimized: true,       // For static export
  },
}
```

### `tsconfig.json`
**Purpose**: TypeScript configuration

Key settings:
- Path aliases (`@/components`, `@/lib`, etc.)
- Strict mode enabled
- JSX as React
- Module resolution
- Include/exclude patterns

### `components.json`
**Purpose**: shadcn/ui configuration

Defines:
- Component installation paths
- Style preferences
- Alias mappings
- UI library settings

### `postcss.config.mjs`
**Purpose**: PostCSS configuration

Plugins:
- Tailwind CSS
- Autoprefixer

### `pnpm-lock.yaml`
**Purpose**: Dependency lock file

Ensures consistent installations across environments.

## 🎯 File Naming Conventions

### Components
- **Format**: `kebab-case.tsx`
- **Examples**: `diagonal-hero.tsx`, `ai-demo-section.tsx`
- **Exports**: PascalCase (`DiagonalHero`, `AIDemoSection`)

### Utilities
- **Format**: `kebab-case.ts`
- **Examples**: `utils.ts`, `helpers.ts`
- **Exports**: camelCase functions

### Types
- **Format**: PascalCase interfaces/types
- **Examples**: `LearningPathItem`, `AIResponse`

### CSS
- **Format**: `kebab-case.css`
- **Examples**: `globals.css`

## 🗂️ Code Organization Principles

### 1. Component Composition
Break large components into smaller, reusable pieces:
```typescript
// ✅ Good: Composed components
<AIDemoSection>
  <SubjectSelector />
  <LevelSelector />
  <GenerateButton />
  <ResultsDisplay />
</AIDemoSection>
```

### 2. Separation of Concerns
- **Components**: UI and presentation
- **Actions**: Business logic and API calls
- **Hooks**: Reusable stateful logic
- **Lib**: Pure utility functions

### 3. Colocation
Place related files close together:
```
components/
├── ai-demo-section.tsx
├── ai-demo-types.ts           # Types specific to ai-demo
└── ai-demo-utils.ts           # Utilities specific to ai-demo
```

### 4. Server vs Client
- Default to Server Components
- Use `"use client"` only when necessary:
  - Interactive components (onClick, useState)
  - Browser APIs (localStorage, window)
  - Third-party libraries requiring client

## 📊 Import Conventions

### Import Order
```typescript
// 1. React and Next.js
import { useState } from "react"
import Image from "next/image"

// 2. External libraries
import { Button } from "@/components/ui/button"
import { Sparkles } from "lucide-react"

// 3. Internal components
import { DiagonalHero } from "@/components/diagonal-hero"

// 4. Actions and utilities
import { generateLearningPath } from "@/app/actions/generate-learning-path"
import { cn } from "@/lib/utils"

// 5. Types
import type { LearningPathItem } from "@/types"

// 6. Styles (if any)
import "./styles.css"
```

### Path Aliases
```typescript
// Use @ alias for absolute imports
import { Button } from "@/components/ui/button"
import { cn } from "@/lib/utils"

// Avoid relative imports
import { Button } from "../../../components/ui/button" // ❌
```

## 🚀 Adding New Features

### Adding a New Page
```bash
# Create page directory
mkdir -p app/new-page

# Create page component
touch app/new-page/page.tsx

# Add route: /new-page
```

### Adding a New Component
```bash
# Create component file
touch components/new-feature.tsx

# Import in page
# app/page.tsx
import { NewFeature } from "@/components/new-feature"
```

### Adding a Server Action
```bash
# Create action file
touch app/actions/new-action.ts

# Mark with "use server"
# Call from client component
```

### Adding UI Primitive
```bash
# Using shadcn/ui CLI
npx shadcn-ui@latest add [component-name]

# Example
npx shadcn-ui@latest add dropdown-menu
```

## 📚 Resources

- [Next.js App Router Docs](https://nextjs.org/docs/app)
- [React Documentation](https://react.dev/)
- [Tailwind CSS Documentation](https://tailwindcss.com/docs)
- [Radix UI Documentation](https://www.radix-ui.com/docs/primitives)
- [TypeScript Handbook](https://www.typescriptlang.org/docs/)

## 🤝 Contributing

When adding new files or directories:
1. Follow existing naming conventions
2. Place files in appropriate directories
3. Update this document if adding new top-level directories
4. Document complex structures in component/file comments

See [CONTRIBUTING.md](CONTRIBUTING.md) for detailed guidelines.

---

**Questions about project structure?** Open an [issue](https://github.com/Aspect022/ThreadMill/issues) or [discussion](https://github.com/Aspect022/ThreadMill/discussions).
