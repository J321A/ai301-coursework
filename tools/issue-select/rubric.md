# Rubric: is this a good first issue?

<!--
THIS IS THE PART YOU WRITE. The skill in SKILL.md executes whatever checks
you define here. It ships empty on purpose: the judgment is your work.

A filled rubric must contain:

1. At least one row in the checks table. Each row needs all four columns:
   - Check: a short name (used in the output JSON).
   - Evidence: exactly what to look at, and where. Name the source
     (repo-facts block, issue body, comment thread, or the locations in
     references/evidence-guide.md). "The repo" is not a source; "the last
     5 default-branch commit dates" is.
   - Pass condition: a condition someone else could apply and get your
     answer. Prefer thresholds with numbers ("a maintainer commented
     within 30 days") over adjectives ("maintainer is responsive").
   - Weight: `required` (a fail here rejects the issue) or `preferred`
     (never changes the verdict; a nice-to-have that helps rank the
     issues you accept).

2. A verdict rule below the table: how the check grades combine into
   accept or reject, including how `unclear` is treated. The verdict
   space is binary. If you write no rule for `unclear`, the skill treats
   it as fail.

Cover what actually kills first contributions. The lecture named four
families: the maintainer is alive, the repo is in use, the scope fits a
newcomer, and nobody else is already on it. A rubric that ignores a family
will fail eval issues designed around that family.
-->

## Checks

| Check | Evidence | Pass condition | Weight |
|---|---|---|---|
| maintainer-alive | Repo facts: "last 5 default-branch commits" (dates and authors) | At least 1 default-branch commit by a human (not `[bot]`), or a bot merging a human's PR, dated within 90 days of the capture date (live mode: today). The maintainer first-response sample does NOT decide this check (slow or missing replies there only lower the `fast-maintainer` preference). | required |
| repo-in-use | Repo facts: "archived:" flag, "last push to any branch", "latest release" | `archived: no` AND last push within 180 days of the capture date. A missing or old release alone does not fail this check. | required |
| bounded-scope | Issue body plus comment thread | Passes when the work asked for is one concrete change (a bug fix, a small feature, a doc/test addition), even when the body is short or has no repro steps. A single bug whose report names several causes or optional follow-up ideas is still one change (fixing the reported problem). Fails on ANY of: (a) the body says it is an umbrella/tracking/meta issue, or explicitly asks for its items to be split into separate PRs; (f) it is a new user-facing feature or behavior change (not a bug fix, doc, or test) that no maintainer (owner/member/collaborator) has endorsed or specified in the thread, so a product decision is still open; (b) the comments show the design or approach is still being argued and no maintainer has stated the approach to take; (c) a maintainer says the fix requires changes to core internals, a rewrite, or a breaking API change; (d) it is a usage/support question, not a request for a change; (e) 2 or more closed, unmerged PRs have already attempted it. | required |
| not-claimed | Repo facts "this issue: assignees:" and "linked PRs:", plus the comment thread (PRs mentioned, claim comments) | Fails on ANY of: (a) the issue has an assignee; (b) an OPEN PR is linked or mentioned in the comments as addressing this issue; (c) someone posted a claim ("I'll take this", "working on this", "can I work on this") within the last 30 days before capture and a maintainer accepted it or did not refuse it. A claim older than 30 days with no PR and no follow-up from the claimer is abandoned and does not fail. Closed/unmerged PRs do not fail this check (see bounded-scope). Live mode in Path Review: apply the scope.md house rule, so other students' claim comments do not fail this check. | required |
| ai-policy-allows | Repo facts "contribution policy" line (live: CONTRIBUTING.md, AI_POLICY.md / AI_USAGE_POLICY.md, PR template) | Fails only on an outright ban on AI-generated or AI-assisted contributions (for example "we do not accept AI-generated code" or "fully AI-generated contributions are rejected" with no assisted-use exception). Conditions (disclose, understand, test, human review) pass. No policy stated passes. | required |
| newcomer-label | Issue labels | Has a label like `good first issue`, `help wanted`, `beginner`, or `easy`. | preferred |
| fast-maintainer | Repo facts "maintainer first-response sample" | Median first response of the 5 sampled issues is 7 days or less. | preferred |

## Verdict rule

Accept if every `required` check passes. Reject if any `required` check
fails. An `unclear` grade on a required check counts as fail, except
`ai-policy-allows`, where the absence of any policy text counts as pass
(silence is not a restriction). Preferred checks never change the
verdict; they only rank accepted issues.
