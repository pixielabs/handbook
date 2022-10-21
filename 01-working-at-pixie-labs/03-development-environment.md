# Development environment

We encourage engineers to hone and refine their development environment. In
fact, we think getting your editor _juuust_ how you like it is one of the
criteria for levelling up as a software engineer!

However we do have some stipulations, and some recommendations.

## Stipulations

- Use macOS. Sorry, we just can't fragment our team into multiple operating
  systems, it makes it harder to share knowledge and introduces a wider
  variety of issues.
- Your development environment must conform to our [security
  guidelines](01-security.md).
- Manage packages with [Homebrew](https://brew.sh/).
- Only run databases (PostgreSQL, Clickhouse) as OS services. Don't run Redis
  as a service, run it per project.
- Do not use Docker unless the project has a _specific_ need for it.

## Recommendations

- Use our [mac-setup](https://github.com/pixielabs/mac-setup) repository to
  get everything installed that you're going to need.
- Use [rbenv](https://github.com/rbenv/rbenv) for managing your Ruby versions.
- Use [nvm](https://github.com/nvm-sh/nvm) or
  [fnm](https://github.com/Schniz/fnm) for managing your Node.js versions.
- Use zsh or bash as your shell.
- Install packages with Homebrew.
- Use [iTerm2](https://iterm2.com/) as your terminal.
- Don't use a GUI for Git.

## What about code editor?

Code editors are a very personal preference and you should experiment with
different ones to find out what works best for you. But remember, your editor
(and your customisations of that editor) should work to _speed you up_ not 
slow you down. If you're spending so long faffing with your code editor that
you're getting less work done, you're doing it wrong.

The team use VSCod{e,ium}, Vim, and Sublime Text (in that order of popularity).

We're happy to buy licenses for code editors!