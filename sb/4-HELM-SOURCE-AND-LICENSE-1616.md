# TRQN HELM source and license, 2026-11-26 16:16

Modified chuspeeism/dashi-taskboard v1.1.27, upstream commit 9d1446df3feefffee932ed6698eb1246dd93ee56. Apache-2.0 license retained. Upstream: https://github.com/chuspeeism/dashi-taskboard

This is not an entirely original or exclusively owned replacement. Existing dependency license notices remain in the repository. No upstream NOTICE file exists in that commit.

The current source archive is identified by the release checksum manifest in /sb/. Extract it, run npm ci, then VITE_HELM_TASK_WRITES=review-candidate npx vite build --config web/vite.demo.config.ts. Use the Node version required by package.json. Output: dist/web-demo/. The source excludes installed dependencies, credentials, account sessions, private records and fixtures.

This UI update adds Chinese status display using the original project labels without changing stored status keys, a compact left-aligned task detail, compact basic properties, collapsible description editing and original information, project search, safe Markdown br line breaks, and an explicit unavailable-image notice for the suspended original attachment service. No HTML execution, CSP expansion, database operation or original task-content rewrite is added. Modified source files retain notices.

The shared existing access switch and workspace checks remain. Basic task operations have local isolated tests, while live saving and reopening still require an explicitly approved real task. Original attachment lifecycle, full TF parity, calendar/Worklog editing and persistent login remain incomplete. The update does not claim to restore old attachment images.
