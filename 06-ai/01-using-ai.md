# Using AI

## Our philosophy

As an engineer at Pixie Labs, you are expected to use AI as part of your daily
workflows.

### Drive it

We embrace automation. We use AI to eliminate toil and move faster. It works
quickly, knows syntax perfectly, and never gets tired. However, it lacks deep
context about Pixie Labs and is occasionally confidently wrong. Always give
clear direction.

### Own it

We use AI to accelerate, not circumvent. We never ship code we don't understand
or haven't reviewed. If you cannot explain how the code works, you cannot merge
it. "AI wrote it" is never a valid root cause.

### Improve it

AI has no long-term memory. It forgets what you told it yesterday. If you keep
repeating yourself, don't just fix the code in silence. Update the project's
CLAUDE.md file or create a shared Skill. If it isn't written down, the AI
doesn't know it.

More importantly, build systems that improve AI effectiveness through back
pressure (see below). The better your feedback mechanisms, the more you can
delegate.

## When to use AI

Use AI to offload the busywork. Let it handle boilerplate and syntax so you can
focus on logic and design.

**Drafting.** Jump straight to the refinement phase. Scaffold new components,
generate initial test suites, and implement standard CRUD operations. Build the
foundation quickly so you can devote energy to the meaningful logic.

**Refactoring.** Automate mechanical edits. Apply consistent patterns, renames,
or formatting changes across the entire codebase. If a task is repetitive, let
the machine handle it to ensure consistency and speed.

**Unblocking.** Decipher complexity with ease. Trace logic across files,
explain dense functions line-by-line, or identify why a specific edge case is
failing. This aligns with our "no rabbit holes" rule—use AI to get unstuck
faster.

**Micro-inefficiencies.** This is where we shine. Use your engineering brain to
identify small, recurring frustrations in your daily work or your clients'
workflows. Then use AI to solve them. Examples:

- Repetitive data transformations that happen manually
- Missing CLI tools that would speed up common tasks
- Small scripts to automate ticket updates or deployment checks
- Quick prototypes to validate ideas before committing to full builds

The compound effect of eliminating dozens of small inefficiencies is massive.
AI makes these optimizations economically viable because the implementation
cost is so low.

## When NOT to use AI

AI mimics patterns; it doesn't understand purpose. Keep these areas under close
human control.

**Business Logic.** Protect domain rules. AI guesses based on variable names;
it doesn't know your client's specific constraints. You may spend more time
correcting it than writing it.

**System Design.** While AI can be an excellent sounding board for exploring
options and generating ideas you might not have considered, final architectural
decisions remain your responsibility. Use AI to think through trade-offs and
propose alternatives, but verify any suggestions against your requirements and
constraints.

**Security & Secrets.** Guard the keys. Authentication, authorization,
cryptography, and PII handling require human oversight from the start. Never
leak secrets to the model.

## AI should never

- Make architectural decisions without human oversight
- Directly modify production data (have it write a script/query instead)
- Commit directly to main or bypass code review
- Handle sensitive credentials or secrets. **Never paste API keys, passwords,
  customer PII, or other sensitive data into prompts.** Treat AI conversations
  as you would any external service.

## Back pressure: The multiplier

Back pressure is automated feedback that helps AI identify and correct mistakes
as it works. This is the most important concept for effective AI usage.

**What it is:** Mechanisms that automatically provide corrective feedback to
the AI without requiring your intervention. Think of it as guard rails that
keep the AI aligned to the task.

**Why it matters:** Back pressure removes you from routine problem-solving.
Instead of manually catching every error, the system provides immediate
corrections. This lets you focus on high-level decisions rather than trivial
issues, dramatically improving your ability to delegate complex work.

**How to implement it:**

- **Enable error visibility.** Encourage Claude Code to run builds, execute
  tests, and read error output. The AI will self-correct based on compiler or
  test failures.
- **Use type systems.** Languages with strong typing (e.g. TypeScript, Rust)
  create natural constraints that prevent invalid code states.
- **Improve error messages.** Good error messages in your codebase train the AI
  better than vague ones. If you're writing error handling, make it detailed
  and actionable.
- **Leverage testing.** Comprehensive test suites provide automatic validation.
  AI can iterate against failing tests without your input.
- **Use linters and formatters.** Tools like RuboCop, ESLint, or Brakeman catch
  issues immediately and guide the AI toward correct patterns.

When you build back pressure into your workflow, AI becomes exponentially more
capable. Prioritize improving back pressure mechanisms—it's one of the
highest-leverage activities you can do.

## Expectations

**Use Claude Code.** We standardize on [Claude
Code](https://www.anthropic.com/claude/code) as our primary AI development
tool. It's an agentic CLI tool that can read files, run commands, and make
edits autonomously.

**Provide context.** AI doesn't know our systems. Provide relevant context on
client conventions, dependencies, and constraints. Use CLAUDE.md files to
document project-specific guidance.

**Watch for scope creep.** AI may "helpfully" refactor adjacent code or add
unrequested features. Review changes carefully against what you asked for. This
aligns with our general philosophy: avoid over-engineering.

**You own the output.** If you commit it, you're responsible for it: bugs,
security issues, everything.

**Understand what you ship.** Don't push or merge code you don't understand. If
AI generates something confusing, ask it to explain or rewrite it.

**Human review required.** All AI-generated code must be reviewed before
merging. First by you, then by the team, as usual.

**Disclose AI assistance.** Let Claude Code automatically add its
`Co-Authored-By` trailer to commits. This helps reviewers know what to look
for.

## Reviewing AI-generated code

Human review is required. Don't hunt for typos; hunt for hallucinations. AI
code is syntactically perfect but often logically flawed.

**Audit the logic.** AI writes plausible code that often solves the wrong
problem. Does the logic actually match the spec? Don't just read it—trace the
execution flow to ensure variables map correctly.

**Cut the slop.** AI loves to over-engineer. Delete unnecessary helper
functions, unused imports, or "helpful" error handling for states that cannot
exist. If it's not strictly needed, it's a liability. This is critical for
erosion resistance.

**Verify safety.** AI assumes inputs are safe. Explicitly check for input
sanitization, null state handling, and ensure no PII is being logged. Run
Brakeman on Rails projects.

**Check for magic values.** Ensure configuration values aren't hard-coded. They
should be in environment variables or Rails encrypted credentials.

## Common pitfalls

AI is a tool, and must be used with care. Keep an eye out for these common
pitfalls.

**Confident hallucinations.** AI says wrong things with confidence. Verify
claims about APIs, versions, and client conventions. Provide context and
documentation.

**Deprecated patterns.** AI suggests outdated dependencies or references old
documentation. It can search the web for the latest, just ask.

**Ignoring existing architecture.** The new code doesn't match existing
patterns—point AI to similar existing code.

**Over-engineering.** AI adds stuff you didn't ask for. Be specific about
scope; review diffs carefully. Tell it to KISS and DRY.

**Plausible but wrong tests.** Tests pass, but don't test the right thing.
Actually read the assertions. Sometimes, AI will even skip the tests to claim
it's "done."

**Falling down rabbit holes.** Just because AI can iterate endlessly doesn't
mean you should let it. If AI is struggling with a problem for more than a few
attempts, stop and reassess. Bring in a human. Our "no rabbit holes" rule
applies to AI workflows too.

## CLAUDE.md files

CLAUDE.md files provide Claude with context for a project. Claude loads the
entire file automatically when you start a session.

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

If you find yourself repeatedly giving Claude basic guidance, add it to the
appropriate CLAUDE.md file. Prefer to add guidance to the project's CLAUDE.md
so the team can benefit!

## Skills

Skills teach Claude how to do specific tasks: PR reviews with our standards,
commit message formats, database queries. They're markdown files that can
include supporting scripts.

CLAUDE.md is always loaded into context. Skills load on demand. Claude reads a
short description of each skill, then only loads the full instructions when
relevant.

Claude uses Skills automatically based on the task.

**Locations:**
- `.claude/skills/` at project root
- `~/.claude/skills/` for personal defaults

## Further reading

- [Don't Waste Your Back Pressure](https://banay.me/dont-waste-your-backpressure/) - Essential reading on automated feedback systems
- [Here's why I switched to Claude Code](https://blog.silennai.com/claude-code) - Practical tips and workflows
