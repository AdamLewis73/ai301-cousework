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

https://github.com/codepath/pathreview-ai301-fa26-s3/issues/61

**Verdict output**

[Your skill's live-mode output for this issue, pasted verbatim and ending with the
fenced JSON verdict block. A summary does not satisfy this field.]

**The verdict must record `accept` for this issue.** Choose an issue your own skill
accepts. If your skill rejects every candidate you try, that is a signal about your
rubric rather than about the issues: revise it and re-run — retries are unlimited and a
partial re-run costs about $0.20 — or run the skill on different candidates. Output
recording `reject` for the issue you chose earns no credit for this field.

```
{
    "item": "https://github.com/codepath/pathreview-ai301-fa26-s3/issues/61",
    "checks": [
      {"name": "maintainer_active", "grade": "pass", "evidence": "Aburke225 (COLLABORATOR) committed to main 2026-09-16 and 2026-08-24; today is 2026-09-18"},
      {"name": "ai_policy", "grade": "pass", "evidence": "docs/CONTRIBUTING.md and PULL_REQUEST_TEMPLATE.md contain no AI restriction; no AI_POLICY file in repo tree"},
      {"name": "unclaimed_issue", "grade": "pass", "evidence": "assignees: [] and no comments on the issue"},
      {"name": "issue_in_use", "grade": "pass", "evidence": "closedByPullRequestsReferences empty; repo has 0 PRs in any state; timeline shows only label events"},
      {"name": "bounded_issue", "grade": "pass", "evidence": "One-file fix: health.py runs db.execute(\"SELECT 1\") and needs sqlalchemy.text(); issue gives repro steps and the exact ArgumentError"}
    ],
    "verdict": "accept"
  },
```

---

## Eval iterations

Quote source text directly in each field below. Paraphrase does not satisfy them.

**Run history**
Run 1:
categories: claimed 4/4  clear-accept 8/8  dead-repo 3/3  policy 0/1  scope 2/4
agreement: 17/20 scored items  (bar: 18/20: below the bar; category floor unmet: no match in policy)

Run 2:
categories: claimed 4/4  clear-accept 3/8  dead-repo 3/3  policy 1/1  scope 3/4
agreement: 14/20 scored items  (bar: 18/20: below the bar)

Run 3:
categories: claimed 4/4  clear-accept 8/8  dead-repo 3/3  policy 1/1  scope 2/4
agreement: 18/20 scored items  (bar: 18/20: PASS)

**Issue analysis**

item      gold    verdict  agree  note
issue-06  accept  reject   NO     failed: ai_policy
Reasoning: the repo did not have an AI policy which threw off my rubric that was expecting one so it just went ahead and failed it

**Check rationale**

[One check from the `rubric.md` uploaded to `tools/issue-select/`, quoted as it is
currently written, with the reasoning behind its current form.]
"|unclaimed\_issue|whether someone is already assigned|no one assigned|required|"
Reasoning: Checks whether someone is already assigned and rejects if they are, so that you don't overlap work and step on the toes of another contributor.

**Trade-offs**

The check has a trade-off of rejecting issues with someone assigned who isn't actually working on it, but it's better safe than sorry.

---

## Selection rationale

Graded on whether all three are answered, in your own words. Not on how good the
reasoning is, and not on length — a short honest answer to each earns the full marks.
This is also the basis for the claim comment you write in Unit 2.

**Selection rationale**

[Answer all three:

1. The issue's fit to your interests and to the time available.

It's a generally okay fit. I've worked in SQL before in the past. The issue seems rather straight forward

2. What the verdict identified correctly, and what you weighed that the rubric could
   not.

The verdict identified it as a bounded issue. I weighed the difficulty of the issue to me, since the rubric can't exactly decide something subjective like that.

3. The anticipated difficulty in claiming it.

It sounds like a simple fix, and I don't expect difficulty.

]



---

Related paths: `eval-run.txt` in this directory; your skill's files in
`tools/issue-select/`.
