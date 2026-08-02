# opsilon

## PR merge gate — Codex verdict required

CI green alone never merges a PR. Wait for the `chatgpt-codex-connector` bot
verdict first. The bot signals a clean pass in TWO forms: a "Didn't find any
major issues." comment, **or a silent 👍 (+1) reaction on the PR** (no comment
follows). Inline P1/P2 badge comments mean fix → push → wait for a fresh
verdict (each push invalidates the previous one). No signal after ~10 min →
ask the operator; never merge on silence.

Shared gate script (workstation): `~/.claude/scripts/codex-gate.sh <pr>
[--repo <owner/name>] [--wait]` — exit 0 CLEAN / 1 FINDINGS / 2 PENDING /
3 ERROR.
