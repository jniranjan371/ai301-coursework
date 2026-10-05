# Rubric: is this a good first issue?

## Checks

| Check | Evidence | Pass condition | Weight |
|---|---|---|---|
| Maintainer still around | Last 5 default-branch commits (repo-facts, or the commit list on the repo front page). Ignore pure bot authors unless the commit is clearly merging a human PR. | At least one human maintainer commit (or merge of a human PR) in the last 90 days, measured from capture date in eval / today in live. | required |
| Maintainers merge PRs | Same commit list: look for merge commits or PR-merge messages on the default branch. | At least one PR merge by a human in the last 90 days. | required |
| Repo not archived | `archived:` on the repo-facts line, or the archived banner on the repo page. | `archived: no` (or no archived banner). | required |
| Repo still ships / moves | `latest release` and `last push to any branch` in repo-facts (or Releases sidebar + newest commit date). | Latest release OR last push is within 180 days of capture/today. | required |
| Scope is one piece of work | Issue body + comment thread + linked PR history in repo-facts. | Asks for one bounded bug fix, feature, or docs task with a clear primary deliverable. Pass when the body lists a main page/change plus related pointer updates, optional "consider also" notes, or several causes/suggestions for the same bug — that is still one piece of work. Fail only if it's an explicit umbrella/tracking list of separate work items, a usage-only question, the thread is still arguing design with no maintainer decision, or the issue has years of unresolved design debate plus several abandoned (closed, unmerged) PRs. | required |
| Size fits a newcomer | Issue body, labels, and maintainer comments in the thread. | Assume newcomer-sized unless evidence says otherwise. Pass for docs that add one page and update a few related pointers, and for maintainer-diagnosed bugs that name causes or optional follow-ups (including perf/threading ideas). Fail only if a maintainer says the fix needs core/parser/architecture work, or the ask is clearly a codebase-wide rewrite across unrelated areas. Do not fail just because the writeup is long, lists multiple causes, or lacks a good-first-issue label. | required |
| Nobody has it | `this issue: assignees` and `linked PRs` in repo-facts, plus claim language in Comments ("I'll take this", "working on this", etc.). | No assignee, no open linked/mentioned PR, and no active unanswered claim. A closed unmerged PR alone does not fail this check (abandoned), but several abandoned PRs plus unsettled design debate fail under Scope above. | required |
| AI policy allows assistive use | `contribution policy` line under Repo facts (or CONTRIBUTING.md / AI policy files on the repo). | Pass if the policy is silent, or only requires disclosure / personal understanding / testing / human review. Fail only on an outright ban of AI-generated code or docs (e.g. "we do not accept AI-generated contributions"). | required |
| Maintainers answer issues | `maintainer first-response sample` in repo-facts (or a few recently updated issues on github.com). | At least half the sample issues get a first Owner/Member/Collaborator reply within 30 days (ignore "no comment yet" only if the issue is younger than 30 days). | preferred |
| People actually use it | Star count on the repo-facts line / repo page. | 100+ stars. | preferred |
| Labeled as newcomer-friendly | Issue labels. | Has a label like `good first issue` / `good-first-issue` / `beginner`. | preferred |

## Verdict rule

Accept only if every **required** check is `pass`. Preferred checks never flip the verdict; use them to rank issues you already accepted (more preferred passes = better pick). Treat `unclear` as `fail` — if you can't verify it, don't take it as a first issue.
