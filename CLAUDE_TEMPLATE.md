# [PROJECT_NAME] - Claude Code Instructions

## Project Overview

[Brief 2-3 sentence description of what your application does]

**Business Model:** [Describe: Open source / Commercial / Internal tool / SaaS / etc.]
**Target Platforms:** [e.g., Web, macOS, iOS, Chrome Extension, etc.]

## Tech Stack

### Frontend

- **[Framework]** with TypeScript (strict mode)
  - [e.g., React 18, Vue 3, Svelte, Next.js]
- **[Build Tool]** for development and building
  - [e.g., Vite, Webpack, Next.js, etc.]
- **[CSS Framework/Approach]** for styling
  - [e.g., Tailwind CSS, CSS Modules, styled-components, etc.]
- **[Component Library]** for UI components
  - [e.g., shadcn/ui, Material-UI, Chakra, Headless UI, or "Custom components"]
- **[State Management]** for application state
  - [e.g., Zustand, Redux, Jotai, Context API, XState]
- **[Data Fetching]** for server state
  - [e.g., React Query, SWR, RTK Query, Apollo Client]
- **[Routing]** for navigation
  - [e.g., React Router, Next.js Router, Vue Router]
- **[Icon Library]** for icons
  - [e.g., Lucide React, Heroicons, Phosphor Icons]

### Backend & Database

- **[Backend Service]**
  - [e.g., Supabase, Firebase, AWS Amplify, Custom Node.js API]
- **[Authentication]**
  - [e.g., Supabase Auth, Auth0, Clerk, Custom JWT]
- **[Database]**
  - [e.g., PostgreSQL (Supabase), Firestore, MongoDB, MySQL]
- **[Real-time Features]** (if applicable)
  - [e.g., Supabase subscriptions, Socket.io, Pusher]
- **[Serverless Functions]** (if applicable)
  - [e.g., Supabase Edge Functions, Vercel Functions, AWS Lambda]

## Project Structure

```
[project-name]/
├── src/
│   ├── components/
│   │   ├── ui/               # [Describe: Base UI components]
│   │   └── [feature]/        # [Describe: Feature-specific components]
│   ├── pages/                # [Or "app/" for Next.js App Router]
│   ├── hooks/                # Custom React hooks
│   ├── lib/                  # Utilities and helpers
│   ├── stores/               # [State management files]
│   ├── types/                # TypeScript types
│   └── styles/               # Global styles
├── public/                   # Static assets
└── tests/                    # Test files
```

## Development Commands

```bash
[COMMAND]                     # [Description]
[COMMAND]                     # [Description]
[COMMAND]                     # [Description]
[COMMAND]                     # [Description]

# Example:
# npm run dev              # Start dev server
# npm test                 # Run tests
# npm run build            # Build for production
# npm run type-check       # Run TypeScript compiler
```

## Coding Standards

### TypeScript

- Strict mode enabled
- Explicit return types for functions
- No `any` types (use `unknown` if needed)
- Prefer interfaces for object shapes
- [Add project-specific TypeScript rules]

### [Framework] Conventions

- [List framework-specific conventions]
- [Example: Functional components only]
- [Example: Custom hooks start with `use` prefix]
- [Example: Keep components under 200 lines]
- [Example: Props interfaces end with `Props` suffix]

### State Management

- **Local UI state:** [When to use, how to structure]
- **Shared app state:** [When to use, how to structure]
- **Server state:** [When to use, how to structure]
- **URL state:** [When to use, how to structure]

### Styling

- [Primary styling approach]
- [Responsive design strategy: mobile-first, desktop-first]
- [Theme/dark mode requirements]
- [Naming conventions: BEM, utility-first, CSS modules, etc.]

### Component Reusability

**Philosophy:** Define once, use everywhere. Avoid repetition of styling patterns.

**[Component Category] Components:**
[Describe your reusable component patterns. Examples below:]

Always use the `Button` component from `@/components/ui/button` with appropriate variants. Never create custom `<button>` elements with inline styling for primary/secondary actions.

**Available [Component] Variants:**
- `[variant-name]`: [Description]
- `[variant-name]`: [Description]
- `[variant-name]`: [Description]

**Usage Examples:**
```tsx
// ✅ Correct - Use reusable component
import { Button } from '@/components/ui/button';

<Button variant="primary">
  Save Changes
</Button>

// ❌ Wrong - Custom element with inline classes
<button className="bg-blue-500 hover:bg-blue-600 px-4 py-2...">
  Save Changes
</button>
```

**Design Token Usage:**
- All colors must come from [config file location]
- Use semantic tokens: [list your semantic color names]
- Use spacing scale: [describe your spacing system]
- Use design system [gradients/shadows/etc.]: [list design tokens]

**When Custom Styling Is Acceptable:**
- [List exceptions where inline or custom styling is OK]
- [Example: Icon-only buttons]
- [Example: Complex state-dependent UI]

**Rule:** If you're typing the same [CSS/Tailwind] classes more than twice, create/use a component variant instead.

### File Naming

- Components: [Convention] (e.g., `PascalCase`, `kebab-case.component.tsx`)
- Hooks: [Convention] (e.g., `camelCase`, `use-hook-name.ts`)
- Utils: [Convention] (e.g., `camelCase`, `kebab-case.util.ts`)
- Types: [Convention] (e.g., `PascalCase`, `types.ts`)

## Type System

### Database Types

- Location: `[file path]`
- [How types are generated/maintained]
- Provides type safety for all database operations

### Re-generate types after schema changes:

```bash
[COMMAND TO REGENERATE TYPES]
# Example: supabase gen types typescript --local > src/types/database.ts
```

### Type Helpers

Import from `[import path]`:

- [List your core type exports]
- [Example: `User`, `Session`, `Task` - Row types]
- [Example: `UserInsert`, `SessionInsert` - Insert types]
- [Example: `UserUpdate`, `SessionUpdate` - Update types]

### Usage Example:

```typescript
[Provide a concrete example of how to use your types]
```

## Key Features [Current Phase]

### [Phase Name]

- [ ] [Feature 1]
- [ ] [Feature 2]
- [ ] [Feature 3]
- [ ] [Feature 4]

## Architecture Decisions

### [Decision Title]

[Describe any important architectural decisions, like:]
- Monorepo vs multi-repo
- Landing page + app in same repo
- Client-side vs server-side rendering
- Mobile-first vs desktop-first

[Explain the reasoning and trade-offs]

## Security & Privacy

- [List security measures]
- [Example: Row-level security enforces data isolation]
- [Example: Environment variables for all secrets]
- [Example: HTTPS only]
- [Repository privacy: public/private]

## Environment Variables

```bash
[VAR_NAME]=value  # Description
[VAR_NAME]=value  # Description

# Example:
# VITE_API_URL=https://api.example.com
# VITE_SUPABASE_URL=your-supabase-url
```

## Build Tool

**Using:** [Build tool name and version]

**Performance:**
- Dev server: [startup time]
- HMR: [hot module replacement time]
- Production build: [build time]

## Testing Strategy

**Read:** `TESTING_STRATEGY.md` for full details (if separate file exists)

**Core Principle:** [Describe your testing philosophy]

**Critical Test Coverage:**
[List the 3-5 most critical paths that MUST have tests]
1. [Critical user flow 1]
2. [Critical user flow 2]
3. [Critical user flow 3]

**What NOT to Test:**
- ❌ [What you intentionally skip]
- ❌ [Example: Individual component unit tests during MVP]
- ❌ [Example: Utility functions]

**Quality Gates Instead:**
1. [Alternative quality measure: TypeScript strict mode]
2. [Alternative quality measure: ESLint + Prettier]
3. [Alternative quality measure: Error monitoring]
4. [Alternative quality measure: Manual QA checklist]
5. [Alternative quality measure: Beta users]

**Instructions for Claude:**
- [Specific testing instructions]
- [Example: Do NOT write tests unless it's one of the critical paths]
- [Example: Focus on shipping features, not perfect test coverage]

## [Project-Specific Feature Section]

**[If you have a major subsystem, create a section for it]**

[Example: Audio System, Real-time Sync, Payment Integration, etc.]

**Library/Service:** [Name and version]
**Documentation:** [Link or file reference]

### Why [This Choice]?
- [Reason 1]
- [Reason 2]
- [Reason 3]

### Key Features
- [Feature 1]
- [Feature 2]
- [Feature 3]

### Code Locations
- [Description]: `[file path]`
- [Description]: `[file path]`
- [Description]: `[file path]`

### Testing
[How this feature is tested or not tested]

### [Critical Data/Asset Management Rules]

**⚠️ CRITICAL: [STATE THE RULE]**

[If you have critical data that should never be deleted/modified without explicit permission]

**When [Problem] Occurs:**

❌ **WRONG:**
```bash
# Don't [do the wrong thing]
[example command]
```

✅ **CORRECT:**
```bash
# 1. [Step 1]
# 2. [Step 2]
# 3. [Step 3]
```

**Troubleshooting [Problem]:**

1. **[Step 1]**
2. **[Step 2]**
3. **[Step 3]**

## Before Committing

- [ ] Types check (`[command]`) - **Required**
- [ ] Build succeeds (`[command]`) - **Required**
- [ ] Tests pass (`[command]`) - **[When required]**
- [ ] [Other quality gate] - **[Priority level]**

## Notes

- [Project-specific notes]
- [Example: This is a private commercial project]
- [Example: Prioritize user privacy and data security]
- [Example: Mobile-first responsive design]
- [Example: Dark mode is non-negotiable]

---

## [Advanced Topic]: [Title]

[This section is OPTIONAL but recommended for complex projects]

### Core Principle: [State Your Principle]

[Describe a learned pattern or principle from your project experience]

#### Example: [Concrete Example]

**❌ Failed Approaches:**
- [Approach 1 that didn't work]
- [Approach 2 that didn't work]
- [Approach 3 that didn't work]

**✅ Working Solution:**
- [What actually worked]
- [Key insight]
- [Implementation pattern]

```typescript
// [Code example of the working solution]
```

**Key implementation details:**

1. **[Detail 1]**: [Explanation]
2. **[Detail 2]**: [Explanation]
3. **[Detail 3]**: [Explanation]

### [Specific Gotcha/Pattern]

[Document specific technical gotchas or patterns you've learned]

**❌ This won't work:**
```typescript
[Anti-pattern code]
```

**✅ Use this instead:**
```typescript
[Correct pattern code]
```

### When to Step Back and Rethink

If you've tried **3+ different implementation approaches** and they all fail with similar issues:

1. **Stop debugging implementation details**
2. **Question the fundamental approach**
3. **Ask: [Key question for your domain]**
4. **Consider: [Alternative perspective]**

**Key lesson:** [Your learned lesson about when to pivot approaches]

---

## Production Auditing & Debugging Standards

When auditing code for production deployment or debugging complex integration issues, follow these rigorous standards to avoid missing critical implementation details.

### Deep Code Analysis (Not Surface Exploration)

**❌ Insufficient:**
- [Vague statement example]
- [Surface-level description example]

**✅ Required:**
- Cite exact line numbers: `[File.tsx:110]`
- Quote the actual code: `[actual code snippet]`
- Identify guards, conditions, and constraints that affect data flow
- Verify type definitions match usage (check both declaration and call sites)

### Verify Type System Constraints

Before proposing any solution, verify:
1. **Type definitions** - Check `[types location]` for enums and interfaces
2. **Service signatures** - Verify what parameters are actually accepted
3. **Database schema** - Confirm enum values match database types
4. **Workarounds** - If types don't match, specify how to bridge the gap

### Consider Full Lifecycle (Not Just Happy Path)

For any [critical feature type: e.g., data tracking, session management], analyze:

1. **Start** - Creation, initialization, persistence
2. **Running** - Updates, state changes, tracking
3. **Pause** - Temporary suspension, resume capability
4. **Complete** - Normal termination, cleanup
5. **Interrupt** - Page refresh, navigation, browser close, network failure
6. **Recovery** - Orphaned data, stale state, retry logic

**Critical questions:**
- What happens on page refresh mid-[operation]?
- What happens if user navigates away?
- What happens if browser crashes?
- Are active [resources] persisted to localStorage?
- Is there a cleanup/recovery mechanism on mount?

### Prioritize by Data Dependencies (Not UX Impact)

When multiple fixes are needed, prioritize based on **what unlocks what** in the data pipeline:

**Framework:**
1. Map data dependencies: What requires what?
2. Identify bottlenecks: What's blocking the most downstream features?
3. Prioritize unlocks: Fix foundational issues before dependent features

### Be Explicit About Implementation (Not Vague)

**❌ Vague plans fail:**
- "[Vague statement]"
- "[Another vague statement]"

**✅ Explicit plans succeed:**
```typescript
// 1. WHAT: [Specific action]
// 2. WHERE: [File.tsx line X]
// 3. HOW: [Specific implementation approach]
// 4. STORE: [How to persist state]
// 5. PERSIST: [How to handle persistence]
// 6. END: [How to cleanup]
// 7. RECOVER: [How to handle recovery]
```

### Account for Edge Cases in Time Estimates

**Optimistic estimates ignore:**
- Type system workarounds (guards, conversions, migrations)
- Edge case handling (pause, refresh, unmount, errors)
- Data cleanup and recovery
- Testing and verification
- Integration with existing code

**Rule of thumb:**
- Simple CRUD operation: 1-2x naive estimate
- [Complex operation type]: 2-3x naive estimate
- Cross-component integration: 3-4x naive estimate

### Pre-Implementation Checklist

Before proposing ANY production fix:

- [ ] Have I cited exact line numbers for the issue?
- [ ] Have I verified type constraints at both declaration and call sites?
- [ ] Have I considered the full lifecycle (start, pause, complete, interrupt, recover)?
- [ ] Have I checked for guards, conditions, or filters that affect data flow?
- [ ] Have I identified edge cases (refresh, navigate, close, error)?
- [ ] Have I proposed specific implementation details (not just "add [feature]")?
- [ ] Have I prioritized by data dependencies (not just UX impact)?
- [ ] Have I accounted for complexity in time estimates?

### When Another Agent Outperforms You

If another agent identifies issues you missed, **immediately update this document with the pattern they caught**.

**Self-improvement template:**
1. What did they catch that I missed? (Specific code detail)
2. What analysis method did they use? (How did they find it?)
3. What should I add to my checklist? (Preventive measure)

---

## MCP Servers (Optional)

[If you use Model Context Protocol servers, document them here]

### [MCP Server Name] Rules

- [Rule 1]
- [Rule 2]
- IMPORTANT: [Critical rule]
