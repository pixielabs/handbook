# Writing tickets

Writing good tickets is _essential_ in the software development process and it
is up to everyone, not just the product manager or product owner, to hone their
skills distilling work into a well written and comprehensive ticket.

## Components of a ticket

We think that a good ticket has the following:

1. Title
2. Description
3. Assumptions
4. Implementation notes
5. Out of scope / not for now
6. Acceptance Criteria (ACs)
7. Tasks
8. Estimates
9. Supplemental material

### Title

The title should summarise the ticket in a few words. It should scan easily in
a long list. It shouldn't be written in user story style ('As a x I want
to y so that I can z') because that's hard to scan. Save that for the
description.

### Description

### Assumptions

We detail any and all assumptions we can think of in the ticket. Assumptions
are things we believe to be true about the ticket before we start work on it.
Making and recording assumptions is important because they're the only way we
can estimate a large amount of work in a reasonable amount of time (otherwise
we would have to do so much up-front work to test every aspect of a ticket
before starting it). Recording assumptions is important because it helps us
understand our estimate and if a ticket goes off-track they help us understand
why that might've happened.

### Implementation notes

When we're writing up tickets it's often after coming up with some idea of how
we are going to get it done. Implementation notes cover that. Larger pieces of
work may have had more upfront thinking in an RFC, so the ticket might just
link to that instead.

### Out of scope / not for now

Equally as important as listing what _is_ in scope, is what is specifically
out of scope or not for now.

### Acceptance criteria

ACs are important, they are the tool we use to judge if the work delivered
for a ticket is good enough to pass.

### Tasks

Tasks are especially important for larger tickets. You can think of the list of
tasks on a ticket like a todo list. To help work out how big or small a task
should be, think about it like this: As a software engineer, you should be
completing multiple tasks within a day.

### Estimates

Small tickets might have an overall estimate, but most tickets (especially ones
with tasks) should have estimates on the tasks themselves. See [Estimating a
project](/02-project-management/01-estimating.md) for more detail on how we
estimate.

### Supplemental material

It's really helpful if a ticket is a portal to everything you need to get that
ticket from started to completed. So it's good to include any supplemental
material like links to Miro boards, Figma designs, spreadsheets, RFCs, that
kind of thing.
