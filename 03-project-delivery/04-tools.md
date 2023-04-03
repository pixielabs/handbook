# Tools for development

## Git

Git is our preferred version control system for managing code changes. We use Git to collaborate on projects, review code, and maintain a revision history of all changes.

### Best practices

To use Git effectively, we follow these best practices:

#### Create a new branch for each feature or bug fix

Create a new branch for each feature or bug fix, and merge it back into the main branch only after testing and review. This helps keep the main branch stable and avoids conflicts with other developers' work.

#### Use descriptive commit messages

We're not super prescriptive on commit message format but if you want to follow a standardised format, you could use the [Commitlint](https://commitlint.js.org/) style, which uses a standardised format for commit messages that includes a type, scope, and subject. For example, a commit message might start with "docs: update README with new information" or "feat: add new feature to user profile page".

#### Regularly push changes to a remote repository

Regularly push changes to GitHub to ensure that your work is backed up and accessible to others on the team. This also helps avoid loss of work due to hardware failure or other issues.

#### Use pull requests for code review and collaboration

Use pull requests for code review and collaboration, especially for significant changes or changes that affect multiple files or modules. This allows other developers to review and provide feedback on the changes before they are merged.

By following these guidelines, we can work together effectively and maintain a high standard of quality for our codebase.

## Strategies for effective Git usage

A good revision history is essential for a project. It's a valuable resource for understanding why the code is the way it is. If you spend time on your commit messages, it can make all the difference for future developers who look back on the project's history.

### Give up on inline commit messages

Try not to be expedient with your commits. The first step to writing a good commit message is to give yourself the space to express your thoughts properly. This means that you should not try to cram your commit mesages into a single line. This will give you sufficient pause for thought to allow you to ask yourself if the commit message is fit for purpose. Adios, `git commit -m "Fix bug"` commits.

### Use Git's patch option to pick out atomic commits

The patch option lets you selectively choose the exact changes in a particular file that you'd like to stage. This is helpful when you want to commit only part of a file's changes.

* Use `git add -p` to interactively stage changes to a file and create atomic commits, making it easier to track changes and simplify the review process.

### Treat local commits as mutable

Until a commit is merged into the main branch, it can be modified or even deleted. Use the amend option to modify the most recent commit or create fix-up commits and squash them down with an auto-squash during a rebase.

* Use git `commit --amend` to edit the message of a specific commit and `commit --amend --no-edit` if you don't need to edit the message.

### Use rebase to restructure commits before pushing

Let's say you have a feature branch ready to push. You check the Git log and see that you have some poorly written commits, a reverted change, and two commits that straddle another that ought to have been committed together. You're in rebase territory.

Use `git rebase -i <commit>` (e.g. `git rebase -i HEAD~5` to rebase the last 5 commits) to interactively rebase the commit history and restructure commits, such as changing commit messages, squashing commits, and reordering commits.
Use the options `pick` to keep a commit as-is, `squash` to combine a commit with the previous commit (up), and `edit` to stop at a specific commit for further changes. You can cut and move lines to re-order the sequence of commits too.
* Don't be afraid to try rebase. You can always use `git rebase --abort` to cancel it if you get unstuck.
* Keep an eye on the helpful feedback from Git on how to use rebase properly.

### Search through revision histories

Use Git's pickaxe option to search through revision histories for any snippet of code across multiple commits and files. Git annotate can also be used to identify the last revision on a particular line.

* Use `git log -S <term>` to search for changes that add or remove a specific term from the codebase.

## GitHub
Use GitHub for all code, whether public, private or for a client.

## Trello
We use [Trello](https://trello.com) for all kinds of lists. Some projects are
managed on Trello, but mostly it’s for blog post ideas, Friday Kicks ideas, and
general housekeeping tasks.

## Pivotal Tracker
[Pivotal Tracker](https://www.pivotaltracker.com/dashboard) is used for projects
requiring a more rigid sprint structure than what can be provided by Trello. It
provides automated analytics around estimates, deadlines, story points, epics
etc.

See 'Sprinting' in our [Tools for teamwork](../01-working-at-pixie-labs/08-tools.md)
guide for more detail on how we use Pivotal Tracker.

We're experimenting with [ClickUp](https://clickup.com) as a replacement for
Pivotal Tracker. We haven't decided for sure if it's our permanent new home,
but it's looking likely.

## Semaphore
We use [Semaphore](https://semaphoreci.com) for continuous
integration. It can also be used for continuous deployment, but usually Heroku
takes care of that.

Semaphore is great because it has straightforward syntax, a good UI, and support
for scaling up available resources. A fast build equals fast development.

Some older projects are still running on GitHub Actions which is OK, but new
projects should use Semaphore where possible.

For projects that would benefit from lots of test parallelism, we use 
[Knapsack Pro](https://knapsackpro.com) to efficient queue up parallel builds.
We've had lots of success combining Semaphore with Knapsack Pro. 

## Codecov
[Codecov](https://codecov.io/) automatically reports code coverage on pull
requests. We aim for 85% code coverage (though this depends on the project).
A PR should not cause code coverage to decrease.

## Dependabot
[Dependabot](https://dependabot.com/) automatically creates PRs for updated
library dependencies. Not only is it good practice, but dependency management is
part of our offering to clients that pay for infrastructure support. Dependabot
helps us do this on multiple projects without having to remember to do it.

Dependabot is now an integral part of GitHub.
[There’s more info here on setting it up.](https://github.blog/2020-06-01-keep-all-your-packages-up-to-date-with-dependabot/)

## Port forwarding tunnels
See [Port forwarding tunnels](https://docs.google.com/document/d/19CqUMPNCDos5R2Efeo2cL9MwjDrNPh73lQ4KQnU5waU/edit)
(this information is not public).
