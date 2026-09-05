# ASII Tajikistan — Controlled Institutional Evaluation Scope

## Objective

Provide a bounded, low-risk way for a regulated financial institution in Tajikistan to evaluate whether ASII improves investigation continuity, evidence traceability, human review, and reporting preparation without replacing the institution's systems of record or regulated decision-makers.

## Evaluation workflow

**Signal → Investigation → Evidence → Human Review → Decision Context → Regulator-ready Reporting Preparation**

The evaluation should demonstrate that an authorized reviewer can later reconstruct:

- what information was available at the relevant time;
- which evidence supported or contradicted the working hypothesis;
- which analyst or reviewer performed each material action;
- what decision or disposition was recorded;
- why that decision was taken;
- what changed when new information arrived.

## Data boundary

Initial evaluation uses **synthetic or appropriately de-identified test data** unless the institution separately approves a governed data-access arrangement.

No production customer data, bank secrets, credentials, raw investigative evidence, or regulated production datasets are required for the first demonstration.

Any later use of institution-controlled data requires separately agreed legal, security, access-control, retention, hosting, confidentiality, and audit boundaries.

## Human decision boundary

ASII does not autonomously make or execute regulated decisions. The evaluation must preserve accountable human review for material actions, including escalation, disposition, regulatory reporting, onboarding restrictions, sanctions-related action, or customer-impacting decisions.

## Architecture boundary

The controlled evaluation is an **overlay**. It should not require replacement of core banking, transaction-monitoring, screening, KYC/KYB, case-management, blockchain-analytics, or reporting systems.

Integration should be limited to what is necessary to prove the evaluation hypothesis. File-based, API-based, or manually controlled synthetic input may be used depending on institutional constraints.

## Suggested participants

Institution-side participation should be limited to the owners needed to evaluate the use case, such as:

- AML/CFT / Financial Monitoring;
- Compliance / MLRO function;
- investigation or transaction-monitoring operations;
- Risk;
- Information Security / Technology where required.

## Proposed evaluation duration

Target: **2–4 weeks** for a bounded technical/compliance evaluation, subject to the institution's governance and procurement process.

The duration is a proposed scope, not a commitment by any institution.

## Minimum evaluation outputs

1. One agreed financial-crime investigation use case.
2. One controlled end-to-end workflow demonstration.
3. Evidence lineage and investigation timeline visible to reviewers.
4. Explicit human-review and decision-context record.
5. Reviewable reporting-preparation output.
6. Documented security and data boundaries.
7. Written findings: fit, gaps, risks, and required next-stage controls.

## Success criteria for stage transition

A successful evaluation-entry outcome is not a meeting alone. It requires an institutional next-step artifact, for example:

- an identified responsible owner or evaluation team; and
- an official follow-up requesting technical material, security review, scoped PoC details, another evaluation session, or internal review for a controlled pilot.

This does not imply procurement, production readiness, regulatory approval, or deployment.

## Explicit non-goals

The first evaluation does not aim to:

- replace an institution's AML/CFT or case-management stack;
- automate final compliance or legal decisions;
- perform autonomous regulatory filing;
- establish production integration;
- claim regulatory approval or endorsement;
- require broad historical-data migration;
- prove every future ASII capability.

## Gate to a controlled PoC or pilot

Progression beyond evaluation requires explicit agreement on at least:

- use case and scope;
- participating roles;
- approved data class and data source;
- access controls;
- hosting and security boundary;
- retention and deletion requirements;
- auditability requirements;
- success criteria;
- human-review controls;
- incident and rollback expectations;
- procurement/legal requirements where applicable.

The ASII core architecture remains unchanged unless a separately reviewed requirement demonstrates that a change is necessary.
