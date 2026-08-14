# FermerMarket — Clean Architecture Recovery

This archive was reconstructed from the uploaded project archive.

## Canonical application structure

- `src/app` — Next.js App Router pages and API routes
- `src/components` — UI/components
- `src/lib` — application services/utilities
- `src/i18n` — next-intl routing/request configuration
- `prisma` — schema and migrations
- `public` — static assets
- `messages` — AZ/EN/RU translations
- `cloudflare` — separate email worker

## Recovery actions

1. Root-level flattened/renamed files such as `route(1).js`, `route (183).js`, `page (24).js`, etc. were excluded from the deployable project.
2. The uploaded root `package.json`, `next.config.js`, `schema.prisma`, and several other root names contained unrelated source code because files had been flattened/renamed. They were not treated as authoritative.
3. `vercel.json` was excluded because the uploaded version contained JavaScript API-route code instead of JSON configuration.
4. The existing canonical `src/` tree was preserved.
5. Internal `@/` and relative imports in the canonical `src/` tree were statically checked; no unresolved local imports were found.
6. The uploaded `.env.local` was intentionally excluded.
7. A separate `Fermermarket-LEGACY-ROOT-BACKUP.zip` contains the non-secret root-level files that were excluded, so nothing was silently discarded.

## Important

`package.json` was reconstructed from the public `main` branch repository manifest and the stale `monitor` script was removed because the uploaded project does not contain `server/monitor.js`.

`package-lock.json` was not fabricated. Run `npm install` in the clean project to generate a lockfile from the recovered manifest.

## Git recovery

Initialize Git only in this directory:

`C:\Users\Mcman\Desktop\Fermermarket`

Do not run Git commands from `C:\Users\Mcman`, and do not use `git add ..`.

## Dependency audit

Static import scanning found two source dependencies missing from the recovered repository manifest: `dompurify` and `svix`. They were added to `package.json`.
