# ASII Tajikistan — Security & Data Boundary Note

## Status and purpose

This note defines the minimum security, data-handling, human-review, and evidence controls for a **controlled institutional evaluation** of ASII in Tajikistan.

It is an evaluation boundary, not a claim of production readiness, regulatory approval, institutional adoption, security certification, or completed deployment. Institution-specific legal, regulatory, information-security, procurement, hosting, retention, and integration requirements remain subject to formal review and written agreement.

## Evaluation principle

The initial evaluation should demonstrate investigation continuity without introducing unnecessary access to institution-controlled systems or data.

**Default boundary: synthetic data, least privilege, no production write path, accountable human review.**

ASII is evaluated as an intelligence and continuity overlay. It does not replace the institution's systems of record or its regulated decision-makers.

## Data classes

| Class | Initial evaluation treatment | Examples |
| --- | --- | --- |
| Synthetic demonstration data | Permitted | Invented persons, entities, transactions, alerts, case notes, and evidence |
| De-identified test data | Conditional | Data whose use and re-identification risk have been approved by the institution |
| Institution-confidential data | Not required for the first demonstration | Internal policies, typologies, workflows, non-public configuration |
| Regulated or personal production data | Prohibited by default | Customer identity data, KYC/KYB files, account and transaction records |
| Restricted investigation material | Prohibited by default | Live alerts, SAR/STR material, sanctions investigations, raw case evidence |
| Secrets and security material | Prohibited | Passwords, tokens, private keys, credentials, cookies, connection strings |

A later phase may admit additional data classes only through a separately approved data-access arrangement specifying lawful basis, purpose, roles, fields, environment, access, retention, deletion, audit, incident handling, and responsible owners.

## Initial environment boundary

The controlled demonstration must not require:

- connectivity to production core banking, transaction-monitoring, sanctions-screening, KYC/KYB, case-management, payment, or regulatory-reporting systems;
- production database credentials or privileged service accounts;
- write access to institution-controlled production environments;
- broad historical-data migration;
- real customer, payment, KYC/KYB, sanctions, or investigation evidence;
- autonomous execution of customer-impacting or regulated actions.

Permitted input methods are limited to manually controlled synthetic files, synthetic API payloads, or other institution-approved test mechanisms. Any connection to an institution-controlled test environment requires explicit technical and security approval.

## Identity and access boundary

Before institution-controlled data or environments are introduced, the parties must agree and verify:

1. named user roles and accountable owners;
2. least-privilege access for each role;
3. authentication method and session controls;
4. authorization enforcement at the server and data layers;
5. administrative-access restrictions;
6. joiner, mover, and leaver handling;
7. access review and revocation;
8. separation of duties for material workflow transitions;
9. audit records for authentication and privileged activity.

Shared credentials are not acceptable. Demonstration access must be time-bounded and removable.

## Evidence continuity requirements

For every material demonstration event, the evaluation should preserve enough context for an authorized reviewer to reconstruct:

- the synthetic source signal and its provenance;
- the evidence or context linked to the case;
- the actor and role responsible for each material action;
- the event time and recorded system time;
- the working hypothesis, unresolved questions, and contradictory evidence;
- the human review, disposition, and rationale;
- any later information that changed the assessment;
- the version of a generated or reviewed output.

Evidence references must not be silently overwritten. Corrections and updates should remain attributable and temporally ordered. The authoritative record for any future production process remains the institution-designated system of record unless separately agreed.

## Human decision boundary

ASII may assist with structuring, retrieval, summarization, correlation, and reporting preparation. Outputs are reviewable working material.

ASII must not autonomously:

- approve or reject a customer;
- close or dispose of an alert or investigation;
- freeze, block, release, or restrict assets or transactions;
- determine a sanctions match;
- file or submit a regulatory report;
- communicate an accusation or regulatory conclusion;
- execute an enforcement or customer-impacting action.

An authorized institutional reviewer remains accountable for every material decision. The evaluation must display or record the distinction between machine-produced material, source evidence, analyst assessment, and final human disposition.

## AI and model-provider boundary

No institution-controlled data may be sent to an external model provider unless the institution has expressly approved the provider, data class, purpose, contractual terms, retention behavior, region, security controls, and transfer mechanism.

For the initial demonstration:

- use synthetic content only;
- treat model output as unverified analytical assistance;
- preserve source references and the human-reviewed final narrative;
- do not present hidden model reasoning as evidence;
- record the model/provider and output version when available and appropriate;
- require human validation before an output is relied upon or exported.

Provider availability, model behavior, and generated text must not determine regulated outcomes without accountable review.

## Logging and observability boundary

Evaluation logs should support troubleshooting and audit without collecting prohibited content.

Logs must not contain:

- secrets or authentication tokens;
- raw KYC/KYB documents;
- full payment-card or private banking data;
- unrestricted transaction evidence;
- confidential model prompts containing institution-controlled data;
- sensitive investigation narratives beyond the agreed test dataset.

Where logging is enabled, define correlation identifiers, access restrictions, retention, deletion, and incident ownership. Error messages and health endpoints must avoid leaking credentials, connection details, stack traces, or sensitive schema information.

## Hosting, transfer, retention, and deletion

The initial synthetic demonstration does not establish a production hosting decision.

Before a controlled PoC using institution-controlled data, written agreement is required on:

- hosting party, environment, region, and tenancy model;
- controller/processor or equivalent data-responsibility roles;
- approved data flows and cross-border transfer constraints;
- encryption requirements in transit and at rest;
- backup and recovery boundaries;
- retention periods and legal holds;
- verified deletion and evidence of disposal;
- subprocessors and external service providers;
- vulnerability, incident, and breach-notification procedures;
- business continuity, rollback, and exit arrangements.

No claim is made in this note that a specific deployment currently satisfies an institution's regulatory or security requirements.

## Controlled demonstration protocol

Before the demonstration:

- confirm that the dataset is synthetic or formally approved;
- identify presenters, reviewers, and accountable institution-side participants;
- record the use case, expected workflow, and success criteria;
- confirm that no production connection or credential is required;
- identify which outputs may be retained and by whom.

During the demonstration:

- show provenance, evidence links, timeline, changes, and human review;
- label generated or inferred material;
- avoid entering real customer, investigation, credential, or payment data;
- record gaps and unresolved questions without improvising production controls.

After the demonstration:

- record attendees and roles;
- record findings, control gaps, and requested evidence;
- identify the owner of any agreed next step;
- remove temporary access where applicable;
- retain or delete demonstration artifacts under the agreed evaluation rule;
- do not represent a meeting as approval, procurement, pilot, or deployment.

## Gate to institution-controlled data

The evaluation must remain synthetic-only until all applicable owners approve a documented scope covering:

1. use case and purpose;
2. approved data fields and classification;
3. legal and regulatory basis;
4. environment and system boundaries;
5. user roles and access controls;
6. provider and subprocessor use;
7. retention, deletion, and exit;
8. logging, monitoring, and audit;
9. incident and vulnerability handling;
10. testing, success criteria, and responsible decision owners.

Absence of any required approval keeps the evaluation within the synthetic-data boundary.

## Open decisions for institutional review

The following items are intentionally unresolved until an institution evaluates the proposal:

- required hosting model and location;
- permitted data classes and fields;
- identity federation and access-control standard;
- security assessment and evidence package;
- integration method and network boundary;
- retention and deletion periods;
- audit-log ownership and system of record;
- incident-response and notification requirements;
- regulatory, legal, procurement, and outsourcing classification;
- criteria for progression from evaluation to controlled PoC or pilot.

These are governance gates, not implementation assumptions.
