# Rubric: is this reproduction package ready to post?

<!--
THIS IS THE PART YOU WRITE. The skill in SKILL.md executes whatever
checks you define here. It ships empty on purpose: the judgment is your
work.

A filled rubric must contain:

1. At least one row in the checks table. Each row needs all four
   columns:
   - Check: a short name (used in the output JSON).
   - Evidence: exactly what to look at, and where in the package. Name
     the part (the claim comment, the repro report's environment
     record, the artifacts read against the issue's description, the
     repo-facts block) or a location from your
     references/evidence-guide.md. "The report" is not a source; "the
     output excerpt read against the error the issue describes" is.
   - Pass condition: a decision rule about the OUTCOME that someone
     else could apply and get your answer. Judge the thing itself (does
     the artifact show the issue's behavior?), never the write-up's
     shape (how many steps it has, how long it is, whether it uses a
     template's headings). Structure-shaped checks are what make
     graders disagree with themselves.
   - Weight: `required` (a fail here holds the package) or `preferred`
     (never changes the verdict).

2. A verdict rule below the table: how the check grades combine into
   accept (ready) or reject (hold), including how `unclear` is
   treated. The verdict space is binary. If you write no rule for
   `unclear`, the skill treats it as fail.

Cover what actually gets bad packages posted. The lecture named the
proof families: the environment is recorded, the steps are complete
and followable, the behavior shown matches the issue (not an adjacent
one), the outcome is stated honestly (an evidenced cannot-reproduce is
a pass, a confident wrong-target is not), and the words respect the
repo's conventions. A rubric that ignores a family will fail eval
packages designed around that family.

## Checks

|Check|Evidence|Pass condition|Weight|
|-|-|-|-|
|os-version-recorded|the issue has written the os that the bug is noticed on, a clear release version number or commit hash, and version numbers of any tools involved in the issue<br />|if the os, tool versions, and release version or git hash are clearly written in the issue|required|
|steps-to-error|steps are recorded on how the user saw the bug|if the user posts clear steps from beginning to bug|required|
|error-codes|the issue includes any error codes the bug creates|if the issue includes what error codes, if any, the user saw|preferred|
|bug-description|the issue describes the consequence of a bug and how it affects the code/action,  as well as what the intended result is supposed to be<br />|whether the issue gives a description of how the bug affects the code/action and what the intended result is supposed to be<br />|preferred|

## Verdict rule

<!-- State how the grades above combine into accept or reject, and how
unclear is treated. Example shape (write your own): "accept if every
required check passes; preferred checks never change the verdict;



ready only if every required pass, preferred can fail and the issue still be a pass, just lower priority. ? count as failed

