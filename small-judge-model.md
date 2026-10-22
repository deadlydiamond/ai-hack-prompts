# Put a 0.25 second judge in front of your AI agents

Big models do the work. Around that work sit hundreds of small yes-or-no questions a day. A small judge model answered 116,097 of them in 20 days, in a median of 245 ms, and only acts alone above a confidence gate.

Read the full hack, with context and what it is good for: https://www.omerbinsaleem.com/hacks/small-judge-model/

## Steps

1. List the small questions your agents answer with a full model run today: is this message asking me to stop, did this change cause this bug, which model should answer this. Each is a yes or no, a pick, or a score.
2. Put a small judge model in front of them. It answers a typed question with a probability in about a quarter of a second, instead of 5 to 14 seconds for a big model.
3. Set a confidence gate. Above 0.9 the judge acts alone. Below it, or when it is down, the old rule decides. Nothing new can break.
4. Keep the dangerous words on the strong model. Merge, prod, deploy and release always go to the big model, after the judge once sent a merge-to-prod to the small one and missed that the work was already merged.
5. Log every decision with its probability for 20 days, then read where it paid and where it was wrong before widening it.

## Prompt to copy

```text
Read my agent code and list every place a large model answers a yes/no, a pick-one, or a score question. For each: the question, how often it runs per day, and what a wrong answer would cost.
Propose which of them a small judge model could answer with a probability, the confidence gate above which it may act alone, and the fallback rule below the gate. Keep merge, deploy, production and release decisions on the strong model, always.
```

Tag: Agents · about 4 minutes · published 2026-10-19
