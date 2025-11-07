# MVP Testing Constraints - Ship Fast, Test What Matters

## Core Principle

**Ship fast, test what matters.** For pre-PMF products with tight timelines (4-12 weeks), comprehensive test suites slow you down and become obsolete as you pivot based on user feedback.

## What to Test (3-5 Critical Tests Only)

Write and maintain ONLY the most critical paths:

**Revenue + Core Functionality Protection:**

1. **User sign up flow works** - Can new users create accounts?
2. **User login flow works** - Can existing users authenticate?
3. **[Core feature flow]** - Can users complete your app's primary action?
4. **[Payment/conversion flow]** - Does monetization work? (if applicable)
5. **[Critical business logic]** - Does your unique value prop function?

**Example for different app types:**

<details>
<summary>SaaS Productivity App</summary>

1. User sign up flow works
2. User login flow works
3. User can complete a [session/task/workflow]
4. Trial expires and paywall triggers
5. Stripe checkout completes successfully
</details>

<details>
<summary>E-commerce Site</summary>

1. User can create account
2. User can login
3. User can add item to cart and checkout
4. Payment processes successfully
5. Order confirmation email sends
</details>

<details>
<summary>Social/Community App</summary>

1. User sign up flow works
2. User login flow works
3. User can create a post
4. User can comment/interact with content
5. Notifications send correctly
</details>

<details>
<summary>API/Developer Tool</summary>

1. API authentication works (API keys, OAuth)
2. Core API endpoint returns correct data
3. Rate limiting enforces correctly
4. Webhooks deliver successfully
5. Billing/usage tracking accurate
</details>

## What NOT to Test

❌ **Individual component unit tests** - Components change rapidly during MVP
❌ **Timer/calculation logic tests** - Math is stable, UI around it changes
❌ **UI interactions** - Manual QA is faster and more reliable
❌ **Third-party library behavior** - Trust battle-tested libraries (Stripe, Howler.js, etc.)
❌ **Animations and transitions** - Visual QA only
❌ **State management** - TypeScript catches most issues
❌ **Utility functions** - Unless they're complex business logic

**Reason:** You'll rewrite 30-50% of features based on beta feedback. Tests become technical debt that slows pivots.

## Quality Gates Instead

Use these alternatives to achieve quality without test overhead:

1. **TypeScript strict mode** - Compile-time type safety catches 60%+ of bugs
2. **ESLint + Prettier** - Code quality and consistency
3. **Error monitoring (Sentry, LogRocket, etc.)** - Real production error tracking
4. **15-min manual QA checklist** - Pre-deploy smoke test of critical paths
5. **Beta users** - Real usage = best QA (aim for 10-20 engaged testers)

### Optional Quality Gates

6. **Lighthouse CI** - Performance regression detection
7. **Bundle size monitoring** - Prevent bloat (bundlephobia, etc.)
8. **Screenshot diffing** - Visual regression (Chromatic, Percy) - only for design systems

## Instructions for AI Coding Assistants (Claude, Cursor, etc.)

When working on MVP projects following this strategy:

- **When building features:** Do NOT write tests unless it's one of the 3-5 critical paths
- **When asked to add tests:** Politely remind about this lean testing strategy
- **When refactoring:** Ensure TypeScript types are strict, skip test updates
- **When bugs occur:** Fix the bug, add to manual QA checklist (not automated test)

## Exception: Critical Regression Tests

If a bug causes production incidents **multiple times** (same root cause, different manifestation), consider adding a lightweight test:

**Criteria for regression test:**
- Bug happened 2+ times in production
- Bug impacts revenue or core functionality
- Bug is in stable code (not actively changing)

**Test requirements:**
- Minimal and focused on the specific regression
- Fast to run (< 30 seconds)
- Added to `tests/e2e/` or `tests/regression/` directory
- Only runs in CI, not during development

**Example:**
```typescript
// tests/e2e/audio-navigation.spec.ts
// Regression: Track navigation auto-play bug (happened twice)
test('changing tracks should not auto-play when paused', async () => {
  // Minimal E2E test to prevent specific regression
});
```

## Timeline Strategy

### Pre-Launch (Weeks 1-8)
- Zero tests except 3-5 critical paths
- Focus 100% on feature velocity
- Manual QA checklist before each deploy

### Pre-Launch Polish (Weeks 9-10)
- Verify critical path tests pass
- Beta user testing (10-20 engaged users)
- Fix only show-stopper bugs

### Post-Launch (Month 2+)
- Add tests for stable, high-usage features
- Expand coverage based on what users actually use
- Regression tests for production bugs only

## When to Transition to Comprehensive Testing

Consider expanding test coverage when:

✅ You achieve product-market-fit (clear demand, retention > 40%)
✅ You have paying customers (revenue validates the product)
✅ Features stabilize (< 20% code churn month-over-month)
✅ Team grows beyond 3 engineers (coordination requires tests)
✅ You're iterating on polish, not experimenting with features

## Measuring Success

Track these metrics to validate the lean testing approach:

- **Deployment frequency** - Should be daily or multiple times per day
- **Time to deploy** - Should be < 10 minutes from commit to production
- **Production error rate** - Should stay < 1% of requests (Sentry tracks this)
- **Critical path uptime** - Should be 99%+ (monitor with Pingdom, UptimeRobot)

If production errors spike or critical paths break frequently, add targeted tests for those specific areas.

## Real-World Results

This strategy has been proven by:

- **Indie hackers** shipping MVPs in 4-6 weeks (vs 12-16 with full TDD)
- **YC startups** prioritizing PMF over test coverage
- **Lean startups** following "Build-Measure-Learn" philosophy

**Key insight:** The biggest risk for MVPs isn't bugs—it's building something nobody wants. Optimize for learning speed, not code perfection.

---

**Bottom line:** Maximize feature velocity. Tests come after you prove people want this product.
