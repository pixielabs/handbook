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

### Fast deployment
If deploying requires a set of instructions, the deployment process might be too
complicated. We deploy frequently, and every developer should be able to do it.
This helps us avoid bottlenecks and keep our clients happy.

### Identifying issues before our clients
If we discover something is wrong primarily from a client emailing us, we have
failed. We should already be aware of, or investigating, an issue before our
clients contact us to say they’ve spotted something is up. See our guides on
[Support Processes](../ongoing-support/support-processes.md) and
[Alerts](../ongoing-support/alerts.md).

## Things we can sacrifice

### Documentation
Beyond code comments, we follow the agile methodology. Functional software over
comprehensive documentation.

### Test coverage
Tests are important. Write good tests for core user journeys, cover some edge
cases, and move on. Don’t chase 100% code coverage.
