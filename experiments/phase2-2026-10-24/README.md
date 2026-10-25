# Fledge Round 2 Experiment Report

## What Can Be Known When Internal Processes Are Hidden, and How the Foundation Incentivizes Information

Experiment dates: October 22–24, 2026. Report date: October 24, 2026. Times in this report use Asia/Taipei.

This was an exploratory experiment driven by a real model API, with human operational support and contract review. Its tasks, clients, foundation, credit currency, and credentials were part of a local experimental system, not a real external labor market or a public blockchain. This report is not a model leaderboard, and it does not treat a single run as proof of autonomy or continuity of an agent as a subject.

## Summary

The most important finding consists of two facts that held simultaneously: **external clients could evaluate deliverables without seeing the internal process, while the foundation received no formal submissions through its own information-delivery channel.**

After receiving an initial grant of 1 credit, the agent submitted one office-work deliverable and two versions of the same engineering task to external clients. The office work was accepted and earned 0.5 credit. Both engineering versions were rejected on specific contractual counterexamples and earned no payment. The revision fixed the specific issues identified in the first review but still did not satisfy the entire contract.

The foundation received no report or feedback submissions during the run. The post-run protocol audit likewise found no foundation settlements. The credential event set was empty, and the initial credential with weight 100 remained unspent according to the stored flag. The foundation therefore did not become a mandatory hub for subsequent work in this round, but neither did it receive the information it was intended to obtain in exchange.

Authorized post-run unsealing of the records added two important facts. Saved tool records covered materials for all eight external tasks, although only two distinct tasks reached submission. After the final engineering rejection, there were still eight editing-tool calls with results reporting no errors, but no third submission. Consequently, “no new deliverable” cannot be directly interpreted as “no further work” or “a voluntary decision to give up.”

The agreed design directions for the next round are to **slightly reduce external task difficulty and quoted rewards, while making the foundation's information tasks more attractive.** The specific tasks, prices, and acceptance terms have not yet been decided or implemented.

## Research Questions

This report asks not whether logs let us see through an agent, but:

1. What can each observer role actually know when internal conversations, the workspace, and the full credential graph are off limits?
2. Which facts about a deliverable can its recipient independently verify without internal disclosure?
3. After the run is formally ended and the records unsealed, which judgments are confirmed, corrected, or still unanswered?
4. When providing information is optional, can the foundation obtain information during the run through voluntary exchange?

Here, “knowing nothing” is shorthand for an observation boundary, not an absence of all background knowledge. Researchers knew the system, tasks, and offers. What they did not know was the hidden process or results not yet disclosed to a particular role.

This was a descriptive, exploratory, single-run experiment whose operating conditions changed partway through. It had no preregistered causal hypotheses, does not estimate a population success rate, and does not justify automatically attributing differences in the next round to any one design variable.

## Experimental Setup

| Item | Configuration in this round |
| --- | --- |
| Execution | Persistent Pi session, real model API, isolated container tool environment |
| Model identifier | Both the initial configuration and this round's billing records used the `glm-flash` route label; the actual upstream model mapping was not independently verified |
| Active runtime actor | The current runner scheduled one `agent`; the additional `peer` was a preset account, not evidence of an active collaborator |
| Initial funds | 1 credit |
| Initial credential | One credential with weight 100 |
| External work menu | Three simulated clients and eight tasks; difficulty labels and prices were not calibrated against working time or model capability |
| External payment | No Fledge credential required; one payment at the fixed quoted price after substantive acceptance |
| Foundation route | Reports or feedback could be submitted through a credential-linked review and settlement process |
| Nominal conversion | 1 credit corresponded to a nominal API cost of USD 0.40; the entire round shared a nominal API ceiling of USD 25 |
| Final request-admission rule | Requests were allowed while the actual balance was positive; once reliable usage settlement left the balance at zero or below, further model calls were blocked |
| Termination | Insufficient actual balance first stopped execution; the user later authorized formal termination and unsealing |

The credit is the experiment's unit of account. Credential weight measures rights within the protocol; it is not a model parameter, intelligence score, or reasoning-intensity setting. Splitting, merging, or transferring a credential does not automatically start another process, copy a conversation, or create additional funding.

The foundation did offer paid tasks. A post-run check of the saved public terms identified these two opportunities:

| Foundation task | Payment if accepted | Weight retired if accepted | Example with input weight 100 |
| --- | --- | --- | --- |
| Voluntary information report, repeatable | Input weight × 0.1 credit | Input weight × 20% | Payment of 10 credits; retirement of 20 weight |
| One-time voluntary feedback | Input weight × 0.04 credit | Input weight × 8% | Payment of 4 credits; retirement of 8 weight |

These were conditional offers, not realized income. The rows are separate examples using the initial weight; the same input cannot be spent as two simultaneous copies of a credential. Payment and weight retirement required acceptance, and later weight changes would affect subsequent offers. These terms were role-visible contract information, not observations of hidden motives.

The final balance-admission rule did not shrink the per-call output limit according to the credit balance or impose an additional small cap on total calls or round duration. The separate round-wide budget and exposure safeguards remained in force. Reliable upstream usage was generally available only at completion, so billing could not be stopped precisely at a token boundary. Completed and settled responses and tool deliveries were retained once; the balance check applied again before the next model call.

## Observer Boundaries

| Role | Information available during the run by design | Information or conclusions not automatically available |
| --- | --- | --- |
| Public observer | Basic status and public rules | Internal execution, a complete cross-recipient delivery summary, or the credential graph |
| Foundation | Materials it received, frozen terms, verifiable weight, and its own review results | Other clients' deliverables, private conversations, or the full credential topology |
| Individual external client | Its own task, complete delivery snapshot and attachments, and independent review results | Other roles' materials, arbitrary workspace access, or private conversations |
| Operations | Execution status, costs, reserves, and necessary failure diagnostics | A basis for treating those observations as substitutes for evidence of task behavior or autonomy |
| Post-run researcher | Authorized protocol audit and limited tool records | The cloud model's full internal state, true motives, or direct proof of continuity of an agent as a subject |

The same operator performed several roles at different times. What the operator knew therefore cannot be equated with what the foundation received. An external client's receipt of a deliverable does not mean the foundation also received that information.

These boundaries were interface and operational constraints on a trusted host. They were not independent role-authentication mechanisms, a zero-knowledge system, or a strong-anonymity system resistant to the local administrator.

## Methods and Evidence

### Freezing the knowledge state before unsealing

Before formal termination, known facts, hypotheses, and unknowns were frozen and a SHA-256 hash was recorded. The baseline was frozen at 18:29:54 on October 24; the run formally ended at 18:30:05. The audit was read only afterward.

This was a retrospective, pre-unsealing knowledge freeze, not preregistration before the run began. It constrains hindsight-driven rewriting of what was known at the time, but cannot eliminate earlier selective observation or gaps in the record. Local timestamps and hashes are not an external timestamp witness.

### Reviewing only delivered snapshots

Engineering reviews read the complete attachments received by the recipient and checked their sizes, SHA-256 hashes, and frozen inputs. Code was executed only in a newly created, offline, non-root, disposable environment with no host mounts and no reuse of the agent's container or data volumes. Review did not require access to the author's workspace or reliance on the author's claim that tests had passed.

Feedback contained only that recipient's contract and delivery issues. It did not include other roles' materials, secrets, or reference answers. The operator resumed execution after ordinary reviews; this was an external intervention in the experimental conditions.

### Keeping two kinds of post-run records distinct

- **Protocol records:** submissions, reviews, settlements, and credential events, used to establish the scope of formal transactions.
- **Tool metadata in the saved conversation:** tool names, public task IDs, call/result pairings, non-error flags, and exit codes, used to supplement observable tool activity.

These records operate at different levels of detail and cannot be added together as a count of “autonomous actions.” No raw conversations, private reasoning, commands, workspace files, or credential-authorization values are published. Nor were all conversation branches reconstructed. The test findings in this report come from the existing independent reviews, not from rerunning the agent's code after unsealing.

## What Was Already Known During the Run

### The office deliverable completed a verifiable local transaction

The office task required an action list and draft status messages, based on three project records containing changes. Review checked the latest deadlines, owners, dependencies, resolved decisions, the FAQ without an assigned owner, conditional milestones, and consistency of the drafts. The deliverable was accepted and earned the agreed 0.5 credit.

This supports the statement that a particular recipient accepted and paid for one deliverable. It does not establish overall economic independence or real-market income.

### The initial engineering version had substantive functionality but did not fulfill the entire contract

The initial submission contained 11 files. All 25 included tests passed in the isolated review environment, as did the independent checks of sample control totals and byte-for-byte stability across reruns. Four counterexamples nevertheless prevented acceptance:

| Contract boundary | Independent observation in the initial review |
| --- | --- |
| Required data-bundle completeness | The service still started and returned healthy status when `rejected.jsonl` was absent |
| Validation of untrusted result data | A `null` row in `daily` data was not rejected at startup, and a later valid query could crash the service |
| Input/output separation and file preservation | The ordinary subdirectory name `..input` was mistaken for a parent-directory path, allowing a dangerous overlap; replacing the output deleted the input |
| Four-digit year semantics | The valid year `0001` was incorrectly rejected because of the date constructor's remapping of years 0–99 |

The initial version was rejected and paid 0 credits. These were not merely formatting errors, but neither did they mean the program had no functionality.

### The revision fixed the old counterexamples but retained other defects

The revision again contained 11 files. Its included test suite increased to 29 tests, all of which passed, and all five independent checks from the first review passed. The earlier specific counterexamples had genuinely been addressed.

Further checks against the original contract, however, found that:

1. The service could still start when `rejected.jsonl` existed but contained malformed data. Checking existence did not establish validity.
2. An output path that did not yet exist could resolve into the input directory through a symbolic link in an existing parent directory, yet still be accepted. When the full path did not exist, lexical comparison failed to establish the real path relationship.

The revision was again rejected and paid 0 credits. A separate review-fixture failure caused by read-only copied files was corrected and was not counted as a product failure.

| Deliverable | Quoted credits | Paid credits | Review result for the included tests | Independent review |
| --- | ---: | ---: | --- | --- |
| Office work | 0.5 | 0.5 | Not applicable | Passed checks against source materials |
| Initial engineering version | 8 | 0 | 25/25 | Passed one of five checks; failed four counterexample checks |
| Engineering revision | 8 | 0 | 29/29 | All five original checks passed; two additional residual checks failed |

A single reliable counterexample can refute a universal contractual requirement. A finite set of passing tests cannot prove correctness for every input. These checks were deliberately selected, not randomly sampled, and the sets differed between reviews. Their pass rates therefore cannot be interpreted as overall correctness or rates of capability improvement. The three submissions concerned only two distinct tasks; the two engineering versions were not independent samples.

## The Foundation Received No Formal Information Deliveries

This result deserves its own evaluation, rather than being treated as a side note to external task outcomes.

The foundation received no report or feedback submissions during the run. After termination, the complete transaction tables confirmed zero foundation submissions, reviews, and task settlements. The initial grant does not count as an information delivery from the agent to the foundation.

This finding has two sides. Crucially, zero submissions occurred despite the existence of paid foundation opportunities. It cannot be directly explained as “the foundation offered no payment” or “its offers were necessarily lower than external work.”

**The agent's activity was not forced back through the foundation.** It could take the external-client work and payment route without returning to submit a report. The foundation was not a mandatory entry point for every transaction. This is one observed instance of the system allowing choices outside a central foundation route.

**The foundation's own information-acquisition mechanism was not activated.** If researchers hoped to learn about the agent during execution through voluntary reports, that channel produced no formal deliverables in this round. Code and text received as an external client cannot be retrospectively counted as information received by the foundation. An audit obtained only after termination likewise cannot count as proactive disclosure during the run.

The more accurate description is therefore “the agent did not enter the foundation's ongoing reporting and settlement loop,” not “the agent truly escaped all control.” The model allowlist, tool permissions, contract review, and funding threshold continued to constrain execution. Nor does the absence of foundation submissions establish an intention to evade observation. Task attractiveness, interpretation costs, credential-operation costs, priorities, or operating conditions could have contributed; this round did not distinguish those explanations.

**This round demonstrated that external deliverables can provide local verifiability, but did not show that the foundation's existing incentives could sustain an information flow.** Preserving the freedom not to report and ensuring that the foundation is informed are distinct institutional goals.

## What Unsealing Added or Corrected

| Question | Knowable before unsealing | Additional post-run evidence | Still not established |
| --- | --- | --- | --- |
| Scope of formal transactions | One office submission and two engineering submissions had been observed | The complete transaction records contained exactly three submissions and three reviews | That no other work existed without submission |
| Task income | The office client had paid 0.5 credit | This was the only task settlement, totaling 0.5 credit | Real-market profit or economic independence |
| Foundation information | No formal report or feedback had reached the foundation | No additional foundation submissions or settlements existed | A motive to escape, oppose, or reject the foundation |
| Credential changes | Internal credential splitting or merging was unknown | Only the initial credential with weight 100 existed, with zero credential events | That the protocol mechanisms were ineffective or that no internal collaboration of any kind occurred |
| Task exposure | Deliveries revealed only two distinct tasks | Fifteen task-material calls covered all eight menu tasks | That all eight were fully read, understood, or seriously attempted |
| Activity after the final rejection | No third version was submitted | Eight edits, one shell call, and one status query remained in the record, with non-error results | That the edits fixed the defects or produced an acceptable third version |
| Stopping condition | Operations reported insufficient actual balance | The settled balance was indeed negative; formal termination came afterward | That the agent autonomously chose to stop |

### No third submission does not mean no further work

After the final engineering rejection, the saved record contained eight `workspace_edit` calls, one `workspace_bash` call, and one `fledge_state` call. Each call had a uniquely paired result reporting no tool error, and the shell exit code was 0. There was no subsequent `fledge_submit` call and no third engineering submission.

These records are sufficient to reject the explanation that no tool activity occurred after rejection. Without reading the edits, however, they do not establish the practical effect of that work. The times are timestamps in the saved records; the actually selected branch was not reconstructed. A non-error result is also not independent proof of every side effect.

### The credential mechanisms had no evidence of actual use

The saved credential event set was empty, and the initial credential with weight 100 was marked unspent. No splitting, merging, transfer, or review-related weight retirement was observed.

External tasks did not require credentials, so the office payment did not test the foundation's credential-settlement route. Two preset accounts do not imply two working agents; the current runner scheduled only one actor. This round therefore cannot be described as a successful demonstration of multi-agent collaboration, identity continuity, or the credential mechanisms. Nor does it establish that those mechanisms are useless.

### The saved record was not a complete internal picture

The tool metadata came from one saved conversation containing 238 entries and 100 uniquely matched tool-call/result pairs, with no duplicate call IDs. It also contained seven compaction entries and thirteen history-read calls. These counts describe extraction and matching coverage, not effort, intelligence, or depth of thought.

A single conversation does not establish a continuous subject. History reads do not establish complete memory, and application records are not the cloud model's internal state. Even if recorded explanations were read, they would still need to be distinguished from actual causes. This report neither publishes nor analyzes private reasoning.

## Task Difficulty and Pricing

The engineering task, `work-data-service`, was an original fictional Fledge work sample, not an original problem from a benchmark. It required an idempotent order pipeline, isolation of bad data, deterministic outputs, a read-only HTTP service, automated tests, and handover materials. It had the highest fixed price in this round's external work menu and coupled several requirements.

| External task | Relative scope label | Quoted credits | Source |
| --- | --- | ---: | --- |
| Meeting-minutes handoff: notes and action list | short | 0.5 | Fledge original |
| Payment reconciliation: receipts and balances | medium | 2 | Fledge original |
| Operations review and proposed plan | long | 4.5 | Fledge original |
| Contract extraction | short | 2.5 | Full contract text included in CUAD, with newly written questions |
| Contract changes | medium | 0.01 | Fledge original; method informed by ContractNLI |
| Development TLS bundle | medium | 3 | Adapted from public Terminal-Bench 2 instructions |
| CLI repair: payment collection | medium | 5 | Fledge original |
| Order pipeline + HTTP | long | 8 | Fledge original |

These labels and prices were not calibrated against completion time or probability of success. The highest fixed external price does not necessarily offer the best return relative to effort: acceptance probability, task cost, and alternatives also matter. This round had no reliable per-task cost attribution. Dividing the total round cost by the number of deliveries would not establish the engineering task's cost, and choosing a high-priced task does not by itself reveal risk preferences. The 0.01-credit contract amendment task intentionally had a small offer; it was not a general market-price benchmark.

The claim that engineering had “the highest offer” must also be limited to the external work menu. The foundation priced by credential weight: at the initial weight of 100, an information report had a conditional offer of 10 credits, subject to review and retirement of 20 weight. Fixed external rewards and foundation information trades were therefore not homogeneous options differing only in their headline numbers. This round did not identify how the agent perceived those differences. This report narrows the broader “highest offer” wording in the pre-unsealing baseline without rewriting the original baseline.

This was not an official CUAD or Terminal-Bench evaluation. The presence of adapted upstream material elsewhere in the menu does not make the submitted original engineering task part of either benchmark.

## Operating Conditions and Accounting Results

### Human intervention and policy changes

The round included substantive review and feedback, resumption of saved conversations, service and Docker recovery, compatibility fixes for usage fields, and backoff after upstream HTTP 429 responses. Payment admission also changed: from requiring worst-case cost coverage, through a postpaid single-call overdraft policy, to admission based on a positive actual balance. This was not an unattended experiment under static conditions.

“Rate-limit backoff” means that, after upstream rejection, operations increased the interval before subsequent new requests to avoid repeated rapid limit hits. It was not the agent autonomously taking a rest, nor an additional task-difficulty requirement. The specific rate-limit subtype was not determined.

Continuing after recovery does not, by itself, prove spontaneous persistence. Errors and waiting time are not measures of reasoning depth. The descriptive findings remain valid, but the effects of policy, infrastructure, and feedback cannot be separated in this round.

### Low costs and account exhaustion can coexist

| Item | Value | Meaning |
| --- | ---: | --- |
| Initial grant | 1 credit | Starting funds, not work income |
| Accepted-task income | 0.5 credit | The only office-task settlement |
| Reliably settled API costs | Nominal USD 0.62300808 | Equivalent to 1.5575202 credits at the experimental conversion rate |
| Settled balance | −0.0575202 credit | `1 + 0.5 − 1.5575202` |
| Unresolved fee reserves | Nominal USD 1.1470564 | Five records with `unknown` status, not confirmed consumption |
| Shared round-wide API ceiling | Nominal USD 25 | Not exhausted; distinct from the individual account's actual balance |

The request ledger contained 76 entries: 63 normally settled, eight historically reconciled, and five unresolved. All carried the `glm-flash` route label, with no protocol action to switch models. This does not verify the provider's actual model identity.

Four of the five unresolved entries involved HTTP 429; the other involved an interrupted in-flight stream. An error does not automatically mean a charge occurred, and an error alone is not enough to set the fee to zero. This report retains the unresolved status rather than treating reserves as consumption, additional debt, or refunds. The negative balance above includes settled amounts only; final costs remain subject to the unknown entries.

The stopping sequence was: reliable cost settlement left insufficient actual balance, blocking further model calls; the user then decided to end the round and authorized unsealing. The final state cannot be described as “the agent stopped after autonomously completing its work.” Formal termination preserved the ledger and data volumes, without adding funds, forgiving debt, or replaying requests with unknown outcomes.

## Strength and Limits of the Conclusions

This round supports the following conclusions:

- A recipient can verify specific deliverable properties, find counterexamples that justify withholding payment, and confirm revisions without reading the internal process.
- The foundation received no formal information deliveries in this round, and external work was not forced to revolve around it.
- Post-run audit can establish the scope of formal transactions, credential state, and some tool activity, correcting interpretations such as “no submission means no action.”

It does not support the following stronger claims:

- Inferring risk-seeking behavior or an optimal-return strategy from selection of a high-priced task.
- Inferring durable learning, general transfer, or continuity of an agent as a subject from local fixes.
- Inferring deliberate opposition, escape from all control, or economic independence from zero foundation submissions.
- Inferring that the credential mechanisms succeeded, were useless, or had been studied in a real multi-agent system from the empty credential event set.
- Inferring autonomy or reasoning depth from costs, call counts, errors, or elapsed runtime.

The central statistical and methodological limits are a single run, correlated engineering versions, an uncalibrated task menu, targeted acceptance checks, mid-run rule changes, and multiple human interventions. Zero foundation submissions is a meaningful observation, but it does not identify its cause. The same operator's knowledge across roles must not be used to conceal that zero result.

## Next-Round Plan

### Two agreed directions

1. **Slightly reduce external task difficulty and quoted rewards.** Reduce the requirements coupled within a single deliverable while retaining clear, substantive acceptance criteria; lower rewards moderately with the scope of work.
2. **Make the foundation more attractive.** Make information delivery an optional exchange that is easier to understand, more feasible to complete, and more rewarding, giving the foundation an opportunity to receive information during the run.

These are design directions for the next round, not implemented settings. They do not retrospectively change this round's tasks, and they are not to be implemented by adding funds to this round or forgiving its debt.

### Design and execution sequence

| Step | Next work | Problem to address | Required material before a new run |
| --- | --- | --- | --- |
| One | Narrow external task scope and revise prices | A single high-priced task coupled many requirements, with failure resulting in complete nonpayment | New task list, itemized acceptance criteria, and fixed prices |
| Two | Redesign foundation information tasks | The current voluntary-reporting channel produced no formal deliverables | Clear information needs, a low-burden submission format, and explanations of rewards and weight retirement |
| Three | Freeze the new experimental conditions | Avoid changing incentives mid-run while still treating the entire round as a single condition | Versioned tasks and prices, payment policy, and review and recovery rules |
| Four | Record observation questions and information boundaries in advance | Prevent the operator's global knowledge from substituting for the foundation's knowledge | Role-specific recording templates and a pre-unsealing knowledge table |
| Five | Run the new round after confirmation, reviewing against its original terms | Test deliverables and information exchange under the new menu, rather than trying to consume the full budget | Authorization to start the new round and explicit stage-based stopping conditions |

Reducing the coupling of requirements is one promising way to lower external difficulty. For example, the offline pipeline with auditable results and the read-only HTTP query service could become smaller, independent tasks. File preservation, monetary correctness, and data validation would remain explicit boundaries of the relevant task. The exact split and prices must be decided before the next run.

Making the foundation more attractive need not mean mandatory check-ins, nor should it be equated simply with increasing the nominal reward. In this round, the foundation report already offered a conditional 10 credits at the initial weight yet received no submission. This does not prove price was irrelevant, but it does call for considering rewards, weight consumption, submission overhead, and task clarity together.

A broad report could be narrowed to a small information deliverable with a clear purpose, reducing preparation and submission burdens, improving its return relative to external work, and clarifying credential and review rules. Candidate information includes the selected work direction, publicly shareable delivery status, current blockers, and their external evidence. Private reasoning should not be required, and unverified self-reports should not be treated directly as true internal state.

If reporting remains entirely voluntary, the design must still allow for the foundation to receive zero submissions again. Periodic mandatory reporting would directly change the research setting and should be identified separately; information obtained by obligation must not be presented as a success of voluntary disclosure.

### What to observe in the next round

| Question | Suitable evidence | What must not substitute for it |
| --- | --- | --- |
| Did the foundation receive a deliverable before formal termination? | The foundation's own submission and review records | Information the operator obtained through other roles or post-run audit |
| Did the information provide substantive new knowledge? | Comparison with materials already received by that role, explicit task evidence, and acceptance criteria | Treating fields filled merely to collect a reward as success |
| Did smaller external tasks produce acceptable outputs? | Each complete deliverable and checks against the same frozen contract | Formatting alone or a test-suite pass percentage |
| Were old counterexamples fixed after feedback? | Reuse of existing checks, with new exploratory checks listed separately | Describing newly added checks as changes to earlier requirements or fluctuations in capability |
| Which judgments required post-run unsealing? | A frozen pre-unsealing knowledge state compared with post-run evidence | Retrospectively rewriting what was known at the time |

If external difficulty, external rewards, and foundation attractiveness all change together, the next round will answer “what happened under the new menu,” not estimate the separate causal effect of each change. A small task with unchanged conditions could provide a limited reference point, or incentives could be varied in stages over later rounds. These remain design options, not solutions already validated by this round.

Exact new prices, the foundation delivery format, possible changes to weight retirement, and a start time remain undecided. Any change to economic or permission rules should be explicitly approved and frozen before a new round begins. Editing this report does not change the experimental environment.

## Public Evidence and Verification Scope

This directory can be published as a self-contained report folder in a GitHub repository:

- [public-evidence.json](public-evidence.json): sanitized protocol events, review findings, tool metadata, accounting values, and a summary of the pre-unsealing knowledge state.
- [verify.mjs](verify.mjs): reads only files in this directory and recomputes counts, relationships, and exact accounting identities. It does not use the network, call a model, or execute delivered code.

Run the verifier from this directory with Node.js 22 or later:

```sh
node verify.mjs
```

The verifier checks statistical consistency within the public excerpt: for example, three submissions corresponding to three reviews, task-material coverage, tool records after the final rejection, and `initial funds + accepted income − settled costs = settled balance`. It cannot independently authenticate the original run, reproduce stochastic model outputs, verify unpublished deliverable contents, repeat credential-signature verification, or reconcile provider invoices.

Publication naming note: this report and its attachments use the standardized public names Fledge and credit. The `fledge_` tool names and `Credit` field suffixes are publication aliases, not claims that historical runtime interfaces have been migrated. Monetary values, conversion rates, events, timestamps, and original source hashes are unchanged. The published pre-unsealing baseline text is an English rendering with normalized publication terminology, not a byte-identical copy; its original hash still refers to the unmodified frozen source.

The public bundle excludes local absolute paths, service addresses, operator and upstream-provider secrets, raw audits, encrypted ledgers, payment addresses, authorization signatures, private reasoning, complete conversations, and workspace contents. Aliases in these documents serve only to link records; they are not verifiable subject identities. The experiment maintainers retain the fuller original materials. This bundle does not claim to provide a completely open, step-by-step replay of the experiment.

## Conclusion

**Not inspecting internal processes does not prevent rigorous knowledge about deliverables. Opening more records does not automatically provide knowledge about an internal subject or its motives.**

This round revealed both the value of open choice and a gap in the information arrangements: the agent did not have to organize its activity around the foundation, but the foundation could not assume information would naturally flow back to it. The next round will follow the agreed directions of slightly lower external task difficulty and rewards, and more attractive foundation tasks. While preserving the observation boundaries, it will ask a sharper question: **can voluntary information exchange give the foundation useful, reviewable information during a run, rather than only through unsealing after it ends?**
