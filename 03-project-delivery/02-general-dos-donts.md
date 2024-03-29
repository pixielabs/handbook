# General Dos and Don'ts

## Dos
- Do keep all code, regardless of its size, in a GitHub repository so the whole
  team can access it.
- Do include a README and add code comments.
- Do use Markdown, not Rdoc.
- Do indent code with spaces, two spaces per indentation.
- Do configure your text editor to use LF newlines. This is default on almost
  all text editors on macOS and Linux. On Windows, some text editors are set
  up to use CRLF (also called 'DOS format') newlines.
- Do configure your editor to [add a newline at the end of a file][newline].
  Most editors enable this by default.
- Do prefer one-off rake tasks for maintenance and migration over code in your
  database migrations.
- Do loosely follow [TomDoc](http://tomdoc.org/) for commenting. Combine this
  with comments within methods for particularly tricky bits of code.
- When working in Ruby on Rails, do use
  [Brakeman](https://github.com/presidentbeef/brakeman) to perform static
  analysis for security vulnerabilities.
- Do write recurring tasks as Sidekiq jobs and schedule them using
  sidekiq-cron. This has proven time and again to most reliably cover all the
  weird edge cases.
- Do use [squoosh](https://squoosh.app/) to compress images and pick
  appropriate formats for them.
- Do set `config.time_zone` in new Rails applications to the appropriate time
  zone for the client (e.g., 'Europe/London').
- Do ensure there is centralized logging in place for every new project. As a
  team, we prefer [Papertrail](https://www.papertrail.com/).
- Do ensure there is exception handling set up for every new project. As a
  team, we prefer [Rollbar](https://rollbar.com/), but we like to use
  [Bugsnag](https://www.bugsnag.com/) for projects centered around a React
  Native mobile application.

## Don'ts
- Don't use the Heroku Scheduler; it doesn't guarantee a run, and we've had
  business-critical jobs fail.
- Don't allow `master`/`main` builds to fail. If they do, ideally, everyone
  should stop what they're doing until it's passing again.

[newline]: https://thoughtbot.com/blog/no-newline-at-end-of-file
