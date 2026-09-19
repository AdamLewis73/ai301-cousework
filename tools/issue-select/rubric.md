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

## Checks

|Check|Evidence|Pass condition|Weight|
|-|-|-|-|
|maintainer\\\_active|the maintainer's activity and whether they have been active in the comments or has merged anything in the last six months|if the maintainer has been active in the last 6 months|required|
|ai\\\_policy|the ai usage policy of the repo| the repo explicity states in its docs that it allows ai to be used or they have no policy banning AI use|required|
|unclaimed\_issue|whether someone is already assigned|no one assigned|required|
|issue\\\_in\\\_use|the existence of PRs linked to the issue|no PRs are linked to the issue|unclear|
|bounded\\\_issue|the scope of the issue and whether it is a straight-forward task that has a definitive goal of success based on the description and issue comments|the issue is properly bounded|preferred|

## Verdict rule

<!-- State how the grades above combine into accept or reject, and how

unclear is treated. Example shape (write your own): "accept if every

required check passes; preferred checks never change the verdict, they




Accept if every required passes. Preferred don't change verdict but rank accepted issues based on the boundedness of the issue. Unclear is fail depending on the activity of the linked issue; if the issue has a linked PR but was never merged and hasn't been actively worked on in the last 30 days, then this counts as a pass as long as the required checks pass.

