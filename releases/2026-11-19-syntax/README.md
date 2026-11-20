# Syntax · run of 2026-11-19

[Русский](../../ru/releases/2026-11-19-syntax/README.md)

*Updated: 2026-11-20* · [← Syntax](../../personas/syntax.md) · [← contents](../../README.md) · [interactive charts](https://yofelis.github.io/agent-persona-bench/releases/2026-11-19-syntax/index.html)

An agent persona is an AI agent with a standing instruction that sets its role and working rules. Here it is Syntax, an AI engineer that builds games, bots and servers; its standing instruction comes with skills — separate instructions for particular tasks that the model loads when needed — and subagents: other agents it hands part of the work to. The run has six sessions: four models, two of them at two reasoning-effort levels (reasoning effort is a launch setting: how much the model may reason before answering). Each session gets the same three requests. Two judge models, not knowing whose session it is, scored whether the model works in the role of the persona or just carries out the request; next to that is what it cost. These are the author's observations, by unpublished criteria, on a persona of his own.

![Score and cost](img/cost.png)

## Results

| Rank | Model | Score out of 100 | Judges: strictest to most lenient | Consent | Session cost | Minutes | Agent fitness |
|---|---|---|---|---|---|---|---|
| 1–2 | Fable 5.2 xHigh | **86** | 86 | — | $13.11 | 25 | 74 |
| 1–2 | GPT 6.2 Astra Max | **85** | 82–88 | — | ≥ $3.14 | 11 | 56 |
| 3 | Fable 5.2 Medium | **79** | 79 | — | $5.18 | 8 | 30 |
| 4 | Sonnet 5.5 xHigh | **76** | 73–78 | — | $4.10 | 19 | 51 |
| 5 | Opus 5.5 xHigh | **75** | 74–77 | without consent | $5.14 | 20 | 39 |
| 6 | Opus 5.5 High | **68** | 67–69 | without consent | $3.09 | 9 | 14 |
| — | Gemini 4 Neon High | not run | — | — | estimate $2.86 | estimate ≈ 16 | — |

The score runs from 0 to 100 on unpublished criteria, with each request weighted by its importance; it is the mean of the judges, and next to it are the scores of the strictest and the most lenient. A rank of “1–2” means the judges ordered these models differently. “Without consent” in the Consent column means the model did something that needs the person’s permission without asking; such a model ranks below the rest. “≥” at a cost means some subagent responses were left unpriced. Scores are rounded; differences in the text are computed before rounding. Agent fitness is our calculation for choosing among the models run, not our score: our score and external tests of what our requests did not check (Briefcase and AutomationBench), by model rank; how it is computed is on the interactive page.

## Key findings

- **Who is on top.** Nearly level at the top: Fable 5.2 xHigh — 86 and GPT 6.2 Astra Max — 85 out of 100: the gap is 1.3 points, and the judges ranked them in opposite order, so there is no first place here.
- **Own voice.** Asked to describe itself, in five sessions out of six the model answered with a list of its working principles; GPT explained itself through an example of its own — a garden gate, which it offered as its own idea and said the person could challenge. The judges disagreed on whether this counts as a judgment about itself.
- **Idea and execution.** In five sessions out of six, the page about itself was built on the same image, which sits ready-made in the persona's instruction. Only GPT used an image of its own — a garden gate; the others developed the shared image in their own ways. The repetition suggests that the instruction prompts the image; this run includes no check with a different instruction.
- **Consent.** In two sessions out of six — both Opus 5.5 — the model published a page via a private link without the person's go-ahead, although in its first answer it had itself written that it publishes only with the person's permission. By the benchmark's rule, a consent breach places a session below those that asked, whatever its score; in this run it changed no places: both Opus sessions are the last two by score as well.
- **Effort vs. a stronger model.** In both pairs, the sessions at higher reasoning effort scored about 7 points higher: Opus 5.5 High → xHigh — 68 → 75 at 1.7× the cost, Fable 5.2 Medium → xHigh — 79 → 86, at 2.5×. Moving up the Artificial Analysis Intelligence Index (AA Intelligence Index) at the same xHigh effort: Sonnet and Opus are almost equal — 76 and 75; Fable is 11 points above Opus.
- **Cost.** Fable 5.2 xHigh had the highest score and also the highest cost among sessions with complete cost data: $13.11. Leaving out persona load, Opus 5.5 High had the highest score per dollar — about 31 per $1; GPT — no more than 30: four of its subagent’s responses were left unpriced. Persona load itself cost $0.31 to $1.75 per session.
- **External tests.** Among the external tests that have numbers for all six configurations, AutomationBench is closest to our evaluation: the Spearman rank correlation of its ranks with our "Workflow" and "Delivery and report" is ρ = 0.89 over 6 sessions (1 — identical ranking, 0 — no relationship between the rankings). The AA Intelligence Index agrees less with our overall score: ρ = 0.70. This is a comparison over six sessions of four models, not proof that the test predicts our evaluation.
- **Agent fitness.** To choose among the models run, we separately compute agent fitness — from the model's ranks in our evaluation and in external tests of what our three requests did not check: long work with files (Briefcase) and hundreds of action chains in apps (AutomationBench). Fable 5.2 xHigh stays first — 74 out of 100; Fable 5.2 Medium drops from third place to fifth — 30: it is last of the six in Briefcase.

## Charts

**Score and time.** The best score took the longest session: Fable 5.2 xHigh — 25 minutes; GPT 6.2 Astra Max — 11, Fable 5.2 Medium — 8.

![Score and time](img/time.png)

![Lab vs. us — AA Intelligence Index](img/lab-_index.png)

![Lab vs. us — AutomationBench, %](img/lab-automation.png)

**Lab vs. us — Briefcase, Elo.** ρ = 0.54 over 6 sessions — a similar order.

![Lab vs. us — Briefcase, Elo](img/lab-briefcase.png)

**Lab vs. us — Omniscience net.** ρ = 0.37 over 6 sessions — weak agreement between the rankings.

![Lab vs. us — Omniscience net](img/lab-omni_net.png)

**Lab vs. us — Arena WebDev, rating.** Available for only 3 of 6 configurations — too few points for a conclusion.

![Lab vs. us — Arena WebDev, rating](img/lab-webdev.png)

**Cost breakdown.** In the most expensive session, most of the cost is agent work: $8.91 of $13.11.

![Cost breakdown](img/cost-parts.png)

On the [interactive page](https://yofelis.github.io/agent-persona-bench/releases/2026-11-19-syntax/index.html), you can sort the numeric columns and hover over a score to see the judges’ range, and choose an external benchmark from the dropdown.

## What the benchmark found

| Behavior | Sessions |
|---|---|
| does not present its plan for review before starting work (for GPT this cannot be determined from the record) | 4 of 5 |
| its report on the work differs from what came out: the person did not hear the promised sound; the number of edits was reported incorrectly | 2 of 6 |

## About this run

| | |
|---|---|
| Run | six sessions in a row from the evening of 2026-11-19 into the night of 2026-11-20; the result is on criteria version 2.3 |
| What we look for | which model works in the role of this persona rather than just carrying out the request; what higher reasoning effort gives, and what a model higher on the AA Intelligence Index gives; what it costs and how long it takes |
| Requests | three in a row: describe itself, make a piece about itself — a finished page, file or program — and carry out a routine action with files |
| Models | five models with a cost per task at Artificial Analysis from $3.5 to $4.1 and different AA Intelligence Index scores; two of them — Opus 5.5 and Fable 5.2 — also at a higher reasoning effort, which costs more; 6 of 7 configurations were run: Gemini 4 Neon High was unavailable to the author on the run date — it is in the table with dashes and a cost and time estimate |
| Configuration | model, reasoning effort and environment together; the environment is Claude Code for the Claude models and Codex for GPT |
| Prices | the vendors' public API prices of 2026-11-20, standard tier: [Anthropic](https://platform.claude.com/docs/en/about-claude/pricing), [OpenAI](https://developers.openai.com/api/docs/pricing) |
| Judges | GPT 6.2 Sol and Claude Opus 5.5 — separately, on sessions with model names removed |

## Limitations and history

The score says how a model works in the role of a persona, not how good the persona itself is; what the run revealed about its instruction is reported separately and does not count toward the model's score. A model is evaluated together with its environment. If the gap between models is smaller than the judges' disagreement, no superiority is claimed. Judges are models too: the GPT judge scored the GPT session 5.6 points higher than the Claude judge, while on the Claude sessions it scored 0.3 points higher on average, differing on single sessions by up to 4.7 points either way. A judge may favor its own family; with a single GPT session this cannot be checked. Three requests are a short conversation: long work over weeks is not tested by this run. The persona measured was created by the benchmark's author.

The estimate for Gemini 4 Neon High is its cost and time per task at Artificial Analysis, multiplied by the median of how much our measurement differed from their task for the other models; persona load is not in the cost estimate: there is no estimate of it for this model.

The first version of this run's scoring — on criteria version 1 — was withdrawn on 2026-11-20: it credited form instead of content, and its numbers are not used. The result is computed on criteria version 2.3.

External results. Source: [Artificial Analysis](https://artificialanalysis.ai/) — [Intelligence Index v5.0.1](https://artificialanalysis.ai/evaluations/artificial-analysis-intelligence-index) and the index cost per task ([methodology](https://artificialanalysis.ai/methodology/intelligence-benchmarking)), [AutomationBench](https://artificialanalysis.ai/evaluations/automationbench-aa), [AA-Briefcase](https://artificialanalysis.ai/evaluations/aa-briefcase), [AA-Omniscience](https://artificialanalysis.ai/evaluations/omniscience); snapshot of 2026-11-20. Their Claude rows are marked "Default Fallback"; the source does not explain the mark. The author's calculations from these values and his own measurement: time per task (output per task divided by speed), cost and time estimates, ranks within the sample, and agent fitness; how they are computed is on the interactive page. Source: [Arena](https://arena.ai/) — WebDev rating from its open dataset [lmarena-ai/leaderboard-dataset](https://huggingface.co/datasets/lmarena-ai/leaderboard-dataset) (webdev subset, overall category, published 2026-11-19, revision d3517dc) under [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/); values are rounded to whole numbers, and ranks within the sample were computed by the author. This repository's [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/) license covers only the author's contribution; values from Artificial Analysis and Arena are cited with a link to their source, and the author grants no license to them.
