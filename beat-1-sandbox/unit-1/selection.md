# Unit 1 — Issue Selection

Path: `beat-1-sandbox/unit-1/selection.md`

Record of the issue carried into Unit 2, and of the evaluation runs that produced
`eval-run.txt`. This file is graded at the path above; a copy kept anywhere else in
the repository is not read.

Complete every labelled field below. Each is graded on its own; content placed under the
wrong label is not graded.

---

## Selected issue

**Issue link**

https://github.com/codepath/pathreview-ai301-fa26-s1/issues/54

**Verdict output**

**The verdict must record `accept` for this issue.** Choose an issue your own skill
accepts. If your skill rejects every candidate you try, that is a signal about your
rubric rather than about the issues: revise it and re-run — retries are unlimited and a
partial re-run costs about $0.20 — or run the skill on different candidates. Output
recording `reject` for the issue you chose earns no credit for this field.

````
I graded all three against your rubric. **#54 and #64 are accepted; #57 is rejected.**

**Repo-level checks (the same for all three):**
- **maintainer-alive: pass.** The last human commit is by Aburke225 on 2026-09-16, 18 days ago.
- **repo-in-use: pass.** The repo isn't archived and was last pushed on 2026-09-16. It has no releases, but that doesn't fail the check.
- **ai-policy-allows: pass.** Neither `docs/CONTRIBUTING.md` nor the PR template says anything about AI use.
- **fast-maintainer (preferred): unclear.** Maintainers have posted only 2 comments across about 100 issues, so there's no response time to measure.

**Ranked (accepted):**

1. **#54, resume section detection fails on leading whitespace.** It's a single bug fix with clear acceptance criteria: 5 tests marked xfail for #54 need to pass, and their markers removed. It fits you best because it's the kind of well-scoped bug you prefer, and you get real practice making failing tests go green. No PR exists yet; everything in the thread is classmates' claims and repro reports, which the house rule says to ignore.
2. **#64, the "partial overlap" test fixture has full overlap.** It's tightly bounded and fits your goal of getting better at tests. It ranks second because the whole fix is changing one fixture string and removing the xfail marker, so there's little to learn. Classmate srithimahi has also already posted that exact fix plan. Under the house rule that doesn't block you, but your PR would be close to identical to theirs.

Neither accepted issue is frontend or API code. Both are Python backend: ingestion and RAG scoring.

**Rejected:**
- **#57, tech detector counts vendored files: fails not-claimed.** Open PR #82 by whitgunt77 (opened 2026-10-02) is formally linked to it. The house rule only waives claim *comments*, and the rubric fails any issue with an open linked PR. If you think classmates' PRs shouldn't block either, that change belongs in `scope.md`.

```json
[
  {
    "item": "https://github.com/codepath/pathreview-ai301-fa26-s1/issues/54",
    "checks": [
      {"name": "maintainer-alive", "grade": "pass", "evidence": "Human commit by Aburke225 on 2026-09-16, 18 days before 2026-10-04"},
      {"name": "repo-in-use", "grade": "pass", "evidence": "isArchived: false; pushedAt 2026-09-16 (within 180 days)"},
      {"name": "bounded-scope", "grade": "pass", "evidence": "Single bug: _detect_sections() anchors patterns at line start so indented text yields []; 5 xfail tests define done"},
      {"name": "not-claimed", "grade": "pass", "evidence": "No assignees, no linked or mentioned PRs; only student claim comments, which the house rule ignores"},
      {"name": "ai-policy-allows", "grade": "pass", "evidence": "No AI policy in docs/CONTRIBUTING.md or PR template"},
      {"name": "newcomer-label", "grade": "pass", "evidence": "Labels: good first issue, tier-1"},
      {"name": "fast-maintainer", "grade": "unclear", "evidence": "Only 2 maintainer comments across ~100 issues; no response sample to compute a median"}
    ],
    "verdict": "accept"
  },
  {
    "item": "https://github.com/codepath/pathreview-ai301-fa26-s1/issues/64",
    "checks": [
      {"name": "maintainer-alive", "grade": "pass", "evidence": "Human commit by Aburke225 on 2026-09-16, 18 days before 2026-10-04"},
      {"name": "repo-in-use", "grade": "pass", "evidence": "isArchived: false; pushedAt 2026-09-16 (within 180 days)"},
      {"name": "bounded-scope", "grade": "pass", "evidence": "Test-only fix: 'Fix the fixture so the overlap is genuinely partial'"},
      {"name": "not-claimed", "grade": "pass", "evidence": "No assignees, no linked or mentioned PRs; only student claim comments, which the house rule ignores"},
      {"name": "ai-policy-allows", "grade": "pass", "evidence": "No AI policy in docs/CONTRIBUTING.md or PR template"},
      {"name": "newcomer-label", "grade": "pass", "evidence": "Labels: good first issue, tier-1, tests"},
      {"name": "fast-maintainer", "grade": "unclear", "evidence": "Only 2 maintainer comments across ~100 issues; no response sample to compute a median"}
    ],
    "verdict": "accept"
  },
  {
    "item": "https://github.com/codepath/pathreview-ai301-fa26-s1/issues/57",
    "checks": [
      {"name": "maintainer-alive", "grade": "pass", "evidence": "Human commit by Aburke225 on 2026-09-16, 18 days before 2026-10-04"},
      {"name": "repo-in-use", "grade": "pass", "evidence": "isArchived: false; pushedAt 2026-09-16 (within 180 days)"},
      {"name": "bounded-scope", "grade": "pass", "evidence": "Single bug: _should_skip_file misses root-level node_modules/ and build/ paths"},
      {"name": "not-claimed", "grade": "fail", "evidence": "Open PR #82 by whitgunt77 (2026-10-02) is formally linked to the issue"},
      {"name": "ai-policy-allows", "grade": "pass", "evidence": "No AI policy in docs/CONTRIBUTING.md or PR template"},
      {"name": "newcomer-label", "grade": "pass", "evidence": "Labels: good first issue, tier-1"},
      {"name": "fast-maintainer", "grade": "unclear", "evidence": "Only 2 maintainer comments across ~100 issues; no response sample to compute a median"}
    ],
    "verdict": "reject"
  }
]
```
````

---

## Eval iterations

Quote source text directly in each field below. Paraphrase does not satisfy them.

**Run history**

1. Run 1 (full, first rubric): `agreement: 14/20 scored items  (bar: 18/20: below the bar)`. Categories: `claimed 4/4  clear-accept 3/8  dead-repo 3/3  policy 1/1  scope 3/4`. Disagreements: issue-01, issue-09, issue-14, issue-16 (all failed on `maintainer-alive`), issue-19 (failed on `bounded-scope`), issue-20 (graded accept, gold reject).
2. Run 2 (full, revised rubric, saved as `eval-run.txt`): `agreement: 20/20 scored items  (bar: 18/20: PASS)`. Categories: `claimed 4/4  clear-accept 8/8  dead-repo 3/3  policy 1/1  scope 4/4`.

Between the runs I made three changes. (1) `maintainer-alive` stopped requiring a maintainer first response within 30 days, so recent human commits alone decide it. (2) `bounded-scope` now treats a single bug with several named causes as one change, and only an explicit request to split counts as an umbrella. (3) `bounded-scope` gained clause (f): a new user-facing feature with no maintainer endorsement fails.

**Issue analysis**

**issue-20** (excalidraw/excalidraw#11811, "Add company logo shape to the toolbar"). Gold label: **reject** (scope category). Run 1: my rubric said **accept**. Run 2: **reject**, agreeing with gold.

Why run 1 accepted it: every check passed on its literal wording. The repo is very active ("2026-08-04 commit by dwelle (human), 1 day before capture"), it is not archived, nobody is assigned, there are no PRs, and CONTRIBUTING.md has "no statement on AI or contribution tooling". My first `bounded-scope` only looked for umbrella issues, design arguments in the thread, maintainer-flagged core rewrites, support questions, and failed prior PRs. This issue has none of those: it has 0 comments, and the body reads like one tidy feature ("logo tool in the shapes toolbar → place/resize/move like other elements → correct export"). So it passed as "one concrete change".

What the rubric missed is that the issue was opened by `cursor[bot] (NONE)`, has no labels, and asks for a new product feature that no maintainer has agreed to. Whether excalidraw even wants a "company logo" tool is a product decision nobody has made, so a newcomer's PR could be declined on the idea itself, not the code. Run 2 added clause (f) to `bounded-scope`, and the grader then failed it with: "New user-facing toolbar feature with 0 comments and no maintainer endorsement or specification (clause f); 'Logo asset TBD'".

**Check rationale**

Check `maintainer-alive`, as currently written:

> Evidence: Repo facts: "last 5 default-branch commits" (dates and authors)
>
> Pass condition: At least 1 default-branch commit by a human (not `[bot]`), or a bot merging a human's PR, dated within 90 days of the capture date (live mode: today). The maintainer first-response sample does NOT decide this check (slow or missing replies there only lower the `fast-maintainer` preference).
>
> Weight: required

Why it has this form: the first version also required "at least 1 sampled issue got a maintainer (owner/member/collaborator) first response within 30 days." In run 1 that clause alone rejected four gold-accept issues. For issue-01, issue-09, and issue-16 the grader wrote "the only sampled maintainer first response is #16275 at 32.9 days (>30)". For issue-14 it wrote "no maintainer comment in thread", even though each of those repos had human commits 1 to 2 days before capture. The response sample is only 5 recently updated issues, and many of those were opened by the maintainers themselves or are only a day old, so it is too noisy to veto anything. Human commits within 90 days directly show someone is merging work. That is what a first PR needs, and it still catches the dead-repo issues (3/3 in both runs). The 90-day window is wide enough to survive a quiet month but not a stopped project. The excluded `[bot]` authors stop dependabot-only repos from looking alive.

**Trade-offs**

Dropping the response-time requirement from `maintainer-alive` gives up one case on purpose: a repo where maintainers still push their own commits but ignore outside issues and PRs. My rubric now accepts that repo even though a newcomer's PR might sit unreviewed. I accept that miss and partly cover it with the `fast-maintainer` preferred check (median first response of 7 days or less), which ranks such issues lower but cannot reject them. The live run shows it happening: Path Review itself grades `fast-maintainer` as "unclear" ("Only 2 maintainer comments across ~100 issues"). Under my old wording `maintainer-alive` would have rejected every Path Review issue for that reason, which would be wrong for a course repo where staff review PRs outside the issue threads.

Nothing else got worse, and I checked rather than assumed: the change could only flip issues that failed on the response-sample half. The run 2 full run shows the dead-repo category still at 3/3, and the 6 run 1 disagreements all flipped to agree while no previously agreeing issue changed (20/20).

---

## Selection rationale

Graded on whether all three are answered, in your own words. Not on how good the
reasoning is, and not on length — a short honest answer to each earns the full marks.
This is also the basis for the claim comment you write in Unit 2.

**Selection rationale**

<!-- DRAFT: rewrite these three answers in your own words before submitting. -->

1. **Fit:** #54 is a single Python bug in resume section detection: `_detect_sections()` anchors its patterns at the start of the line, so indented text returns nothing. Five xfail tests define "done", which suits my goal of getting better at tests, and the size fits the time I have this unit. It is backend Python rather than the frontend/API work I listed, but no accepted candidate was frontend.
2. **What the verdict got right / what I weighed:** It correctly saw that there is no assignee or open PR, that the repo is active (human commit on 2026-09-16), and that the bug is bounded. What the rubric can't weigh: how many classmates are on the same issue, and whether I can actually run the test suite locally. I also chose #54 over #64 because #64 is a one-string fixture change that a classmate has already planned out.
3. **Claiming difficulty:** The thread already has many classmate claim comments. The house rule says those don't block me, but I need to write a claim comment that adds something (my own repro) rather than another "can I take this". I also need to check for a linked PR again right before claiming, since a classmate's PR is what sank #57.

---

Related paths: `eval-run.txt` in this directory; your skill's files in
`tools/issue-select/`.
