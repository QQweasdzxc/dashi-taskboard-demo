# TRQN HELM source and license, 2026-11-26

This is a modified build of chuspeeism/dashi-taskboard v1.1.27, upstream commit 9d1446df3feefffee932ed6698eb1246dd93ee56, under Apache License 2.0. It is not an entirely original or exclusively owned replacement. Upstream: https://github.com/chuspeeism/dashi-taskboard

The original LICENSE and existing dependency notices in the repository are retained. The original upstream commit contains no tracked NOTICE file.

## This release

/sb/ connects to the existing Supabase task data. This release uses the existing shared application-access switch and workspace membership. It adds basic task creation, supported content fields, status changes, member comments and replies, and request-result recovery. These basic operations passed disposable local database and browser tests. Live authenticated read/display and unauthenticated rejection were verified before deployment. Live task creation or modification was not used as a test.

Advanced assignment, task relations, attachment lifecycle, comment editing/resolution/reactions and full original workflow parity remain incomplete. Unsupported operations fail closed. Original Google Drive attachment storage is not replaced. No new product service is required.

## Recovery source

HELM-SOURCE-20261126-1546.zip contains the exact reviewed frontend source, package lock, build scripts and original license. It contains no dependencies, sessions, private task records, credentials or test fixtures. Extract the archive, run npm ci, then VITE_HELM_TASK_WRITES=review-candidate npx vite build --config web/vite.demo.config.ts using the Node version required by package.json. Output: dist/web-demo/.

Modified web source includes the Traditional Chinese HELM interface, responsive navigation, existing calendar reading, Supabase adapter, Google PKCE sign-in, scoped task transport, pending-request recovery and original-field mapping. The source archive retains upstream copyright and modification notices. The database installation is managed separately, and the archive does not grant access or install it.

HELM-MANIFEST-20261126-1546.sha256 identifies the released assets. The root demonstration and old assets remain unchanged. This release does not claim persistent login or complete calendar/Worklog editing and export support.
