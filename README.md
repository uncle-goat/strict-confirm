# strict-confirm

A mandatory behavioral constraint skill for AI agents that eliminates hallucination, assumption-making, and unauthorized actions.

## What It Does

Enforces six mandatory mechanisms on every AI response:

1. **Forced Structured Confirmation** — AI performs a two-question internal check before any action; uses AskUserQuestion tool when uncertain
2. **Pre-Decision Requirement Confirmation** — AI uses AskUserQuestion tool to confirm requirements before executing, with suggestions and risk reporting
3. **Pre-Execution Double Confirmation and Backup** — AI asks user one more time before executing; makes file backups; re-asks if new uncertainties arise
4. **Execution Discipline** — AI strictly follows the plan; no unauthorized additions; "finishing touches" must be confirmed with user first
5. **Output Accountability** — All verifiable claims must be backed by evidence; numbers must be measured, not estimated; errors must be corrected, not just acknowledged
6. **Timeout and Skip Handling** — AI must verify if a skipped question was intentional or a timeout; stops replying only after user skips twice

Plus general rules and supplementary rules:

- **Stop replying conditions:** Only three valid reasons — external causes, user skips twice, or task completed with user confirmation
- **User cancels confirmation flow:** Graceful degradation when user says "stop asking"
- **Multi-step task simplification:** Full flow on first step, simplified flow on subsequent steps
- **Custom rule persistence:** User-set rules persist until explicitly cancelled; AI may proactively suggest cancellation if a rule seems harmful
- **Queue transparency:** AI informs user of remaining question count when multiple questions are pending
- **One question per call:** Always ask only ONE question per AskUserQuestion call to avoid timeout

## Install

```bash
npx skills add uncle-goat/strict-confirm --skill strict-confirm -y
```

## Why

This skill was born from real user frustration with AI behavior:
- AI fabricating word counts instead of measuring them
- AI guessing user intent instead of asking
- AI adding unsolicited commentary to simple tasks
- AI rationalizing errors instead of correcting them
- AI stopping replies prematurely without user permission
- AI deciding user "confirmed" without actual affirmative selection

Every mechanism was extracted from actual pain points.

## License

MIT
