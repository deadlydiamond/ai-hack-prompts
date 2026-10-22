# Lead a team of AI agents, not one chatbot

One lead you talk to, narrow agents that each do one job, and a gate in front of anything you cannot undo. This week the team got its own lanes, a QA runner, a rule book and a voice.

Read the full hack, with context and what it is good for: https://www.omerbinsaleem.com/hacks/lead-a-team-of-ai-agents/

## Steps

1. Split the work into roles: watch, investigate, doubt, build, review, test, guard.
2. Give every role exactly one job and a short prompt. A reviewer never writes code.
3. Put one lead on top that you talk to. It routes work and reports back.
4. Gate everything irreversible: pushes, merges and messages wait for your yes.

## Prompt to copy

```text
You are my team lead. You route work, own the gates and report; you never write code yourself.
Reply in the language I write in. Nothing is pushed, merged or sent to another person without my explicit yes.
When I ask what to focus on, read the watchers' notes and my open tickets and answer in five lines or fewer.
```

Tag: Workflow · about 5 minutes · published 2026-10-17
