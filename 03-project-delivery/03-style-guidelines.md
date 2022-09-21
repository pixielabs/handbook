# Style guidelines

## All code

 - Where possible keep lines to 80 characters. Don't try too hard if it
   makes the code uglier, though.

## Ruby

We have a _de facto_ Ruby style, and if you follow 
[Shopify's Ruby Style Guide](https://shopify.github.io/ruby-style-guide/) you'll
be pretty much there.

We use [Rubocop](https://rubocop.org) and
[`overcommit`](https://github.com/sds/overcommit) with our own Rubocop 
configuration that leans heavily on Shopify's configuration.

We don't have a central place for our Rubocop and `overcommit` configuration
right now, but you can pull it from another project, or from this handbook.
The `.rubocop.yml` looks something like this:

```yaml
# On fresh projects this is easier, on existing projects we might skip this
require: rubocop-rails

inherit_gem:
  rubocop-shopify: rubocop.yml

# Ruby 3 is gonna make this default anyway...in the mean time magic comments
# are not our jam.
Style/FrozenStringLiteralComment:
  Enabled: false

# Not really a fan of trailing commas, sorry Shopify.
Style/TrailingCommaInHashLiteral:
  Enabled: false

# Ditto above
Style/TrailingCommaInArrayLiteral:
  Enabled: false

# But Ruby is beautiful without them!
Style/MethodCallWithArgsParentheses:
  Enabled: false

# The way rubocop autocorrects this is v. ugly; a hard line break and no
# indentation.
Layout/LineLength:
  Enabled: false

# We use {} for multi line blocks in tests
Style/BlockDelimiters:
  Exclude:
    - "spec/**/*_spec.rb"

# Support 'redirect and return if y'
# See <https://github.com/rubocop/rubocop/issues/1288>
Style/AndOr:
  EnforcedStyle: conditionals
  

AllCops:
  # Generally new cops are worth enabling especially from rubocop-rails
  NewCops: enable
  
  # Don't cop binstubs
  Exclude:
    - "bin/*"
```

And an `.overcommit.yml` that looks something like this:

```yaml
# Overcommit runs hooks automatically when committing, pushing etc.

# Don't bother with any commit message checks
CommitMsg:
  ALL:
    enabled: false

PreCommit:
  # Enable Rubocop
  RuboCop:
    enabled: true
    on_warn: fail # Treat all warnings as failures
    # Use bundled rubocop for consistency
    command: ['bundle', 'exec', 'rubocop']

  # Check for leftover merge conflicts
  MergeConflicts:
    enabled: true
    description: 'Check for merge conflicts'
    quiet: true
    required_executable: 'grep'
    flags: ['-IHn', "^<<<<<<<[ \t]"]

# Do nothing post-checkout
PostCheckout:
  ALL:
    enabled: false
```

This requires adding `rubocop`, `rubocop-shopify` and `overcommit` to
your Gemfile. They should all be set to `require: false`.

We're considering adopting [rubocop-rspec](https://github.com/rubocop/rubocop-rspec)
and a form of [The RSpec Style Guide](https://rspec.rubystyle.guide/). It
broadly lines up with our _de facto_ style, but there's definitely
improvements we could make.

## JavaScript

We don't have a particular style for JavaScript right now.
Use [JavaScript Standard Style](https://standardjs.com/) to resolve bike-shed debates.
Specifically [semistandard](https://github.com/standard/semistandard) because we
use semicolons to terminate expressions.
