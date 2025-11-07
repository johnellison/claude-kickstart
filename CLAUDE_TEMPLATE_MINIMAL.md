# [PROJECT_NAME] - Claude Code Instructions

## Project Overview

[Brief 2-3 sentence description of what your application does]

**Target Platforms:** [e.g., Web, Mobile, Desktop]

## Tech Stack

### Core Technologies

- **Frontend:** [Framework + TypeScript]
- **Styling:** [CSS approach]
- **State:** [State management solution]
- **Backend:** [Backend service or API]
- **Database:** [Database choice]

## Project Structure

```
[project-name]/
├── src/
│   ├── components/        # Reusable UI components
│   ├── [features]/        # Feature modules
│   ├── hooks/             # Custom hooks
│   ├── lib/               # Utilities and helpers
│   └── types/             # TypeScript types
├── public/                # Static assets
└── tests/                 # Test files
```

## Development Commands

```bash
[start-dev-command]        # Start development server
[build-command]            # Build for production
[test-command]             # Run tests
[type-check-command]       # Check TypeScript types
```

## Coding Standards

### TypeScript
- Strict mode enabled
- Explicit return types for functions
- No `any` types (use `unknown` if needed)

### Components
- [Naming convention]
- [Component organization principle]
- [State management principle]

### Styling
- [Primary styling approach]
- [Responsive design strategy]
- [Theme requirements]

### Component Reusability

**Rule:** If you're typing the same classes/styles more than twice, create a reusable component instead.

**Example:**
```tsx
// ✅ Correct - Use reusable Button component
<Button variant="primary">Save</Button>

// ❌ Wrong - Repeated inline styles
<button className="bg-blue-500 px-4 py-2...">Save</button>
```

## File Naming

- Components: [Convention]
- Hooks: [Convention]
- Utils: [Convention]
- Types: [Convention]

## Type System

**Type Generation:** `[command to regenerate types]`

**Core Types:** Import from `[import path]`

## Testing Strategy

**Critical paths that need tests:**
1. [Critical flow 1]
2. [Critical flow 2]
3. [Critical flow 3]

**Quality gates:**
- TypeScript strict mode
- [Linter/formatter]
- [Error monitoring tool]

## Before Committing

- [ ] Types check - **Required**
- [ ] Build succeeds - **Required**
- [ ] [Other check] - **[Priority]**

## Key Principles

1. [Core principle 1]
2. [Core principle 2]
3. [Core principle 3]

## Notes

- [Important project-specific note]
- [Another important note]
