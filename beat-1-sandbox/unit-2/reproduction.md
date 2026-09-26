# Unit 2 — Claim and Reproduce

Path: `beat-1-sandbox/unit-2/reproduction.md`

Record of your claim and reproduction on the issue you chose in Unit 1, and of the
evaluation runs that produced `eval-run.txt`. This file is graded at the path above; a copy
kept anywhere else in the repository is not read.

Complete every labelled field below. Each is graded on its own; content placed under the wrong
label is not graded.

---

## Your identity upstream

**GitHub username**

AdamLewis73

---

## Posted upstream

**Claim comment**

https://github.com/codepath/pathreview-ai301-fa26-s3/issues/26#issuecomment-5841085676

I believe I can claim this issue. I will run this issue on master, reproduce the reported behavior, and report back.

**Reproduction comment**

https://github.com/codepath/pathreview-ai301-fa26-s3/issues/26#issuecomment-5841465703

Reproduced by running the app as the README describes. I recorded safety events in Redis in the format SafetyMonitor uses, and GET /health still returned "safety_events_last_hour": 0.

### Environment
Commit:	2f4e82f52efbcfcc57d65b3fa5348672163ca088 (main)
Version Numbers:  Windows 11 25H2 (10.0.26200.9445), Python 3.11.15, Docker Engine 29.3.1, GNU Make 4.3, Postgres 16.15, Redis 7.4.11,
ChromaDB 0.4.22, fastapi 0.141.1, starlette 1.7.0, uvicorn 0.54.0, redis 8.1.0, SQLAlchemy 2.1.1, asyncpg 0.31.0, pydantic 2.13.5, structlog 26.1.0

### Steps to reproduce
Set up and start the app with the README quick start:
```
git clone https://github.com/codepath/pathreview-ai301-fa26-s3
cd pathreview-ai301-fa26-s3
cp .env.example .env
docker compose up -d
make setup
make run
```
In a second terminal, call the health endpoint:
```
curl -s -w "\nHTTP %{http_code}\n" localhost:8000/health
```
Record three safety events: 2 × injection_attempt and 1 × pii_detected. Nothing in the app calls SafetyMonitor.log_event() yet, so this writes the counters directly, with the same keys log_event() increments (safety:events:<type>):
```
docker compose exec -T redis redis-cli INCR safety:events:injection_attempt
docker compose exec -T redis redis-cli INCR safety:events:injection_attempt
docker compose exec -T redis redis-cli INCR safety:events:pii_detected
```
Call the health endpoint again:
```
curl -s -w "\nHTTP %{http_code}\n" localhost:8000/health
```
### Expected
After step 3, safety_events_last_hour should reflect the recorded events (3 in total, or a per-type breakdown).

### Observed
Step 2, before recording any events:
```
{"detail":{"status":"unhealthy","dependencies":{"postgres":"unhealthy","redis":"unhealthy","vector_db":"healthy"},"safety_events_last_hour":0,"timestamp":"2026-09-26T00:05:07.168448"}}
HTTP 503
```
Step 3 printed 1, 2, 1, so the counters were written.

Step 4, after recording 3 events:
```
{"detail":{"status":"unhealthy","dependencies":{"postgres":"unhealthy","redis":"unhealthy","vector_db":"healthy"},"safety_events_last_hour":0,"timestamp":"2026-09-26T00:05:19.255192"}}
HTTP 503
```

## Eval iterations

Answer all four sections. Quote source text directly; paraphrase does not satisfy these
fields.

**Run history**

agreement: 18/20 scored items  (bar: 18/20: below the bar; category floor unmet: no match in disclosure)

**Package analysis**

pkg-19  reject  accept   NO     graded accept

I think my rubric read it this way because there is not AI policy stated. I don't have an AI policy in my rubric, because I assumed this would be run after the issue-select skill which does check for that.

**Check rationale**

"os-version-recorded	the issue has written the os that the bug is noticed on, a clear release version number or commit hash, and version numbers of any tools involved in the issue
	if the os, tool versions, and release version or git hash are clearly written in the issue	required"

I specifically changed this to include git hash. It reads that way because sometimes some repos don't have official software release versions, so if there are no release version numbers, it should state commit hash. Branch names are not good enough ("master", etc.) because if the issue sits stale for awhile, those branches could have multiple pushes that change how the issue behaves.

**Trade-offs**

[Every check gives something up. Any one of these is a complete answer: a package whose
result it changes, a canary you re-ran with `--only`, a case you accept it will miss, or a
stated reason nothing changed elsewhere. "Nothing changed, and here is how I know" earns
the point in full when the reason follows.]

I specifically did not include AI policy in this check because I believe this should be run after the issue-select command. This is something you run when you have selected your issue, so if you already checked for repo wide AI policy when selecting, you don't need to check again when working on it.

---

Related paths: `eval-run.txt` in this directory; your skill's files in
`tools/repro-check/`.
