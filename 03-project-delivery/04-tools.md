# Tools for development

## GitHub
Use GitHub for all code, whether public, private or for a client.

## Trello
We use [Trello](https://trello.com) for all kinds of lists. Some projects are
managed on Trello, but mostly it’s for blog post ideas,
[Friday Kicks](../01-working-at-pixie-labs/03-friday-kicks.md) ideas, and general
housekeeping tasks.

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
