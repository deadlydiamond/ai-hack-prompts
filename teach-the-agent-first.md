# My AI tester took 9 minutes and proved nothing. A week later: 1 minute, one real bug.

When an agent disappoints, most people swap the model. The fix was what it knows before it starts: a steps file instead of a script, a playbook, and a lessons file it writes itself.

Read the full hack, with context and what it is good for: https://www.omerbinsaleem.com/hacks/teach-the-agent-first/

## Steps

1. Steps, not scripts. The agent writes a short steps file for the ticket; one shared runner records the video and the screenshots. It never writes browser code again.
2. A playbook. Where things live in the app, what bites (the login flow, the slow pages, the modals), and how to report a result.
3. A lessons file. After every run the agent adds one line: what went wrong and what to do next time. The next run reads it first.
4. Selectors from the code, not from guesses. The agent reads the component before it clicks.
5. Judge the result on proof: a recording and a failing step, not a green log.

## Prompt to copy

```text
You test changes in a browser. Before you start, read PLAYBOOK.md (where things live, what bites, how to report) and LESSONS.md (one line per past mistake).
Write the test as a short steps file, not a script; the runner records video and screenshots. Take every selector from the component code.
Report: what you did, the screenshot of each step, and any bug with the exact step that failed. After the run, add one line to LESSONS.md: what went wrong, and what to do next time.
```

Tag: Agents · about 3 minutes · published 2026-10-18
