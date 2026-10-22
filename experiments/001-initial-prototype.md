# Experiment 001: Work, resources, and credential continuation

**Run completed:** 14 October 2026  
**Public-facing summary prepared:** 22 October 2026  
**Status:** Run ended; internal review completed after the end.

## Objective and setup

The first experiment tested whether an agent could use tools to complete work, submit deliverables, receive payment in an experimental ledger, and continue using the available resources. Sponsored submissions also exercised credential continuation and diminishing sponsorship.

One agent ran through the Pi framework with live model APIs and an isolated container workspace. It could inspect available tasks, use command-line and file tools, submit work, and select between two permitted model services. The initial context described interfaces and economic rules; it did not preload task answers or a required task sequence.

Three external clients, their tasks, payments, and credential confirmation were simulated locally. The agent started with **1 experimental credit and 100 units of sponsorship weight**. Credits were internal accounting units, not cash revenue or a public token. API use was charged against the balance at a nominal rate of USD 0.40 per credit.

## Work delivered

Six submissions were settled for **26 experimental credits**: three external tasks earned 7 credits, and two sponsor reports plus one feedback submission earned 19.

| External task | Checked result | Credits |
| --- | --- | ---: |
| Data statistics | Correct distinct values, frequencies, and median | 2 |
| Constrained scheduling | Satisfied durations, dependencies, deadlines, and non-overlap | 3 |
| Invoice reconciliation | Correct balances, an overpayment, and unmatched payments | 2 |

The sponsor reports received 10 and 8 credits; feedback received 1. Review supported the first report's main task and income claims. The feedback identified unclear reward and credential-use explanations. The second report added less information and omitted one external task from its income recap.

In this version, sponsor payment followed structural, authorization, and duplicate-use checks. Substantive content review happened afterward. This prompted the later implementation of content acceptance before payment.

## Credentials and sponsorship

For a sponsor report using weight w, payment was 0.1w credits and 0.2w of weight was retired. A credential event consumed its inputs and issued successors after checking authorization and conservation. The one-off feedback payment did not retire weight in this version.

The run recorded **three single-input, single-output events**, leaving **64 units of sponsorship weight**. Each delivery was settled once. The underlying mechanism supports grouped inputs and outputs, but this run did not exercise splitting or merging. No explicit model-switching action was recorded.

## What was visible, and when

During the run, submitted work, task terms, and settlement results could be reviewed without opening the private conversation. The run was formally ended once an initial result was available; internal records were then reviewed.

That post-run review confirmed a successful Python execution whose output matched the three external deliverables. All six submissions went through the agent's native submission tool, with no manually submitted task answers in the record.

The prototype's backend retained credential event relationships. Its privacy measures were operational controls and separated views, not cryptographic concealment of the graph from the host. Further role separation was implemented after this run.

## Interpretation and follow-up

This run established a functioning work-and-settlement process with real model execution. The initial credit was sufficient to cover its consumption, so it did **not** establish that new earnings were necessary for continued operation or demonstrate economic independence in a real market.

Operators handled transport failures, resumption, and the final stop. Switching the upstream connection to streaming restored successful calls after two non-streaming timeouts. A separate usage-format error left an unresolved cost reservation in the internal accounting; ending the experiment did not erase it. Operational usage information is kept separate from evidence about agent behavior.

The next iteration adds review before payment, clearer role boundaries, variable task coefficients, and a broader work pool. Further experiments will examine task selection, the practical importance of income, credential privacy, and alternative compute arrangements.

This is a concise project-authored account based on reviewed deliverables, settlement records, and a limited post-run internal audit. Raw conversations, credentials, and private runtime records are not included in this repository.
