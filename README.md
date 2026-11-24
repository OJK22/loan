# Library Lending and Subscription Prototype

An experimental React + TypeScript interface exploring subscriber, guarantor, subscription, and lending workflows with Supabase.

> **Prototype status:** this repository is experimental. It is not a production-ready lending or financial-record system and must not be used with real personal, subscriber, or financial data in its current state.

## Features represented in the current source

- Subscriber and guarantor data-entry workflows
- Subscription creation, editing, and renewal
- Loan, return, and late-return screens
- Online loan-request screens
- Alerts and reporting pages
- Supabase client integration and SQL migrations

## Technology

- React 18 and TypeScript
- Vite
- Supabase JavaScript client
- React Router
- Tailwind CSS and shadcn/ui
- Vitest and ESLint

## Requirements

- Node.js and npm compatible with the versions declared in `package.json` and `package-lock.json`.
- A Supabase project for local integration testing.

## Run locally

1. Install dependencies:

   ```bash
   npm ci
   ```

2. Create a local environment file from the template:

   ```bash
   cp .env.example .env
   ```

3. Set the Supabase project URL and publishable key in `.env`:

   ```dotenv
   VITE_SUPABASE_URL=https://your-project-id.supabase.co
   VITE_SUPABASE_PUBLISHABLE_KEY=your-publishable-key
   ```

4. Start the development server:

   ```bash
   npm run dev
   ```

## Quality checks

```bash
npm run lint
npm test
npm run build
```

These are the scripts declared by the project; run them locally or in CI before treating a change as verified.

## Security limitations — do not deploy as-is

The current migrations include permissive public Row Level Security policies that allow unrestricted operations on tables containing subscriber, guarantor, subscription, loan, and related records. Authentication and least-privilege RLS policies must be designed, implemented, and tested before this prototype can handle any real data.

The Supabase publishable key is intended for browser use, but it does not provide data protection by itself. Never put a Supabase `service_role` key in a `VITE_*` variable or browser bundle.

The repository's existing `.env` file was already tracked before the environment-file ignore rule was added. A `.gitignore` rule does not untrack an existing file or remove it from Git history. Review the repository history and rotate any credential that was mistakenly exposed. Do not post the key value in issues or discussions.

## Related repositories

- [Main library frontend](https://github.com/OJK22/front)
- [Books management UI](https://github.com/OJK22/books)
- [Staff administration UI](https://github.com/OJK22/admin)

## License and project rights

No open-source license is currently included. Do not assume permission to reuse or redistribute this code until the rights holder(s) have selected and added an OSI-approved license. Confirm any municipal and team ownership obligations first.
