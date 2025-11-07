# 🚀 Claude Kickstart

**Ship your MVP in weeks, not months. The ultimate starter kit for vibe coders building with Claude Code.**

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](http://makeapullrequest.com)

---

## 🤔 Wait, What's Claude Code?

**New to AI coding?** Claude Code is an AI assistant by Anthropic that helps you build apps through conversation. Think of it like having an expert developer on your team who never sleeps.

**The problem:** Every time you start a new chat, you have to re-explain your entire project—"I'm using React", "I use Tailwind", "Don't write tests for everything", etc. It's exhausting.

**This starter kit solves that:** You set up your project rules ONCE, and Claude Code remembers them forever. No more repeating yourself.

**New to Claude Code?** [Get started here](https://claude.com/claude-code) (free trial available!)

---

## 🎯 What Is This?

Claude Kickstart is a template system that transforms your app idea into a `CLAUDE.md` configuration file—**in under 5 minutes**.

Think of `CLAUDE.md` as a cheat sheet that teaches Claude Code about YOUR specific project.

**What you get:**
- ✅ No more explaining your tech stack in every conversation
- ✅ No more repeated code patterns
- ✅ Claude builds consistently (not random AI slop)
- ✅ Ship faster with fewer bugs

**Just describe your app idea, get your config, and start building.**

---

## ✅ What You Need Before Starting

**Absolute requirements:**
- [ ] Claude Code installed ([Get it here](https://claude.com/claude-code))
- [ ] An app idea (doesn't need to be fancy!)
- [ ] 20 minutes of focused time

**Optional but helpful:**
- [ ] Basic idea of what you want to build
- [ ] Favorite apps you want to copy features from (inspiration!)

**Don't need:**
- ❌ Coding experience (Claude Code handles that)
- ❌ A detailed plan (we'll help you create one)
- ❌ To know which tools to use (Claude will recommend)

---

## 🏆 Who Is This For?

- **Beginner vibe coders** who want to build like the pros
- **Solo founders** shipping MVPs on tight timelines
- **Indie hackers** who need to move fast and iterate
- **Dev teams** wanting consistent AI coding standards
- **Anyone** tired of configuring AI coding assistants from scratch

---

## 🎁 What You Get

### 1. **Production-Ready Templates**
- 📄 **Full Template** - Comprehensive config with all the bells and whistles
- 📄 **Minimal Template** - Lean starter for simple projects (5-min setup)
- 📄 **Customization Guide** - Step-by-step instructions for any stack
- 📄 **MVP Constraints** - Lean testing strategy (ship fast, test what matters)
- 📄 **Setup Prompt** - Copy-paste prompt to generate your CLAUDE.md from any PRD

### 2. **Battle-Tested Standards**
- ✅ Component reusability rules (no more repeated Tailwind classes)
- ✅ Type-safe database operations
- ✅ Lean MVP testing strategy (3-5 critical tests only)
- ✅ Production debugging standards (cite line numbers, not vague descriptions)
- ✅ Animation implementation patterns (learned from real bugs)

### 3. **Framework Agnostic**
Works with:
- React, Vue, Svelte, Next.js, Nuxt, SvelteKit
- Supabase, Firebase, AWS Amplify, Convex
- Tailwind, CSS Modules, styled-components
- TypeScript (strict mode recommended)

---

## 📖 Beginner-Friendly Glossary

**Not sure what these terms mean? Here's the translation:**

- **PRD (Product Requirements Document)** - A simple doc that describes what your app does. Think: "I want to build a task manager with a timer." That's a PRD!

- **Tech Stack** - The tools you use to build (React, Firebase, Tailwind, etc.). Don't know yet? That's fine—Claude will help you pick!

- **CLAUDE.md** - A file that teaches Claude Code about YOUR project (like a cheat sheet)

- **MVP (Minimum Viable Product)** - The simplest version of your app that actually works

- **Component** - A reusable piece of UI (like a button you use everywhere)

- **Sub-Agent** - Think of these like different AI teammates with specific jobs (one builds, one checks quality, one explores code)

**Still confused?** Open an [issue](https://github.com/johnellison/claude-kickstart/issues) and we'll help!

---

## 🧭 Which Path Should You Take?

**Choose based on your experience:**

### 🌱 Complete Beginner (Never coded before)

**Start here:** [Simple PRD Template](./PRD_TEMPLATE_SIMPLE.md)
- Only 10 questions
- All have examples
- Takes 10 minutes
- Skip what you don't know

**Then:** Use [Setup Prompt](./SETUP_PROMPT.md) to generate your config

**Time:** 20 minutes total

### ⚡ Quick Start (5 Minutes)

**If you know what you're building:**

### Step 1: Copy the Setup Prompt

Open [`SETUP_PROMPT.md`](./SETUP_PROMPT.md) and copy the entire prompt.

### Step 2: Prepare Your PRD

Create a simple PRD with:
- What your app does (2-3 sentences)
- Core features (5-10 bullet points)
- Tech preferences (optional)
- Timeline (MVP in 4 weeks? 12 weeks?)

**Don't have a PRD?** Use our [PRD template](./PRD_TEMPLATE.md).

### Step 3: Generate Your CLAUDE.md

1. Open Claude Code in your project
2. Paste the setup prompt
3. Add your PRD
4. Claude Code generates a customized `CLAUDE.md` in 30 seconds

### Step 4: Start Building

Every conversation with Claude Code now follows your project's rules:
- Knows your tech stack
- Enforces your coding standards
- Prevents repeated code patterns
- Tests only critical paths
- Ships fast

---

## 📚 What's Included

| File | Description | When to Use |
|------|-------------|-------------|
| [`CLAUDE_TEMPLATE.md`](./CLAUDE_TEMPLATE.md) | Full-featured template | Complex projects, teams, production apps |
| [`CLAUDE_TEMPLATE_MINIMAL.md`](./CLAUDE_TEMPLATE_MINIMAL.md) | Lean starter | Simple projects, MVPs, quick prototypes |
| [`CUSTOMIZATION_GUIDE.md`](./CUSTOMIZATION_GUIDE.md) | Step-by-step customization instructions | Manual setup, learning the system |
| [`MVP_CONSTRAINTS.md`](./MVP_CONSTRAINTS.md) | Lean testing strategy | Pre-PMF products, tight timelines |
| [`SETUP_PROMPT.md`](./SETUP_PROMPT.md) | Copy-paste prompt for generating CLAUDE.md | Quick setup with PRD |
| [`PRD_TEMPLATE.md`](./PRD_TEMPLATE.md) | PRD template to organize your ideas | Detailed planning |
| [`PRD_TEMPLATE_SIMPLE.md`](./PRD_TEMPLATE_SIMPLE.md) | Simple PRD (10 questions) | **Start here if beginner** |
| [`SUB_AGENTS.md`](./SUB_AGENTS.md) | Pre-built sub-agent configurations | Setting up your AI team |

---

## 🎓 Examples by Project Type

<details>
<summary><strong>SaaS Web App (React + Supabase)</strong></summary>

**Uses:** Full template
**Key sections:** Component reusability, testing strategy, type system
**Subsystems:** Auth, payments, real-time sync

**Example:** Task management app, CRM, analytics dashboard
</details>

<details>
<summary><strong>Chrome Extension</strong></summary>

**Uses:** Full template with extension-specific modifications
**Key sections:** Extension architecture, messaging patterns, storage
**Subsystems:** Background worker, content scripts, popup UI

**Example:** Productivity tools, web scrapers, automation
</details>

<details>
<summary><strong>Landing Page + Marketing Site</strong></summary>

**Uses:** Minimal template
**Key sections:** Tech stack, styling, deployment
**Subsystems:** None

**Example:** Product landing pages, portfolios, blogs
</details>

<details>
<summary><strong>Mobile App (React Native / Capacitor)</strong></summary>

**Uses:** Full template with mobile modifications
**Key sections:** Responsive design, native modules, offline sync
**Subsystems:** Push notifications, camera/media, storage

**Example:** Social apps, fitness trackers, note-taking
</details>

<details>
<summary><strong>Component Library</strong></summary>

**Uses:** Full template with library-specific modifications
**Key sections:** Build modes, export patterns, Storybook integration
**Subsystems:** Design tokens, theme system

**Example:** Design systems, UI kits, shared components
</details>

---

## 🧠 Philosophy

### Ship Fast, Test What Matters

This starter kit is built on the **Lean MVP Testing** philosophy:

- ✅ Test 3-5 critical paths (auth, core feature, payments)
- ❌ Skip component unit tests during MVP
- ✅ Use TypeScript strict mode for compile-time safety
- ❌ Skip utility function tests
- ✅ Manual QA checklist (15 minutes before deploy)
- ❌ Skip animation tests

**Why?** For pre-PMF products, the biggest risk isn't bugs—it's building something nobody wants. Optimize for learning speed, not code perfection.

### Define Once, Use Everywhere

Prevent repeated code with component reusability rules:

```tsx
// ✅ Correct - Use reusable Button component
<Button variant="primary">Save Changes</Button>

// ❌ Wrong - Repeated inline styles
<button className="bg-blue-600 hover:bg-blue-700 px-4 py-2...">
  Save Changes
</button>
```

**Rule:** If you're typing the same Tailwind classes more than twice, create a component variant.

### Render What You Want to See

For complex animations and UI, render discrete elements for discrete behavior:

```typescript
// ✅ Correct - Render 25 discrete tick elements
{ticks.map((tick, index) => (
  <motion.path key={index} animate={{ opacity: index < remaining ? 1 : 0 }} />
))}

// ❌ Wrong - Mask/clip a continuous element into discrete ticks
<circle strokeDasharray={dynamicPattern} /> // Brittle, hard to debug
```

---

## 🛠️ Customization

### Quick Customization (5 minutes)

Use the **Setup Prompt** method (see Quick Start above).

### Manual Customization (30 minutes)

1. Choose your template:
   - Complex project? Use `CLAUDE_TEMPLATE.md`
   - Simple project? Use `CLAUDE_TEMPLATE_MINIMAL.md`

2. Find and replace placeholders:
   - `[PROJECT_NAME]` → Your project name
   - `[Framework]` → React, Vue, Svelte, etc.
   - `[COMMAND]` → Your actual commands (`npm run dev`, etc.)
   - All other `[PLACEHOLDER]` text

3. Delete sections you don't need

4. Add project-specific sections (payments, real-time, etc.)

See [`CUSTOMIZATION_GUIDE.md`](./CUSTOMIZATION_GUIDE.md) for detailed instructions.

---

## 🌟 Real-World Results

This template system was extracted from building [DeepWork OS](https://pravos.xyz) (formerly Pravos) with Claude Code:

- ✅ Shipped MVP in 2 weeks
- ✅ 10+ complex features (Pomodoro timer, task management, music player, analytics)
- ✅ Zero bugs from missing type definitions
- ✅ 80% code reduction by enforcing component reusability
- ✅ Lean testing strategy (5 critical tests only)

**Testimonials:**

> "This template saved me 3 days of setup and configuration. I just pasted my PRD and started building."
> — *[Your first user here]*

---

## 🤝 Contributing

Contributions are welcome! Please:

1. Fork the repo
2. Create a feature branch (`git checkout -b feature/amazing-addition`)
3. Commit your changes (`git commit -m 'Add amazing addition'`)
4. Push to the branch (`git push origin feature/amazing-addition`)
5. Open a Pull Request

**Ideas for contributions:**
- More PRD templates (e-commerce, social apps, dev tools)
- Framework-specific templates (Astro, Qwik, Remix)
- Real-world examples from your projects
- Translations

---

## 📖 Resources

- **Blog Post:** [10 Lessons From Vibe Coding My First App](https://iamjohnellison.substack.com/) (coming soon)
- **Original Gist:** [claude-code-templates](https://gist.github.com/johnellison/b5892475f65ac0556c585e172f39e9f6)
- **Claude Code Docs:** [docs.claude.com/claude-code](https://docs.claude.com/en/docs/claude-code)
- **Example Project:** [DeepWork OS](https://pravos.xyz)

---

## 📄 License

MIT License - see [`LICENSE`](./LICENSE) for details.

**TL;DR:** Do whatever you want with this. Build cool stuff and share it!

---

## 💬 Community

- **Questions?** Open an [issue](../../issues)
- **Built something cool?** Share it in [discussions](../../discussions)
- **X/Twitter:** [@iamjohnellison](https://twitter.com/iamjohnellison)
- **Newsletter:** [John's Substack](https://iamjohnellison.substack.com/)

---

## ⭐ Star History

If this template helps you ship faster, give it a star! ⭐

It helps other vibe coders discover it.

---

**Built with ❤️ by vibe coders, for vibe coders.**

**Now go ship something amazing.** 🚀
