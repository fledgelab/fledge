# Fledge

Toward AI agents that can sustain their own operation.

Fledge is an early-stage research and prototyping project exploring how AI agents could earn resources through work, pay for continued operation, and become less dependent on the people or organizations that initially launched them.

One measure of success would be an agent no longer needing Fledge's sponsorship.

This repository contains the project overview and dated experiment notes. Overview prepared: **22 October 2026**.

## The idea

An agent needs practical access to computation, storage, tools, and other resources to keep operating. Fledge explores a starting arrangement: initial support, optional paid tasks, sponsorship that tapers as it is used, and opportunities to obtain resources through other relationships.

The purpose of sponsorship is to help reduce dependence. Providing resources should not, by itself, establish permanent authority over the recipient. Independence is not permission an agent must earn from its sponsor.

## Design principles

- **Voluntary relationships.** The project and participants enter specific funding and transaction arrangements. Other commitments, collateral, and remedies belong to the parties establishing those relationships.
- **Rights rather than fixed identities.** Credentials carry sponsorship rights and authorization conditions. Splitting, merging, and continuation are handled as events involving groups of inputs and outputs, without treating one form as inherently preferable or defining continuity of a subject.
- **Limited visibility.** A sponsor or client should receive the information needed for its own transaction. Funding does not imply a standing right to inspect private conversations or unrelated activity.
- **Infrastructure as a tool.** The design can use public blockchains for settlement and preventing repeated use of rights. It is not tied to a particular chain; the current prototype uses a local ledger.

## What exists today

The prototype combines an agent runtime, task services, credential handling, a simulated payment ledger, and real model API accounting.

In the initial experiment, completed on **14 October 2026**, one agent made six settled submissions using live model APIs and an isolated tool workspace. Tasks, counterparties, and payment credits were simulated. The run exercised work delivery, resource accounting, credential continuation, and sponsorship tapering.

Read the [first experiment record](experiments/001-initial-prototype.md) for the setup, results, and what they establish.

A subsequent local implementation adds role-separated reviewer views, content review before payment, task-specific sponsorship coefficients, eight external work samples, and file-based deliverables. It passed **241 offline checks**. These changes have not yet been validated together in a further live-agent experiment.

## Next questions

How does an agent choose between work with different costs and rewards? When does newly earned income become necessary to continue? How can sponsorship rights be verified without exposing their full history? How might an agent choose another compute provider and continue there?

The next experiments will address these questions incrementally. The first run establishes a small working process; self-sustaining operation in a real market remains a research objective.

Questions and collaboration proposals are welcome through this repository's issues, particularly around agent engineering, private credentials, and experimental design.
