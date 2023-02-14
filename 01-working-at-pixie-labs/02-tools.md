# Tools for teamwork

## Sprinting
We use [ClickUp](https://app.clickup.com/)).

**We follow this story lifecycle on ClickUp:**

| State            | Description                                                                             |
|------------------|-----------------------------------------------------------------------------------------|
| New              | Ticket template created with a brief explanation of the value being provided.           |
| Spec Added       | Description, ACs, scope and designs have been confirmed and documented.                 |
| Subtasks Added   | The work has been broken down into subtasks.                                            |
| Estimated        | Subtasks have been estimated and PR Review time has been added.                         |
| Ready To Start   | Necessary details added, the work is ready to be picked up.                             |
| In Progress      | Someone has taken this and started work on it.                                          |
| Ready For Review | PR has been crated and is ready for code review.                                        |
| Ready For QA     | The work has been internally reviewed and is ready for the client to review in staging. |
| Passed           | The work has been checked by the product owner.                                         |
| Ready For Deploy | The is ready to be rolled out to production.                                            |
| Done             | The work has been successfully rolled out to production.                                |


For some projects it may be necessary to merge PRs to master before they have
been accepted by the product owner (e.g. if the product owner is not regularly
reviewing progress during the sprint).

## Sharing passwords / secrets
Share credentials in the business [1Password vault](https://1password.com/). Do
not use any communication tool. Encourage our clients to do the same.

If clients must share a credential with you via a communication tool, encourage
phone calls, in person, or (as a last resort) WhatsApp.

If a client shares a password with you via email, politely encourage them to
change it.

## Storing files
Use Google Drive for documents (e.g. spreadsheets, word documents,
presentations).

It's really painful managing anything other than documents in Google Drive,
e.g. assets, large files such as videos. It's also painful managing anything
that Google Drive can't open such as Figma or Sketch files. So in these
situations, use Dropbox. Encourage clients to use Dropbox to share these
kinds of files. Set up a shared Dropbox folder for them if necessary.

## Tracking time
Use [Harvest](https://www.getharvest.com) to track your time against subtasks 
directly from ClickUp. We track our time so we know we are balancing our client
projects correctly. Use[Forecast](https://forecastapp.com/) to see what projects
you arebooked on in the coming days and weeks. This allows you to effectively
manage your time between projects.

## Communicating
We use [Slack](https://slack.com/) for day-to-day communication and
[Front](https://frontapp.com/) for emails. Front is a key part of how we
support our clients, as it enables us to efficiently handle support queries via
a shared inbox. See our guide on [Support
processes](../04-ongoing-support/02-support-processes.md).

### Video and voice calls
We're big believers in avoiding email ping-pong, and instant messaging via 
Slack is great but it can be a big distraction. So much communication nuance
(e.g. speech inflection, body language) is lost in text communication. So we
don't hesitate to jump on a call with each other, clients, or partners.

Generally speaking we use two tools for two different types of calls:

 - We use [Zoom](https://zoom.us) for formal calls e.g. team meetings or
   conversations with external people (e.g. clients, partners).

 - We use [Slack Huddles](https://slack.com/intl/en-gb/help/articles/4402059015315-Use-huddles-in-Slack)
   for quick, informal discussions amongst ourselves e.g. helping with a
   problem or getting clarity on something.

An IRL comparison is as follows: Use Zoom for anything you'd book a meeting
room for, Slack Huddles for a conversation you'd have at someone's desk, or
if you were taking a walk together.

We've evaluated [Tandem](https://tandem.chat/) instead of Slack Huddles but
found it was a bit buggy, we didn't really like the UX, and a third tool felt
overkill for what it provided, especially once Slack launched Huddles.

We're keeping an eye on apps like [Tuple](https://tuple.app/) to help us
with technical calls e.g. pair programming. Neither Slack, nor Zoom, provide 
the best experience for this in our opinion, but we don't have a better 
alternative just yet.
