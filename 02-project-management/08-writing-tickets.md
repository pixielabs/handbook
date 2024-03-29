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
7. Designs and UX
8. Tasks
9. Estimates
10. Metrics
11. Supplemental material

### Title

The title should summarise the ticket in a few words. It should scan easily in
a long list. It shouldn't be written in user story style ('As a x I want
to y so that I can z') because that's hard to scan. Save that for the
description.

### Description

To make sure we as a team understand the context of the problem we're fixing, what 
kind of user we're solving it for, and what value solving this problem provides to the customer or business, 
we need a brief description to set the scene for the solution we're providing. This is often 
the first section of a ticket we populate (in addition to the title) to ensure the value being 
delivered from this ticket is easy to understand and clearly documented.

### Assumptions

We detail any and all assumptions we can think of in the ticket. Assumptions
are things we believe to be true about the ticket before we start work on it.
Making and recording assumptions is important because they're the only way we 
can estimate a large amount of work in a reasonable amount of time (otherwise
we would have to do so much up-front work to test every aspect of a ticket
before starting it). Assumptions also help us understand our estimate better and 
if a ticket goes off-track they help us understand why that might've happened.

### Implementation notes

When we're writing up tickets it's often after coming up with some idea of how
we are going to get it done. Implementation notes cover that. Larger pieces of
work may have had more upfront thinking in an RFC, so the ticket might just
link to that instead.

### Out of scope / not for now

Equally as important as listing what _is_ in scope, is what is specifically
out of scope or not for now.

### Acceptance criteria

Acceptance criteria (ACs) are a set of conditions or requirements that must be 
met in order for a ticket to be considered 'Done'. It helps to clearly define 
what is expected and ensures that the feature being delivered aligns with the 
customer’s needs and expectations. Acceptance criteria typically include functional
requirements, performance requirements, and design requirements. They should be specific,
measurable, and verifiable, and should be agreed upon by all members involved in the 
planning and delivering of the ticket.

### Designs and UX

This section should feature a URL to the _finished_ designs, whether it be somewhere like 
Figma or Miro. Some tickets don't need designs (e.g back-end tickets), but in this case we 
should still write something like 'n/a' to make it clear that designs are not applicable.


### Subtasks

Subtasks are especially important for larger tickets. You can think of the list of
subtasks on a ticket like a todo list from a development perspective. To help work 
out how big or small a task should be, think about it like this: As a software engineer, 
you should be completing multiple tasks within a day. Subtasks shouldn't be confused with
ACs however, as ACs are a checklist of the expected functionality, not the steps to 
achieve that functionality unlike subtasks.

### Estimates

Small tickets might have an overall estimate, but most tickets (especially ones
with tasks) should have estimates on the subtasks themselves. See [Estimating a
project](/02-project-management/01-estimating.md) for more detail on how we
estimate.

### Metrics

A ticket should have some idea of how the impact/value it delivers is going to
be measured. So the ticket should cover any new product analytics events
(e.g. MixPanel events) that need to be added, what data they need to include,
when they should be sent. We should also upfront decide what success looks like
once the feature has been delivered, using those metrics.

### Supplemental material

It's really helpful if a ticket is a portal to everything you need to get that
ticket from started to completed. So it's good to include any supplemental
material like links to Miro boards, Figma designs, spreadsheets, RFCs, that
kind of thing.
