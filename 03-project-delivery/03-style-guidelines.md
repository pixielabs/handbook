# Style guidelines

## Ruby

We have a _de facto_ Ruby style, and if you follow 
[Shopify's Ruby Style Guide](https://shopify.github.io/ruby-style-guide/) you'll
be pretty much there.

We use [Rubocop](https://rubocop.org) and
[`overcommit`](https://github.com/sds/overcommit) with our own Rubocop 
configuration that leans heavily on Shopify's configuration.

We don't have a central place for our Rubocop and `overcommit` configuration
right now, but you can pull it from another project. The `.rubocop.yml` looks
something like this at the time of writing:

```yaml
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
```

## JavaScript

We don't have a particular style for JavaScript right now.