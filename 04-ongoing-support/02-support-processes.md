# Support processes

## Critical support

We cover critical support with the following tools and processes:

- **A suite of monitoring tools and alerts** so we know when something goes
  wrong. See our guide on [Alerts](/04-ongoing-support/04-alerts.md) for more information.
- **A weekday rota** so we know who orchestrates responding to incidents using
  the Trello board (not public). 
- **Runbooks** so we know what to do.
- **Incident post-mortem** so we know how to stop it from happening in the future.

You should also read Abigail’s blog post on
[being a developer on support](https://blog.pixielabs.io/help-im-a-developer-on-support-8ad0528acfc6)
to understand how we juggle this with everyday coding.

### A weekday rota
If you are on the rota for a day your responsibility is to:

- Respond to alarms during office hours (or delegate it to someone, e.g. if
  you're out at lunch!).
- Track ongoing incidents and software support requests on Trello.
- Communicate with clients and other stakeholders when an issue has arisen that
  impacts them or their customers.
- Continue to communicate with clients as we work to resolve the issue.
- Investigate and attempt to resolve the issue yourself, or coordinate the right
  people to resolve the issue where you are unable to.
- Be the first to respond to client emails.

The rota is managed by setting it as our General Slack channel topic.

### Runbooks
A runbook details common ways to resolve alarms and other issues. There should
be one for each major client or client project. They’re freely editable!

### Incident post-mortem
Major incidents and issues should be followed up with a post-mortem. This can be
anything from a five minute chat to a full-on meeting, but should loosely
follow:

- What happened?
- What went well?
- What didn’t go well?
- Action items (e.g. add tasks to backlog)

## Consulting

When a client contacts us with an issue, the person on the weekday rota is
responsible for orchestrating a response. This should include:

- **An initial response** so our clients know we are on the case, and that they can
  relax.
- **Prioritisation and assignment** so the right person can respond, minimising the
  impact on other projects.
- **Not deploying any code.**

### An initial response
The person on rota for the day should respond to the client before beginning to
prioritise and assign the query. This first response should make no guarantee of
a resolution time, it is purely to reassure the client that we have received
their message and are handling it.

### Prioritisation and assignment
Some support questions are more important than others. The client may be just
asking a random question, or they may be in a meeting right now and need
something fixed ASAP. It’s the job of the person on rota to work this out with
the help of the rest of the team.

Once the support question has been assigned to someone, the work of the person
on rota is done (unless they assign it to themselves!).

### Not deploying any code
As a team, we optimise for erosion resistance. This means generally speaking we
do not fix bugs outside of sprints. Software is never done, and bugs are always
waiting to be found. If we are ‘in sprint’ with a client, bugs should still be
logged and scheduled along with the rest of the backlog.

If a bug is so severe that it impacts all customers it should be handled as
critical support issue. It also should’ve been picked up by an alarm!
