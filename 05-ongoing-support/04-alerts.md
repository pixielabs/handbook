# Alerts

Alerts should:

- Be noise-free. If an alarm occurs, action is needed. 
- Be visible. If a client site is down, it should go to Slack. Other alerts
  should go to the support inbox.
- Be actionable. If an alarm requires no action, the alarm needs to be fixed.
  If an alarm has an ambiguous action, it needs to be better, or needs a better
  runbook entry.

It doesn’t matter what service you use to achieve this, but we tend to use:

- [AWS Cloudwatch](https://aws.amazon.com/cloudwatch/)
- [Rollbar](https://rollbar.com)
- [UptimeRobot](https://uptimerobot.com/)
- [Scout](https://scoutapm.com/)
- [Librato](https://www.librato.com/)
- [DataDog](https://www.datadoghq.com/) (to collate all the above)
