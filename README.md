# Codex Learning Path — Zero to Pro

Public standalone, source-first learning path with 25 bilingual lessons, 6 career directions, 5 skill tiers, safe practice prompts, completion checkpoints and self-assessed evidence. This is independent educational content, not OpenAI certification.

**Live course:** https://codex.xuanhieu.org/demos/codex-path/

**Start locally:** run python3 -m http.server 4179 --bind 127.0.0.1 from this repo, then open http://127.0.0.1:4179. No API credentials needed.

**Test:** node --test tests/test_engine.cjs (30 unit tests).

**Curriculum regeneration:** python3 builders_curriculum.py uses the included academy-source/lessons.json fixture.

Original upstream lesson links are available per lesson. References may become outdated; verify against current official Codex documentation.

The source vendor/ascii-reveal-core.js remains under its own MIT notice in vendor/ASCII_REVEAL_LICENSE.txt. Other source is not automatically relicensed by the vendor license.

## Security and scope

All course progress, notes and checklists remain in local browser storage and optional user-initiated JSON export. The app does not execute Codex, connect to accounts or certify a learner. Never paste genuine secrets into exercise prompts.

## Development notes

# Codex Path — Learning & Career OS

**Independent learning and career planning product** by the local Codex Ambassador workspace.

## Try the app

- Local: from `<local project checkout>/codexpro-amb`, run `python3 -m http.server 4197 --bind 127.0.0.1` then open `http://127.0.0.1:4197/demos/codex-path/`.
- Public (after verified Cloudflare release): `https://codex.xuanhieu.org/demos/codex-path/`.
- Cross-link: Academy `../codex-academy/`; Mission Control `../../dashboard/#workspace`.

## Real features

1. Career discovery: six curated career profiles (AI Automation, Growth & SEO, AI Product Engineer, Agent Systems Engineer, AI Creator/Educator, AI Team Enablement).
2. Adaptive scheduler: select learning baseline (Zero/Beginner/Intermediate/Advanced/Pro), 2–20 study hours per week and 2–32 target weeks. Lessons come from the current Academy data snapshot, prerequisite closure is enforced, and capstone is split into three 60-minute segments. It is an **estimate**.
3. Native lesson/quiz reader: 25 bilingual VI/EN exercises with links to source docs, quiz feedback, prerequisite gate and explicit human completion confirmation.
4. Practice and portfolio: search/filter all lessons, capstone evidence requirements, HTTPS URL syntax feedback, self-attested readiness gate and review checklist.
5. Privacy: no login, account, third-party API, SDK or external tracker. Learning state is stored in browser localStorage only. Export/import bounded JSON and export Markdown.
6. Optional Academy bridge: explicitly import completed lesson IDs from the Academy app on the same browser origin; don't silently mutate Academy storage.
7. Navigation to Academy, dashboard and existing standalone educational demos.
8. Theme switcher, VI/EN UI, responsive layout and keyboard reachable native controls.

## Guided practice update (2026-10-24)

Each of the 25 bilingual lessons now includes a concrete exercise checklist with state persisted locally, a copy-ready bilingual prompt for a synthetic practice session with Codex/ChatGPT, a quiz, a personal reflection note, and a required learner acknowledgement. Marking a lesson complete requires passing its quiz, completing its exercise checklist and satisfying prerequisite gates. This is **self-assessed practice**, not remote Codex execution or official certification.

The local JSON backup retains completed practice steps. Older version-1 backups continue to import correctly. Public source and the live app deliberately do not collect personal emails, code samples or secrets.

## Skills, systems and visual references

- **Frontend**: local `ak-frontend-design`, `ak-frontend-development` guidance; the product uses plain HTML/CSS/JS, no JS framework or remote dependencies.
- **Design language**: inspired by the existing Noti-style dashboard: blue/cyan tokens, tempered glass surfaces, compact nav, legible small typography, semantic progress states.
- **ASCII reveal**: the *actual* upstream `ascii-reveal` core (Quan Hoang) is vendored at `vendor/ascii-reveal-core.js` with unmodified MIT license `vendor/ASCII_REVEAL_LICENSE.txt`. Used only for first-level headings, respects reduced-motion, save-data and low-capacity devices, destroys controllers after animation. See `PROVENANCE.md`.
- The Academy's 25 VI/EN lessons are copied from `../codex-academy/lessons.json` by `builders_curriculum.py`, with references preserved. Refresh dataset when source Academy content changes.

## Commands

```bash
cd demos/codex-path
python3 builders_curriculum.py
node --test tests/test_engine.cjs
node --check app.js
node --check motion.js
node --check engine.js
```

Verified 2026-10-24: **30/30 Node unit tests and 48 Chrome interactions** (390/768/1440px, including the new exercise-step completion gate).

Browser QA (from workspace root): `cd agents/BR-20261024-PARALLEL && ONLY_IDS=PATH node qa_multi.mjs`.

## Data lifecycle and limitations

- App does not execute Codex, verify remote repository contents, run tests on the learner's machine, promise job placement, or grant any credential/certificate.
- URLs are checked for `https://` syntax only; independently verify evidence, license and source access.
- Offline after page load but initial curriculum fetch requires HTTP. `file://` is unsupported.
- Browser profile/session privacy applies; shared device users should avoid importing sensitive data.
- Source links were drawn from the existing Academy snapshot dated 2026-10-24; users must check official pages for current guidance.
- No public claims about an OpenAI Ambassadors acceptance decision.
