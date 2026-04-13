# Ticket statuses

We use a standard set of ticket statuses across our projects so that everyone
— clients, designers, engineers, and project managers — can tell at a glance
where a piece of work sits. The statuses are grouped into five categories:
Backlog, Unstarted, Started, Completed, and Cancelled.

## Backlog

| Status    | Meaning                                                                                   |
| --------- | ----------------------------------------------------------------------------------------- |
| Backlog   | Issues not fully formed yet, not ready to start, and not prioritised to start.            |

## Unstarted

| Status          | Meaning                                                                             |
| --------------- | ----------------------------------------------------------------------------------- |
| Spec required   | We want to do this ticket but it's incomplete in some way so can't be picked up yet.|
| Ready to start  | Issues that are ready for someone to pick up.                                       |

## Started

| Status             | Meaning                                                       |
| ------------------ | ------------------------------------------------------------- |
| Blocked external   | Blocked by something out of our hands.                        |
| In progress        | Someone is actively working on the ticket.                    |
| In Code Review     | There's an open PR and someone is due to review it.           |
| Ready for Sign Off | Ready for the client to sign off.                             |
| Ready to merge     | Ready to be merged and/or deployed to production.             |

## Completed

| Status    | Meaning                                                                       |
| --------- | ----------------------------------------------------------------------------- |
| Done      | For non-dev tasks that don't need deploying, but we want to mark as done.     |
| Deployed  | This issue has been deployed to production.                                   |

## Cancelled

| Status    | Meaning                                                   |
| --------- | --------------------------------------------------------- |
| Cancelled | We decided not to do this ticket.                         |
| Duplicate | Another ticket already covers this work.                  |
