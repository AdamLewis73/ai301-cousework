# Evidence guide: where proof lives in a reproduction package

<!--
THIS IS THE PART YOU WRITE (new this week: Unit 1 handed you this file
finished; the scaffolding fades). The skill uses this guide as its map:
for every kind of proof a rubric check names, this file says WHERE to
find it in a package and WHAT GOOD LOOKS LIKE when you do.

Under each family heading below, write:

- Where it lives: the exact places to look. In an eval bundle (which
  section of the package: the issue context, the repo-facts block, the
  claim comment, the repro report and its parts). In live mode (where
  on GitHub or in the draft: the issue thread, the repo's docs, the
  student's draft comment).
- What good looks like: one or two sentences someone else could apply.
  Prefer observable conditions ("the versions named match what the
  issue targets, or the difference is called out") over adjectives
  ("environment is thorough").

A rubric check whose evidence this guide cannot locate is a check
nobody else can execute; the rubric swap showed you what that feels
like. Write the map you wish your grader had.
-->

## Environment

<!-- Where the environment record lives, and what a sufficient one
looks like against the issue's stated target. -->

- Where it lives: The Environment: line at the top of the repro report. Compare it with the issue's own Environment: line.

- What good looks like: It names the version and OS the repo's bug template asks for, and matches the issue's version or says why it doesn't.

## Steps

<!-- Where the reproduction steps live, and what makes them followable
by a stranger, starting state to trigger. -->

- Where it lives: The reproductions steps are in the repro-report. Compare against the reporter's steps in the issue context.

- What good looks like: It should clearly state steps to reproduce the issue from launch to the bug. The steps begin from a named clean state (fresh clone at a stated SHA, new virtual environment, empty config) and list every command or action in order, including setup like install, build, and fixture data, ending at the one step that triggers the behavior

## Behavior shown

<!-- Where the artifacts live (output excerpts, logs, screenshots),
and what it means for an artifact to show the issue's behavior rather
than an adjacent one. -->

- Where it lives: Either in the issue description or after the repro-report. 

- What good looks like: It should clearly state the output behavior (error message, failing function or ability, wrong value, etc.) and the repercussions on end result (compare expected vs actual). Compare against the error message and expected behavior in the issue context.

## Honesty

<!-- Where claims and their backing meet: how to tell a report that
says exactly what happened (including an honest cannot-reproduce) from
one that claims more than its evidence shows. -->

- Where it lives: The issue summary and the claims made throughout the description of the issue and its reporduction.

- What good looks like: Repoduction steps only appear when steps exactly match the output under stated conditions. Differing behavior is clearly stated. Validation only states what environment it was tested on (i.e. tested on Linux only doesn't become that it was validated on all computer OS platforms). Does not claim more than it shows. 

## Comms

<!-- Where the words meet the repo: the claim comment against the
issue, the comments against the repo's stated templates and
contribution policy (including AI-use disclosure requirements), and
what specific-and-honest looks like next to boilerplate. -->

- Where it lives: The claim comment, read against the issue context (labels, assignee, existing claims, linked PRs, maintainer replies) and the repo-facts block, such as CONTRIBUTING.md, issue and PR templates, code of conduct, claiming or assignment process, AI-use policy, etc.

- What good looks like: The comment follows the repo's stated claiming process. It states the outcome of reproducing the issue with the version or SHA and names well-defined next steps or specific questions. It also includes an AI-use disclosure in the form the repo's policy requires.





