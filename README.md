# Tanso documentation

This repository contains the public documentation for
[Tanso Core](https://github.com/tansohq/tanso-oss), a self-hosted B2B SaaS
monetization engine. The site is built with [Mintlify](https://mintlify.com).

## Local preview

Install Node.js and the Mintlify CLI, then start the preview from this
repository's root:

```bash
npm install --global mint
mint dev
```

Open `http://localhost:3000`.

If the preview fails after a CLI update, run `mint update` and try again.

## Repository layout

- `docs.json` defines navigation, branding, and site-wide settings.
- Root-level `.mdx` files contain the documentation pages.
- `logo/` and `favicon.svg` contain site assets.
- `AGENTS.md` records project terminology and writing guidance.

When adding a page, include YAML frontmatter with a `title` and `description`,
then add the page slug to `docs.json`.

## Keep behavior accurate

The [Tanso Core repository](https://github.com/tansohq/tanso-oss) is the source
of truth for API routes, request models, authentication, and runtime behavior.
Verify examples against the implementation before publishing them. Label
planned behavior explicitly instead of presenting it as available.

Before opening a pull request:

1. Run `mint dev` and open every changed page.
2. Test commands and request bodies against a local Tanso Core instance.
3. Check internal links and confirm every page appears in `docs.json`.
4. Review the rendered page at desktop and mobile widths.
