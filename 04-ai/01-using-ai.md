# Using AI

Writing code has never been the primary job of a developer—it's solving problems. AI doesn't change this; it just adds another layer of abstraction. Using Claude Code sits in the same evolution as moving from assembly language to higher-level languages: we're delegating the mechanical details to focus on what matters.

## Our philosophy

As an engineer at Pixie Labs, you're expected to use AI as part of your daily workflows. Here's what that means in practice:

- **Embrace automation to move faster.** AI is fast, handles syntax flawlessly, and works without fatigue. However, it lacks deep context about Pixie Labs and is occasionally confidently wrong; always give clear direction.
- **Full ownership required.** We use AI to accelerate, not circumvent. Never merge code you haven't understood and reviewed thoroughly. You must be able to explain every line - "AI generated it" isn't an acceptable excuse. This is especially critical for junior developers: you're accountable for understanding the patterns and decisions in the code, not just that it works.
- **Build better systems.** AI doesn't retain context between sessions. If you keep repeating yourself, don't just fix the code in silence; update the project's CLAUDE.md file or create a shared Skill. More importantly, build systems that improve AI effectiveness through back pressure (see below). The better your feedback mechanisms, the more you can delegate.

## When to use AI

**Drafting.** Skip the grunt work and start refining. Let AI create component scaffolds, initial tests, and basic CRUD operations whilst you focus on the interesting problems.

**Refactoring.** Let AI handle systematic changes across your codebase - pattern application, bulk renames, and formatting updates. Repetitive tasks are perfect AI candidates.

**Unblocking.** Use AI to understand complex code. Ask it to trace execution paths, break down complicated functions, or explain edge case failures. This aligns with our "no rabbit holes" rule; use AI to get unstuck faster.

**Micro-inefficiencies.** This is where we shine. Use your engineering brain to identify small, recurring frustrations in your daily work or your clients' workflows, then use AI to solve them. Examples:

- Repetitive data transformations that happen manually
- Missing CLI tools that would speed up common tasks
- Small scripts to automate ticket updates or deployment checks
- Quick prototypes to validate ideas before committing to full builds

The compound effect of eliminating dozens of small inefficiencies is massive. AI makes these optimisations economically viable because the implementation cost is so low.

## When NOT to use AI

AI recognises patterns but lacks contextual understanding. Maintain human control in these areas.

**Business logic.** Safeguard your domain logic. AI infers from naming conventions but doesn't understand your client's requirements. Manual coding may be faster.

**System design.** Whilst AI can be an excellent sounding board for exploring options and generating ideas you might not have considered, final architectural decisions remain your responsibility. Use AI to think through trade-offs and propose alternatives, but verify any suggestions against your requirements and constraints.

**Security and secrets.** Keep security decisions in human hands. Auth, encryption, and sensitive data handling need careful oversight from the beginning. **Never paste API keys, passwords, customer PII, or other sensitive data into prompts.** Handle AI interactions with the same caution you'd use for any third-party service.

## Back pressure: the multiplier

Back pressure is automated feedback that helps AI self-correct without your intervention. Think of it as guard rails keeping the AI aligned whilst you focus on high-level decisions. This is the most important concept for effective AI usage.

**How to implement it:**

- **Enable error visibility.** Encourage Claude Code to run builds, execute tests, and read error output. The AI will self-correct based on compiler or test failures.
- **Use type systems.** Languages with strong typing (e.g. TypeScript, Rust) create natural constraints that prevent invalid code states.
- **Improve error messages.** Good error messages in your codebase train the AI better than vague ones. If you're writing error handling, make it detailed and actionable.
- **Leverage testing.** Comprehensive test suites provide automatic validation. AI can iterate against failing tests without your input.
- **Use linters and formatters.** Tools like RuboCop, ESLint, or Brakeman catch issues immediately and guide the AI towards correct patterns.

When you build back pressure into your workflow, AI becomes exponentially more capable. Prioritise improving back pressure mechanisms - it's one of the highest-leverage activities you can do.

## Expectations

**Use Claude Code.** We standardise on [Claude Code](https://www.anthropic.com/claude/code) as our primary AI development tool. It's an agentic CLI tool that can read files, run commands, and make edits autonomously.

**Provide context.** AI doesn't know our systems. Provide relevant context on client conventions, dependencies, and constraints. Use CLAUDE.md files to document project-specific guidance.

**Watch for scope creep.** AI often adds unsolicited improvements or refactors nearby code. Carefully verify the changes match your actual request. This aligns with our general philosophy: avoid over-engineering.

**You own the output.** You're accountable for everything you merge - bugs, vulnerabilities, all of it.

**Human review required.** All AI-generated code must be reviewed before merging. First by you, then by the team, as usual.

**Disclose AI assistance.** Let Claude Code automatically add its `Co-Authored-By` trailer to commits. This helps reviewers know what to look for.

## Juniors: learn what you're wielding

AI is harder to use well when you're still building fundamentals. If you're earlier in your career, add these processes:

- **Understand before accepting.** Don't just verify the code works—understand why it works. Ask AI to explain its approach, then verify that explanation against documentation.
- **Build mental models.** When AI generates a solution, trace through it manually. What would break if you changed a variable? Why did it choose this pattern?
- **Cross-reference learning.** If AI introduces a new concept, library, or pattern, spend time reading the official docs. AI gives you the shortcut; make sure you know the long route too.
- **Pair with seniors more often.** Get code reviewed not just for correctness, but for learning. Ask questions about why AI made certain choices.
- **Practice without AI regularly.** Set aside time to solve problems manually. You're building skills that will make your AI usage far more effective later.

The goal isn't to avoid AI—it's to ensure you're learning the fundamentals that make AI a force multiplier rather than a crutch.

## Reviewing AI-generated code

All AI-generated code must follow our standard [code review process](../03-project-delivery/06-reviews.md). In addition to those guidelines, pay special attention to these AI-specific concerns:

Look for logical errors, not typos. AI writes syntactically clean code that may solve the wrong problem.

**Verify correctness.** AI produces convincing solutions that may miss the mark. Verify the logic matches requirements by tracing execution paths and validating variable usage.

**Eliminate over-engineering.** AI loves to add unnecessary complexity. Delete unused helper functions, redundant imports, or "helpful" error handling for states that cannot exist. If it's not strictly needed, it's a liability. This is critical for erosion resistance.

**Check security implications.** AI doesn't validate inputs by default. Explicitly verify input sanitisation, null state handling, and ensure no PII is being logged. Run Brakeman on Rails projects.

**Watch for magic values.** Ensure configuration values aren't hard-coded. They should be in environment variables or Rails encrypted credentials.

## Common pitfalls

Like any powerful tool, AI requires careful use. Watch for these frequent mistakes:

**Confident hallucinations.** AI makes mistakes confidently. Double-check its assertions about APIs, versions, and project conventions. Supply context and docs to improve accuracy.

**Deprecated patterns.** AI suggests outdated dependencies or references old documentation. It can search the web for the latest, just ask.

**Ignoring existing architecture.** The new code doesn't match existing patterns - point AI to similar existing code.

**Plausible but wrong tests.** Passing tests don't guarantee correctness. Review assertions carefully - AI sometimes writes tests that pass without testing anything meaningful, or skips them entirely.

**Falling down rabbit holes.** Just because AI can iterate endlessly doesn't mean you should let it. If AI is struggling with a problem for more than a few attempts, stop and reassess. Bring in a human. Our "no rabbit holes" rule applies to AI workflows too.

## CLAUDE.md files

CLAUDE.md files give Claude project-specific context that's loaded at session start.

**What to include:**
- Common bash commands
- Code style guidelines and conventions
- Testing instructions
- Repository structure overview
- Project-specific warnings or gotchas

**Locations:**
- `./CLAUDE.md` at project root (checked into git, shared with team)
- `./CLAUDE.local.md` for local overrides (git ignored)
- `~/.claude/CLAUDE.md` for personal defaults (applies to all projects)

Repeating the same instructions to Claude? Document them in CLAUDE.md. Use the project file so teammates benefit too.

## Skills

Skills teach Claude how to do specific tasks: PR reviews with our standards, commit message formats, database queries. They're markdown files that can include supporting scripts.

CLAUDE.md loads automatically whilst Skills load only when needed. Claude sees skill summaries first, then fetches full instructions if relevant.

Claude automatically applies Skills when appropriate for the task.

**Locations:**
- `.claude/skills/` at project root
- `~/.claude/skills/` for personal defaults

## Further reading

- [Don't Waste Your Back Pressure](https://banay.me/dont-waste-your-backpressure/) - essential reading on automated feedback systems
- [Here's why I switched to Claude Code](https://blog.silennai.com/claude-code) - practical tips and workflows
