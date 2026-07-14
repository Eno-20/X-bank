# 🏦 X-Bank — Learn Linux by Running a Bank

Welcome to **X-Bank**, a hypothetical bank that runs entirely on a Linux server — and you've just been hired as its systems team.

This is a hands-on Linux course. There are no abstract exercises here: every lab arrives as a **work ticket from Head Office**, and everything you type has a business consequence. Lock the vault wrong and money leaks. Miss a backup and the bank loses its books. Precision matters — banks do not tolerate "close enough."

## 🧰 Prerequisites

- A Linux environment: a native install, a virtual machine (Ubuntu recommended), or WSL2 on Windows.
- A terminal and a willingness to break things (you will — that's part of the course).
- No prior Linux experience required. Ticket #001 assumes you're starting from zero.

##  Getting Started

Clone this repository onto your Linux machine:

```bash
git clone https://github.com/Nerdymaxx/X-bank.git
cd X-bank
```

Then open your current ticket and get to work.

## 🗺️ How the Course Works

Each session follows the same loop:

1. **Concept brief** — a short introduction to the idea behind the ticket.
2. **Guided lab** — we build together.
3. **Solo ticket** — same skill, new scenario. You're on your own.
4. **Break-it round** — something in the bank gets sabotaged. You find it and fix it.

The course ends with **Incident Day**: a deliberately broken bank, a 90-minute window, and an incident report. Your command history is your audit trail — treat it that way from day one.

## 📋 Course Roadmap

| Ticket | Title | You'll Learn |
|--------|-------|--------------|
| #001 | Open the Branch | Filesystem navigation, directories, paths |
| #002 | Hire the Staff | Users, groups, sudo |
| #003 | Lock the Vault | Permissions, ownership, special bits |
| #004 | Keep the Books | Text processing: grep, awk, sort, pipes |
| #005 | Automate the Tellers | Bash scripting |
| #006 | Night Shift | Cron, backups, log rotation |
| #007 | The Bank Must Not Sleep | Processes, services, systemd |
| #008 | Remote Branch | SSH, remote file transfer |
| 🚨 | Incident Day | Everything, under intense pressure |

---

# 🎫 Work Ticket #001: "Open the Branch"

**From:** Head Office
**To:** New Systems Team
**Priority:** High — the branch opens Monday.

X-Bank has just leased a Linux server for its new branch. Head office has sent the official blueprint. Your first job: build the branch exactly as specified.

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
5. **Submit your evidence:** `tree /srv/bank` output plus your command history saved to a file called `ticket001_evidence.txt` in your home directory, push to github and submit your github link.

**Bonus:** rebuild the entire blueprint from scratch in **one single command**.

## Acceptance Criteria

- Structure matches the blueprint character-for-character.
- Account files contain the opening line.
- You can explain, out loud, the difference between the path you used in 4(b) and the one in 4(d).

---

*Stuck? Good. Read the error message — Linux is telling you exactly what's wrong. That's lesson zero.*
