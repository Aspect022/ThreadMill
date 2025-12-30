# Quick Start Guide 🚀

Welcome to ThreadMill Education! This guide will get you up and running in under 5 minutes.

## Prerequisites Checklist

Before you begin, ensure you have:

- [ ] **Node.js 18.x or higher** - [Download here](https://nodejs.org/)
- [ ] **pnpm** (recommended) - Install with: `npm install -g pnpm`
- [ ] **Git** - [Download here](https://git-scm.com/)
- [ ] **Google Gemini API Key** - [Get one here](https://makersuite.google.com/app/apikey)

## 5-Minute Setup

### Step 1: Clone the Repository (1 minute)

```bash
git clone https://github.com/Aspect022/ThreadMill.git
cd ThreadMill
```

### Step 2: Install Dependencies (2 minutes)

```bash
pnpm install
# or: npm install
# or: yarn install
```

### Step 3: Configure Environment (1 minute)

Create a `.env.local` file in the root directory:

```bash
cp .env.example .env.local
```

Edit `.env.local` and add your Google Gemini API key:

```env
GOOGLE_GENERATIVE_AI_API_KEY=your_api_key_here
```

**How to get a Gemini API Key:**
1. Visit [Google AI Studio](https://makersuite.google.com/app/apikey)
2. Sign in with your Google account
3. Click "Create API Key"
4. Copy and paste into `.env.local`

### Step 4: Start Development Server (1 minute)

```bash
pnpm dev
```

Open [http://localhost:3000](http://localhost:3000) in your browser 🎉

## What You'll See

After starting the server, you'll see:

1. **Hero Section** - Animated landing with CTA buttons
2. **Dashboard Mockup** - Real-time analytics visualization
3. **ThreadMap** - Interactive learning path with connected nodes
4. **AI Demo** - Generate personalized learning paths
5. **Achievement Arcade** - Gamification badges
6. **Mobile Experience** - Responsive design preview
7. **Features Section** - Platform capabilities
8. **Testimonials** - User feedback

## Quick Commands

```bash
# Start development server
pnpm dev

# Build for production
pnpm build

# Start production server
pnpm start

# Run linter
pnpm lint
```

## Common Issues & Solutions

### Issue: "Module not found" error

**Solution:** Delete `node_modules` and reinstall:
```bash
rm -rf node_modules pnpm-lock.yaml
pnpm install
```

### Issue: API rate limit / "AI is taking a coffee break"

**Solution:** This is normal! The app automatically falls back to demo data when the API rate limit is reached. Wait a few minutes and try again, or use the demo data for testing.

### Issue: Port 3000 already in use

**Solution:** Kill the process using port 3000 or use a different port:
```bash
# Use different port
pnpm dev --port 3001

# Or kill existing process
lsof -ti:3000 | xargs kill -9  # macOS/Linux
netstat -ano | findstr :3000  # Windows (then use Task Manager)
```

### Issue: Blank page or build errors

**Solution:** Clear Next.js cache:
```bash
rm -rf .next
pnpm dev
```

## Project Structure Overview

```
ThreadMill/
├── app/              # Pages and routes
│   ├── actions/     # Server actions (API logic)
│   └── page.tsx     # Home page
├── components/      # React components
│   ├── ui/         # Reusable UI primitives
│   └── *.tsx       # Feature components
├── public/         # Static assets
└── package.json    # Dependencies
```

## Next Steps

### For Users
1. 🎯 Try the **AI Demo** section to generate a learning path
2. 🗺️ Explore the **ThreadMap** to see learning progression
3. 🏆 Check out the **Achievement Arcade** badges
4. 📱 Test on mobile devices (responsive design)

### For Contributors
1. 📖 Read [CONTRIBUTING.md](CONTRIBUTING.md)
2. 🐛 Check [open issues](https://github.com/Aspect022/ThreadMill/issues)
3. 💡 Join [discussions](https://github.com/Aspect022/ThreadMill/discussions)
4. 🔧 Make your first contribution!

## Key Features to Explore

### 1. AI Learning Path Generator
Navigate to the AI Demo section and:
- Select a subject (e.g., "Python", "Machine Learning")
- Choose your level (Beginner, Intermediate, Advanced)
- Click "Generate My Path"
- See a personalized 5-week learning curriculum

### 2. ThreadMap Visualization
- Interactive nodes showing learning topics
- Color-coded status (green = completed, blue = active, gray = locked)
- Shows how topics connect and unlock
- Hover over nodes to see details

### 3. Achievement System
- 6 badge tiers from Bronze to Legendary
- Each badge has unique requirements
- Click badges to see detailed requirements
- Gamification motivates consistent learning

### 4. Real-Time Dashboard
- Learning speed meter showing pace
- Difficulty adaptation tracking
- Topics mastered counter
- XP points earned
- Recent activity feed

## Development Tips

### Hot Module Replacement
Changes to files are automatically reflected in the browser (no refresh needed).

### Component Development
All components are in the `components/` directory. To add a new component:

```bash
touch components/my-component.tsx
```

Then import it in your page:

```typescript
import { MyComponent } from "@/components/my-component"
```

### Styling
Use Tailwind CSS classes directly in components:

```tsx
<div className="rounded-lg border p-6 bg-white dark:bg-slate-900">
  Content here
</div>
```

### Using Server Actions
For API calls, create server actions in `app/actions/`:

```typescript
"use server"

export async function myAction() {
  // Server-side code here
}
```

## Performance Tips

- **Build Time**: First build may take 1-2 minutes
- **Dev Server**: Hot reload is instant for most changes
- **Production Build**: Use `pnpm build` for optimized bundle
- **Memory**: Requires ~2GB RAM for development

## Browser Compatibility

✅ **Supported Browsers:**
- Chrome 90+
- Firefox 88+
- Safari 14+
- Edge 90+
- Mobile: iOS Safari 14+, Chrome Mobile 90+

## Need Help?

- 📚 [Full Documentation](README.md)
- 🤝 [Contributing Guide](CONTRIBUTING.md)
- 🐛 [Report Issues](https://github.com/Aspect022/ThreadMill/issues)
- 💬 [Ask Questions](https://github.com/Aspect022/ThreadMill/discussions)
- 📧 Email: support@threadmill.education (if applicable)

## Deployment (Optional)

### Deploy to Vercel (Recommended)

1. Push your code to GitHub
2. Visit [vercel.com](https://vercel.com)
3. Import your repository
4. Add environment variables:
   - `GOOGLE_GENERATIVE_AI_API_KEY`
5. Click Deploy!

Your app will be live at `your-app.vercel.app` in ~2 minutes.

## What's Next?

Now that you're set up:

1. **Explore the Code**: Browse through `components/` to see how features work
2. **Try Making Changes**: Edit a component and see live updates
3. **Read the Docs**: Check out [PROJECT_STRUCTURE.md](PROJECT_STRUCTURE.md)
4. **Join the Community**: Star the repo and join discussions

---

**Welcome to ThreadMill Education! Happy learning and coding! 🎓✨**

[← Back to README](README.md) | [Contributing Guide →](CONTRIBUTING.md)
