# Product Requirements Document (PRD) Template

Use this template to organize your product idea before generating your CLAUDE.md with Claude Code.

**Don't overthink it!** Fill in what you know. Claude Code will help you refine the rest.

---

## Project Overview

### Project Name
**[Your App Name]**

### Tagline (1 sentence)
[What does your app do in one sentence?]

**Example:** "TaskMaster is a collaborative task management app for remote engineering teams."

### Problem Statement
[What problem are you solving? Who has this problem?]

**Example:**
```
Remote engineering teams struggle to coordinate async work across multiple tools—
they use Jira for tasks, Slack for updates, GitHub for code, and Zoom for standups.
This context switching kills productivity and creates information silos.
```

### Solution
[How does your app solve this problem?]

**Example:**
```
TaskMaster combines Kanban boards, time tracking, and async standup reports in one interface.
Engineers update tasks, log time, and submit daily summaries without leaving the app.
Managers get real-time visibility into sprint progress and team workload.
```

---

## Target Users

### Primary User Persona
- **Who:** [Role/job title]
- **Needs:** [What do they need to accomplish?]
- **Pain Points:** [What frustrates them about current solutions?]
- **Success Criteria:** [What does success look like for them?]

**Example:**
```
- Who: Remote software engineers (IC level)
- Needs: Track tasks, log time, avoid daily standup meetings
- Pain Points: Context switching between 5+ tools, repetitive standup updates
- Success Criteria: Spend 10 more hours/week on deep work instead of coordination
```

### Secondary User Persona (optional)
- **Who:** [Role/job title]
- **Needs:** [What do they need to accomplish?]
- **Pain Points:** [What frustrates them about current solutions?]
- **Success Criteria:** [What does success look like for them?]

---

## Core Features (MVP)

List 5-10 features for your Minimum Viable Product. Focus on **what users can DO**, not how it's implemented.

### Must-Have Features (MVP Blockers)

1. **[Feature Name]**
   - **Description:** [What does this feature do?]
   - **User Story:** As a [user], I want to [action] so that [benefit]
   - **Acceptance Criteria:** [How do you know it works?]

**Example:**
```
1. Kanban Board
   - Description: Drag-and-drop task board with columns (To Do, In Progress, Done)
   - User Story: As an engineer, I want to move tasks across columns so I can visualize my workflow
   - Acceptance Criteria:
     - Create/edit/delete tasks
     - Drag tasks between columns
     - Real-time updates when teammates move tasks
```

2. **[Feature Name]**
   - Description: [What does this feature do?]
   - User Story: As a [user], I want to [action] so that [benefit]
   - Acceptance Criteria: [How do you know it works?]

3. **[Feature Name]**
   - Description: [What does this feature do?]
   - User Story: As a [user], I want to [action] so that [benefit]
   - Acceptance Criteria: [How do you know it works?]

4. **[Feature Name]**
   - Description: [What does this feature do?]
   - User Story: As a [user], I want to [action] so that [benefit]
   - Acceptance Criteria: [How do you know it works?]

5. **[Feature Name]**
   - Description: [What does this feature do?]
   - User Story: As a [user], I want to [action] so that [benefit]
   - Acceptance Criteria: [How do you know it works?]

### Nice-to-Have Features (Post-MVP)

6. **[Feature Name]** - [Brief description]
7. **[Feature Name]** - [Brief description]
8. **[Feature Name]** - [Brief description]

---

## Technical Requirements

### Target Platforms
- [ ] Web (desktop browser)
- [ ] Web (mobile browser)
- [ ] Native mobile (iOS)
- [ ] Native mobile (Android)
- [ ] Desktop app (macOS/Windows/Linux)
- [ ] Browser extension
- [ ] Other: [Specify]

### Tech Stack Preferences

**Do you have specific tech preferences?** (If unsure, skip this—Claude will recommend a stack)

- **Frontend Framework:** [React / Vue / Svelte / Next.js / None specified]
- **Backend/Database:** [Supabase / Firebase / AWS / Custom API / None specified]
- **Styling:** [Tailwind / CSS Modules / styled-components / None specified]
- **Must-haves:** [Any specific requirements? e.g., "Must be real-time", "Must work offline", "Must support 10K+ users"]

**Example:**
```
- Frontend Framework: React 18 with TypeScript
- Backend/Database: Supabase (need real-time for collaborative editing)
- Styling: Tailwind CSS (fast iteration)
- Must-haves: Real-time collaboration, mobile web responsive, TypeScript strict mode
```

### Performance Requirements

- **Expected Users:** [How many users at launch? 100? 10K? 100K?]
- **Data Volume:** [How much data per user? Small text? Large files? Media?]
- **Response Time:** [How fast should it feel? Instant? < 1 second? < 3 seconds?]
- **Uptime:** [How critical is availability? 95%? 99%? 99.9%?]

**Example:**
```
- Expected Users: 500 users at launch, 5K within 6 months
- Data Volume: Lightweight (text-based tasks, no file uploads)
- Response Time: < 300ms for task updates (real-time feel)
- Uptime: 99%+ (not mission-critical, but users rely on it daily)
```

---

## User Flows

### Critical User Flow #1: [Name]
[Describe the most important user journey in your app]

**Example: Create and Complete a Task**
```
1. User clicks "New Task" button
2. Modal opens with task form (title, description, assignee, due date)
3. User fills in details and clicks "Create"
4. Task appears in "To Do" column
5. User drags task to "In Progress"
6. User logs time spent (timer or manual entry)
7. User drags task to "Done"
8. Task marked complete, time logged to sprint report
```

### Critical User Flow #2: [Name]
[Describe the second most important user journey]

### Critical User Flow #3: [Name]
[Describe the third most important user journey]

---

## Success Metrics

### Primary Metric (North Star)
[What's the ONE metric that defines success?]

**Example:**
```
Active teams per week (teams that create 10+ tasks/week)
```

### Secondary Metrics
- [Metric 2]
- [Metric 3]
- [Metric 4]

**Example:**
```
- Tasks completed per user per week
- Average session duration (target: 30+ minutes)
- Weekly active users (WAU)
```

### Revenue Metrics (if applicable)
- [How will you make money?]
- [What's your pricing model?]
- [What's your conversion target?]

**Example:**
```
- Freemium: Free for teams < 5 users, $10/user/month for larger teams
- Target: 10% conversion from free to paid within 30 days
- Target MRR at 6 months: $5K
```

---

## Timeline & Milestones

### MVP Timeline
- **Total Time to MVP:** [4 weeks? 8 weeks? 12 weeks?]
- **Launch Target:** [Specific date or "ASAP"]

### Milestones

**Week 1-2:**
- [Key deliverables]

**Week 3-4:**
- [Key deliverables]

**Week 5-6:**
- [Key deliverables]

**Week 7-8:**
- [Key deliverables]

**Example:**
```
Total Time to MVP: 8 weeks
Launch Target: End of Q1 2025

Week 1-2: Auth + basic task CRUD
Week 3-4: Kanban board with drag-and-drop
Week 5-6: Time tracking + team features
Week 7-8: Analytics dashboard + polish
```

---

## Constraints & Assumptions

### Budget Constraints
- [Are you bootstrapped? VC-funded? What's your monthly budget?]

**Example:**
```
- Bootstrapped, $500/month budget for infrastructure
- Using free tiers for Supabase, Vercel, Sentry
```

### Team Constraints
- [How many people? Solo founder? Small team?]
- [What skills do you have? What do you need to learn?]

**Example:**
```
- Solo founder (technical, full-stack)
- Strong in React, learning Supabase
- No designer (using Tailwind UI components)
```

### Technical Constraints
- [Any limitations? e.g., "Must integrate with existing API", "Must support IE11"]

**Example:**
```
- Must integrate with GitHub API (show commits alongside tasks)
- Must work on mobile web (no native apps for MVP)
```

### Assumptions
- [What are you assuming to be true?]

**Example:**
```
- Users have basic familiarity with Kanban boards
- Teams are 5-50 people (not optimizing for enterprise scale)
- Users prefer async communication over real-time chat
```

---

## Out of Scope (For MVP)

[What are you explicitly NOT building in MVP?]

**Example:**
```
- ❌ Native mobile apps (web only)
- ❌ Video/voice chat (Zoom integration instead)
- ❌ Advanced reporting (basic analytics only)
- ❌ Integrations beyond GitHub (Jira, Slack, etc. post-MVP)
- ❌ White-labeling or enterprise features
```

---

## Design & UX Requirements

### Design Inspiration
[Any apps/websites you want to emulate?]

**Example:**
```
- Linear (clean, keyboard-first UX)
- Notion (flexible, intuitive drag-and-drop)
- Figma (collaborative, real-time)
```

### Branding
- **Colors:** [Primary colors, or "TBD"]
- **Typography:** [Font choices, or "TBD"]
- **Tone:** [Professional? Playful? Minimal? Bold?]

**Example:**
```
- Colors: Deep blue (#1E40AF), white, gray scale
- Typography: Inter for UI, SF Mono for code
- Tone: Professional but approachable (like Linear)
```

### Accessibility
- [Any specific accessibility requirements?]

**Example:**
```
- Keyboard navigation for power users
- WCAG 2.1 AA compliance (contrast, screen readers)
- Mobile touch targets 44x44px minimum
```

---

## Risks & Mitigation

### Technical Risks
- **Risk:** [What could go wrong technically?]
- **Mitigation:** [How will you address it?]

**Example:**
```
- Risk: Real-time updates might be slow with many users
- Mitigation: Use Supabase's optimized real-time subscriptions, add pagination
```

### Market Risks
- **Risk:** [What could go wrong in the market?]
- **Mitigation:** [How will you address it?]

**Example:**
```
- Risk: Users might not switch from Jira (network effects)
- Mitigation: Target small teams (5-20) who find Jira overkill, focus on speed
```

### Product Risks
- **Risk:** [What could go wrong with the product?]
- **Mitigation:** [How will you address it?]

**Example:**
```
- Risk: Core features might not be compelling enough
- Mitigation: Beta test with 10 teams, iterate based on feedback before launch
```

---

## Additional Context

### Competitive Landscape
[Who are your competitors? What do they do well? What do they do poorly?]

**Example:**
```
- Jira: Powerful but overkill for small teams, slow and complex
- Trello: Simple but lacks time tracking and reporting
- Linear: Great UX but expensive for small teams ($8/user/month)
- Asana: Strong for project management, weak for engineering workflows
```

### Why Now?
[Why is this the right time to build this?]

**Example:**
```
- Remote work is permanent (60% of companies now remote-first)
- Engineers expect better tools (raised expectations from Linear, Notion, Figma)
- Supabase makes it possible to build real-time apps fast (competitive moat)
```

### Unique Insight
[What do you know that others don't?]

**Example:**
```
Engineers hate daily standups but love async updates. Most tools force synchronous
communication. By making async the default, we eliminate 30 minutes of meetings/day.
```

---

## Appendix (Optional)

### Wireframes/Mockups
[Link to Figma, sketches, or images]

### User Research
[Link to user interviews, surveys, or feedback]

### Technical Specs
[Link to architecture diagrams, API docs, or database schemas]

---

## Next Steps

Once you've filled out this PRD:

1. Open Claude Code
2. Copy the prompt from [`SETUP_PROMPT.md`](./SETUP_PROMPT.md)
3. Paste this PRD into the prompt
4. Claude Code will generate a customized `CLAUDE.md` for your project

**Let's ship! 🚀**
