# Priorities

## Things we prioritise

### No rabbit holes!
**This is the number one Pixie Labs engineering rule.** Never fall down a rabbit
hole. Timebox difficult problems and reach out to a fellow team member for help
if you're stuck.

### Code quality
The quality of your code is more important than the speed you write it. We
should be proud of the work we do, the way we solve problems, and the code we
write. If we’re not proud of it, it might need refactoring.

### Erosion resistance
We look after a lot of apps and systems, being used by thousands of people every
day. We do not have the resources to actively monitor and maintain all these at
once, nor are we paid to do so.

Instead, we optimise for erosion resistance. This means writing code and
deploying infrastructure that, once let loose, will continue to run indefinitely
with little or no interaction from us.

We do this by:

- Using Heroku. They share our priorities.
- Using the latest versions of libraries.
- Keeping dependencies up to date when we can.
- Automating tasks.

### Fast, continuous(-ish) deployment
If deploying requires a set of instructions, the deployment process might be too
complicated. We deploy frequently, and every developer should be able to do it.
This helps us avoid bottlenecks and keep our clients happy.

We should be deploying continuously too. Both to staging / QA environments _and_
production. We should separate developer process from business process e.g.
a release of a new feature for a client should not be blocked by a developer
managing a deploy. Instead, use feature flags for features that can't be released
whenever we want.

Feature flags can be difficult to architect around complex functionality e.g.
big refactors, overhauls, or data migrations. This is a bit of an amber flag
that we might not be breaking down our work correctly, but if we're confident
it's the right approach it's OK to sacrifice feature flags in these cases for
the sake of pace. Ultimately we should use feature flags to _speed us up_,
not slow us down.

### Identifying issues before our clients
If we discover something is wrong primarily from a client emailing us, we have
failed. We should already be aware of, or investigating, an issue before our
clients contact us to say they’ve spotted something is up. See our guides on
[Support Processes](../05-ongoing-support/02-support-processes.md) and
[Alerts](../05-ongoing-support/04-alerts.md).

## Things we can sacrifice

### Documentation
Beyond code comments, we follow the agile methodology. Functional software over
comprehensive documentation.

### Test coverage
Tests are important. Write good tests for core user journeys, cover some edge
cases, and move on. Don’t chase 100% code coverage.
