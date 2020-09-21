# Testing

## Frontend testing
In a monolithic Ruby on Rails application we test with Rspec, Capybara, and
Chromedriver. For everything else, we use [Cypress](https://www.cypress.io/).

Write a single end-to-end test encompassing the most important customer journey
that doesn’t stub out any calls to APIs. Once you’ve established this is
working, use stubs in tests for additional features and edge cases. There is no
benefit in using/generating real data here.

## General performance testing
Use [rack-mini-profiler](https://github.com/MiniProfiler/rack-mini-profiler) in
development and in production (only for logged in developers) for checking page
load speed.

Use the [bullet gem](https://github.com/flyerhzm/bullet) for checking for N+1
queries in code.

## Load testing
We haven't yet settled on a _de jure_ load testing tool, but we have some
options.

### JMeter
[JMeter](https://jmeter.apache.org/load-testing tools. We’re exploring using
[ruby-jmeter](http://flood-io.github.io/ruby-jmeter/) - a tool for writing load
test plans in Ruby. ruby-meter allows you to define your tests programmatically,
generate test plans and load these in the JMeter GUI to view results.

Crucially, ruby-jmeter allows you to extract variables from the response
(using regex or xpath), for example the CSRF token for submitting data via
Rails forms.

Although you can run and view jmeter test results in the GUI, this is not
recommended other than for debugging purposes. We are currently investigating
ways to best run tests and visualise results.

## Locust
[Locust](https://docs.locust.io/en/stable/index.html) is a user load-testing
tool comparable to JMeter, allowing you to write tests in Python and view
results immediately, in real-time, on their web-based UI.

Unlike JMeter, Locust is events-based and therefore allows you to simulate
thousands of concurrent users on one machine, much more that you could do with
JMeter.

Locust lacks the response extraction capabilities that ruby-jmeter gives you,
which makes it unsuitable for testing expansive web applications in a
feature-testing fashion. For this reason, we would use Locust primarily for load
testing APIs.

## Taurus
[Taurus](https://gettaurus.org/docs/Index/#Taurus-Tool-Documentation) is an
open-source automation framework for running a wide variety of load testing
tools but we have found most success using Taurus to run
[JMeter](https://jmeter.apache.org/usermanual/index.html) and
[Selenium](https://www.seleniumhq.org/docs/) tests.

JMeter is ideal for analysing request speeds, so we use it to test our JSON
APIs. Selenium tests allow us to run a headless browser for each artificial user
and allow us to programatically interact with our web app as a user would.

Taurus tests are written in a yaml file, which can be uploaded to
[Blazemeter](https://www.blazemeter.com/). Blazemeter can run Taurus tests in
the cloud allowing us to put our apps under far more load than we could locally.

## Volume testing
Volume testing is where you test an application’s performance with large volumes
of data. This simulates how an application will perform over time. It’s
particularly relevant for full-stack web applications which have data backed by
a database. Typically we do this by seeding the database with a large amount of
sample data.

This is a very domain-specific problem. Therefore, we set it up on a
project-by-project basis. This typically involves:

1. Loading the database with generated data
2. Running the test suite against this database
3. Verifying if there is any data loss
4. Checking the system’s response time
5. Verifying if the data is stored correctly
6. Checking if the data is overwritten without any notification

[This document](http://www.softwaretesting.no/testing/volumetest.pdf) sets out
some useful guidelines in more detail.

Volume testing will also help you uncover brittleness in your test suite.
For example:

- Do your tests rely on creating stubs for seeded data? Does this need to be
  the case?
- Are you running tests that check attributes on the ‘first’ model instance? Can
  you be more specific about the record you are testing?
- Are your tests reliant on the absolute number of records in the database? Can
  you check whether the number has changed instead?
- Are you running `Model#update_all` as a shortcut somewhere?

Even without a volume testing set up, thinking about how your test suite would
perform against a non-empty database will improve the overall quality and
specificity of your tests.

RSpec allows you to conditionally run configuration blocks before certain tagged
tests. If you have specific volume tests where you want to seed the database
with data, see
[this documentation](https://relishapp.com/rspec/rspec-core/docs/hooks/when-first-matching-example-defined-hook).

You can bake in assertions about performance under high-volume workloads by
measuring response times in RSpec test cases.

In a Rails application, keep your performance tests within your spec folder,
but don’t suffix them with ‘_spec’. This means they won’t run locally with the
`rspec` command. Instead, call the performance tests explicitly in your
continuous integration setup.

## Visual testing
We use visual testing to take screenshots of applications at certain parts of
user journeys in order to quickly validate that we’ve not introduced any visual
regressions and to speed up QA. We’re evaluating
[Percy by Browserstack](https://percy.io/) for this as it integrates very easily
with Rails and Capybara.