# Library Lending and Subscription Prototype

An experimental React + TypeScript application exploring subscriber, guarantor, subscription, and lending workflows with Supabase.

> **Prototype warning:** this repository is experimental and is not production-ready. Do not use it with real personal, subscriber, or financial data.

## Features

- Subscriber and guarantor data-entry workflows
- Subscription creation, editing, and renewal
- Loan, return, and late-return screens
- Online loan-request workflows
- Alerts and reporting screens
- Supabase client integration and SQL migrations

## Technology

- React 18 and TypeScript
- Vite and React Router
- Supabase JavaScript client
- Tailwind CSS and shadcn/ui
- Vitest and ESLint

## Requirements

Use a supported Node.js version and npm. A Supabase project is required for integration testing.

## Run locally

```bash
npm ci
cp .env.example .env
# Set VITE_SUPABASE_URL and VITE_SUPABASE_PUBLISHABLE_KEY in .env
npm run dev
```

## Quality checks

```bash
npm run lint
npm test
npm run build
```

## Security limitations

The current database migrations include permissive Row Level Security policies. Authentication and least-privilege policies must be designed, implemented, and tested before this prototype can handle real data. A Supabase publishable key is intended for client use but does not protect database records by itself. Never expose a `service_role` key in a browser bundle.

If a real credential was ever committed, rotate it; adding it to `.gitignore` does not remove it from Git history. Do not share secrets or personal data in issues.

## Related projects

- [Main library frontend](https://github.com/OJK22/front)
- [Books management UI](https://github.com/OJK22/books)
- [Staff administration UI](https://github.com/OJK22/admin)

## Contributing

This is an exploratory prototype. Contributions should preserve the prototype warning, include clear reproduction steps, and avoid implying production readiness.

## License

MIT. See [LICENSE](./LICENSE).
