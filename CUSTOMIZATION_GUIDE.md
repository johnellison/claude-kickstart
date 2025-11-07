# Claude Code Instructions Template - Customization Guide

This guide helps you adapt the `CLAUDE_TEMPLATE.md` for your project.

## Quick Start

1. **Choose your template:**
   - `CLAUDE_TEMPLATE.md` - Full-featured template with all sections
   - `CLAUDE_TEMPLATE_MINIMAL.md` - Minimal starter (5 min setup)

2. **Copy to your project:**
   ```bash
   cp CLAUDE_TEMPLATE.md /path/to/your-project/CLAUDE.md
   # OR
   cp CLAUDE_TEMPLATE_MINIMAL.md /path/to/your-project/CLAUDE.md
   ```

3. **Find and replace placeholders:**
   - `[PROJECT_NAME]` - Your actual project name
   - `[COMMAND]` - Actual commands (`npm run dev`, `pnpm build`, etc.)
   - `[Framework]` - Your actual framework (React, Vue, Svelte, etc.)
   - All other `[PLACEHOLDER]` text

4. **Delete sections you don't need**

5. **Add project-specific sections**

## Section-by-Section Guide

### 1. Project Overview (Required)

**What to fill in:**
- 2-3 sentence description of your app
- Business model (open source, SaaS, internal tool, etc.)
- Target platforms (web, mobile, desktop, etc.)

**Example:**
```markdown
TaskFlow is a collaborative task management platform designed for remote teams.
It combines Kanban boards, time tracking, and team chat in a unified interface.

**Business Model:** Open source core with paid cloud hosting
**Target Platforms:** Web (React), Desktop (Tauri), Mobile (React Native)
```

### 2. Tech Stack (Required)

**Fill out what you're using:**

| Category | Common Options |
|----------|----------------|
| **Frontend Framework** | React, Vue, Svelte, Next.js, Nuxt, SvelteKit, Solid |
| **Build Tool** | Vite, Webpack, Next.js, Turbopack, esbuild |
| **CSS/Styling** | Tailwind CSS, CSS Modules, styled-components, Sass, vanilla-extract |
| **Component Library** | shadcn/ui, Radix UI, Headless UI, Material-UI, Chakra UI, Ant Design |
| **State Management** | Zustand, Redux Toolkit, Jotai, Recoil, XState, Context API, Pinia (Vue) |
| **Data Fetching** | React Query, SWR, RTK Query, Apollo Client, tRPC |
| **Backend** | Supabase, Firebase, AWS Amplify, Convex, Pocketbase, Custom API |
| **Database** | PostgreSQL, MySQL, MongoDB, Firestore, DynamoDB |

**Delete sections you don't use:**
- No backend? Delete the "Backend & Database" section
- No icons library? Delete that line
- Using vanilla CSS? Remove component library line

### 3. Project Structure (Required)

**Adapt to your actual folder structure:**

```bash
# Run this in your project to see your structure:
tree -L 2 src/

# Or on Windows:
dir src /s /b | findstr /v node_modules
```

**Common patterns:**

<details>
<summary>Next.js App Router</summary>

```
your-app/
├── app/
│   ├── (auth)/              # Route groups
│   ├── (dashboard)/
│   ├── api/                 # API routes
│   └── layout.tsx
├── components/
│   ├── ui/
│   └── features/
├── lib/
└── public/
```
</details>

<details>
<summary>React + Vite</summary>

```
your-app/
├── src/
│   ├── components/
│   ├── pages/
│   ├── hooks/
│   ├── stores/
│   ├── lib/
│   └── types/
├── public/
└── tests/
```
</details>

<details>
<summary>Vue 3 + Vite</summary>

```
your-app/
├── src/
│   ├── components/
│   ├── views/
│   ├── composables/
│   ├── stores/
│   ├── router/
│   └── assets/
└── public/
```
</details>

### 4. Development Commands (Required)

**Fill in YOUR actual commands:**

```bash
# Find your commands in:
cat package.json | grep "scripts"

# Common patterns:
npm run dev          # or: pnpm dev, yarn dev, bun dev
npm run build        # or: pnpm build, yarn build
npm test             # or: pnpm test, vitest, jest
npm run type-check   # or: tsc --noEmit
npm run lint         # or: eslint, biome
```

### 5. Coding Standards (Required)

**Customize these sections:**

#### TypeScript Rules
- Keep the defaults (strict mode, explicit returns, no `any`)
- Add project-specific rules (e.g., "Use Zod for runtime validation")

#### Framework Conventions
**React example:**
```markdown
### React Conventions
- Functional components only
- Custom hooks start with `use` prefix
- Keep components under 200 lines
- Props interfaces end with `Props` suffix
- Use `React.FC` only for components with children
```

**Vue example:**
```markdown
### Vue Conventions
- Use Composition API (not Options API)
- Keep composables under 100 lines
- Props use `defineProps<T>()` syntax
- Emit events with `defineEmits<T>()`
```

#### State Management
**Fill in YOUR strategy:**
```markdown
### State Management
- **Local UI state:** `useState` / `ref()` for component-only state
- **Shared app state:** Zustand store in `src/stores/` for cross-component state
- **Server state:** React Query for all API data
- **URL state:** useSearchParams() for filters, pagination, tabs
```

### 6. Component Reusability (Highly Recommended)

**This section prevents repetitive code. Customize to YOUR design system:**

**Step 1: Identify your most-used components**
- Buttons (primary, secondary, danger, ghost, link)
- Inputs (text, email, password, search)
- Cards, modals, dropdowns, etc.

**Step 2: Document your variants**

```markdown
**Available Button Variants:**
- `primary`: Blue background, white text (main CTAs)
- `secondary`: White background, blue border (secondary actions)
- `danger`: Red background, white text (destructive actions)
- `ghost`: No background, hover effect (nav items)
- `link`: No background, underline on hover (inline links)
```

**Step 3: Add usage examples**

```tsx
// ✅ Correct - Use Button component
<Button variant="primary">Save Changes</Button>

// ❌ Wrong - Custom button with repeated classes
<button className="bg-blue-600 hover:bg-blue-700 px-4 py-2...">
  Save Changes
</button>
```

**For Tailwind projects, add design tokens:**

```markdown
**Design Token Usage:**
- All colors from `tailwind.config.js` (no hex codes in components)
- Use semantic tokens: `primary`, `secondary`, `accent`, `error`, `success`
- Use spacing scale: `px-4` (not arbitrary `px-[17px]`)
- Use design system shadows: `shadow-card`, `shadow-elevated`
```

### 7. Type System (If Using TypeScript)

**For Supabase projects:**
```bash
supabase gen types typescript --local > src/types/database.ts
```

**For tRPC projects:**
```bash
# Types auto-generated from your router
```

**For Prisma projects:**
```bash
npx prisma generate
```

**For GraphQL projects:**
```bash
npm run codegen  # graphql-codegen
```

### 8. Testing Strategy (Recommended)

**Philosophy options:**

<details>
<summary>Lean Testing (MVP/Pre-PMF)</summary>

```markdown
**Core Principle:** Ship fast, test what matters. Pre-PMF with tight timeline.

**Critical paths only (3-5 tests):**
1. User can sign up
2. User can log in
3. [Core feature flow]

**Skip:**
- Component unit tests
- Utility functions
- UI interactions

**Quality gates instead:**
- TypeScript strict mode
- ESLint + Prettier
- Sentry for production errors
- Manual QA checklist
```
</details>

<details>
<summary>Balanced Testing (Growing Product)</summary>

```markdown
**Core Principle:** Test critical paths, skip trivial code.

**Test coverage:**
1. Authentication flows (sign up, login, logout, password reset)
2. Core user journeys (5-8 main flows)
3. Payment/subscription logic (if applicable)
4. Data mutations (create, update, delete)

**Skip:**
- Pure UI components (unless complex logic)
- Simple utility functions
- Third-party integrations (mock them)

**Quality gates:**
- TypeScript + ESLint
- Integration tests for critical paths
- E2E tests for purchase flows
- Error monitoring (Sentry)
```
</details>

<details>
<summary>Comprehensive Testing (Mature Product)</summary>

```markdown
**Core Principle:** High confidence through comprehensive coverage.

**Test strategy:**
- Unit tests for utilities and pure functions
- Component tests for complex UI logic
- Integration tests for feature flows
- E2E tests for critical user journeys
- Visual regression tests (Chromatic, Percy)

**Coverage targets:**
- Utilities: 90%+
- Components: 70%+
- Integration: 80%+
- E2E: 100% of critical paths
```
</details>

### 9. Project-Specific Feature Sections (Optional)

**Add sections for major subsystems:**

**Examples:**
- Audio System (music players, podcasts)
- Real-time Sync (collaborative editing)
- Payment Integration (Stripe, subscriptions)
- File Upload/Storage (images, documents)
- Email System (transactional emails)
- Search/Indexing (Algolia, Meilisearch)

**Template:**
```markdown
## [Subsystem Name]

**Library/Service:** [Name and version]
**Documentation:** [Link or file path]

### Why [This Choice]?
- [Reason 1]
- [Reason 2]

### Key Features
- [Feature 1]
- [Feature 2]

### Code Locations
- Manager: `src/lib/[subsystem]-manager.ts`
- Store: `src/stores/[subsystem]Store.ts`
- Hook: `src/hooks/use[Subsystem].ts`

### Critical Rules

**⚠️ NEVER [DO THING] UNLESS [CONDITION]**

[Describe data/asset protection rules]
```

### 10. Animation/UI Patterns (Optional, Advanced)

**Only include if you have complex animations or learned hard lessons.**

**When to include this section:**
- You use Framer Motion, GSAP, or complex CSS animations
- You've discovered non-obvious gotchas (SVG animations, coordinate systems, etc.)
- You want Claude to follow specific animation patterns

**What to document:**
- Core animation principle (e.g., "Render what you want to see")
- Failed approaches and why they didn't work
- Working solutions with code examples
- Library-specific gotchas (Framer Motion limitations, etc.)

**Skip this if:**
- You're using simple CSS transitions
- Animations are straightforward
- You haven't hit any major animation bugs

### 11. Production Auditing Standards (Optional, Advanced)

**When to include:**
- You've had bugs reach production due to shallow code review
- Your app has complex data flows that are easy to misunderstand
- You want Claude to provide rigorous analysis (not surface-level)

**What it enforces:**
- Cite exact line numbers, not vague descriptions
- Verify type constraints before proposing solutions
- Consider full lifecycle (start, pause, complete, interrupt, recover)
- Prioritize by data dependencies, not just UX impact

**Skip this if:**
- Your app is simple CRUD
- You don't need deep auditing
- You're in rapid prototyping mode

### 12. MCP Servers (Optional)

**Only if you use Model Context Protocol:**

```markdown
## MCP Servers

### Figma MCP Server Rules
- IMPORTANT: Use localhost sources directly
- DO NOT import new icon packages
- DO NOT create placeholders if asset URL provided

### [Other MCP Server]
- [Rule 1]
- [Rule 2]
```

## Common Customization Patterns

### Monorepo Projects

If you have multiple packages:

```markdown
## Monorepo Structure

workspace-root/
├── apps/
│   ├── web/              # Next.js app
│   ├── mobile/           # React Native app
│   └── docs/             # Documentation site
├── packages/
│   ├── ui/               # Shared UI components
│   ├── config/           # Shared configs (ESLint, TS, Tailwind)
│   └── database/         # Prisma schema and client
└── package.json          # Workspace root

**Development Commands:**
```bash
pnpm dev              # Start all apps
pnpm dev --filter web # Start specific app
pnpm build            # Build all packages
pnpm test             # Run all tests
```
```

### Component Library Projects

```markdown
## Component Development

This is a component library, not an application.

**Build Modes:**
- Development: Storybook (`npm run storybook`)
- Production: Build ESM + CJS bundles (`npm run build`)
- Testing: Vitest + React Testing Library

**Export Pattern:**
All components must be exported from `src/index.ts` with proper TypeScript types.

**Storybook Stories:**
Every component must have at least 2 stories:
1. Default state
2. All variants/props
```

### Chrome Extension Projects

```markdown
## Extension Architecture

**Manifest:** `manifest.json` (Manifest V3)

**Entry Points:**
- Background: `src/background/service-worker.ts`
- Content Script: `src/content/index.ts`
- Popup: `src/popup/index.tsx`
- Options: `src/options/index.tsx`

**Storage:**
Use `chrome.storage.local` (not localStorage)

**Messaging:**
```typescript
// Content script → Background
chrome.runtime.sendMessage({ type: 'ACTION', payload: data });

// Background → Content script
chrome.tabs.sendMessage(tabId, { type: 'ACTION', payload: data });
```

**Build Command:**
```bash
npm run build  # Outputs to dist/ for Chrome Web Store
```
```

### Mobile-First Web Apps

```markdown
## Responsive Design Strategy

**Mobile-First Approach:**
1. Design for 375px width first (iPhone SE)
2. Add tablet breakpoint at `md:` (768px)
3. Add desktop at `lg:` (1024px)
4. Add large desktop at `xl:` (1280px)

**Testing Devices:**
- iPhone SE (375px) - minimum supported
- iPhone 14 Pro (393px)
- iPad (768px)
- Desktop (1440px)

**Touch Targets:**
- Minimum 44x44px for all interactive elements
- No hover-only interactions (must work on touch)
```

## Validation Checklist

Before sharing your CLAUDE.md:

- [ ] All `[PLACEHOLDER]` text replaced with actual values
- [ ] Commands tested and work (`npm run dev`, etc.)
- [ ] File paths are correct (`src/types/database.ts`, etc.)
- [ ] Deleted sections you don't use
- [ ] Added project-specific sections
- [ ] Design tokens match your `tailwind.config.js` (if using Tailwind)
- [ ] Component variants match your actual components
- [ ] Testing strategy matches your actual approach
- [ ] Removed the DeepWork OS examples that don't apply

## Sharing Your Template

### Create a Gist (Recommended)

```bash
# Install GitHub CLI if you haven't
brew install gh  # macOS
# or: https://cli.github.com/

# Create a public gist
gh gist create CLAUDE.md --public --desc "Claude Code instructions for [Your Project Type]"

# Share the URL with your followers!
```

### Create a GitHub Template Repository

1. Create new repo: `your-username/claude-code-template-[project-type]`
2. Add files:
   - `CLAUDE.md` (your customized template)
   - `README.md` (instructions for using the template)
   - `LICENSE` (MIT recommended)
3. Mark as template repository in Settings
4. Share the "Use this template" button URL

### Blog Post Template

```markdown
# Claude Code Template for [Your Stack]

I've created a Claude Code instructions template for [React + Supabase / Vue + Firebase / etc.] projects.

## What's Included
- [List key sections]
- [Highlight unique parts]

## Quick Start
1. Copy [CLAUDE.md](link) to your project root
2. Replace placeholders: [PROJECT_NAME], [COMMAND], etc.
3. Delete sections you don't need
4. Start building with Claude Code!

## Key Features
[Highlight 2-3 unique sections, like component reusability rules or testing strategy]

## Get It Here
- Template: [GitHub link]
- Minimal version: [GitHub link]
- Customization guide: [GitHub link]

Built for my own [project name] and sharing with the community. Let me know if you use it!
```

## Need Help?

**Common issues:**

1. **"Not sure which sections to keep"**
   - Keep: Project Overview, Tech Stack, Coding Standards, File Naming
   - Optional: Testing Strategy, Component Reusability, Advanced sections
   - Delete: Sections that don't apply (e.g., Audio System if no audio)

2. **"My project doesn't fit the template"**
   - That's OK! Use CLAUDE_TEMPLATE_MINIMAL.md and add what you need
   - Claude Code is flexible - the template is guidance, not rules

3. **"Template feels too long"**
   - Use CLAUDE_TEMPLATE_MINIMAL.md (5-minute setup)
   - Add sections as you encounter issues
   - Length is OK - Claude can handle it (200K context window)

## Examples by Stack

Want to see filled-out examples? Check:
- **React + Supabase**: Original DeepWork OS `CLAUDE.md`
- **Next.js + Prisma**: [Community example needed]
- **Vue + Firebase**: [Community example needed]

**Contribute yours!** Share a gist and I'll link it here.
