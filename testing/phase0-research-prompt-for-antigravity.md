# Prompt for Antigravity — Phase 0 Research (sms_web / diyo_web)

Copy everything below into Antigravity as one prompt.

---

## Your role

You are doing **research only** on the `sms_web` repository (package name `shree-sitakunda-school`, ecosystem `diyo_web`). This is a **live production school-management app with real student, fee, and PII data**. You have full folder access to trace code, but this task produces **one markdown file and zero code changes**.

Read `AGENTS.md`, `code_structre_skills.md`, `AGENT.md`, `REFACTOR_ROADMAP.md`, and `ARCHITECTURE_REDESIGN_ROADMAP.md` in the repo root first, so you understand the existing conventions and the reason this research is being done: `admin-dashboard.ts` threads 43 factory modules together via plain object literals at their call sites, which has caused multiple live production bugs (crashes, missing data on page load) that `tsc` did not catch. Before any restructuring work happens, we need a complete, accurate map of that coupling plus a few other baseline facts. **You are producing that map. You are not fixing anything, deleting anything, or moving anything.**

## Hard constraints — read before doing anything

1. **Do not edit, create, move, or delete any file in `src/`, `supabase/`, or any application code.** The only file you create is the single output markdown file described at the end of this prompt.
2. **Do not run `eslint --fix`, formatters, codemods, or any command that mutates files.**
3. You may run read-only commands: `grep`, `tsc --noEmit` (for the error count, per `AGENTS.md`'s documented flags), `git log`, `git blame`, `wc -l`, test runners in read-only/report mode, etc.
4. If you're not sure whether something counts as a "change," don't do it — ask instead in the output file's "Open questions" section.
5. Where the existing docs already state a number (e.g. "43 factory modules," "1,352 `any` usages," "180 files with deep relative imports"), **re-verify it against the current codebase rather than copying it** — the docs explicitly warn these numbers drift and should be re-measured. Flag clearly anywhere your fresh count disagrees with the doc's stated number, and by how much.

## What to produce (map this to `ARCHITECTURE_REDESIGN_ROADMAP.md` §5, Phase 0)

### 1. Full dependency map of `admin-dashboard.ts`

Open `src/pages/admin/dashboard.astro` and the inline/imported bootstrap script that wires up the admin panel (this may be `admin-dashboard.ts` under `src/scripts/admin/` — locate the actual current file, since the roadmap notes it was extracted/renamed during Phase C of the refactor; confirm the real path and current line count first).

For **every factory call site** in that orchestrator (the roadmap counted 43 — verify this count), produce a table row with:
- File path of the factory module (e.g. `scripts/admin/tabs/students-form.ts`)
- Function name called (e.g. `initStudentsForm`)
- **Every key** in the object passed in at the call site, with its source (local variable? return value of an earlier factory call? global `window.*`? shared module like `data-store.ts`?)
- **Every value returned** by the factory, and which later call site(s) consume each returned value
- The **call order position** (1st, 2nd, 3rd... of the sequence) and whether anything about that order looks load-bearing (i.e., would breaking the order cause a TDZ/reference-before-declaration crash based on what you can trace)
- A risk tag: 🔴 (10+ dependencies), 🟠 (5–9), 🟢 (1–4) — recompute this from the actual current dependency count, don't assume the roadmap's tier list is still accurate

Cross-reference this fresh list against the roadmap's existing risk-tiered list (§6 Phase 2 of `ARCHITECTURE_REDESIGN_ROADMAP.md`) and call out explicitly: which files moved risk tiers, which files are new since that doc was written, and which files listed there no longer exist or were already refactored.

### 2. The two duplicate-implementation questions

These need **investigation and a clear presentation of evidence**, not a decision on your part (the roadmap is explicit that the decision needs a human owner, not an agent).

**a) Academic-year rollover** — `Detail_sms_web.md` §8.1 claims the flat `academic-year-rollover.ts` (top-level) is what the UI actually calls, and the nested `academic-year/rollover.ts` has zero callers and is safe to delete. Verify this directly:
- Find every UI call site (search for the fetch/API call path in `src/scripts/` and any `.astro` files) that hits either rollover endpoint.
- Find every import/reference to each rollover file from anywhere else in the codebase (routes, tests, cron, other lib files).
- State plainly which one is actually live, and whether the "zero callers" claim on the other one holds up or not.
- Check `git log` on both files — which was modified more recently, and does the commit history support one being the abandoned one?

**b) Attendance tables** — `daily_attendance`, `daily_attendance_archive`, `current_month_attendance_logs` vs. the newer `attendance_sessions` / `attendance_exceptions` exception-based model (since migration dated 2026-07-09).
- Search all of `src/` for any remaining read or write references to the legacy table names.
- Search `supabase/migrations/` for any migration after the 2026-07-09 exception-based switch that still touches the legacy tables (backfills, RPCs, etc.), and list them.
- Report whether the legacy tables are truly dead in *this app's* code (Detail_sms_web.md claims they're kept alive only for `diyo_admin`'s maintenance purge, which you cannot verify since that's a separate repo — say so explicitly rather than guessing).

### 3. Baseline metrics (must be freshly measured, not copied from the docs)

- `tsc` error count, using the exact command documented in `AGENTS.md`/`Detail_sms_web.md` §10 (`NODE_OPTIONS="--max-old-space-size=8192" pnpm exec tsc --noEmit -p tsconfig.json --ignoreDeprecations 6.0`). Report **total** and a **per-file breakdown**, since the docs explicitly say per-file diffing is what matters, not the raw total.
- Count of `any` usages in `src/` (the doc claims 1,352, up from ~860). Show your search method (e.g. exact grep/rg pattern used) so the count is reproducible later.
- Count of files with `../../..`-or-deeper relative imports (doc claims 180). Show your search method.
- Vitest pass/fail count and which subdirectories genuinely have zero test files (doc claims `tabs/`, `principal/`, `classes/`, `fee-management/`, `academic-year-settings/` — verify against the current file tree).
- File-level test coverage ratio: count of `*.test.ts` files vs. total source files under `src/`.
- Playwright test count and whether all currently pass (note: don't actually run e2e tests against a real environment if that risks touching production data or requires live credentials — if running them is unsafe or requires secrets you don't have, say so and skip, don't fabricate a result).

Do **not** produce a manual "does the dashboard load" browser checklist as part of this Phase 0 pass — that's Phase 1 work per the roadmap, and doing it now would go beyond a read-only research task.

### 4. Response-envelope and path-alias survey

- For every file under `src/pages/api/`, note which response shape it currently returns (`{ data }`, `{ ok: true }`, `{ success: true }`, bespoke key, binary, 204, etc.) — produce a simple count per shape, so we know exactly how much Phase 4 migration work exists. `Detail_sms_web.md` §5.6 lists known shapes as a starting reference, but verify counts don't assume them.
- Count current adoption of `@/`, `@components/`, `@data/`, `@layouts/` path aliases vs. relative imports for new cross-directory imports, to confirm or correct the doc's "0% adoption" claim.

## Output format — the only file you create

Create a single file named `PHASE0_RESEARCH_FINDINGS.md` in the repo root (or wherever the person running this prompt tells you to place it if that differs). Structure it exactly like this:

```markdown
# Phase 0 Research Findings — [today's date]

## 0. Summary for a human to read in 60 seconds
(3-6 bullet points: the single most important finding, whether prior doc numbers held up
or drifted, and the one thing that most needs an owner decision before Phase 2 starts.)

## 1. Dependency map — admin-dashboard.ts / orchestrator
(the full table described above, plus a short paragraph on any load-bearing ordering risk
you found that isn't already flagged in ARCHITECTURE_REDESIGN_ROADMAP.md)

## 2. Duplicate system A — academic-year rollover
(evidence, call sites, git history, your finding — NOT a decision)

## 3. Duplicate system B — attendance tables
(evidence, call sites, migration history, your finding — NOT a decision)

## 4. Baseline metrics
(each metric, the exact command/search used to get it, the result, and a one-line diff
against what the existing docs claimed)

## 5. Response envelope & path alias survey
(counts, broken down as described above)

## 6. Discrepancies vs. existing docs
(a table: claim in doc / doc source / what you actually found / delta)

## 7. Open questions for the human
(anything you couldn't verify safely, anything that needs a judgment call, anything
that seemed important but was out of scope for this pass)
```

Keep prose sections tight — tables and bullet points over paragraphs wherever possible, since this file's job is to be a fast, accurate reference for planning Phase 2, not a narrative.

## One more reminder before you start

If at any point a task in this prompt would require you to modify, delete, or "clean up" anything in the codebase to get an answer — stop, don't do it, and note in the output file that you skipped it and why. Read-only, one output file, nothing else touched.
