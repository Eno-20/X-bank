# 🎫 UnigweBank — Work Ticket #001: "Open the Branch"

**From:** Head Office
**To:** New Systems Team
**Priority:** High — the branch opens Monday.

Welcome to UnigweBank. We've just leased a Linux server for our new branch. Head office has sent the official blueprint. Your first job: build the branch exactly as specified. Banks do not tolerate "close enough."

## The Blueprint

```
/srv/bank/
├── accounts/
├── vault/
├── transactions/
├── dropbox/
├── reports/
├── bin/
└── logs/
```

## Your Tasks

1. **Build the entire structure.** Every directory, exact spelling.
2. **Prove it:** install `tree` if you don't have it, and run `tree /srv/bank`.
3. **Open the bank's first three customer accounts** — create empty files `ACC1001.txt`, `ACC1002.txt`, `ACC1003.txt` inside `accounts/`, then put the line `OPENED: 2026-07-14` inside each one *without opening a text editor*.
4. **Navigation drill:** `cd` into `transactions/`. From there, in a single command each:
   - (a) print exactly where you are
   - (b) move to `reports/` using a **relative** path
   - (c) jump to your home directory
   - (d) return to `reports/` using an **absolute** path
5. **Submit your evidence:** `tree /srv/bank` output plus your command history saved to a file called `ticket001_evidence.txt` in your home directory.

**Bonus (for the ambitious):** rebuild the entire blueprint from scratch in **one single command**.

## Acceptance Criteria

- Structure matches the blueprint character-for-character.
- Account files contain the opening line.
- You can explain, out loud, the difference between the path you used in 4(b) and the one in 4(d).

---

<!-- ✂️ CUT HERE — everything below is for the instructor only -->

# 🔑 Instructor Notes (not for students)

## The Designed Ambush

`/srv` is owned by root. Their very first `mkdir` will fail with `Permission denied`. This is intentional — **do not warn them.** When they hit it, deliver the line:

> "Permission denied isn't an error. That's the bank's security doing its job. Your first lesson: Linux says no by default."

Then show `sudo` just enough to unblock them — full sudo/users theory is Ticket #002's territory, so keep it to "this is you showing your manager's badge."

## Answer Key Highlights

- **Bonus one-liner:** `sudo mkdir -p /srv/bank/{accounts,vault,transactions,dropbox,reports,bin,logs}` — brace expansion will blow their minds; save it for after they've done it the long way.
- **Task 3 without an editor:** `touch` + `echo "OPENED: 2026-07-14" > ACC1001.txt` (or `>>`). Watch for students who don't know `>` vs `>>` yet — plant that seed, it pays off in module 4.
- **Evidence:** `history > ~/ticket001_evidence.txt` — tell them their history is the bank's audit trail from day one. This habit sets up Incident Day.

## Break-It Round (end of session)

While they're on break, sabotage one machine — rename `vault` to `vualt` or delete `dropbox`. Announce: *"Head office audit found a discrepancy at one branch. Find it and fix it."* They must diff their `tree` output against the blueprint by eye. First taste of an incident.

## What They've Actually Learned When This Ticket Closes

Filesystem hierarchy, `mkdir -p`, `touch`, `echo`, redirection, `pwd`, `cd`, relative vs absolute paths, `sudo` as a concept, `history` — and, most importantly, that precision matters.
