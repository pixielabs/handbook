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