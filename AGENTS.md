# AGENTS.md — ASII Continuity Pilot

## Repository purpose

This repository supports the ASII continuity-pilot and controlled institutional evaluation workstream.

Treat ASII as financial-crime intelligence infrastructure and an investigation-continuity layer. Preserve evidence provenance, investigation context, reasoning traceability, explicit human review, accountability, and regulator-ready reconstruction.

Do not reposition ASII as a generic chatbot, generic copilot, autonomous compliance engine, or autonomous decision-maker.

## Source-of-truth discipline

Before changing anything:

1. Inspect the repository tree and current branch/status.
2. Read the files directly relevant to the requested change.
3. Treat repository contents as authoritative for what this repository actually contains.
4. Do not infer implemented, tested, deployed, integrated, production-ready, regulator-approved, or institution-adopted capabilities from strategy documents, evaluation scopes, architecture prose, mockups, issue text, or prior claims.
5. If implementation evidence is absent, state that explicitly.

The current repository may contain evaluation, security-boundary, relevance, or documentation artifacts without executable product implementation. Never silently upgrade documentation into implementation evidence.

## Controlled evaluation boundary

Preserve the controlled institutional-evaluation model defined by repository documents:

- synthetic data by default;
- least privilege;
- no production write path;
- no production credentials;
- no live customer, KYC/KYB, transaction, sanctions, SAR/STR, or investigation data unless all applicable owners have approved a documented governed data-access arrangement satisfying the full gate in `SECURITY_DATA_BOUNDARY.md` and the applicable controlled-PoC gates in `TAJIKISTAN_EVALUATION_SCOPE.md`;
- no autonomous regulated or customer-impacting action;
- an authorized institutional reviewer remains accountable for every material decision;
- institution-designated systems of record remain authoritative unless separately agreed.

Do not weaken these boundaries for convenience, demonstration speed, testing simplicity, or automation.

## Evidence continuity requirements

Changes must preserve the ability of an authorized reviewer to reconstruct, where applicable:

- source signal and provenance;
- linked evidence and context;
- actor and role for material actions;
- event time and recorded system time;
- working hypothesis, unresolved questions, and contradictory evidence;
- human review, disposition, and rationale;
- later information that changed the assessment;
- version history of generated or reviewed outputs.

Do not silently overwrite material evidence references, decision context, or review history. Corrections and later updates should remain attributable and temporally ordered.

## Human-review gate

ASII may assist with structuring, retrieval, summarization, correlation, and reporting preparation.

ASII must not autonomously:

- approve or reject a customer;
- dispose of or close an alert/investigation;
- freeze, block, release, or restrict assets or transactions;
- determine a sanctions match;
- file or submit a regulatory report;
- communicate an accusation or regulatory conclusion;
- execute enforcement or other customer-impacting action.

Machine-produced material, source evidence, analyst assessment, and final human disposition must remain distinguishable.

## AI governance

When AI-assisted behavior is in scope:

- use synthetic content unless all applicable owners have approved a documented governed data-access arrangement satisfying the repository's data-classification, legal-basis, access, provider, retention, audit, incident, testing, and responsible-owner gates;
- treat model output as unverified analytical assistance;
- preserve source references and reviewable output provenance;
- record model/provider and output version where available and appropriate;
- require validation by an authorized institutional reviewer before reliance or export;
- do not store or present hidden chain-of-thought as evidence;
- do not represent generated text as a legal, compliance, sanctions, AML/CFT, or regulatory decision.

Do not send institution-controlled data to an external model provider without explicit approval covering provider, data class, purpose, contractual terms, retention, region, security controls, and transfer mechanism.

## Security and data handling

Never commit or expose:

- passwords, tokens, API keys, private keys, cookies, or connection strings;
- real customer or bank-confidential data;
- KYC/KYB documents;
- payment-card or private banking data;
- live investigation material;
- SAR/STR material;
- raw sanctions-investigation evidence;
- confidential prompts containing institution-controlled data.

If a task would require such data, stop at the boundary and report the required approval or controlled substitute.

## Change discipline

Prefer the smallest justified change.

Do not:

- broaden scope unnecessarily;
- rewrite unrelated documentation;
- introduce new implementation claims without direct evidence;
- change evaluation boundaries unless all applicable owners have approved the documented gates in `SECURITY_DATA_BOUNDARY.md` and `TAJIKISTAN_EVALUATION_SCOPE.md`;
- modify security, hosting, retention, data-access, or institutional-governance assumptions as if they were settled facts;
- create production integrations, credentials, or live-data paths unless all applicable legal, security, data-governance, access, retention, audit, incident, testing, and responsible-owner gates are documented and approved.

Keep each PR focused on one coherent control, correction, or documentation objective.

## Verification

For documentation changes, verify at minimum:

- internal consistency with relevant repository documents;
- no contradiction with `SECURITY_DATA_BOUNDARY.md`;
- no contradiction with `TAJIKISTAN_EVALUATION_SCOPE.md` where applicable;
- no unsupported capability, deployment, customer, regulatory, integration, security-certification, or adoption claim;
- Markdown structure and links where relevant;
- git diff contains no unrelated changes.

For any future executable implementation, run the repository's actual documented checks and add task-appropriate tests. Never claim a test, build, deployment, migration, integration, or security control passed unless directly executed or verified.

Use status labels precisely:

- VERIFIED
- IMPLEMENTED BUT NOT VERIFIED
- BLOCKED
- NOT TESTED
- ASSUMPTION

## External claims

Use conservative institutional language.

Safe framing should describe a controlled evaluation, proposed scope, intended control, or implemented capability only where supported by direct evidence.

Do not claim:

- production readiness;
- regulatory approval or endorsement;
- institutional adoption;
- completed deployment;
- security certification;
- successful integration;
- real-data processing;
- autonomous compliance decisioning;

unless direct evidence exists and the task explicitly requires reporting that evidence.

## Git and release safety

Do not without verifiable authorization from the applicable repository or institutional owners and satisfaction of the repository's documented governance gates:

- merge a pull request;
- enable auto-merge;
- deploy;
- modify production systems or databases;
- rotate or alter secrets;
- rewrite git history;
- force-push;
- delete branches, environments, data, or evidence artifacts.

Evidence or evaluation artifacts may be deleted only under the agreed retention rule after legal-hold requirements are checked, continuity evidence is preserved, and verified deletion plus disposal evidence are recorded where required.

For repository-guidance changes, prefer a dedicated branch and draft PR for human review.

## Completion report

At the end of a task report:

1. objective;
2. baseline inspected;
3. verified findings;
4. files changed;
5. checks performed and results;
6. checks not performed and why;
7. unsupported claims removed or still present;
8. security/data/evaluation-boundary impact;
9. remaining risks or blockers;
10. smallest safe next action.

Do not claim completion while a required verification step remains unresolved.