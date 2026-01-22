# Support processes

## Critical support

We manage critical support with the following tools and processes:

- **A suite of monitoring tools and alerts** so we're promptly informed when 
  something goes wrong. More details can be found in our guide on 
  [Alerts](/05-ongoing-support/04-alerts.md).
- **A weekday rota** ensuring there's always someone orchestrating incident 
  responses using our ClickUp board.
- **Runbooks** providing guidelines on how to handle common issues.
- **Incident post-mortem** to analyse and learn from major incidents to prevent 
  future occurrences.

Abigail’s blog post on
[being a developer on support](https://blog.pixielabs.io/help-im-a-developer-on-support-8ad0528acfc6)
provides insight into how we balance support with regular coding.

### A weekday rota

Being on the rota for the day entails responsibilities such as:

- Responding or delegating responses to alarms during office hours.
- Tracking ongoing incidents and software support requests on ClickUp.
- Keeping clients and other stakeholders informed about issues affecting them or 
  their customers, and maintaining communication as we work to resolve the issue.
- Investigating and attempting to resolve the issue yourself or coordinating with 
  the right people to handle it when needed.
- Being the first respondent to client emails.

Keep in mind:

- Always acknowledge receipt of an issue to the clients.
- If you need help, ask another engineer.
- Ensure a proper handover if a support issue spans multiple days.
- Assign issues to only one engineer at a time, and ensure they have the capacity 
  to take it on before doing so.

The rota is managed by setting it as our General Slack channel topic.

### Runbooks

Runbooks outline the common procedures for resolving issues related to alarms 
and other incidents. There should be one for each major client or client project. 
They’re available for editing whenever necessary.

### Incident post-mortem

Significant incidents and issues should be followed up with a post-mortem. The 
format can range from a short chat to a full meeting, but should loosely address:

- What happened?
- What went well?
- What didn’t go well?
- Action items (e.g., add tasks to backlog)

## Consulting

When a client contacts us with an issue, the person on the weekday rota is 
responsible for coordinating a response, which should include:

- **An initial response** reassuring our clients that we're aware of the issue.
- **Prioritisation and assignment** ensuring the right person is attending to the 
  issue promptly.
- **Avoid deploying any code.**

### An initial response

The person on rota should respond to the client before starting to prioritise 
and assign the issue. This initial contact should reassure the client without 
promising a resolution timeframe.

### Prioritisation and assignment

Support requests vary in importance. The person on rota is responsible for 
determining the urgency of a request with the help of the rest of the team. Once 
the support request is assigned, the work of the person on rota is completed 
(unless they assign it to themselves!).

### Avoid deploying any code

Our team prioritises erosion resistance, which means we generally don't fix bugs 
outside of sprints. Bugs are always waiting to be found and software is never 
perfect. If we're 'in sprint' with a client, bugs should still be logged and 
scheduled along with the rest of the backlog.

If a bug severely impacts all customers, it should be handled as a critical 
support issue and would have likely triggered an alarm.
