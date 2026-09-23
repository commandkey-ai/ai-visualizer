# Notice of modification (AGPL-3.0 section 5(a))

This is a **modified version** of `ai-visualizer` by Jared Rhodenizer (upstream: https://github.com/jaredrhod/ai-visualizer), prepared by **Executive Stack** and dated **2026-09-22**, revised **2026-09-23**.

- Based on upstream commit: `6921e1d4b06bdd4a34c5264882d5257c4d5f70fd` (upstream author `jaredrhod`, dated 2026-08-30).
- Executive Stack release: `es-2026.09.23-r1` (the name in `ES_RELEASE`), on branch `es-release`.
- License: unchanged, GNU Affero General Public License v3.0 or later. The `LICENSE` file, every copyright line, and every `SPDX-License-Identifier` header are intact. The VT323 font stays under the SIL Open Font License 1.1 with its license text at `assets/VT323-OFL.txt`. Source for this modified version is the mirror repository itself.
- Each modified source file carries a "Modified by Executive Stack, <date>" line near its SPDX header (or an HTML comment at the top of Markdown files), dated 2026-09-22 or 2026-09-23, the date of the last Executive Stack edit to that file.
- The runtime (`server.py`, `core.js`, `index.html`, every face under `faces/`, every asset, `run.sh`, `run.bat`) is **unchanged** from upstream. Only install and update pointers and documentation were modified.

## Why

Executive Stack ships this software to its clients from a reviewed, pinned mirror. The changes below make a client install land on exactly the reviewed release and stay there: no install or update path resolves a moving branch, no unreviewed repository or download source is pulled in, and the author's community and marketing material is replaced with the Executive Stack support pointer (author attribution and license credit are kept).

## Files changed, and why

| File | Change |
|---|---|
| `README.md` | Install commands point at the Executive Stack mirror at the release tag; the demo-video embed removed; sibling-repo links point at the mirror; update wording describes the pinned-tag update; the hands piece removed from the closing section; YouTube, Discord and Ko-fi replaced with the Executive Stack support pointer; license section keeps the author's copyright and adds the modification notice. |
| `TROUBLESHOOTING.md` | The Updating entry describes the pinned-tag update and its Windows equivalent. |
| `ai-visualizer.md` | The backtalk pointer moved to the mirror; Phase 5.5 drops barehands, points the one-piece install and the fullstack-agent one-liners at the mirror at the tag (hash-checked Windows zip, whose SHA-256 is published in the fullstack-agent GitHub Release notes and sent by the Executive Stack contact), and replaces Discord and YouTube with the support pointer; Phases 5.75 and 6 describe the pinned-tag update, say the updater asks before applying, and list the origin, name-pattern and tag self-name checks for a by-hand update. |
| `CONTRIBUTING.md` | A header stating this is Executive Stack's reviewed mirror, routing software bugs and features to the upstream repository and Executive Stack release questions to info@executivestack.ai. The upstream text below it is unchanged. |
| `update.sh` | Rewritten to update only to the release tag published in `ES_RELEASE` on the mirror's `es-release` branch (never `origin/main` or `git pull`); refuses to run when `origin` is not the Executive Stack mirror (never re-points it); validates every release name against `^es-\d{4}\.\d{2}\.\d{2}-r\d+$` before git sees it and verifies the tag's own `ES_RELEASE` names it; tells a fetch refused over a moved tag apart from a network failure; shows what is arriving and asks y/N before applying (`--yes` to skip); a zip-installed folder is wired to the mirror pinned to its own `ES_RELEASE` with no tracking branch on `main`. |
| `update.bat` | The comment block now gives the mirror/tag commands (with the origin and tag self-name checks, without a tracking branch) instead of the upstream remote and `reset --hard origin/main`; the spoken update phrase updated. |
| `ES_RELEASE` | New: the release tag name this checkout belongs to. |
| `NOTICE-EXECUTIVE-STACK.md` | New: this notice. |

Files not listed are byte-for-byte identical to the upstream commit. Two upstream references remain in unchanged files on purpose: a docstring in `server.py` naming the upstream backtalk repository as the origin of the signal-bus contract, and the default display name `JARVIS` in `server.py`, `core.js`, `index.html` and `ai-visualizer.json.example`, which the setup wizard replaces with the client's agent name.
