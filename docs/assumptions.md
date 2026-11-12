# Assumptions

Decisions made in this private copy of Ember, including where Ember's own guidelines (`CLAUDE.md`,
`AGENTS.md`, `docs/development.md`) override the Golden Rules.

## Ember's guidelines win over the Golden Rules where they conflict

- Assumption: Upstream conventions take precedence, and the Golden Rules govern only changes and
  additions made in this copy.
- Why: The copy takes Ember's releases through `update-ember.yml`; restyling upstream code would
  make each update a merge conflict and hide upstream changes from security review.
- Recorded by: Claude (Opus 5.5)
- Date: 2026-11-11

## Filenames stay kebab-case

- Assumption: TypeScript files are named in kebab-case (`chat-room.ts`, `auth-page.tsx`), not
  camelCase.
- Why: Every existing file and shadcn/ui's generator use kebab-case.
- Recorded by: Claude (Opus 5.5)
- Date: 2026-11-11

## Migrations are append-only

- Assumption: Schema changes follow Ember's rules (new files only, never edit a released migration,
  add to tables rather than remove), which are stricter than the Golden Rules' deprecation policy.
- Why: Deployments update from release to release (`docs/development.md#releasing`).
- Recorded by: Claude (Opus 5.5)
- Date: 2026-11-11

## Logging goes through console on Workers

- Assumption: The Worker logs with `console.*`, which Workers Logs captures and indexes; structured
  fields should be passed as an object rather than replacing console with a logging library.
- Why: That is the platform's logging path, and Ember already uses it.
- Recorded by: Claude (Opus 5.5)
- Date: 2026-11-11

## Comments and prose follow Ember's style

- Assumption: Comments only where behavior is non-obvious, icons only from Iconoir, colors only from
  the tokens in `apps/web/src/index.css`, as `CLAUDE.md` says.
- Why: Project owner's stated conventions.
- Recorded by: Claude (Opus 5.5)
- Date: 2026-11-11

## Health endpoints, metrics and alerting are open items

- Assumption: The Golden Rules' `/healthz`, `/readyz`, deep `/health`, metrics and external
  monitoring requirements are not met upstream; they are tracked as review findings rather than
  added blindly.
- Why: Adding routes to the Worker changes upstream code; whether and how is a review decision.
- Recorded by: Claude (Opus 5.5)
- Date: 2026-11-11
