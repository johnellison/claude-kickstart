# Sub-Agents for Claude Code

## 🌱 For Beginners: Start Here

**TL;DR:** Sub-agents are like having different AI teammates. Each one has a specific job.

**You don't need to understand this deeply right now.** Just use these two to start:

### 🔨 Builder Agent (Use This 90% of the Time)

**What it does:** Builds your features

**When to use:** Every time you want to add something to your app

**How to use:** Just ask Claude to build something. It automatically calls this agent.

**Example:**
```
You: "Build a login page with email and password"
Claude: [Automatically uses Builder agent to create it]
```

### ✅ Checker Agent (Use Before Finishing)

**What it does:** Makes sure everything works together

**When to use:** After building 3-5 features, or before calling your app "done"

**How to use:** Tell Claude: "Check if everything works together"

**Example:**
```
You: "I've built the login page, signup page, and home page. Check if they work together."
Claude: [Uses Checker agent to verify integration]
```

**That's all you need for now!** The rest of this guide is for advanced users.

---

## 🎓 Advanced: Complete Sub-Agent Guide

Ready to level up? Here's the full breakdown of all 5 sub-agents and when to use them.

Sub-agents are specialized AI agents that handle specific responsibilities in your development workflow. Think of them as different engineers on your team—each with a specific role.

**Why use sub-agents?**
- Prevents the "code fast, break everything" problem
- Divides labor between building and validating
- Maintains code quality without slowing down
- Catches integration issues early

---

## Quick Reference

Claude Code comes with several built-in sub-agents. Here are the configurations I use for most projects:

### 1. Implementation Pair (Your Builder)

**Role:** General-purpose software engineer that implements specifications and completes subtasks.

**When to use:**
- Building new features
- Implementing designs
- Writing code
- Refactoring existing code

**Configuration:**
```yaml
subagent_type: implementation-pair
model: sonnet  # Use sonnet for most work (fast, cost-effective)
```

**Example usage:**
```
User: "Build a login form with email and password fields. Use the Button
component from our design system. Add form validation."

Claude: [Calls implementation-pair sub-agent]
```

**Best practices:**
- Give specific, focused tasks (not vague "build auth system")
- Reference your CLAUDE.md standards (it will follow them)
- Keep tasks under 30 minutes of work
- Use this agent for 70-80% of your development

---

### 2. Integration Validator (Your Quality Gate)

**Role:** Reviews code every 3-5 completed subtasks to ensure system coherence across multiple changes.

**When to use:**
- After completing 3-5 features
- Before major releases
- When multiple components interact
- After refactoring sessions

**Configuration:**
```yaml
subagent_type: integration-validator
model: sonnet  # Extended thinking optional for complex systems
```

**Example usage:**
```
User: "I've built the login form, signup form, and password reset flow.
Run the integration validator to make sure everything works together."

Claude: [Calls integration-validator sub-agent]
```

**What it checks:**
- Components actually integrate (not just individual unit tests)
- Data flows correctly between features
- No conflicting state management
- Consistent UI patterns
- Type safety across boundaries

**Best practices:**
- Run after every 3-5 subtasks (don't wait until the end)
- Give context on what you built since last validation
- Fix issues immediately before building more
- Use this as a forcing function to keep quality high

---

### 3. Explore Agent (Your Researcher)

**Role:** Fast agent specialized for exploring codebases, finding files, and answering questions about code structure.

**When to use:**
- Understanding existing code
- Finding where features are implemented
- Searching for patterns across the codebase
- Answering "how does X work?" questions

**Configuration:**
```yaml
subagent_type: Explore
thoroughness: medium  # Options: quick, medium, very thorough
```

**Example usage:**
```
User: "Where is authentication handled in this codebase?"

Claude: [Calls Explore sub-agent with thoroughness: medium]
```

**Thoroughness levels:**
- **quick** - Basic searches, single-location checks (30 seconds)
- **medium** - Moderate exploration, multiple file checks (2 minutes)
- **very thorough** - Comprehensive analysis across codebase (5 minutes)

**Best practices:**
- Use "quick" for simple lookups
- Use "medium" for understanding feature implementation
- Use "very thorough" for architectural questions
- Always use Explore instead of manually grepping (it's smarter)

---

### 4. Quality Gate (Your Pre-Deploy Checklist)

**Role:** Fast verification of quality standards before task completion. Proactive final check.

**When to use:**
- Before committing major features
- Before deploying to production
- After fixing critical bugs
- When you want a final "sanity check"

**Configuration:**
```yaml
subagent_type: quality-gate
tools: [Read, Bash, Grep, Glob]  # Limited toolset for speed
```

**Example usage:**
```
User: "I'm done with the payment integration. Run the quality gate before I commit."

Claude: [Calls quality-gate sub-agent]
```

**What it checks:**
- TypeScript types pass
- Build succeeds
- No obvious security issues
- Follows CLAUDE.md standards
- Critical paths still work

**Best practices:**
- Use proactively (don't wait to be asked)
- Run before every git commit of major work
- Fix issues immediately
- Add findings to your CLAUDE.md if they're patterns

---

## Advanced: Plan Agent

**Role:** Explores codebase and creates implementation plans for complex features.

**When to use:**
- Starting a complex feature
- Refactoring large systems
- When you're not sure where to start
- Planning multi-day work

**Configuration:**
```yaml
subagent_type: Plan
thoroughness: medium
```

**Example usage:**
```
User: "I want to add real-time collaboration to the task board. Create a plan."

Claude: [Calls Plan sub-agent]
```

**Output:**
- Breakdown of subtasks
- Dependency graph
- Risk assessment
- Estimated complexity

**Best practices:**
- Use for features that will take 4+ hours
- Review the plan before accepting it
- Push back on over-engineering
- Break the plan into smaller tasks for implementation-pair

---

## Workflow: How to Use Sub-Agents Together

### Typical Feature Development Flow

```
1. PLAN (Plan agent)
   └─> Break feature into 5-8 subtasks

2. BUILD (Implementation-pair agent)
   └─> Implement subtask 1
   └─> Implement subtask 2
   └─> Implement subtask 3

3. VALIDATE (Integration-validator agent)
   └─> Check that subtasks 1-3 work together
   └─> Fix any integration issues

4. BUILD (Implementation-pair agent)
   └─> Implement subtask 4
   └─> Implement subtask 5

5. VALIDATE (Integration-validator agent)
   └─> Check that all 5 subtasks work together

6. QUALITY GATE (Quality-gate agent)
   └─> Final checks before commit

7. COMMIT
   └─> Git commit with detailed message
```

### When to Use Extended Thinking

For most work, standard Sonnet is fine. Use **extended thinking** when:

- Planning complex features (Plan agent)
- Debugging gnarly integration issues (Integration-validator)
- Architectural decisions (should I use X or Y?)
- Performance optimization strategies

**How to enable:**
Add to your sub-agent call:
```yaml
model: sonnet
use_extended_thinking: true
```

---

## Configuration in Claude Code

### Method 1: In Your CLAUDE.md

Add this section to your `CLAUDE.md`:

```markdown
## Sub-Agent Strategy

**Implementation:** Use implementation-pair (sonnet) for all feature building
**Validation:** Run integration-validator every 3-5 subtasks
**Exploration:** Use Explore agent for codebase questions
**Pre-commit:** Use quality-gate before every major commit

**Rules:**
- ALWAYS validate after 3-5 subtasks (don't skip this)
- Use Explore instead of manual file searches
- Run quality-gate proactively before committing
- Use extended thinking for complex architectural decisions
```

### Method 2: Direct Tool Use

When you want to call a sub-agent directly:

```
User: "Call the implementation-pair sub-agent to build this feature: [spec]"
```

Claude Code will invoke it automatically based on your CLAUDE.md configuration.

---

## Real-World Examples

### Example 1: Building a Payment Integration

```
User: "I need to integrate Stripe checkout. Let's plan this first."

Claude: [Calls Plan agent]
Plan output:
1. Set up Stripe API keys in env
2. Create checkout session endpoint
3. Build checkout UI component
4. Handle webhook for payment confirmation
5. Update user subscription status in database

User: "Great. Let's start with subtask 1."

Claude: [Calls implementation-pair]
[Implements Stripe API setup]

User: "Now subtask 2."

Claude: [Calls implementation-pair]
[Implements checkout endpoint]

User: "Now subtask 3."

Claude: [Calls implementation-pair]
[Implements checkout UI]

User: "Run the integration validator."

Claude: [Calls integration-validator]
Findings:
✅ API keys loaded correctly
✅ Endpoint works
❌ Checkout UI doesn't handle loading states
❌ No error handling for failed payments

User: "Fix those issues."

Claude: [Calls implementation-pair]
[Fixes loading states and error handling]

User: "Continue with subtasks 4-5."

Claude: [Implements webhook + database updates]

User: "Run quality gate."

Claude: [Calls quality-gate]
✅ Types pass
✅ Build succeeds
✅ Security check (no API keys in client code)
✅ Follows CLAUDE.md standards

User: "Commit this."

Claude: [Creates git commit with detailed message]
```

### Example 2: Debugging a Broken Feature

```
User: "The timer isn't syncing with the audio player. Use Explore to understand
how these components communicate."

Claude: [Calls Explore agent with thoroughness: medium]
Findings:
- Timer: src/components/FocusTimer.tsx
- Audio: src/components/AudioPlayer.tsx
- They communicate via Zustand store: src/stores/sessionStore.ts
- Timer updates session.isActive
- Audio subscribes to session.isActive
- Problem: Audio subscribes AFTER timer mount, misses initial state

User: "Fix this race condition."

Claude: [Calls implementation-pair]
[Implements fix: Audio now reads initial state on mount]

User: "Run integration validator to make sure this doesn't break anything else."

Claude: [Calls integration-validator]
✅ Timer and audio now sync correctly
✅ Task list integration still works
✅ Break timer not affected
✅ No type errors
```

---

## Common Mistakes

### ❌ Mistake 1: Only using implementation-pair
**Problem:** Code gets built fast but breaks integration points.
**Fix:** Run integration-validator every 3-5 subtasks.

### ❌ Mistake 2: Never using Explore
**Problem:** Spending 10 messages asking "where is X?" instead of just searching.
**Fix:** Use Explore for any codebase question.

### ❌ Mistake 3: Skipping quality-gate
**Problem:** Committing code that doesn't build or breaks types.
**Fix:** Run quality-gate proactively before committing.

### ❌ Mistake 4: Using extended thinking for everything
**Problem:** Slow responses and higher costs for simple tasks.
**Fix:** Only use extended thinking for complex planning or debugging.

### ❌ Mistake 5: Vague sub-agent prompts
**Problem:** "Build auth" → agent builds enterprise-grade OAuth system.
**Fix:** Be specific: "Build a login form with email/password. Use Supabase Auth. Follow the Button component from design system."

---

## Customizing Sub-Agents

Want to create your own sub-agent patterns? Add to your CLAUDE.md:

```markdown
## Custom Sub-Agent: [Name]

**Role:** [What does this agent do?]

**When to use:**
- [Scenario 1]
- [Scenario 2]

**Configuration:**
[How to invoke it]

**Example usage:**
[Real example]

**Best practices:**
- [Tip 1]
- [Tip 2]
```

---

## Resources

- **Claude Code Docs:** [Sub-agent documentation](https://docs.claude.com/en/docs/claude-code)
- **GitHub Repo:** [claude-kickstart](https://github.com/johnellison/claude-kickstart)
- **Discussion:** [Share your sub-agent workflows](https://github.com/johnellison/claude-kickstart/discussions)

---

**Questions?** Open an issue or discussion on GitHub. I'd love to hear how you're using sub-agents!
