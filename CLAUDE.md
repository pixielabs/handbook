# Pixie Labs Handbook

This is the company handbook for Pixie Labs, documenting how the team works
together, manages projects, delivers software, and supports clients. It's
hosted at https://handbook.pixielabs.io and built with docsify.

## Project Structure

Content is organized in numbered directories:
- `01-working-at-pixie-labs/` - Security, tools, development environment
- `02-project-management/` - Estimating, meetings, tickets, working with designers
- `03-project-delivery/` - Priorities, style, testing, reviews, deployment
- `04-ai/` - Using AI in projects
- `05-ongoing-support/` - Support types, debugging, alerts, incidents
- `06-personal-development/` - Billable time, non-billable priorities

Each section contains markdown files with guides and processes.

## Key Files

- `_sidebar.md` - Navigation menu (update when adding/removing pages)
- `_coverpage.md` - Homepage cover
- `index.html` - Docsify config and theme
- Individual `.md` files in numbered directories contain the handbook content

## Local Development

```bash
npm i docsify-cli -g
docsify serve
# Visit http://localhost:3000
```

## Content Guidelines

- Write in clear, direct language
- Use markdown formatting (headings, lists, code blocks)
- Keep content practical and actionable
- Target audience is engineers at Pixie Labs
- This is a living document - it should evolve with the company

## Making Changes

1. Edit the relevant markdown file
2. Update `_sidebar.md` if adding/removing pages
3. Test locally with `docsify serve`
4. Commit and push (deploys via GitHub Pages)

## License

Content is CC0 1.0 Universal - public domain, free to use without attribution.
