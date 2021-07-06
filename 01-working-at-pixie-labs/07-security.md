# Security

## General
- Don’t be a n00b. Responsibility, not restriction. Generally, everyone should
  be trusted to be sensible.
- Use a passphrase-based SSH key.
- Use total volume encryption (e.g. FileVault). This is strongly enforced when
  dealing with client data.
- Everything is shared and searchable (except for financial/legal). 
- We trust Pixies - but everyone should behave responsibly with privileged
  company and client information.
- Always enable 2FA if it is available. Store the OTP in 1Password.
- Regularly (once a month) check permissions across key accounts e.g. Google,
  calendars, third-party applications (e.g. oAuth apps). Build up a list of
  accounts that you need to check this for. This is good practice for personal
  accounts (e.g. social media) too.

## Passwords
- You must use [1Password](https://1password.com/) for Pixie Labs-related
  credentials.
- Never reuse passwords.
- We strongly encourage (one step short of enforcing) using 1Password for
  personal passwords too, as personal accounts can be used as a vector to
  attack Pixie Labs.
- Pixie Labs will pay for you to have a 1Password Personal or Families account
  whilst you work for Pixie Labs if you do not want to use the company account
  for your personal passwords. Ask David!
- If you forget your master password or secret key, David, Pete or Philip can
  help you recover your account.

## Backups
- Your machine should be backed up with [Backblaze](https://www.backblaze.com/).
- Pixie Labs will not access your device backups without your permission.
- Add a private encryption key via the Backblaze preferences panel. Keep this
  safe (store it in 1Password), you’ll need it if you need to restore anything.

## Device security
- Your company MacBook must be enrolled in our centralised device management.
  Speak to David to be pointed in the right direction.
- Details about our device management policies must not be public; this would be
  an information risk.
- Keep your apps and operating system up to date.
- If you use a personal device (e.g. your phone or a secondary machine) for
  anything related to Pixie Labs, that must also have total volume/device
  encryption enabled. If it doesn’t support that, don’t use it for
  Pixie Labs-related activities. You must also have a reasonably short screen
  lock timer (at most two minutes).
  
## Code and data security
- There are very few situations where you should commit credentials to code. Use
  environment variables or Rails encrypted credentials.
- Never, except with prior approval, pull down a production database on to your
  own machine.
- Do not give third-party applications access to GitHub (e.g. via sign-in with 
  GitHub, oAuth, API access etc) without checking it's OK with someone else.
- Do not share client code with anyone who is not a member of Pixie Labs.
- You should not copy code from one client to another, or to any other project or
  codebase, whether Pixie Labs or not.
