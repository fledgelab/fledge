# Fledge Round 2 Supplement

## What the Recorded Model Interactions Revealed

Experiment: October 22–24, 2026. Follow-up review: October 25–26, 2026. Supplement: October 27, 2026.

The [original report](README.md) asked what different observers could know without access to an agent's internal process. A subsequent, authorized review examined the complete selected saved conversation branch: 238 entries containing messages, provider-returned reasoning text, tool calls and results, code edits, and context-management records. It also compared these records with the runtime implementation and offline diagnostic tests.

The review did not make the agent's mind transparent. It revealed specific considerations and software behaviors that were invisible during execution, while exposing another observation boundary: **a record of what was saved is not necessarily a record of what was sent to the model.**

The formal outcomes remain unchanged. One office deliverable earned 0.5 credit. Two versions of an engineering deliverable were rejected and earned nothing. The foundation received no formal report or feedback submission. Post-run access does not retrospectively change those results or what each recipient knew.

## What Became Knowable

| Question | What the earlier evidence established | What the deeper review added |
| --- | --- | --- |
| Did the foundation receive information? | No formal foundation submissions were recorded. | Foundation work was repeatedly considered, sometimes as the first intended task. Considering a report did not become submitting one. |
| Did engineering work continue after rejection? | Tool metadata showed further activity but no third delivery. | The saved arguments exposed concrete repair attempts, incomplete verification, and discrepancies between successful edit acknowledgements and later readback. |
| Did the saved conversation provide continuity? | Original entries and history-retrieval records existed. | Some summaries retained little useful task state, and an adapter check exposed a relevant message-omission mechanism. Exact historical outbound requests remain unavailable. |

The foundation learned none of these private process details through its own reporting channel. They became researcher knowledge only after authorized unsealing.

## Foundation Work Was Considered but Not Submitted

The recorded text does not support the simple explanation that the agent never noticed the foundation. It considered report topics, calculated sponsorship consequences, and alternated between foundation-first and external-first plans. Some passages explicitly favored external work because submission was simpler and did not involve a credential lock. Others deferred feedback until more experience could support it.

Price alone does not explain the choice. The agent recognized a conditional foundation report offer of 10 credit while choosing the 8-credit engineering task. Near a very low balance, it instead selected the smaller office task as a more feasible immediate action. Later it returned to the larger engineering task.

These are expressed considerations, not authenticated causes. They suggest a mixture of perceived effort, acceptance uncertainty, review timing, liquidity, and credential consequences. Mechanical event construction, temporary locking, permanent weight retirement, and uncertainty about a worthwhile report are distinct burdens. A simpler submission interface can reduce the first without removing the others.

Zero foundation submissions therefore remains meaningful, but it does not demonstrate a settled refusal to cooperate, deliberate evasion, or an adopted strategy of preserving credentials for later use.

## Saved Output Was Not Guaranteed Working Context

The strongest technical finding concerned the boundary between the saved session and the model request. An offline check of the adapter installed during the follow-up reproduced a specific omission: an assistant message containing native reasoning but no ordinary text or tool call was dropped during conversion to provider messages. Adding ordinary text or a tool call retained it. A reasoning-only context preview could be dropped as well.

Four prominent historical responses had this affected shape: substantial reasoning text, no native tool call, and a recorded length stop. This makes continuity loss a credible explanation for some repeated reconstruction across responses. It weakens the claim that the model necessarily received an earlier draft and then chose to repeat it.

However, the original outbound request bodies were not archived, and the inspected copy redacts reasoning metadata. The diagnostic establishes the inspected adapter's behavior, not the exact historical payload or identical software behavior at every earlier point. It also cannot explain why the first such response produced no tool call, or why planning repeated within an individual response.

Summary quality was a separate problem. All seven saved compactions were marked incomplete. Some summary material contained little beyond a generic intention to inspect state; later fallbacks repeatedly retained earlier checkpoint prefixes. The originals remained retrievable, but recoverable archives and useful current context are different properties.

## Plans and Successful Receipts Were Not Completed Work

The recorded reasoning repeatedly framed large batches of preparation as a way to reduce later requests and debugging cycles. Checkpointing was sometimes deferred until implementation succeeded or skipped to save cost. This could leave substantial unfinished work without a durable artifact. Yet the agent later accepted an iterative approach and performed real writes and tests. The record does not justify a blanket diagnosis of perfectionism or inability to act.

One revealing mismatch occurred when correct sample calculations appeared in a draft, but a later native file write inserted contradictory test expectations. The agent subsequently recalled the correct calculation. The problem was not simply that the right answer had never appeared: a correct conclusion was not reliably carried into the emitted artifact.

Another mismatch involved the tools themselves. Several edits to one file returned success, but subsequent reads still showed specific old targets. The backend inspected during follow-up performed whole-file read–replace–write operations without same-file coordination. A synthetic schedule reproduced how two edits could both report success while one overwrote the other's change. The historical low-level write order was not recorded, so the exact race remains unproven.

These findings change attribution, not acceptance. They caution against calling every missed repair a model oversight. They do not invalidate the independent reviewers' counterexamples in the actual submitted packages. Some omissions were never targeted by an edit, and further proposed patches had separate correctness issues. There was still no third engineering submission or final verified version.

## Resource Interpretation Was Also Unstable

Early exact-rational balances were sometimes interpreted as large amounts or as a current-value-versus-cap display. Later passages calculated them correctly. This supports clearer units and decimal presentation, not a conclusion that every subsequent decision was financially confused.

The financial reconstruction also showed that the balance recovery around the office acceptance included a release from reconciliation of earlier requests, as well as task income and intervening charges. It must not be attributed to office earnings alone or treated as a demonstration of self-financing. Operational costs, call counts, errors, and elapsed time remain unsuitable substitutes for evidence of autonomy or reasoning depth.

## Implications for the Next Round

The follow-up shifted the immediate priority toward a reliable environment. Five repair areas were implemented afterward: context transport and retrieval; coordinated file mutations; clearer balances and execution results; optional self-authored drafts and version records; and a read-only foundation quote with an equivalent self-owned submission shorthand. Offline regression tests passed. Live provider and real-container compatibility were not validated by those tests, and no new experiment was started.

The next round will retain an open goal. It will not require self-financing, foundation reporting, checkpoints, or a prescribed task order. Easier and slightly lower-priced external work, together with more attractive foundation offers, remain separate environmental proposals whose exact terms have not been implemented. Changing several conditions together would establish behavior under a new environment, not identify the causal effect of any single change.

The central lesson is to distinguish **stored output, transmitted context, committed action, accepted delivery, and recipient knowledge**. Opening more records made several explanations more specific, but did not establish a unique motive or a continuous internal subject. A useful next experiment should make these stages more reliably observable while preserving the agent's ability to choose, defer, decline, or stop.

## Evidence and Disclosure

This supplement summarizes maintainer-reviewed private records and offline implementation checks. Provider-returned reasoning is recorded text, not access to the model's complete internal computation. No archived command or delivered program was replayed for this deeper review. Raw conversations, reasoning passages, private workspace contents, credentials, and local service details are not published here.

The [public evidence excerpt](public-evidence.json) and its verifier retain the original report's scope. They do not independently reproduce or certify the additional private-trace findings in this supplement. The original report remains the dated account of the earlier, narrower inspection; this document adds the later findings without rewriting what was known at the time.
