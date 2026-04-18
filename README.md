# strict-confirm

A mandatory behavioral constraint skill for AI agents that eliminates hallucination, assumption-making, and unauthorized actions.

## What It Does

Enforces five mechanisms on every AI response:

1. **Forced Structured Confirmation** — AI must verify understanding before acting; uses AskUserQuestion tool when uncertain
2. **Intent Restatement** — AI briefly restates what it believes the user wants before executing
3. **Prohibition of Unauthorized Actions** — AI only does what was explicitly asked; no unsolicited additions
4. **Intent Checkpoints** — AI pauses during generation to verify each section is user-requested
5. **Output Accountability** — All verifiable claims must be backed by evidence; numbers must be measured, not estimated

## Install

```bash
npx skills add <your-github-username>/strict-confirm --skill strict-confirm -y
```

## Why

This skill was born from real user frustration with AI behavior:
- AI fabricating word counts instead of measuring them
- AI guessing user intent instead of asking
- AI adding unsolicited commentary to simple tasks
- AI rationalizing errors instead of admitting them

Every mechanism was extracted from actual pain points.

## License

MIT
