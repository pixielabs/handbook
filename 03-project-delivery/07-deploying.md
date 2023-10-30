# Deploying

## Web apps
We deploy applications to [Heroku](https://www.heroku.com/). We use Heroku
because:

- Spinning up a new Heroku app is trivial.
- They manage infrastructure for us.
- It has a healthy community of add-ons.
- It’s proven at scale.
- There’s an understandable migration path from Heroku to AWS for larger
  projects.
- [They optimise for erosion resistance, like us.](https://devcenter.heroku.com/articles/erosion-resistance)

Sometimes Heroku is not suitable for a project. That’s usually because:

- The client already uses something other than Heroku.
- The project requires multiple parallel tasks and budget is too tight for
  Heroku dynos.
- The project has a large database from the word go, but budget is still tight.
  Generally this means the budget is too small, but sometimes you might have a
  data-heavy problem that is a relatively small project otherwise.

In which case, our second choice is usually to provision EC2 servers directly.
In that case we use a combination of:

- [Ansible](https://www.ansible.com/), for automated server provisioning.
- [Capistrano](http://capistranorb.com/), for code deployment and remote
  administration.

We’re exploring IaaS options but have never needed anything that Heroku and our
ad-hoc AWS provisioning do not satisfy. We’re evaluating:

- [AWS CloudFormation](https://aws.amazon.com/cloudformation/)
- [Terraform](https://www.terraform.io/)

We have found that serverless architectures such as Google Cloud Functions or
AWS Lambda do not work at our two-pizza team scale. The same goes for homegrown
container-based architectures such as those based on the Docker family or
Kubernetes. Heroku can do a much better job of building that architecture than
us.

## Native mobile app build tools
- [Fastlane](https://fastlane.tools/) for automated app builds and releases.
- For future projects, we would also like to try
[Match](https://codesigning.guide/) for managing code signing.

We also looked into:
- [Bitrise](https://www.bitrise.io/) - We discounted Bitrise because the
  interface is confusing. We also struggled to get a simple app to build.

## Static sites
- [Netlify](https://www.netlify.com/) - We used to like Netlify but they
  increased their pricing and we had some real issues getting complex sites to
  build. We’ll be evaluating alternatives next time we build a static site.
  
## Our standard deployment process

Most projects should be set up as follows:

 - The `main` branch is connected via Heroku to automatically deploy the staging
   application.
 - The `production` branch will automatically deploy the production application.

A deploy to production is then:

1. Open a pull request from `main` to `production`. Title it with the date & 
   'production deploy'. Use the template below. Detail in the PR description
   what is going to be deployed. Check through the diff for any tasks that need
   to be run manually e.g. one-off rake tasks, and document them in the
   description too so you don't forget.
2. Let the project team know on Slack you're preparing a deploy.
3. Before deploying, liaise with another developer on the project to ensure
   there are no impending merges that might conflict with your deployment. 
   This step helps to mitigate the risk of simultaneous merges, especially from 
   main to production, that might inadvertently escalate the scope of
   deployment.
4. Wait for CI to pass the commit you're merging.
5. Merge the PR.
6. Wait for CI to pass the merge commit (you can watch this on GitHub).
7. Once CI passes the merge commit, the deploy should start on Heroku and you
   should see it on the Heroku dashboard for that app. Keep one eye on it.
   
Once deployment finishes, let the project team know it's live and run any 
one-off tasks you documented at the start of the process.

### PR template

This template is loosely based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/)

```
_Delete any empty headings_

### Added
_New features._

### Changed
_Changes in existing functionality._

### Deprecated
_Soon-to-be removed features._

### Removed
_Now removed features._

### Fixed
_Any bug fixes._

### Security
_Any vulnerabilities fixed_

### Deployment notes
_Any steps that need to be performed as part of deployment e.g. rake tasks_
```
