# Security review notes — prototype only

This repository is a prototype, not a production-ready lending system.

## Important findings
- The current Supabase migrations grant unrestricted public `FOR ALL` access to tables containing subscriber, guarantor, subscription, loan, and related records. This allows unauthenticated clients to read and modify sensitive records if the project is reachable.
- Do not connect real personal, financial, or borrower data to this project until authentication and least-privilege Row Level Security policies have been designed and tested.
- The browser publishable/anon key is intended to be public; it is not a substitute for database authorization. Never put a Supabase `service_role` key in a Vite `VITE_*` variable or any browser bundle.
- The existing `.env` file is already tracked in the repository. Adding it to `.gitignore` does not remove it from Git history or stop Git from tracking that existing file. This branch deliberately does not delete it, in keeping with the no-deletion requirement.

## Changes in this branch
- Ignore local `.env*` files going forward, while allowing `.env.example`.
- No migration or existing application data was changed. RLS changes are intentionally deferred because tightening policies without a verified authentication/authorization design could break the prototype.
