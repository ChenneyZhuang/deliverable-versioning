---
name: deliverable-versioning
description: |
  Keep deliverable files trustworthy over time: once a file has been sent it
  is immutable — new content becomes a new dated file; names carry date and
  content instead of the word final; one authoritative delivery directory per
  project holds what actually went out; a ledger ties date, filename, count,
  and recipient; and before building a new version the existing files are
  checked first. Use when sending spreadsheets, reports, or documents to a
  client or stakeholder, fixing a folder full of FINAL/FINAL2/final_v3 files,
  answering "which version did we send them", or setting up a new project's
  output structure.
  触发词：交付版本 / 文件命名 / 哪个是最终版 / 版本管理。
license: MIT
metadata:
  version: "0.1.0"
---

# Deliverable Versioning: sent means immutable

A folder of `FINAL`, `FINAL_v2`, and `FINAL_really` files means nobody trusts
any of them. The fix is mechanical: immutability after sending, dates over
the word final, one authoritative directory, and a ledger that answers
"what did we send" as a lookup instead of an archaeology dig.

## Rules

1. **Sent means immutable.** A file that has left your hands keeps its bytes:
   new content becomes a new file, and the sent one stays exactly as
   received. Editing a sent file in place destroys the only proof of what the
   recipient actually saw.
2. **Dates beat final.** Names carry date and content
   (`proposal_2026-09-14.xlsx`); the word final is retired as a name — it
   always gets violated, and each violation costs the name's meaning.
3. **One authoritative delivery directory per project.** It holds exactly
   what went out; drafts and working files live elsewhere. The directory,
   not chat history, is the source of truth for "what did we send".
4. **Ledger the sends.** One row per send: date, filename, item count,
   recipient. The ledger and the directory must reconcile: every sent file
   has a row, every row names a file that exists.
5. **Check before building.** Before producing a new version, look in the
   delivery directory: rebuilding an existing deliverable creates a second
   source of truth, and the second one is always the wrong one.
6. **Supersede with a trace.** A replaced file stays in the directory and is
   marked superseded in the ledger with a pointer to its replacement;
   documents that referenced the old file get their references updated.

## Steps

1. **Establish the directory and ledger.** One delivery directory per
   project, one ledger file beside it, with the row shape: date, filename,
   count, recipient, status (current / superseded → pointer).
   Done when: both exist and the ledger header states the row shape.
2. **Sweep the backlog.** List existing deliverable files; for each, record
   or reconstruct its ledger row from filenames and send history; flag
   ambiguous ones (same name, different dates; two files claiming final).
   Done when: every existing file has a row or an explicit ambiguity flag.
3. **Name and send.** New deliverables get date+content names, land in the
   delivery directory, and get their ledger row the moment they are sent.
   Done when: the sent file exists in the directory and its row reconciles
   with the send.
4. **Revise by new file.** Changes to a sent deliverable become a new dated
   file with a supersede row pointing back; references are updated to the
   new name.
   Done when: the old file is untouched, the new file exists, and the
   supersede pointer is recorded.

## Done when

The project has one delivery directory whose contents match the ledger, sent
files have kept their bytes, names carry dates instead of final, and "what
did we send, to whom, when, how many" is answerable from the ledger alone.
