# Documentation project instructions

## About this project

- This repository contains the public documentation for Tanso Core.
- The primary audience is developers integrating Tanso and operators running
  a self-hosted deployment.
- The site uses Mintlify. Pages are MDX files with YAML frontmatter, and site
  configuration lives in `docs.json`.
- The `tanso-oss` application repository is the source of truth for behavior.

## Terminology

- Use **account** for the tenant that owns a catalog and customer data.
- Use **customer** for an account's end customer.
- Use `customerReferenceId` for the customer's identifier in an integrator's
  system.
- Use `featureKey` for the stable feature identifier used by events and
  entitlement checks.
- A **plan** groups features. A **plan feature rule** defines pricing, cost,
  limits, and credit behavior for one feature in that plan.
- An **event** records usage. An **entitlement** answers whether a customer may
  use a feature.
- A **credit pool** holds a customer's balance in one credit denomination.
- Use **Client API** for `/api/v1/client/**`, **Admin API** for the JWT-protected
  `/api/v1/**` routes outside the Client API, and **MCP server** for `/mcp`.

## Writing style

- Use active voice and address the reader as "you."
- Keep sentences short and use sentence case for headings.
- Put commands, paths, field names, and literal values in code formatting.
- Make examples copy-pasteable. Include required headers and complete request
  bodies when they affect whether an example works.
- Explain observable behavior and status codes. Do not infer behavior from a
  class or method name.
- Label limitations and planned behavior explicitly.
- Never include real API keys, JWTs, passwords, customer data, or Stripe
  secrets.

## Verifying technical claims

When the application repository is available, verify documentation against:

- `src/main/java/**/controller/` for routes, authentication annotations, and
  response status codes.
- `src/main/java/**/model/` for request and response fields.
- `src/main/java/**/service/` for runtime behavior and edge cases.
- `src/main/java/**/config/SecurityConfig.java` for authentication boundaries.
- `deploy/` and `.env.example` files for self-hosting commands and settings.

Do not describe intended behavior as current behavior when the implementation
does something different. If a discrepancy matters to integrators, document
the current behavior and identify it as a limitation.

## Validation

- Run `mint dev` from the repository root.
- Open every changed page and check internal links.
- Confirm each MDX file has `title` and `description` frontmatter.
- Add new page slugs to the appropriate group in `docs.json`.
