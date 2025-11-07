# Claude Code Setup Prompt - Generate Your CLAUDE.md

Copy and paste this entire prompt to Claude Code at the start of your project, along with your PRD.

---

## PROMPT START

I'm starting a new project and need help creating a customized `CLAUDE.md` file for Claude Code based on my Product Requirements Document (PRD).

**Templates available:**
https://gist.github.com/johnellison/b5892475f65ac0556c585e172f39e9f6

Please:

1. **Review my PRD** (attached below) and identify:
   - Project type and core features
   - Tech stack (or recommend one if not specified)
   - Target platforms
   - Key architectural decisions
   - Critical user flows
   - MVP timeline and constraints

2. **Fetch the templates** from the gist above:
   - Use `CLAUDE_TEMPLATE.md` as the base (or `CLAUDE_TEMPLATE_MINIMAL.md` if this is a simple project)
   - Use `MVP_CONSTRAINTS.md` for the testing strategy
   - Reference `CUSTOMIZATION_GUIDE.md` for best practices

3. **Generate a customized CLAUDE.md** by:
   - Replacing ALL `[PLACEHOLDER]` text with actual values from my PRD
   - Filling in tech stack sections with appropriate choices for my project type
   - Defining 3-5 critical test paths based on my core features
   - Creating component reusability rules for my design system
   - Adding project-specific sections for major features (e.g., payments, real-time sync, file uploads)
   - Removing sections that don't apply to my project
   - Keeping the Production Auditing Standards and Animation Patterns sections (if applicable)

4. **Recommendations:**
   - Suggest a tech stack if I haven't specified one (explain your reasoning)
   - Identify which features should have dedicated subsystem sections
   - Recommend file naming conventions based on my chosen framework
   - Suggest state management strategy based on app complexity

5. **Output:**
   - A complete, ready-to-use `CLAUDE.md` file
   - A brief explanation of key decisions you made
   - A checklist of items I should review/customize further

---

## My PRD:

[PASTE YOUR PRD HERE]

---

If my PRD is incomplete or vague, please ask me clarifying questions before generating the CLAUDE.md.

## PROMPT END

---

# How to Use This Prompt

## Step 1: Prepare Your PRD

Your PRD should include:
- **What the app does** (1-2 paragraphs)
- **Target users** (who is this for?)
- **Core features** (5-10 bullet points of main functionality)
- **Tech preferences** (if any: "I want to use React", "Must work on mobile", etc.)
- **Timeline** (MVP in 4 weeks? 12 weeks? No rush?)
- **Monetization** (free, paid, freemium, etc.)

**Example PRD:**
```
Project: TaskMaster Pro

Description:
TaskMaster Pro is a collaborative task management app for remote engineering teams.
It combines Kanban boards, time tracking, and async standup reports in one interface.

Target Users:
- Remote engineering teams (5-50 people)
- Engineering managers tracking sprint progress
- Individual contributors who hate context switching

Core Features:
1. Kanban boards with drag-and-drop
2. Time tracking per task
3. Daily standup async reports
4. GitHub integration (auto-create tasks from issues)
5. Slack notifications
6. Team analytics dashboard
7. Mobile app (view-only for MVP)

Tech Preferences:
- Must be real-time (collaborative editing)
- Mobile web must work well
- Need good TypeScript support

Timeline:
- MVP in 8 weeks
- Pre-PMF, need to ship fast and iterate

Monetization:
- Freemium: Free for teams < 5, $10/user/month after
```

## Step 2: Copy the Prompt

1. Copy the entire prompt from "PROMPT START" to "PROMPT END"
2. Paste it into Claude Code
3. Replace `[PASTE YOUR PRD HERE]` with your actual PRD
4. Send it to Claude Code

## Step 3: Review the Output

Claude Code will generate a customized `CLAUDE.md`. Review:

- [ ] All placeholders are filled in with real values
- [ ] Tech stack matches your needs (or accept Claude's recommendations)
- [ ] Critical test paths cover your revenue/core functionality
- [ ] Component reusability rules match your design system
- [ ] File naming conventions match your framework choice
- [ ] Sections you don't need are removed
- [ ] Project-specific subsystems (payments, real-time, etc.) have dedicated sections

## Step 4: Iterate

If something doesn't look right, just ask Claude Code:

```
"Can you recommend a different state management solution?
This app will have a lot of collaborative real-time features."
```

```
"Add a section for the Stripe payment integration with
code locations and critical rules."
```

```
"This seems too complex for my simple app. Can you use
the minimal template instead?"
```

## Step 5: Save and Commit

Once you're happy with it:

```bash
# Save the generated CLAUDE.md to your project root
# (Claude Code will offer to do this for you)

git add CLAUDE.md
git commit -m "feat: add Claude Code instructions"
git push
```

Now every conversation with Claude Code will follow your customized rules!

---

## Troubleshooting

**"Claude couldn't fetch the gist"**
- Copy the template content directly from the gist and paste it into the chat
- Or download the files and attach them to your message

**"The output has too many sections I don't need"**
- Ask Claude: "Simplify this by removing advanced sections. I just need the core standards."
- Or use `CLAUDE_TEMPLATE_MINIMAL.md` as the base

**"My PRD is just a vague idea"**
- That's OK! Describe your idea in a few sentences
- Claude will ask clarifying questions to help you flesh it out
- The CLAUDE.md can grow as your project evolves

**"I want to share this with my team"**
- Add a "Team Workflow" section explaining how contributors should use Claude Code
- Include onboarding instructions
- Consider adding this to your project's main README.md

---

## Example Projects by Type

**SaaS Web App (React + Supabase):**
- Uses: Full template
- Key sections: Component reusability, testing strategy, type system
- Subsystems: Auth, payments, real-time sync

**Chrome Extension:**
- Uses: Full template with extension-specific modifications
- Key sections: Extension architecture, messaging patterns, storage
- Subsystems: Background worker, content scripts, popup UI

**Component Library:**
- Uses: Full template with library-specific modifications
- Key sections: Build modes, export patterns, Storybook integration
- Subsystems: Design tokens, theme system

**Simple Landing Page:**
- Uses: Minimal template
- Key sections: Tech stack, styling, deployment
- Subsystems: None

**Mobile App (React Native):**
- Uses: Full template with mobile modifications
- Key sections: Responsive design, native modules, offline sync
- Subsystems: Push notifications, camera/media, storage

---

**Questions?** Check the [Customization Guide](https://gist.github.com/johnellison/b5892475f65ac0556c585e172f39e9f6) or ask Claude Code!
