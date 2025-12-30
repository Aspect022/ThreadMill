# Contributing to ThreadMill Education 🤝

First off, thank you for considering contributing to ThreadMill Education! It's people like you that make ThreadMill such a great tool for learners worldwide.

## 📋 Table of Contents

- [Code of Conduct](#code-of-conduct)
- [How Can I Contribute?](#how-can-i-contribute)
  - [Reporting Bugs](#reporting-bugs)
  - [Suggesting Enhancements](#suggesting-enhancements)
  - [Your First Code Contribution](#your-first-code-contribution)
  - [Pull Requests](#pull-requests)
- [Style Guides](#style-guides)
  - [Git Commit Messages](#git-commit-messages)
  - [TypeScript Style Guide](#typescript-style-guide)
  - [React Component Guidelines](#react-component-guidelines)
- [Development Setup](#development-setup)
- [Project Structure](#project-structure)
- [Testing Guidelines](#testing-guidelines)
- [Documentation](#documentation)

## 📜 Code of Conduct

This project and everyone participating in it is governed by our [Code of Conduct](CODE_OF_CONDUCT.md). By participating, you are expected to uphold this code. Please report unacceptable behavior to the project maintainers.

## 🤔 How Can I Contribute?

### 🐛 Reporting Bugs

Before creating bug reports, please check the existing issues to avoid duplicates. When you create a bug report, include as many details as possible:

**Use the bug report template** which includes:
- A clear and descriptive title
- Exact steps to reproduce the problem
- Expected behavior vs actual behavior
- Screenshots (if applicable)
- Environment details (browser, OS, Node version)
- Any error messages or logs

**Example of a good bug report:**

```
Title: AI Demo Section fails to generate learning path for specific subjects

Steps to Reproduce:
1. Navigate to the AI Demo section
2. Select "Machine Learning" as subject
3. Select "Advanced" as level
4. Click "Generate My Path"
5. Error appears instead of learning path

Expected: A personalized learning path should be generated
Actual: Error message "AI is taking a coffee break"

Environment:
- Browser: Chrome 120.0
- OS: Windows 11
- Node: 20.10.0

Console Error:
TypeError: Cannot read property 'learningPath' of undefined
```

### 💡 Suggesting Enhancements

Enhancement suggestions are tracked as GitHub issues. When creating an enhancement suggestion:

- Use a clear and descriptive title
- Provide a detailed description of the suggested enhancement
- Explain why this enhancement would be useful
- List any alternative solutions or features you've considered
- Include mockups or examples if applicable

**Example enhancement suggestion:**

```
Title: Add export functionality for learning paths

Description:
Users should be able to export their generated learning paths as PDF or JSON for offline reference.

Why it's useful:
- Users can share their paths with mentors
- Enables offline access to learning plans
- Helps with progress tracking outside the platform

Alternatives considered:
- Email the learning path
- Screenshot functionality
```

### 🚀 Your First Code Contribution

Unsure where to begin? Look for issues tagged with:
- `good first issue` - Simple issues perfect for newcomers
- `help wanted` - Issues where we need community help
- `documentation` - Documentation improvements

**Steps to get started:**

1. **Fork the repository**
   ```bash
   # Click the "Fork" button on GitHub
   ```

2. **Clone your fork**
   ```bash
   git clone https://github.com/your-username/ThreadMill.git
   cd ThreadMill
   ```

3. **Set up the upstream remote**
   ```bash
   git remote add upstream https://github.com/Aspect022/ThreadMill.git
   ```

4. **Create a branch**
   ```bash
   git checkout -b feature/your-feature-name
   ```

5. **Make your changes** (follow our style guides)

6. **Test your changes**
   ```bash
   pnpm lint
   pnpm build
   ```

7. **Commit your changes** (follow commit message guidelines)

8. **Push to your fork**
   ```bash
   git push origin feature/your-feature-name
   ```

9. **Open a Pull Request**

### 📬 Pull Requests

Please follow these steps for pull requests:

1. **Update documentation** if you've changed functionality
2. **Follow the code style** of the project (ESLint will help)
3. **Write meaningful commit messages**
4. **Test your changes** locally
5. **Link related issues** in the PR description
6. **Request review** from maintainers

**Pull Request Template:**

```markdown
## Description
Brief description of what this PR does

## Type of Change
- [ ] Bug fix (non-breaking change that fixes an issue)
- [ ] New feature (non-breaking change that adds functionality)
- [ ] Breaking change (fix or feature that would cause existing functionality to not work as expected)
- [ ] Documentation update

## Related Issues
Closes #123

## Testing
How has this been tested?
- [ ] Local development testing
- [ ] Manual testing in different browsers
- [ ] Verified with different user scenarios

## Screenshots (if applicable)
Add screenshots to show the changes

## Checklist
- [ ] My code follows the style guidelines of this project
- [ ] I have performed a self-review of my own code
- [ ] I have commented my code, particularly in hard-to-understand areas
- [ ] I have made corresponding changes to the documentation
- [ ] My changes generate no new warnings
- [ ] I have checked my code and corrected any misspellings
```

## 📝 Style Guides

### Git Commit Messages

We follow the [Conventional Commits](https://www.conventionalcommits.org/) specification:

**Format:**
```
<type>(<scope>): <subject>

<body>

<footer>
```

**Types:**
- `feat`: A new feature
- `fix`: A bug fix
- `docs`: Documentation only changes
- `style`: Changes that don't affect code meaning (white-space, formatting)
- `refactor`: Code change that neither fixes a bug nor adds a feature
- `perf`: Performance improvements
- `test`: Adding missing tests or correcting existing tests
- `chore`: Changes to build process or auxiliary tools

**Examples:**
```bash
feat(ai-demo): add support for custom learning duration

fix(thread-map): resolve node connection rendering issue

docs(readme): update installation instructions

style(components): format code with prettier

refactor(dashboard): extract analytics logic to custom hook

perf(thread-map): optimize node rendering with memoization

test(ai-demo): add unit tests for path generation

chore(deps): update dependencies to latest versions
```

### TypeScript Style Guide

#### General Rules
- Use TypeScript for all new files
- Avoid `any` type - use proper types or `unknown`
- Define interfaces for component props
- Use type inference where possible
- Export types that are used across multiple files

#### Component Props
```typescript
// Good
interface DiagonalHeroProps {
  title: string
  subtitle?: string
  onCtaClick?: () => void
}

export function DiagonalHero({ title, subtitle, onCtaClick }: DiagonalHeroProps) {
  // ...
}

// Avoid
export function DiagonalHero(props: any) {
  // ...
}
```

#### State Types
```typescript
// Good
interface LearningPathItem {
  week: number
  topic: string
  hours: number
  description: string
}

const [learningPath, setLearningPath] = useState<LearningPathItem[]>([])

// Avoid
const [learningPath, setLearningPath] = useState([])
```

### React Component Guidelines

#### File Organization
```typescript
"use client" // If client component

import { useState } from "react" // React imports
import { Button } from "@/components/ui/button" // Internal imports
import { Sparkles } from "lucide-react" // External imports

// Types/Interfaces
interface ComponentProps {
  // ...
}

// Main component
export function ComponentName({ prop1, prop2 }: ComponentProps) {
  // Hooks at the top
  const [state, setState] = useState()
  
  // Event handlers
  const handleClick = () => {
    // ...
  }
  
  // Effects
  useEffect(() => {
    // ...
  }, [])
  
  // Render
  return (
    // ...
  )
}
```

#### Naming Conventions
- **Components**: PascalCase (`DiagonalHero`, `AIDemoSection`)
- **Files**: kebab-case for components (`diagonal-hero.tsx`)
- **Utilities**: camelCase (`generateLearningPath`)
- **Constants**: UPPER_SNAKE_CASE (`MAX_LEARNING_HOURS`)
- **CSS Classes**: Tailwind utilities

#### Component Best Practices
```typescript
// ✅ Good: Small, focused components
export function FeatureCard({ title, description, icon: Icon }: FeatureCardProps) {
  return (
    <div className="rounded-lg border p-6">
      <Icon className="w-6 h-6 mb-2" />
      <h3 className="font-bold">{title}</h3>
      <p className="text-sm text-muted-foreground">{description}</p>
    </div>
  )
}

// ❌ Avoid: Large, monolithic components
export function MegaComponent() {
  // 500 lines of code...
}
```

#### Client vs Server Components
```typescript
// Use "use client" only when necessary
// Client component (needs interactivity)
"use client"
import { useState } from "react"

export function InteractiveButton() {
  const [count, setCount] = useState(0)
  return <button onClick={() => setCount(count + 1)}>{count}</button>
}

// Server component (default, better performance)
export function StaticContent() {
  return <div>This is static content</div>
}
```

### CSS and Styling

#### Tailwind CSS Guidelines
- Use Tailwind utility classes
- Keep custom CSS minimal
- Use CSS variables for theming
- Follow mobile-first responsive design

```typescript
// ✅ Good: Utility classes, mobile-first
<div className="w-full md:w-1/2 lg:w-1/3 p-4 bg-white dark:bg-slate-900">

// ❌ Avoid: Inline styles
<div style={{ width: "50%", padding: "16px" }}>
```

#### Animation Guidelines
- Use Framer Motion for complex animations
- Use Tailwind transitions for simple animations
- Keep animations performant (avoid animating expensive properties)
- Respect `prefers-reduced-motion`

## 🛠️ Development Setup

### Prerequisites
- Node.js 18.x or higher
- pnpm 8.x or higher (recommended)
- Git
- Google Gemini API key

### Local Development

1. **Install dependencies**
   ```bash
   pnpm install
   ```

2. **Set up environment variables**
   ```bash
   cp .env.example .env.local
   # Edit .env.local with your API keys
   ```

3. **Run development server**
   ```bash
   pnpm dev
   ```

4. **Run linter**
   ```bash
   pnpm lint
   ```

5. **Build for production**
   ```bash
   pnpm build
   ```

### Development Tools

- **ESLint**: Automatic code linting
- **TypeScript**: Type checking
- **Prettier**: Code formatting (if configured)
- **Vercel**: Preview deployments for PRs

## 📂 Project Structure

Understanding the project structure helps you know where to make changes:

```
ThreadMill/
├── app/                    # Next.js App Router
│   ├── actions/           # Server actions (API logic)
│   ├── globals.css        # Global styles
│   ├── layout.tsx         # Root layout
│   └── page.tsx           # Home page
├── components/            # React components
│   ├── ui/               # Reusable UI primitives (Radix)
│   └── *.tsx             # Feature components
├── hooks/                # Custom React hooks
├── lib/                  # Utility functions
├── public/               # Static assets
└── styles/               # Additional stylesheets
```

**Where to add new features:**
- **New UI Component**: `components/your-component.tsx`
- **New Server Action**: `app/actions/your-action.ts`
- **New Hook**: `hooks/use-your-hook.ts`
- **New Utility**: `lib/your-utility.ts`
- **New Page**: `app/your-page/page.tsx`

## 🧪 Testing Guidelines

While formal testing infrastructure is being developed, please:

1. **Manual Testing**: Test your changes in multiple browsers
2. **Responsive Testing**: Check mobile, tablet, and desktop views
3. **Edge Cases**: Test with unusual inputs
4. **Error Handling**: Verify error states work correctly
5. **Performance**: Ensure no significant performance regression

**Testing Checklist:**
- [ ] Chrome, Firefox, Safari tested
- [ ] Mobile responsive (375px, 768px, 1024px, 1440px)
- [ ] Dark/Light theme tested
- [ ] Error states handled gracefully
- [ ] Loading states work correctly
- [ ] No console errors or warnings
- [ ] Accessibility considerations met

## 📚 Documentation

Good documentation is crucial. When contributing:

### Code Comments
```typescript
// ✅ Good: Explain WHY, not WHAT
// Fetch with retry logic because Gemini API occasionally times out
const fetchWithRetry = async (url: string) => { ... }

// ❌ Avoid: Stating the obvious
// This function fetches data
const fetchData = async () => { ... }
```

### Component Documentation
```typescript
/**
 * DiagonalHero component displays the main hero section with animated background
 * 
 * Features:
 * - Animated gradient diagonal background
 * - Staggered text animations
 * - Call-to-action buttons with scroll behavior
 * 
 * @example
 * ```tsx
 * <DiagonalHero />
 * ```
 */
export function DiagonalHero() { ... }
```

### README Updates
If your PR affects:
- Installation process → Update Getting Started
- New features → Update Features section
- Configuration → Update Configuration section
- Dependencies → Update Technology Stack

## 🎯 Contribution Areas

### High Priority
- User authentication implementation
- Database integration
- Additional learning subjects/topics
- Performance optimizations
- Accessibility improvements
- Mobile app development

### Medium Priority
- Additional gamification features
- Social features
- Advanced analytics
- Multi-language support
- Offline support

### Low Priority
- UI polish and animations
- Additional themes
- Easter eggs and hidden features

## 💬 Communication

- **Questions?** Open a [Discussion](https://github.com/Aspect022/ThreadMill/discussions)
- **Bug or Feature?** Open an [Issue](https://github.com/Aspect022/ThreadMill/issues)
- **Need Help?** Comment on the issue you're working on
- **Suggestion?** Start a discussion first before creating PR

## 🏆 Recognition

Contributors will be:
- Listed in the project README
- Mentioned in release notes
- Credited in the CHANGELOG
- Given contributor badge on GitHub

## 📜 License

By contributing, you agree that your contributions will be licensed under the MIT License.

---

**Thank you for contributing to ThreadMill Education! Together, we're transforming learning for everyone. 🎓✨**
