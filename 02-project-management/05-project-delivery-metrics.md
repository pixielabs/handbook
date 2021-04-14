# Project delivery metrics

We track three engineering code metrics. These are not used for individual
engineer performance but rather as a health-check for our projects.

## Pull request cycle time

**Target: 80% of pull requests in under 10 working hours**

[Pull request cycle
time](https://codeclimate.com/blog/software-engineering-cycle-time/) is the
most important metric we track. It is the time between the first commit and
merge. A lot has been written about why this is important.

Off-target pull requests should be discussed on a case-by-case basis to
identify areas of improvement. This could include:

 - Breaking down work more.
 - Doing more upfront investigation work before starting to write code.
 - Better communication when code is ready to review.

## Pull request size

**Target: 80% of pull requests in under 200 lines of code**

Not all PRs can be small, but small pull requests are easier to review, which
helps keep the cycle time down. If pull requests are off target we should 
investigate them on a case-by-case basis. Examples of questions you might want
to ask include:

 - Could it have been broken down differently?
 - Are there problematic areas of our code that cause high churn?

## Pull request time to review

**Target: 80% of pull requests reviewed in under 4 working hours**

No PR should be stuck without a review for more than half a day. This de-risks
our work by ensuring we have plenty of time for review cycles, and helps keep
our overall pull request cycle time down.

Off-target pull requests should be investigated. Things that can cause time to
review to be slow include:

 - Did something make them challenging to review?
 - Are the team overloaded? Are there competing priorities?
 - Do we need to tighten up our communication?