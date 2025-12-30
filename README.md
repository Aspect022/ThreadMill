# ThreadMill Education 🎓

<div align="center">

![ThreadMill Logo](public/placeholder-logo.svg)

**Transform Your Learning with AI-Powered Adaptive Education**

[![Next.js](https://img.shields.io/badge/Next.js-16.0.7-black?logo=next.js)](https://nextjs.org/)
[![React](https://img.shields.io/badge/React-19.2.0-blue?logo=react)](https://react.dev/)
[![TypeScript](https://img.shields.io/badge/TypeScript-5.x-blue?logo=typescript)](https://www.typescriptlang.org/)
[![Tailwind CSS](https://img.shields.io/badge/Tailwind-4.1.9-38B2AC?logo=tailwind-css)](https://tailwindcss.com/)
[![License](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)

[Features](#features) • [Demo](#demo) • [Getting Started](#getting-started) • [Documentation](#documentation) • [Contributing](#contributing)

</div>

---

## 🌟 Overview

ThreadMill Education is a revolutionary adaptive learning platform that personalizes education to your unique learning style. Using cutting-edge AI technology and gamification, we create customized learning paths that adapt to how you think and grow.

Join 50,000+ learners who are transforming the way they acquire knowledge!

## ✨ Features

### 🧠 **AI-Powered Adaptation**
- Neural learning engine analyzes your learning patterns
- Creates unique curriculum tailored just for you
- Powered by Google Gemini AI for intelligent content generation

### ⚡ **Micro-Learning Bursts**
- Bite-sized lessons that fit your schedule
- Learn in 5-minute sessions designed for maximum retention
- Mobile-optimized for learning on the go

### 🎮 **Gamified Learning Experience**
- Earn badges and unlock achievements
- 6 badge tiers: Bronze, Silver, Gold, Platinum, Diamond, and Legendary
- Compete on leaderboards with learners worldwide
- Visual progress tracking with interactive ThreadMap

### 👥 **Collaborative Threads**
- Connect with learners globally
- Share insights and solve problems together
- Build a community of knowledge seekers

### 📊 **Real-Time Analytics**
- Comprehensive progress dashboards
- Identify strengths and areas for improvement
- Track learning speed and difficulty adaptation
- Monitor XP earnings and topic mastery

### 🎯 **Smart Goal Tracking**
- Set personalized learning goals
- AI-guided path to achievement
- Adaptive difficulty based on performance

## 🚀 Demo

### Interactive Features
- **ThreadMap**: Visualize your learning journey with an interactive node-based map
- **AI Demo Section**: Generate personalized learning paths in real-time
- **Achievement Arcade**: Explore and unlock achievement badges
- **Dashboard Mockup**: See real-time progress analytics
- **Mobile Experience**: Responsive design for learning anywhere

## 🛠️ Technology Stack

### Frontend
- **Framework**: [Next.js 16.0.7](https://nextjs.org/) with App Router
- **UI Library**: [React 19.2.0](https://react.dev/)
- **Language**: [TypeScript 5.x](https://www.typescriptlang.org/)
- **Styling**: [Tailwind CSS 4.1.9](https://tailwindcss.com/)
- **Animations**: [Framer Motion](https://www.framer.com/motion/)
- **Components**: [Radix UI](https://www.radix-ui.com/) primitives
- **Icons**: [Lucide React](https://lucide.dev/)

### AI Integration
- **AI SDK**: [Vercel AI SDK](https://sdk.vercel.ai/)
- **LLM Provider**: [Google Gemini 1.5 Flash](https://ai.google.dev/)
- **Features**: Real-time learning path generation

### Forms & Validation
- **Form Management**: [React Hook Form](https://react-hook-form.com/)
- **Validation**: [Zod](https://zod.dev/)

### UI Components
- **Toast Notifications**: [Sonner](https://sonner.emilkowal.ski/)
- **Date Handling**: [date-fns](https://date-fns.org/)
- **Carousel**: [Embla Carousel](https://www.embla-carousel.com/)
- **Charts**: [Recharts](https://recharts.org/)

### Developer Experience
- **Package Manager**: [pnpm](https://pnpm.io/)
- **Analytics**: [Vercel Analytics](https://vercel.com/analytics)
- **Code Quality**: [ESLint](https://eslint.org/)

## 📋 Prerequisites

Before you begin, ensure you have the following installed:
- **Node.js**: 18.x or higher
- **pnpm**: 8.x or higher (recommended) or npm/yarn
- **Git**: Latest version

## 🚀 Getting Started

### 1. Clone the Repository

```bash
git clone https://github.com/Aspect022/ThreadMill.git
cd ThreadMill
```

### 2. Install Dependencies

```bash
pnpm install
# or
npm install
# or
yarn install
```

### 3. Set Up Environment Variables

Create a `.env.local` file in the root directory:

```bash
# Google Gemini API Key (required for AI features)
GOOGLE_GENERATIVE_AI_API_KEY=your_api_key_here
# or
Gemini_API=your_api_key_here
```

To get a Google Gemini API key:
1. Visit [Google AI Studio](https://makersuite.google.com/app/apikey)
2. Sign in with your Google account
3. Create a new API key
4. Copy and paste it into your `.env.local` file

### 4. Run the Development Server

```bash
pnpm dev
# or
npm run dev
# or
yarn dev
```

Open [http://localhost:3000](http://localhost:3000) in your browser to see the application.

### 5. Build for Production

```bash
pnpm build
pnpm start
# or
npm run build
npm start
```

## 📁 Project Structure

```
ThreadMill/
├── app/                      # Next.js App Router directory
│   ├── actions/             # Server actions
│   │   └── generate-learning-path.ts
│   ├── globals.css          # Global styles
│   ├── layout.tsx           # Root layout
│   └── page.tsx             # Home page
├── components/              # React components
│   ├── ui/                  # Reusable UI components (Radix)
│   ├── achievement-arcade.tsx
│   ├── ai-demo-section.tsx
│   ├── dashboard-mockup.tsx
│   ├── diagonal-hero.tsx
│   ├── features-section.tsx
│   ├── navigation.tsx
│   ├── thread-map.tsx
│   └── ...                  # Other feature components
├── hooks/                   # Custom React hooks
├── lib/                     # Utility functions
├── public/                  # Static assets
├── styles/                  # Additional styles
├── components.json          # shadcn/ui configuration
├── next.config.mjs         # Next.js configuration
├── package.json            # Project dependencies
├── postcss.config.mjs      # PostCSS configuration
├── tailwind.config.ts      # Tailwind CSS configuration
└── tsconfig.json           # TypeScript configuration
```

See [PROJECT_STRUCTURE.md](PROJECT_STRUCTURE.md) for detailed documentation.

## 🎨 Key Components

### DiagonalHero
The landing section with animated gradient backgrounds and call-to-action buttons.

### AIDemoSection
Interactive demo that generates personalized learning paths using Google Gemini AI.

### ThreadMap
Visual representation of learning progress with interconnected topic nodes.

### DashboardMockup
Real-time analytics dashboard showing learning speed, difficulty, and progress.

### AchievementArcade
Gamification system with 6 tiers of badges and achievements.

### FeaturesSection
Showcases the platform's core features with smooth scroll animations.

## 🔧 Configuration

### Tailwind CSS
The project uses Tailwind CSS 4.x with custom animations. Configuration is in `tailwind.config.ts`.

### Next.js
- TypeScript build errors are ignored in production (set in `next.config.mjs`)
- Image optimization is disabled for static export compatibility

### ESLint
Run linting with:
```bash
pnpm lint
# or
npm run lint
```

## 🌐 Deployment

### Deploy to Vercel (Recommended)

[![Deploy with Vercel](https://vercel.com/button)](https://vercel.com/new/clone?repository-url=https://github.com/Aspect022/ThreadMill)

1. Push your code to GitHub
2. Import your repository to [Vercel](https://vercel.com)
3. Add your environment variables
4. Deploy!

### Environment Variables for Production
Remember to set these in your deployment platform:
- `GOOGLE_GENERATIVE_AI_API_KEY` or `Gemini_API`

### Other Platforms
The application can be deployed to any platform that supports Next.js:
- Netlify
- AWS Amplify
- Railway
- Render
- Self-hosted with Docker

## 🧪 Testing

Currently, the project focuses on development and user experience. Testing infrastructure can be added based on your needs:

- **Unit Tests**: Jest + React Testing Library
- **E2E Tests**: Playwright or Cypress
- **Component Tests**: Storybook

## 📚 Documentation

Comprehensive documentation is available to help you get started and contribute:

- **[Quick Start Guide](QUICK_START.md)** - Get up and running in 5 minutes
- **[Documentation Index](DOCUMENTATION.md)** - Complete documentation guide
- **[Contributing Guide](CONTRIBUTING.md)** - How to contribute to the project
- **[Project Structure](PROJECT_STRUCTURE.md)** - Detailed code organization
- **[Security Policy](SECURITY.md)** - Security and vulnerability reporting
- **[Code of Conduct](CODE_OF_CONDUCT.md)** - Community guidelines
- **[Changelog](CHANGELOG.md)** - Version history and updates

## 🤝 Contributing

We welcome contributions from the community! Please read our [CONTRIBUTING.md](CONTRIBUTING.md) for guidelines on how to contribute.

### Quick Start for Contributors

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🔒 Security

Found a security vulnerability? Please read our [SECURITY.md](SECURITY.md) for reporting guidelines.

## 📞 Support & Community

- **Issues**: [GitHub Issues](https://github.com/Aspect022/ThreadMill/issues)
- **Discussions**: [GitHub Discussions](https://github.com/Aspect022/ThreadMill/discussions)
- **Email**: support@threadmill.education (if applicable)

## 🗺️ Roadmap

### Current Features (v0.1.0)
- ✅ AI-powered learning path generation
- ✅ Interactive ThreadMap visualization
- ✅ Achievement system with 6 badge tiers
- ✅ Real-time progress dashboard
- ✅ Mobile-responsive design
- ✅ Dark/Light theme support

### Upcoming Features
- 🔄 User authentication and profiles
- 🔄 Database integration for progress persistence
- 🔄 Social features and collaboration tools
- 🔄 Advanced analytics and insights
- 🔄 Course marketplace
- 🔄 Mobile native apps (iOS/Android)
- 🔄 Offline learning support
- 🔄 Multi-language support

## 📊 Performance

ThreadMill is built with performance in mind:
- Server-side rendering with Next.js App Router
- Optimized animations with Framer Motion
- Lazy loading of components
- Efficient state management
- Minimal bundle size with tree-shaking

## 🙏 Acknowledgments

- Built with [Next.js](https://nextjs.org/) by Vercel
- UI components from [Radix UI](https://www.radix-ui.com/)
- Icons by [Lucide](https://lucide.dev/)
- AI powered by [Google Gemini](https://ai.google.dev/)
- Inspired by modern learning platforms and gamification principles

## 📝 Changelog

See [CHANGELOG.md](CHANGELOG.md) for a detailed history of changes.

---

<div align="center">

**Made with ❤️ by the ThreadMill Team**

[⭐ Star us on GitHub](https://github.com/Aspect022/ThreadMill) • [🐛 Report Bug](https://github.com/Aspect022/ThreadMill/issues) • [✨ Request Feature](https://github.com/Aspect022/ThreadMill/issues)

</div>
