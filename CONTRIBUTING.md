# Contributing to Claude Kickstart

First off, thanks for taking the time to contribute! 🎉

The following is a set of guidelines for contributing to Claude Kickstart. These are mostly guidelines, not rules. Use your best judgment, and feel free to propose changes to this document in a pull request.

## How Can I Contribute?

### 🐛 Reporting Bugs

Before creating bug reports, please check the [issue list](https://github.com/johnellison/claude-kickstart/issues) as you might find out that you don't need to create one. When you are creating a bug report, please include as many details as possible:

* **Use a clear and descriptive title**
* **Describe the exact steps which reproduce the problem**
* **Provide specific examples to demonstrate the steps**
* **Describe the behavior you observed after following the steps**
* **Explain which behavior you expected to see instead and why**
* **Include screenshots if relevant**

### 💡 Suggesting Enhancements

Enhancement suggestions are tracked as [GitHub issues](https://github.com/johnellison/claude-kickstart/issues). When creating an enhancement suggestion, please include:

* **Use a clear and descriptive title**
* **Provide a step-by-step description of the suggested enhancement**
* **Provide specific examples to demonstrate the steps**
* **Describe the current behavior** and **explain which behavior you expected to see instead**
* **Explain why this enhancement would be useful** to most Claude Kickstart users

### 📝 Pull Requests

* Fill in [the required template](PULL_REQUEST_TEMPLATE.md)
* Do not include issue numbers in the PR title
* Follow the [style guide](#style-guide)
* Document new code based on the [Documentation Styleguide](#documentation-styleguide)
* End all files with a newline

## Style Guide

### Git Commit Messages

* Use the present tense ("Add feature" not "Added feature")
* Use the imperative mood ("Move cursor to..." not "Moves cursor to...")
* Limit the first line to 72 characters or less
* Reference issues and pull requests liberally after the first line
* Use conventional commits format:
  * `feat:` for new features
  * `fix:` for bug fixes
  * `docs:` for documentation changes
  * `chore:` for maintenance tasks
  * `refactor:` for code refactoring

Example:
```
feat: add PRD template for e-commerce projects

- Add example PRD for online store
- Include payment integration considerations
- Add inventory management features

Closes #42
```

### Markdown Style Guide

* Use [GitHub Flavored Markdown](https://guides.github.com/features/mastering-markdown/)
* Use `**bold**` for emphasis, not `__underscores__`
* Use `-` for unordered lists, not `*`
* Use code blocks with language specification: ` ```typescript `
* Keep line length to 100 characters or less (for readability in diffs)

### Documentation Styleguide

* Use [Markdown](https://daringfireball.net/projects/markdown/) for documentation
* Reference code with inline \`code\` blocks
* Provide context and examples for complex concepts
* Keep it beginner-friendly (target audience: vibe coders)

## What to Contribute

### High-Impact Contributions

We'd especially love contributions in these areas:

#### 1. **PRD Templates for Different Domains**
- E-commerce (Shopify alternative, marketplace, etc.)
- Social apps (Twitter clone, Instagram clone, etc.)
- Developer tools (CLI, API, SDK, etc.)
- Content platforms (Blog, CMS, video platform, etc.)
- Fintech (payment processor, budgeting app, etc.)

**How to contribute:**
1. Create `PRD_TEMPLATE_[DOMAIN].md` (e.g., `PRD_TEMPLATE_ECOMMERCE.md`)
2. Fill in domain-specific examples
3. Highlight unique technical considerations
4. Submit a PR

#### 2. **Framework-Specific Templates**
- Astro (content-focused sites)
- Remix (full-stack web apps)
- Qwik (resumable apps)
- SvelteKit (Svelte with SSR)
- Angular (enterprise apps)

**How to contribute:**
1. Create `CLAUDE_TEMPLATE_[FRAMEWORK].md` (e.g., `CLAUDE_TEMPLATE_REMIX.md`)
2. Adapt conventions, file structure, and commands for that framework
3. Add framework-specific gotchas and best practices
4. Submit a PR

#### 3. **Real-World Examples**
Share your `CLAUDE.md` from actual projects!

**How to contribute:**
1. Create `examples/[YOUR_PROJECT_TYPE]/` directory
2. Add your anonymized `CLAUDE.md`
3. Add a `README.md` explaining the project type and tech stack
4. Submit a PR

**Example structure:**
```
examples/
├── saas-react-supabase/
│   ├── CLAUDE.md
│   └── README.md (explains the project)
├── chrome-extension-vue/
│   ├── CLAUDE.md
│   └── README.md
└── nextjs-ecommerce/
    ├── CLAUDE.md
    └── README.md
```

#### 4. **Advanced Patterns**
- Animation implementation patterns (like the timer ticks example)
- Complex state management patterns
- Performance optimization rules
- Accessibility standards
- Mobile-first responsive patterns

**How to contribute:**
1. Add to relevant template sections
2. Use the "❌ Wrong / ✅ Correct" pattern
3. Provide code examples
4. Explain WHY (not just how)
5. Submit a PR

#### 5. **Translations**
Help non-English speakers access these templates!

**How to contribute:**
1. Create `translations/[LANGUAGE]/` directory
2. Translate all markdown files
3. Keep code examples in English (universally understood)
4. Submit a PR

**Supported languages:**
- Spanish (`es`)
- French (`fr`)
- German (`de`)
- Japanese (`ja`)
- Chinese (`zh`)
- Portuguese (`pt`)
- Korean (`ko`)

### Low-Effort, High-Impact Contributions

Not ready for a big PR? These small contributions are super valuable:

- **Fix typos** - Every PR counts!
- **Improve examples** - Make them clearer or more realistic
- **Add links** - Reference helpful resources
- **Report issues** - Found a problem? Let us know
- **Star the repo** - Helps with discoverability ⭐

## Code of Conduct

### Our Pledge

We as members, contributors, and leaders pledge to make participation in our community a harassment-free experience for everyone, regardless of age, body size, visible or invisible disability, ethnicity, sex characteristics, gender identity and expression, level of experience, education, socio-economic status, nationality, personal appearance, race, religion, or sexual identity and orientation.

### Our Standards

**Positive behavior includes:**
* Using welcoming and inclusive language
* Being respectful of differing viewpoints and experiences
* Gracefully accepting constructive criticism
* Focusing on what is best for the community
* Showing empathy towards other community members

**Unacceptable behavior includes:**
* Trolling, insulting/derogatory comments, and personal or political attacks
* Public or private harassment
* Publishing others' private information without explicit permission
* Other conduct which could reasonably be considered inappropriate

## Questions?

Feel free to open an issue with the `question` label, or reach out to:

* **X/Twitter:** [@iamjohnellison](https://twitter.com/iamjohnellison)
* **Email:** [Your email if you want to share it]

---

**Thank you for contributing! 🚀**

Together, we're helping vibe coders ship faster and build better.
