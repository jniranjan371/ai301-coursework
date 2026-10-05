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

https://github.com/codepath/pathreview-ai301-fa26-s3/issues/11

**Verdict output**

Verdict: accept. Issue #11 passes all required checks.

- Maintainer still around: pass — Aburke225 human commits on 2026-09-16
- Maintainers merge PRs: pass — ascherj merged PR #176 on 2026-07-18 (within 90 days of 2026-10-04)
- Repo not archived: pass — archived: no
- Repo still ships / moves: pass — last push 2026-09-16 (within 180 days)
- Scope is one piece of work: pass — one docs section in docs/ARCHITECTURE.md
- Size fits a newcomer: pass — ~2–3 hours; good first issue / tier-1
- Nobody has it: pass — no assignee, no linked PR; classmate comments ignored per Path Review house rule
- AI policy allows assistive use: pass — no ban stated (silence passes)
- Maintainers answer issues (preferred): unclear — no maintainer reply sample on this thread
- People actually use it (preferred): fail — ~6 stars
- Labeled as newcomer-friendly (preferred): pass — good first issue

```json
{
  "item": "https://github.com/codepath/pathreview-ai301-fa26-s3/issues/11",
  "checks": [
    {"name": "Maintainer still around", "grade": "pass", "evidence": "Human commits by Aburke225 on 2026-09-16 (within 90 days of 2026-10-04)"},
    {"name": "Maintainers merge PRs", "grade": "pass", "evidence": "ascherj merged PR #176 on 2026-07-18 (within 90 days)"},
    {"name": "Repo not archived", "grade": "pass", "evidence": "archived: no"},
    {"name": "Repo still ships / moves", "grade": "pass", "evidence": "No release, but last push 2026-09-16 (within 180 days)"},
    {"name": "Scope is one piece of work", "grade": "pass", "evidence": "One docs section: hybrid retrieval scoring formula, default weights, and an example in docs/ARCHITECTURE.md"},
    {"name": "Size fits a newcomer", "grade": "pass", "evidence": "Estimated 2-3 hours; labels include good first issue, docs, tier-1"},
    {"name": "Nobody has it", "grade": "pass", "evidence": "Assignees: none; linked PRs: none. Classmate investigation comments ignored per Path Review house rule"},
    {"name": "AI policy allows assistive use", "grade": "pass", "evidence": "No AI ban stated; silence passes"},
    {"name": "Maintainers answer issues", "grade": "unclear", "evidence": "No maintainer first-response sample shown for this thread (preferred; does not flip verdict)"},
    {"name": "People actually use it", "grade": "fail", "evidence": "~6 stars (preferred; under 100)"},
    {"name": "Labeled as newcomer-friendly", "grade": "pass", "evidence": "Labels include good first issue and tier-1"}
  ],
  "verdict": "accept"
}
```

---

## Eval iterations

Quote source text directly in each field below. Paraphrase does not satisfy them.

**Run history**

1. First full run with an early rubric (no AI-policy check; stricter scope/size): `agreement: 16/20 scored items (bar: 18/20: below the bar; category floor unmet: no match in policy)`. Misses: issue-01, issue-12, issue-15, issue-19.
2. Revised rubric (added AI-policy check; loosened docs/size; tightened stale design + abandoned PRs). Cheap `--only issue-01,issue-12,issue-15,issue-19` then `--only issue-01,issue-19` until those matched gold.
3. Confirming full run written to `eval-run.txt`: `agreement: 18/20 scored items (bar: 18/20: PASS)` with `categories: claimed 4/4 clear-accept 8/8 dead-repo 3/3 policy 1/1 scope 2/4`. Remaining disagreements: issue-15 and issue-20 (gold reject, graded accept).

**Issue analysis**

issue-12. Gold label: reject. Rubric's decision: reject. Reasoning: the issue looked good on all other fronts, but BookWyrm does not accept AI-generated code or documentation. The `AI policy allows assistive use` should fail when repo disallows AI, so the verdict is reject even though every other check would pass. 

**Check rationale**

From `tools/issue-select/rubric.md`:

> | AI policy allows assistive use | `contribution policy` line under Repo facts (or CONTRIBUTING.md / AI policy files on the repo). | Pass if the policy is silent, or only requires disclosure / personal understanding / testing / human review. Fail only on an outright ban of AI-generated code or docs (e.g. "we do not accept AI-generated contributions"). | required |

I added this after the first full run scored `policy 0/1`.. Without it, a “perfect” first issue in a repo that bans AI work would still be accepted. Check only blocks hard bans, and treats silence as a pass.

**Trade-offs**

This check is what turns issue-12 from a wrong accept to a correct reject. The trade-off is intentional narrowness: repos that require disclosure still pass and repos that discourage ai contributions might still pass. 
---

## Selection rationale

Graded on whether all three are answered, in your own words. Not on how good the
reasoning is, and not on length — a short honest answer to each earns the full marks.
This is also the basis for the claim comment you write in Unit 2.

**Selection rationale**

1. Fit / time: #11 is a small docs change in one file (`docs/ARCHITECTURE.md`), labeled good first issue / tier-1. It will probably  take about 2-3 hours, a few hours to understand the task & a few hours to complete the task. This is a task that is completable without having to understand the entire system's architecture.
2. What the verdict got right / what I weighed: The skill correctly saw limited scope/ good for a first issue, no assignee/linked PR, and an accept under Path Review house rules. I would prefer to write code for my first task, but I am ok with contributing documentation before I get more familiar with the repo. 
3. Claiming difficulty: The hardest part will probably be writing a clear section that matches the actual formula and weights in rag/retriever/hybrid.py

---

Related paths: `eval-run.txt` in this directory; your skill's files in
`tools/issue-select/`.
