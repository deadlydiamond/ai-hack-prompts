# Your team's questions already have answers. Give them a command.

Every week the same four questions hit the team channel. The answers were already in Jenkins, GitLab, the gateway and Jira. Four read-only commands now answer them in seconds.

Read the full hack, with context and what it is good for: https://www.omerbinsaleem.com/hacks/jarvis-commands/

## Steps

1. Read a month of your team channel and list the questions that come back every week. Ours: is my fix deployed, what can merge, does the gateway route this endpoint, what is in the release.
2. For each one, find the tool that already knows the answer. Build history knows what is deployed, the merge requests know what is approved, the gateway config knows its routes, the tracker knows the release.
3. Make each answer a read-only command: /deployed, /mergequeue, /gatewaycheck, /releasenotes. Read-only means anyone can run it and nothing can break.
4. Post the answer in the channel, not in a private reply, so the whole team sees it once instead of asking again.
5. Tag people by name only when the line is theirs, like the author of a merge request that is ready.

## Prompt to copy

```text
Read the last 30 days of our team channel. List every question that was asked more than twice, with how often and who answered it.
For each one, name the tool that already holds the answer (CI, merge requests, API gateway, issue tracker) and the exact data the answer needs.
Then propose one read-only Slack command per question: its name, its input, and a sample answer in three lines or fewer. Nothing in it may write, merge or deploy.
```

Tag: Workflow · about 3 minutes · published 2026-10-15
