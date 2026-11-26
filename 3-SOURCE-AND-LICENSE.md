# Source and license record

This integration is a modified build of [chuspeeism/dashi-taskboard](https://github.com/chuspeeism/dashi-taskboard), upstream commit `9d1446df3feefffee932ed6698eb1246dd93ee56` (v1.1.27). It is not an entirely original or exclusively owned replacement. The original `LICENSE` is Apache License 2.0 and remains applicable to the upstream code. No upstream `NOTICE` file exists in that commit's tracked tree. Dependency license notices are preserved separately in `2-THIRD-PARTY-NOTICES.txt`.

The repository root is the original demonstration build. `/sb/` is a separate, owner-gated read-only integration against the existing Supabase data source. Do not describe the root demonstration as production data, or `/sb/` as a write-capable release.

## Modifications, 2026-11-26

The modified files are preserved in `1-SOURCE-SNAPSHOT.zip`, together with unchanged upstream source, license, dependency lockfile and build configuration. The archive contains no installed dependencies, account session, private task data or secrets.

- `web/src/main.tsx`, `web/index.html`: integration entry and restrictive content policy.
- `web/src/supabase/`: existing owner-read data mapping, Google PKCE login, in-memory session/snapshot, stale-response guards, read-only field display, navigation, and a monthly-record candidate. The monthly-record entry remains disabled pending separate live verification.
- `web/src/api.ts`, `storage.ts`: read adapter and no task-data persistence; original mutation calls refused.
- `web/src/App.tsx`, `types.ts`, `i18n.tsx`, card/list/detail/icon components: retain original task UI while displaying raw TF status and extra read-only fields and hiding unavailable write controls.
- `web/src/styles.css`: integration shell, persistent navigation, full-name project selector and responsive layouts.
- `web/src/vendor/dhtmlxgantt.css`: remove external Google font references from the shipped stylesheet.
- `web/vite.demo.config.ts`: static single-bundle build.
- `test-sb-*`: read mapping, auth races, month validation, and responsive navigation regressions.

All modified source files are listed in this record so modifications are explicit. Upstream copyright and license text are retained. No patent, trademark, or exclusive-ownership claim is added.

## Restore and build

Extract `1-SOURCE-SNAPSHOT.zip`, enter its `dashi-taskboard` directory, and use `npm ci`, `npm run typecheck`, then `npx vite build --config web/vite.demo.config.ts`. Output is `dist/web-demo/`. Installation requires the public package registry. This source archive is a recovery snapshot, not a promise of byte-identical output across future tool versions. The deployed `/sb/3-MANIFEST.sha256` identifies the currently shipped bytes. Deployment renames the bundle and stylesheet; update the index references and manifest together. Do not deploy task fixtures or session values.

The owner-read RPCs and OAuth callback already exist in the owner's separate Supabase and site configuration; this source archive does not grant access, install database functions, or broaden permissions.

## Third-party notices

`2-THIRD-PARTY-NOTICES.txt` conservatively preserves LICENSE, NOTICE and COPYING files found throughout the installed dependency tree, including build and optional dependencies. The build's direct packages all had license files. This is a source-and-notice preservation record, not a legal opinion or a new license for third-party work.
