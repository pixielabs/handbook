# Reviews

[We also wrote about this on our blog.](https://blog.pixielabs.io/how-we-review-code-ba43462e1e87)

## As a 'reviewee'
- Your code should always be reviewed by someone else before being accepted.
- Generally code you commit should be placed on a branch, rather than committed
  directly to master.
- We don’t have a naming convention for branches. Just call it something
  sensible that describes what it is.
- Aim for smaller branches, rather than larger branches. If you have branches
  depending on each other though, this is a sign you need to get code merged or
  reduce the number of branches.
- Before reviewing, consider self-reviewing using the suggestions below. You 
  might catch some things before your reviewer does, which will reduce the
  time to merge and the number of PR cycles, both metrics we strive to keep
  low to help us move at pace.

## As a 'reviewer'
- Be comfortale in passing the PR on to someone else for a second opinion,
  especially if you’re not confident merging it in. Remove yourself as the
  assignee and add the next person!
- Code reviews can vary depending on the size and scale of the feature/fix.
  Everything from skimming over the diff, to running the tests, to running
  through multiple scenarios by hand.
- Prefer to involve the person at your desk/on a Zoom call, rather than just
  communicating backwards and forwards over pull request comments. But
  ultimately you be the judge!
- Delete the branch after merging the pull request.

## Things to look for in a code review
- Code should be tested. CodeCov should say that the test coverage is increasing
  or staying the same.
- You should be able to understand the code by reading it. If there is something
  that isn’t immediately obvious, does it have a comment above it explaining it?
- Are there comment blocks above new classes or methods?
- Do new variables, methods or classes all have names that you agree with?
  Can you understand what they are from the name? Are there any variables named
  'a, b, c' or '_1, _2'? If so, can they be renamed or refactored?
- If new dependencies have been added, are they justifiable? Are there any
  dependencies that are unused (maybe they were added during development)?
  Is it the latest version of that library?
- Look for hard-coded magic values that should be added to config.
- Rails: Are there any obvious DB performance issues with new SQL/ActiveRecord
  queries?
- Rails: Are all ActiveRecord finders correctly scoped to a parent model where
  necessary? (e.g. `current_user.comments#find` not `Comment#find`)
- Rails: Is there anything committed to the `schema.rb` or `structure.sql` that
  doesn’t look like it belongs in this branch? (Your teammate might be working
  on multiple sets of DB changes)
- Rails: Does brakeman report any new security issues?
- Asset pipeline JavaScript: Have any ES6-isms snuck in e.g. const/let, arrow
  functions? This is OK if the JS is being compiled by Webpacker or similar.

## Review apps
We use Review Apps on Heroku to quickly spin up disposable Heroku apps for pull
requests.

Review apps can be configured to be automatically created for new PRs, or they
can be created manually from the Heroku dashboard.

Heroku will provide you with a link to access the review app from the PR and
from the dashboard and will destroy the app when the PR is closed. You can also
set review apps to automatically destroy themselves if the PR has not been
updated for a configurable number of days.

For applications with a database or some kind of initial set up, we write a
bootstrap task (e.g. a rake task, if it’s a Ruby on Rails application) which we
set up to run automatically using app.json. If the application has complicated
user journeys, this task should also include setting up some predefined test
users at different stages of the journey, for fast QA.

## Pull request templates

We use [pull request templates](https://docs.github.com/en/communities/using-templates-to-encourage-useful-issues-and-pull-requests/creating-a-pull-request-template-for-your-repository)
to help us remember the steps we need to do before and after submitting a PR.

It's very straightforward. PR templates should speed us up, not slow us down.
If they're slowing us down, we need to rethink the format.

Currently, it looks like this:

```markdown
## Changes
**Description of what you did**

## Ticket
**Insert link to Pivotal ticket here**

## Before submitting have you:

- [ ] Included a link to any relevant Pivotal Tracker ticket
- [ ] Included links to Rollbar/Front conversations if this is a support issue

## After submitting remember to:

- [ ] Mark the Pivotal Tracker ticket as ready for review
- [ ] Include the PR on the Pivotal Tracker ticket
- [ ] Assign a single reviewer
- [ ] Give an update on Slack - nudge the reviewer, let everyone know what you're going to do next.
```
