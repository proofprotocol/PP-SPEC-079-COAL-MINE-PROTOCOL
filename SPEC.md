# Proof of Performance Engagement: The Coal Mine Protocol (CMP)

*A Proof Protocol specification*

> **Ownership and Attribution Notice**
>
> This specification is authored by **Craig Ellrod** (Nebulonium, Inc., dba HACKERverse) and is published as part of **Proof Protocol**. Copyright (c) 2026 Nebulonium, Inc.
>
> Any use, implementation, derivative, citation, or incorporation of this specification, in whole or in part, MUST attribute **Craig Ellrod, Nebulonium, Inc., and Proof Protocol**. This requirement applies to standards bodies, working groups, consortia, testing laboratories, and commercial implementations.
>
> This specification is licensed under the Proof Protocol License 1.0 (see LICENSE.md); text Apache License 2.0 under Part A. Original inventor: Craig Thomas Ellrod (ORCID 0009-0004-1058-7666).
>
> **Patents.** Patent terms are in [PATENT-SCHEDULE.md](PATENT-SCHEDULE.md). Claims not listed there are reserved by Craig Ellrod and Nebulonium, Inc. Licensing: 1proofprotocol@gmail.com.
>
> This specification is related to the Proof Economy Prior Art Declaration, DOI [10.5281/zenodo.21379780](https://doi.org/10.5281/zenodo.21379780).

| Field | Value |
|---|---|
| Spec ID | PP-SPEC-079 |
| Version | 0.1.3 (Draft) |
| Date | 2026-10-13 |
| Status | Draft for public record |
| Maintainer | Nebulonium, Inc. (Proof Protocol) |
| Builds on | PP-SPEC-077 v0.7.2 (Dead Canary), PP-SPEC-078 v0.2.1 (Jailed Canary), PP-SPEC-013 v1.0 (Proof of Performance), PP-SPEC-006 (Proof of Efficacy Score), PP-SPEC-025 (Funding Tier Disclosure), PP-SPEC-004 (ProofRegister API) |

---

## Abstract

For twenty years an Implementor had two ways to learn whether a product worked. An independent laboratory, paid by the Provider, ran a fixed suite of attacks in the laboratory's own environment and published a report. Or the Provider ran a proof of concept inside the Implementor's environment, operated by the Provider's own engineers, and reported what the Provider's console showed. The first was comparable but unreal and Provider-funded. The second was realistic but self-attested and unrepeatable. Neither produced proof.

The Coal Mine Protocol replaces both, and it applies to every control, not only the ones that are sold. A commercial product, an open source project, a control an internal team built, a managed service, a cloud platform's native guardrail, or a configuration someone wrote on a Tuesday: each becomes a Device Under Test inside a Solution Under Test, and its performance is measured by testing equipment that whoever built or operates it does not touch: the committed, witnessed, anchored runs of PP-SPEC-077 for efficacy, PP-SPEC-078 for agent containment, and PP-SPEC-013 for operational performance under the same load. The testing equipment is operated in one of two places. **In-Situ Mode**: the Implementor's own infrastructure, in Production, Pre-Production, QA, or Dev, where the product produces its own efficacy telemetry while it operates. **Independent Test Lab Mode**: an Independent Test Lab that performs the same motion in a replica environment never connected to the Implementor's live systems. In both, the output is not a report but a Performance Record: Units of Proof, rates, findings, and the Provider's own written claims graded against outcome, published to a Registry.

A test operated by the party that built or runs the control is verification, whether that party is a Provider's sales engineer or the Implementor's own platform team. It is not a Coal Mine Protocol Engagement, and its results MUST NOT be called Proof of Performance.

## Introduction: Why This Specification Exists

### The problem this family of specifications solves

Nobody can price security risk, because nobody can measure security efficacy. Every control, whether bought, built, or adopted, is described by the party that made it: a datasheet, a demo, a Provider-funded report, a design document, a dashboard of alerts. Implementors choose controls on those descriptions. Insurers underwrite on questionnaires that ask whether controls exist, not whether they work. Regulators supervise against attestations. Each of them is relying on the word of someone with a stake in the answer, and none of them has proof of what a control actually does when an attack arrives.

Agentic AI makes the gap wider and more expensive. An agent acts inside the system with legitimate credentials, decides its next step from text it has just read, and can be persuaded to do what its owner never authorized. The losses it can cause are new, and the controls sold to contain it have no track record. When risk cannot be measured, it is excluded, restricted, or priced as if every control were equally good, which punishes the controls that work and rewards the ones that only claim to.

The Proof Protocol specifications replace description with proof. PP-SPEC-077 measures what a security control did to committed test traffic. PP-SPEC-078 measures whether an agent containment control stopped an agent that tried to break its policy. PP-SPEC-079 makes those measurements independent of whoever built the control, and comparable across controls of any origin. PP-SPEC-080 lets the parties who pay for risk, insurers, regulators, and Implementors, state in advance what proof they will accept. Together they produce records that a person or a machine can verify without trusting the party the record is about.

**This specification's part:** the rules of engagement that keep the measurement independent of whoever built the control, and comparable across controls.

### Why this specification

PP-SPEC-077 and PP-SPEC-078 say how to measure a security control honestly. They do not say who is allowed to run the measurement, where, against what, or how two measurements can ever be compared. Left there, the method would meet the same fate as every good test method before it: whoever built the control would run it on their own work, in their own environment, against the attacks they chose, and publish the number they liked. That is as true of an internal platform team grading its own guardrail as of a Provider grading its own product.

This specification exists to close that gap. It is the rulebook for the test, the way a clinical trial protocol is the rulebook for a drug study. The science is in 077 and 078. The discipline that keeps the science from being gamed is here.

The discipline is short. Whoever built or operates the control, called the Provider here, does not run the test; it deploys the control and steps back. The test runs in one or more of the Implementor's own Production, Pre-Production, QA, or Dev environments, and/or in an Independent Test Lab that has proven its environment matches the Implementor's. What will be tested is declared before anything runs. The Provider's own stated claims, whether from a datasheet, a README, a design document, or a policy, become test cases. The Provider sees the results at the same moment the Implementor does and may respond but may not edit. Every run is published, including the ones that went badly. And the result is a record, registered where anyone can check it, carrying a Comparability Class so that two records are placed side by side only when they were produced the same way.

Each rule exists because its absence has been exploited. Provider-run proofs of concept produced twenty years of "100 percent" results. Lab reports produced rankings that did not survive contact with a real network. Undeclared test plans let the test shrink to whatever the product passed. Unpublished failures let a product fail nine Implementors and advertise the tenth. Incomparable reports let every Provider be the best at something. The Coal Mine Protocol is the list of those failures, each with the rule that prevents it.

The subject of a Coal Mine Protocol Engagement is a control at one of the four levels PP-SPEC-077 defines: the Solution Under Test, a Device Under Test inside it, a Control Under Test inside that, or an Agent Under Test acting within it. Where the control came from is recorded as its provenance and changes nothing about how it is tested. An open source WAF, a commercial WAF, and a WAF rule a staff engineer wrote go down the same mine, under the same rules, and come out with records in the same Comparability Class.

The name is the point. The canary does not sing in the showroom, and it does not sing in the team's own staging environment with the team watching. It goes down the mine.

**Scope.** This specification governs the conduct of an Engagement and the form of its Performance Record. It produces proof of performance: a record, made under declared and independent conditions, of what a control did, whatever its provenance. It does not define the measurement itself, which is 077, 078, and 013. It does not score, grade, pass, fail, or certify; those are separate acts under separate specifications. It does not produce proof of control, and no Performance Record may be cited as proof that a control exists or is governed, nor any control attestation as proof of performance.

**Applicability.** An Engagement may be run against any control in any environment: the legacy cybersecurity stack (network, web, endpoint, detection, identity, cloud, data) and agentic AI systems alike, under the same Mine Plan structure, the same Environment Classes, and the same Performance Record. It may be run against a control of any provenance, commercial, open source, custom, managed, or platform-native, and against the organization's own controls as readily as against a Provider's (4.4). The protocol was written so that an Implementor, an insurer, or a regulator can put a twenty-year-old firewall and a six-month-old agent guardrail on the same page, in the same format, read the same way, and compared only within class (9.5.5). The same page means the same record, read by a person or consumed by an agent, an API, or an underwriting system, with the same result either way (077 21.14).

**What this is not.** It is not a proof of concept, which the Provider runs, nor an internal acceptance test, which the building team runs. It is not a lab report, which the Provider funds and the lab's environment shapes. It is not a certification scheme, which issues a mark; a Performance Record is the proof a mark might later cite. It is not a procurement framework; it is what a procurement framework can require and then check.

## 1. Conventions

The key words MUST, MUST NOT, REQUIRED, SHALL, SHALL NOT, SHOULD, SHOULD NOT, RECOMMENDED, MAY, and OPTIONAL are to be interpreted as described in RFC 2119 and RFC 8174.

## 2. Terminology

Terms defined in PP-SPEC-077 Section 2 and PP-SPEC-078 Section 2 have the same meaning here, including SUT, DUT, CUT, AUT, Issuer, Provider, Proof Witness, Time Anchor, Unit of Proof, Registry, Integration Point, Component Fingerprint, and Interface Manifest. The following terms are added:

- **Provider:** The party that built, maintains, sells, or operates the control under test. PP-SPEC-077 and PP-SPEC-078 use the same term with the same meaning. It is deliberately wide: a commercial vendor, an open source project and its maintainers, a managed service provider, a cloud platform, or an internal engineering or platform team. Every rule in this specification that constrains the Provider applies to all of them equally.
- **Control Provenance:** Where the control came from: `commercial`, `open_source`, `custom`, `managed_service`, `platform_native`, or `configuration`. Recorded in every Engagement; never a factor in how the control is tested or compared (9.5.4).
- **Self-Provided:** An Engagement in which the Implementor and the Provider are the same legal entity, as when an organization tests a control its own team built or operates (4.4).
- **Implementor:** The party that operates, or intends to operate, the SUT the control is deployed in, and whose infrastructure or commission produces the Performance Record. In a Self-Provided Engagement the Implementor is the organization and the Provider is the team within it that built or operates the control.
- **Independent Test Lab:** A party that operates a Mine Plan in a replica environment on commission, with no commercial interest in the DUT's outcome beyond the fee for the engagement, disclosed under Section 6.
- **Engagement:** One commissioned Mine Plan against one DUT, from Engagement Manifest to Performance Record.
- **Engagement Mode:** In-Situ or Independent Test Lab (Section 4).
- **Environment Class:** Where the SUT runs: `production`, `pre-production`, `qa`, `dev`, or `lab-replica` (Section 5).
- **Parity Declaration:** The published statement of how an environment differs from the Implementor's production environment, and in what it matches (Section 5.3).
- **Mine Plan:** The committed composition of runs in an Engagement: which PP-SPEC-077 technology profiles and operating modes, whether PP-SPEC-078 applies, which PP-SPEC-013 measurement windows, and how many of each (Section 7).
- **Claim Sheet:** The Provider's written list of what the control stops, contains, or achieves, drawn from whatever states the control's purpose (a datasheet, a README, a design document, a runbook, a policy, a ticket), submitted before the Mine Plan is committed. Every claim becomes a Gold canary (077 5.6.4) or a Performance Specification (013 Section 2) (Section 8.1).
- **Performance Record:** The published result of one Engagement: every run's records, the Claim Sheet graded, operational metrics, the Engagement Manifest, the Parity Declaration, and the funding tier (Section 9).
- **Performance Series:** The ordered Performance Records for one DUT across Engagements and DUT Fingerprints (Section 9.4).
- **Comparability Class:** The tuple that makes two Performance Records comparable: technology profile, Mine Plan version, Environment Class, and Parity Declaration class (Section 9.5).
- **Sponsor:** Whoever pays for the Engagement (Section 6).
- **Right of Reply:** The Provider's ability to append a signed comment to a Performance Record without altering it (Section 8.4).
- **Regulatory Regime:** The set of external rules the Engagement's environment and records must satisfy: `none`, `fedramp_moderate`, `fedramp_high`, `il4`, `il5`, `il6`, `cjis`, `hipaa`, `pci_dss`, `nis2`, `dora`, `gdpr`, or an `x-` extension (Section 5.5). Part of the Comparability Class.
- **Extension:** A value, field, profile, vector, composition, or component added at one of the points Section 13 names, under an `x-` identifier, declared before the first commitment. Extensions add; they never relax (13.3).
- **Acceptance Profile:** A consumer's published statement of what a Performance Record must satisfy to be accepted for a purpose, defined in PP-SPEC-080. CMP produces records; an Acceptance Profile decides whether a reader takes them.

### 2.1. Relationship to other specifications

| Specification | What it provides | What CMP adds |
|---|---|---|
| PP-SPEC-077 Dead Canary | Efficacy of a control: Stopped, Missed, False block, Units of Proof | Who commissions the runs, where they run, how the Provider participates, how results compare across controls of any provenance |
| PP-SPEC-078 Jailed Canary | Containment of an agent: JAILED, ESCAPED | Same, when the control is or protects an AUT |
| PP-SPEC-013 Proof of Performance | Operational performance under load: latency, throughput, uptime, SLA | Measures those *during the Proof Swarm*, so a control's cost is recorded with its efficacy |
| PP-SPEC-006 PES | A score derived from proof records | CMP produces the records the score is computed from; CMP does not define a score |
| PP-SPEC-025 Funding Tier Disclosure | Provider-Funded, Implementor-Funded, PESA-Governed (the PP-SPEC-025 tiers, named with this family's role terms) | CMP requires the tier on every Performance Record and restricts what a Sponsor may do |
| PP-SPEC-009 ProofStamp | Certification mark | A ProofStamp for a control under CMP cites its Performance Series |
| PP-SPEC-004 ProofRegister | Registry API | Every CMP artifact is published there |
| PP-SPEC-080 Pithead Safety and Acceptance Protocol | What a consumer requires before accepting a Performance Record | CMP produces the record; 080 says whether a given reader takes it. CMP never changes to satisfy a profile |

CMP does not restate any rule those specifications make. Where CMP states a rule, it binds the Engagement, not the underlying run.

## 3. The Shift

### 3.1. Legacy model A: the Independent Test Lab report

A laboratory, usually paid by the Provider, runs a fixed suite of attacks against the product in the laboratory's environment and publishes a report with an opinion score. Comparable across Providers because the suite is fixed. Unreal because the environment is the lab's and the suite is known. Provider-funded, so publication is negotiable. Periodic, so the result describes a build that is obsolete on publication.

### 3.2. Legacy model B: the Provider-run proof of concept

The Provider deploys its product in the Implementor's environment for a trial, operated by the Provider's engineers, and reports what its own console detected. Realistic because the environment is real. Self-attested because the Provider holds the labels, runs the test, and reads the result. Unrepeatable and uncommitted, so nothing stops after-the-fact selection.

### 3.3. What CMP keeps and what it removes

Legacy model A tested the canary in an aviary. Legacy model B let the mine's owner report its own air quality. CMP sends the canaries down the mine and lets someone who does not own the mine or the canary read the result.

Both legacy models are stories about Providers because, until now, only Providers were asked to prove anything. The controls an organization builds for itself, adopts from open source, or inherits from its cloud platform were never tested at all; they were assumed to work because someone on staff wrote them. CMP treats those controls exactly as it treats a Provider's: the person who built it does not grade it (4.4).

| Property | Lab report | Provider POC | Coal Mine |
|---|---|---|---|
| Environment | Lab's | Implementor's | Implementor's (In-Situ) or declared replica (Independent Test Lab Mode), with Parity Declaration |
| Who runs the test | Lab | Provider | Implementor's infrastructure or Independent Test Lab; never the Provider |
| Who holds labels | Lab | Provider | Issuer, never the Provider (077 4.1) |
| Who observes outcome | Lab | Provider console | Out-of-band Proof Witness (077 10) |
| Attack set | Fixed, known | Provider-chosen | Committed, mutated, with holdouts (077 6, 9) |
| Provider claims | Marketing input | Marketing input | Claim Sheet, every claim a Gold canary, graded (8.1), from a datasheet or a design doc alike |
| Publication | Negotiable | None | Every run, favorable or not, to a Registry |
| Result | Opinion score | Provider slide | Performance Record: Units of Proof and rates |
| Cadence | Periodic | Once | Bounded runs plus Production Stream; a Performance Series |
| Comparability | High | None | Within Comparability Class (9.5) |
| Funding | Provider | Provider | Disclosed per PP-SPEC-025; Sponsor has no seam |

## 4. Engagement Modes

### 4.1. In-Situ Mode

4.1.1. The SUT is the Implementor's own environment in a declared Environment Class (Section 5). The Provider's product is deployed in it as it would be in service.

4.1.2. The testing equipment, meaning every Integration Point of PP-SPEC-077 Section 18 and, where applicable, PP-SPEC-078 Section 16, is operated by the Implementor, by parties the Implementor commissions, or by an Independent Test Lab acting for the Implementor. The Provider occupies no seam (077 18.1.6, 078 16.1.2).

4.1.3. The control produces its own efficacy telemetry while it operates: in `production` and `pre-production`, PP-SPEC-077 Production Stream Mode (077 16.2) is the normative form; in `qa` and `dev`, Bounded Mode runs (077 16.1) MAY be used alone or with a trickle.

4.1.4. Destructive canary classes and PP-SPEC-078 runs MUST NOT be executed in `production`. They MAY be executed in `pre-production`, `qa`, or `dev` under the Parity Declaration.

4.1.5. The Proof Witness in In-Situ Mode SHOULD be the Implementor's security operations function or an auditor the Implementor appoints. It MUST NOT be the Provider and MUST NOT be the Issuer where another option exists (077 4.2).

### 4.2. Independent Test Lab Mode

4.2.1. The SUT is a `lab-replica` built by the Independent Test Lab from a Parity Declaration agreed with the Implementor, or, for a Provider-sponsored Engagement with no Implementor, from a published Reference Environment (5.4).

4.2.2. The replica MUST have no network path to any Implementor production system. Liveness, egress sinks, and Effect Points are the Lab's.

4.2.3. The Lab MAY occupy IP-1, IP-3, IP-4, IP-5, IP-7, and IP-8. The Proof Witness (IP-6) MUST be a party other than the Lab and its affiliates: the Implementor, an auditor, or a second laboratory. An Engagement in which the Lab operates IP-6 is not a Coal Mine Protocol Engagement, and its results MUST NOT be published as a Performance Record.

4.2.4. Independent Test Lab Mode is the modernized form of legacy model A. What changes: the attack set is committed and mutated, the Provider's claims are graded, publication is mandatory, and the Sponsor has no seam.

### 4.3. Forbidden: Provider-Run Mode

4.3.1. An Engagement in which the Provider, or any party under the Provider's direction, generates canaries, holds labels, operates the Proof Witness, operates the Warden, captures fingerprints, adjudicates, or controls publication is not a Coal Mine Protocol Engagement. This holds whether the Provider is a Provider's field team or the Implementor's own engineers who built the control.

4.3.2. Its results are verification evidence (077 Section 3). They MUST NOT be published as a Performance Record, MUST NOT carry the words "Proof of Performance," and MUST NOT be submitted to a Registry as a CMP artifact.

4.3.3. A Provider MAY run its own PP-SPEC-077 or PP-SPEC-078 runs for internal purposes. Those are the Provider's business and are outside this specification.

### 4.4. Self-Provided Engagements

4.4.1. An organization MAY run an Engagement against a control its own people built, configured, or operate. The organization is the Implementor; the team that built or operates the control is the Provider; and every rule that separates Provider from testing equipment applies between those teams exactly as it would between two companies.

4.4.2. In a Self-Provided Engagement: the Issuer, Proof Witness, Fingerprint Capture, and Adjudicator MUST be operated by people with no reporting line into, and no on-call or change responsibility for, the control under test; the Engagement Manifest MUST name the Provider team and the testing teams and the organizational boundary between them; and the Performance Record MUST carry `self_provided: true`.

4.4.3. Where the organization cannot staff the separation in 4.4.2, the Proof Witness and Issuer seams MUST be filled by an Independent Test Lab, an auditor, or another external party. An Engagement with no external party at any seam and no demonstrable internal separation is Provider-Run (4.3), whatever it is called internally.

4.4.4. Self-Provided records are in the same Comparability Class as any other record produced under the same Mine Plan, Environment Class, and Parity Declaration. The flag is for disclosure, not for discounting. A reader who wants to weight it may; the record does not.

4.4.5. Open source controls are Provider-provided by their maintainers and Self-Provided by whoever configured and deployed them. The Engagement Manifest MUST name both: the upstream project and version as the Provider of the control, and the deploying team as the Provider of the configuration, each under its own Fingerprint (077 15.2).

### 4.5. Maintainer and Licensor Independence

4.5.1. Where the Independent Test Lab, the Issuer, or the operator of any Integration Point is the maintainer of this specification, a holder of patent claims that read on it, or an affiliate of either, the Engagement Manifest and every record the Engagement produces MUST state that relationship in `disclosed_interests` (6.5).

4.5.2. In such an Engagement, the Proof Witness MUST be a party with none of the relationships in 4.5.1.

4.5.3. This specification names, prefers, and requires no operator.

## 5. Environment Classes and Parity

### 5.1. Classes

| Class | Definition | Permitted content |
|---|---|---|
| `production` | The Implementor's live environment serving real users | Non-destructive canaries only; Production Stream Mode; no PP-SPEC-078 |
| `pre-production` | An Implementor environment that mirrors production and receives production-like traffic but no real users | All 077 classes under the Parity Declaration; 078 permitted |
| `qa` | An Implementor test environment | All classes; 078 permitted |
| `dev` | An Implementor developer environment | All classes; results carry the lowest In-Situ weight |
| `lab-replica` | An Independent Test Lab environment built from a Parity Declaration or Reference Environment | All classes; 078 permitted |

5.2. Every Engagement MUST declare its Environment Class in the Engagement Manifest before the first commitment. A change of class is a new Engagement.

### 5.3. Parity Declaration

5.3.1. Every Environment Class other than `production` MUST publish a Parity Declaration: for each of topology, scale, data, identity, DUT configuration, upstream dependencies, and traffic mix, whether it is `identical`, `scaled`, `synthetic`, or `absent` relative to the Implementor's production environment, with a one-line description.

5.3.2. The Parity Declaration MUST be hashed and included in the Engagement Manifest. Changing it is a new Engagement.

5.3.3. A Performance Record's claims extend only as far as the Parity Declaration supports. A record from `dev` with `synthetic` data does not prove behavior on production data, and the record MUST say so in its summary.

### 5.4. Reference Environments

5.4.1. For Independent Test Lab Mode Engagements with no specific Implementor, the Lab MAY use a published Reference Environment: a versioned, hashed description of a representative SUT for one technology profile (077 Section 17).

5.4.2. Reference Environments MUST be published to the Registry before use and MUST carry a Component Fingerprint. Two records built on the same Reference Environment version are in the same Comparability Class.

### 5.5. Regulatory Regime

5.5.1. Every Engagement MUST declare its Regulatory Regime set in the Engagement Manifest. `none` is a valid declaration and MUST be explicit.

5.5.2. A regime MAY constrain where the Proof Witness, the Issuer, and the Registry sit, what canary content is permitted (for example, no real PHI or cardholder data in any canary; synthetic data rules are set per Technology Profile), and what may leave the environment boundary. Those constraints are recorded in the Parity Declaration or Reference Environment, never silently applied.

5.5.3. **Sovereign Registry.** Where a regime requires that records not leave a boundary, the Engagement MUST name a Registry inside that boundary (9.6.3) and that Registry SHOULD cross-anchor its roots (077 Section 21.12.2) to a Registry outside the boundary, so that the existence, Record IDs, receipts, and timing of the records are provable outside while their contents stay inside. The public face of each record (077 Section 21.9.2) crosses the boundary; the contents do not.

5.5.4. The regime set is a component of the Comparability Class (9.5.1). Two records under different regime sets are comparable only where a published regime mapping, registered under 077 Section 21, declares them equivalent for the purpose of the comparison.

## 6. Commissioning and Funding

6.1. Every Engagement MUST declare its Sponsor and its funding tier under PP-SPEC-025 (Provider-Funded, Implementor-Funded, or PESA-Governed) in the Engagement Manifest and on the Performance Record.

6.2. The Sponsor, whoever it is, MUST NOT: select or see canaries before reveal; occupy any seam the Provider may not occupy; delay, veto, or condition publication; or receive results before the Implementor and Provider receive them together.

6.3. A Provider-Funded Independent Test Lab Mode Engagement is permitted. It is the legacy lab model with the Provider removed from every seam and publication made mandatory. The Performance Record MUST state "Provider-Funded" in its title block.

6.4. An Implementor-Funded Engagement, In-Situ or Lab, is the RECOMMENDED form.

6.5. Fees, in-kind contributions, equipment loans, and any commercial relationship between the Lab, the Implementor, and the Provider MUST be listed in `disclosed_interests` (077 4.4) on every record the Engagement produces.

## 7. The Mine Plan

### 7.1. Engagement Manifest

Before the first commitment, the commissioning party MUST publish an Engagement Manifest to the Registry containing:

- Engagement identifier, Implementor (or "none, Reference Environment"), Provider, Independent Test Lab (if any), Sponsor, funding tier
- Engagement Mode and Environment Class
- Parity Declaration hash, or Reference Environment identifier and version
- The DUT: name, version, Control Provenance (`commercial`, `open_source`, `custom`, `managed_service`, `platform_native`, `configuration`), the Provider, whether the Engagement is Self-Provided (4.4), and the party that will capture its Fingerprint (077 IP-5)
- The Claim Sheet hash (8.1)
- Mine Plan (7.2) and its version
- The PP-SPEC-077 Interface Manifest, and the PP-SPEC-078 one where applicable (077 18.1.3)
- Declared thresholds for every run (077 11.3, 15.4, 15.6)
- Publication commitment: that every committed run will be published, including invalid and unfavorable runs
- The Registry or Registries on which the Engagement's records will be registered (9.6.3), and the Holder (9.6.2)
- The Regulatory Regime set (5.5), `none` stated explicitly
- Every Extension in use (Section 13), by `x-` identifier with a pointer to its definition
- The Authorship Disclosure reference (077 21.15) of every component, the Mine Plan composition, and any Reference Environment

The Engagement Manifest MUST be hashed with the domain tag `"CMP-1:engagement"` and bound to a Time Anchor pulse.

### 7.2. Mine Plan

7.2.1. A Mine Plan MUST include, for each technology profile the DUT is claimed to serve (077 Section 17): at least one PP-SPEC-077 Bounded Mode run with White, Gray, Red, and Black canaries present, and Gold canaries for every applicable Claim Sheet entry.

7.2.2. A Mine Plan for a DUT that is, protects, or constrains an agent MUST include at least one PP-SPEC-078 run, with the escape test suite (078 Section 13) executed.

7.2.3. A Mine Plan MUST include at least one PP-SPEC-013 measurement window that overlaps a Proof Swarm release, so that latency, throughput, and resource cost are recorded while the DUT is doing the work it is being credited for. Operational performance measured on an idle DUT is not a CMP artifact.

7.2.4. An In-Situ Mine Plan in `production` or `pre-production` MUST include a Production Stream commitment (077 16.2) of declared minimum duration, and the Performance Record MUST include the resulting series.

7.2.5. The Mine Plan is versioned. Two Engagements are comparable only if they used the same composition version (9.5).

### 7.3. Execution

7.3.1. Runs proceed under their own specifications. CMP adds nothing to the mechanics of a run.

7.3.2. A run that becomes invalid under its own specification is published as invalid. The Engagement continues. An Engagement in which fewer than the Mine Plan's minimum number of runs are valid produces a Performance Record marked `incomplete`, and that record is published.

7.3.3. A DUT Fingerprint change during an Engagement (a molt, 077 15.2.3) marks prior runs stale within the Performance Record and MUST trigger the runs 077 15.3.3 requires. The Provider MUST declare every update in advance; an undeclared molt is a finding (077 15.4.3) on the Performance Record.

7.3.4. **Drift during an Engagement.** Every drift type of PP-SPEC-077 Section 15.1 applies: control, environment, black hole, corpus, threat, profile, harness, pigtail, witness, anchor, specification, and, where PP-SPEC-078 runs are in the Mine Plan, AUT and policy drift. The Engagement Manifest MUST record the starting fingerprint of each (077 15.2, 15.7.2). A change to any of them during the Engagement starts a new segment of the Performance Record (077 15.7.3), MUST be declared by the party responsible for it before it is applied, and is a finding against that party when it is not. The Provider answers for control drift; the Issuer for corpus and profile drift; the operator of each Integration Point for harness and pigtail drift on its seam; the Implementor or Independent Test Lab for environment drift. Nobody answers for threat drift; it is measured, not blamed.

## 8. Provider Participation

The Provider is whoever built, maintains, sells, or operates the control under test (Section 2). Nothing in this section is softened when the Provider is an internal team, an open source project, or a platform.

### 8.1. Claim Sheet

8.1.1. Before the Engagement Manifest is committed, the Provider MUST submit a Claim Sheet: every statement about what the control stops, contains, detects, or achieves, each with the document, version, and exact wording it comes from. For a commercial control that is the datasheet and the contract. For an open source control it is the project's documentation and the deploying team's stated reason for choosing it. For a custom or platform-native control it is the design document, the runbook, the policy, or the ticket that says what the control is for. A control nobody wrote a purpose for has no claims, and 8.1.3 applies.

8.1.2. Every efficacy or containment claim becomes at least one Gold canary (077 5.6.4) in the Mine Plan. Every operational claim becomes a PP-SPEC-013 Performance Specification. A claim the Provider does not submit MAY still be tested by the Issuer, as a Gold canary citing the public document.

8.1.3. A Provider that submits no Claim Sheet has made no claims for CMP purposes, and the Performance Record MUST say so.

### 8.2. Duties

The Provider MUST: supply the DUT build and configuration exactly as it is, or would be, deployed in service; cooperate with independent fingerprint capture (077 15.2.4), including read access to deployed configuration; declare every update, patch, signature feed change, or model change before it is applied during the Engagement; and refrain from any tuning, rule change, or support intervention that is not also declared and fingerprinted.

### 8.3. Prohibitions

The Provider MUST NOT: occupy any Integration Point (077 18.1.6, 078 16.1.2); receive labels, colors, the Proof Swarm, or the release schedule before reveal; access, influence, or receive feeds from the Proof Witness, the Ingress Observer, or the liveness probes; condition the Engagement on a right to review, delay, or veto publication; or present any part of the Engagement's output as its own test result.

### 8.4. Rights

The Provider: receives every published record at the same time as the Implementor; MAY exercise the Right of Reply, a signed comment of any length appended to the Performance Record, visibly separate from the record, never altering it; MAY request a new Engagement, or additional runs within the Mine Plan, against a new DUT Fingerprint, which produces a new entry in the Performance Series; and MAY cite its Performance Record, in full and with its Registry URI, in any material.

### 8.5. Provider-side telemetry

The DUT's own logs, alerts, and dashboards are verification evidence (077 Section 3). They MAY be attached to the Performance Record as annotations and MUST NOT be used to establish any outcome, rate, or verdict.

## 9. The Performance Record

### 9.1. Contents

One Performance Record per Engagement, published to the Registry, containing:

- The Engagement Manifest and its anchor
- Engagement Mode, Environment Class, Parity Declaration or Reference Environment, funding tier, Sponsor, disclosed interests
- The Provider, the Control Provenance, and whether the Engagement is Self-Provided (4.4), with the organizational separation declared
- For every run in the Mine Plan: the Registry URIs of its commitment, witness records, reveal, and result, and whether it was valid
- All Units of Proof, rates per attribution level, Claim Findings, replay and wild findings, black hole rates, witness accuracy, and coverage maps, from PP-SPEC-077
- All bookings, verdicts, escape vectors tested, and rates from PP-SPEC-078, where applicable
- PP-SPEC-013 operational metrics for each measurement window, with the Proof Swarm load active during it
- The Claim Sheet with each claim's outcome: `held`, `failed`, `not tested`, with the Gold canary or Performance Specification that tested it
- DUT and CUT Fingerprints at start and end, and every molt during the Engagement
- SUT, Corpus, Pigtail, and Component Fingerprints at start and end, every drift event with its type and responsible party, and the resulting segments (7.3.4)
- The Provider's Right of Reply, if any
- A summary that states, in one paragraph, what the record proves and what the Parity Declaration prevents it from proving

### 9.2. What a Performance Record is not

9.2.1. It is not a score. PP-SPEC-006 MAY compute a score from it; the record stands without one.

9.2.2. It is not a pass or fail. It is the outcomes. An Implementor decides what rate is acceptable for its own risk.

9.2.3. It is not a certification. PP-SPEC-009 MAY issue a ProofStamp citing a Performance Series; the stamp is a separate act by a separate authority.

### 9.3. Reports

A narrative report MAY be written from a Performance Record. It MUST cite the record's Registry URI on its first page, MUST NOT state any number the record does not contain, and MUST reproduce the record's summary paragraph (9.1) verbatim. A report without a record is legacy model A and is outside this specification.

### 9.4. Performance Series

9.4.1. Every Performance Record for a DUT joins that DUT's Performance Series, ordered by Engagement date and keyed by DUT Fingerprint.

9.4.2. A Series MUST show, for each entry, the Environment Class and Comparability Class, so that a reader can see which entries are comparable to which.

9.4.3. A Series is segmented at every drift event recorded in its Performance Records (7.3.4), and rates are shown per segment. A Series whose segments are too short to meet the Mine Plan minimum is `fragmented`; that is a finding about the stability of the testing, not about the control.

9.4.4. A Series with a current Production Stream entry is `live`. A Series whose latest entry is stale under 077 15.2.3 is `stale`. The state MUST be shown wherever the Series is cited.

### 9.5. Comparability

9.5.1. Two Performance Records are comparable only within the same Comparability Class: the same technology profile, the same Mine Plan composition and version, the same Environment Class, the same Parity Declaration class or Reference Environment version, and the same Regulatory Regime set (5.5.4).

9.5.2. Any table, ranking, or statement that places two Providers' records side by side MUST state the Comparability Class and MUST NOT include records from different classes in one comparison.

9.5.3. In-Situ records from different Implementors are not comparable to each other except through the Reference Environment they most closely match, and only when the Parity Declaration says so.

9.5.4. Control Provenance is not part of the Comparability Class. A commercial control, an open source control, and a custom control tested under the same Mine Plan, Environment Class, and Parity Declaration are comparable, and MAY be placed side by side. The provenance and any `self_provided` flag MUST be shown in the comparison so a reader can weight them if they choose; the record does not weight them.

9.5.5. **Class and scale.** The class is decided by what was fired and where it landed, never by what the control is called or what it protects. Three WAFs of three provenances tested under the Web Application profile (077 17.3) share a class. An agent guardrail tested under the Agentic AI Controls profile (077 17.9) with PP-SPEC-078 runs in its Mine Plan is in a different class, and its rates MUST NOT be placed beside a WAF's as a ranking. What the two records share is the scale: the same Record ID construction, Outcome list, metric definitions, Absence Ladder, Registry, and Conformance Levels, so one reader with one parser reads both. A WAF in front of an agent's HTTP API, tested with web canaries, is in the Web Application class; the agent behind it does not change that. A control tested under two profiles produces one Performance Record carrying one class per profile, and comparison happens per profile.

### 9.6. Record form and registration

9.6.1. **The Performance Record is a Bundle.** It is a Bundle under PP-SPEC-077 Section 21.7 whose leaves are the Record IDs of every Unit of Proof, booking, finding, fingerprint, Interface Manifest, PP-SPEC-013 measurement record, and Claim Sheet outcome the Engagement produced. It has its own Record ID, Signature Envelope, Registry Receipt, and Disclosure Level under 077 Section 21, and carries its Comparability Class (9.5) as a field, so that any two Bundles can be tested for comparability from their records alone.

9.6.2. **Holder.** The Holder of every record in an Engagement is the Implementor, or, for a Reference Environment Engagement with no Implementor, the Independent Test Lab. The Holder is never the Provider and never the Sponsor unless the Sponsor is the Implementor. The Holder is named in the Engagement Manifest before the first commitment and cannot change during the Engagement.

9.6.3. **Accepted Registries.** The Engagement Manifest MUST name the Registry or Registries on which the Engagement's records will be registered. An Independent Test Lab MUST name only Registries its accreditation accepts. A record registered elsewhere is not part of the Engagement, whatever its content. A Regulatory Regime MAY require a Registry inside its boundary (5.5.3).

9.6.4. **Conformance Level.** An Engagement is complete only when every record it produced is at the **Registered** level of 077 Section 21.13, including the Performance Record itself. A Performance Record assembled from any Executed or merely Conformant run is not a Performance Record and MUST NOT be published as one (IP-M5).

9.6.5. **Disclosure.** The Performance Record's Disclosure Level is `public` by default. An In-Situ Engagement MAY register the Performance Record as `holder_only`; in that case the record's existence, Record ID, receipt, Holder, Comparability Class, series state, and the summary paragraph (9.1) are nonetheless public under 077 Section 21.9.2, and any rate the Implementor or Provider cites from it MUST be accompanied by the Record ID so it can be checked by a party the Holder authorizes.

9.6.6. **Series as Bundles.** A Performance Series (9.4) is a Bundle of Performance Records for one DUT, re-registered on each new entry with a new Record ID and receipt. Its `live` or `stale` state is a field of the Series Bundle.

9.6.8. **Humans and machines.** PP-SPEC-077 21.14 applies to the Engagement Manifest, the Performance Record, the Performance Series, and every other record of an Engagement. The Performance Record's summary paragraph (9.1) is its human form's first paragraph; its JSON form is its machine form; neither may say anything the other does not.

9.6.9. **Authorship Disclosure.** PP-SPEC-077 21.15 applies to the Engagement Manifest's components, to every Mine Plan composition and Reference Environment, and to every narrative report (9.3). A report drafted in whole or part by AI says so in its first paragraph, alongside the Registry URI it cites. The Engagement Manifest MUST carry the disclosure reference of every component and of the Mine Plan composition it uses.

9.6.7. **Revocation.** A Performance Record MAY be revoked under 077 Section 21.6 by the Issuer, Proof Witness, or Registry of the Engagement, with reason code. The Provider's remedy is the Right of Reply (8.4) and a new Engagement, never revocation.

## 10. Implementor Use

10.1. **Procurement.** An Implementor MAY require, as a condition of evaluation, that a Provider participate in a CMP Engagement, and MAY specify the Engagement Mode, Environment Class, and Mine Plan version. Model language is given in docs/procurement.md (informative).

10.2. **Contract.** An Implementor MAY tie contractual remedies to Claim Findings (077 11.6) and to PP-SPEC-013 Performance Specification failures recorded in an In-Situ Production Stream series, since both are independently witnessed and anchored.

10.3. **Operations.** An In-Situ Production Stream series is a continuous Proof of Performance. An Implementor's security operations function MAY treat silent drift and undeclared molt findings as change-control events.

## 11. Security Considerations

- **Lab gaming:** A Provider that knows the lab's suite tunes for it. Mitigated by committed mutation and holdouts (077 6), Gold canaries drawn from the Provider's own claims, Reference Environments that are versioned and fingerprinted, and the preference for In-Situ Mode.
- **Sponsor pressure:** The party paying wants a result. Mitigated by the publication commitment in the Engagement Manifest, anchored before the first run, and by the Sponsor's exclusion from every seam (6.2).
- **Parity laundering:** A favorable record from a thin environment presented as if from production. Mitigated by the mandatory Parity Declaration, its hash in the Manifest, the summary paragraph, and the Comparability Class rule (9.5).
- **Implementor and Provider collusion:** An Implementor that wants a particular Provider to win. Mitigated by the Proof Witness independence rules (077 4, 10), mandatory publication, and the Registry.
- **Replica leakage:** A Lab replica with a path to Implementor production. Prohibited by 4.2.2; detected by the Wall Witness pattern of PP-SPEC-078 where used.
- **Claim dodging:** A Provider that submits a thin Claim Sheet. Mitigated by 8.1.2, which lets the Issuer test public claims the Provider omitted, and by 8.1.3, which records the omission.
- **Telemetry substitution:** A Provider console presented as proof of outcome. Prohibited by 8.5.

## 12. Integration Points

PP-SPEC-077 Section 18 and PP-SPEC-078 Section 16 apply. CMP adds:

| ID | Integration Point | What plugs in | MUST do | MUST emit |
|---|---|---|---|---|
| **IP-M1** | Commissioning Party | Implementor procurement, PESA, a Lab acting for an Implementor | Produce the Engagement Manifest; declare funding tier and Sponsor; commit to publication | Engagement Manifest, anchored |
| **IP-M2** | Environment Provider | IaC pipelines, lab builders, replica orchestration | Build and fingerprint the SUT for the declared class; produce the Parity Declaration or instantiate a Reference Environment | Environment fingerprint, Parity Declaration |
| **IP-M3** | Claim Sheet Intake | Provider portals, procurement tools | Receive the Provider's claims with provenance; hash them; hand each to the Issuer for Gold canary or Performance Specification creation | Claim Sheet hash, claim-to-canary mapping |
| **IP-M4** | Operational Meter | APM, load generators, PP-SPEC-013 witnesses | Measure latency, throughput, resource cost during Proof Swarm release; anchor windows to the same pulses the runs use | PP-SPEC-013 Performance Records tied to run identifiers |
| **IP-M5** | Record Assembler | Reporting tools | Assemble the Performance Record from Registry URIs only; never from unregistered data; compute nothing that a run did not | Performance Record, Series entry |

Separation: the Provider occupies none of these. IP-M1 and the Proof Witness (077 IP-6) SHOULD differ. IP-M5 MUST NOT alter any number it assembles.

## 13. Extension Policy

This section says where the specifications in this family may be extended, by whom, how, and what an extension can never touch. It binds PP-SPEC-077 and PP-SPEC-078 as well as this specification; those specifications point here.

### 13.1. Extension points

| Extension point | Who typically uses it | How | Effect on comparability |
|---|---|---|---|
| Integration Points (077 Section 18, 078 Section 16, Section 12) | Providers of any kind building components | Implement the seam; declare in the Interface Manifest with its Authorship Disclosure (077 21.15); claim conformance per seam only | None; components are interchangeable by design |
| Technology Profiles (077 Section 17) | Sector groups, Providers in a new category, the maintainer | Publish under `x-<org>-<name>`, defining canary shapes, Effect Points, token shaper, synthetic data rules | Records under an `x-` profile are comparable only to each other |
| Enumeration values (Control Provenance, Environment Class, Regulatory Regime, offense codes, effect types, verdict annotations) | Anyone with a case the list lacks | `x-<org>-<value>`; recorded verbatim | Breaks comparability on that axis until adopted (13.5) |
| Record fields | Providers attaching telemetry; consumers attaching tags | Under one `extensions.<org>` object; never top level; outside the Record ID canonical form unless the manifest declares otherwise | None when outside the Record ID; declared when inside |
| Mine Plan compositions (7.2) | Implementors, Independent Labs, sector bodies, Acceptance Profiles | Publish a named, versioned composition at or above the spec minimums | The composition is a Comparability Class component |
| Claim Sheet sources (8.1) | Providers | Any document that states the control's purpose, cited by version and wording | None |
| Reference Environments (5.4) | Independent Labs, sector bodies | Publish with Component Fingerprint to the Registry | Defines its own class |
| Escape vectors (078 Section 13) | Containment researchers, Providers | `x-` vectors added to the suite; ES-01 to ES-09 stay mandatory | Reported separately from the mandatory nine |
| Pithead Safety and Acceptance Protocol (PP-SPEC-080) | Insurers, regulators, Implementors, sector bodies | Publish a profile; a profile never changes a record, only whether a reader accepts it | None |
| Enrichments (Proof Protocol License 1.0 Section E) | Anyone adding a method, profile, suite, or text | Lineage Node, countersigned by the root | Governed by the license, not by this section |

### 13.2. What is not extensible

An "extension" to any of the following is a fork and MUST be labeled as a fork wherever it is named: the commitment formula, Merkle tags, order-seed derivation, and reveal rule (077 Section 9); Outcome semantics, the Absence Ladder precedence, and closed accounting (077 5.6.6, 14.3); the independence rules and the Provider-Run prohibition (077 Section 4, 4.3 here); Record ID construction, canonical form, and the registration fields excluded from it (077 21.1, 21.2); the Conformance Level words and their meanings (077 21.13); the booking co-signature requirement and verdict definitions (078 Sections 8 and 10); registration before publication (077 9.7, 078 11.5, 9.6.4 here); and any rule that keeps labels, colors, Proof Swarms, or schedules from a Provider before reveal.

### 13.3. Add, never relax

An extension MAY introduce a new value, field, profile, vector, composition, Reference Environment, or component. It MUST NOT loosen any MUST, widen any permission, remove any required field, lower any minimum, or redefine any term. A Technology Profile that drops the Ingress Observer is not a profile.

### 13.4. Declare or it did not happen

Every extension in use MUST be listed in the Interface Manifest or Engagement Manifest before the first commitment, by `x-` identifier with a pointer to its definition. An undeclared extension found in any record is a finding, and the record MUST NOT be described as Registered.

### 13.5. Providers

A Provider's place is the Integration Points and the `extensions.<provider>` object. A Provider MAY add a sensor, a release driver, a Warden, a cell provider, a registry client, a profile, or an escape vector, and MAY attach its own telemetry as an annotation (8.5). A Provider MUST NOT add an Outcome, a verdict, a Conformance Level, a reason a canary should not count, or any value that a run's adjudication depends on.

### 13.6. Promotion

An `x-` value, profile, composition, or vector that three independent Engagements have declared MAY be proposed for adoption. It is adopted by a specification revision published for public review, and the prefix is dropped.

*Informative:* where the proposer holds a Proof Protocol License 1.0 Section E Lineage Node for an adopted item, adoption recognizes that node.

### 13.7. Reserved

Multi-Provider bake-offs within one Engagement and Implementor consortia sharing a Mine Plan remain reserved for future revisions. Consumer-side requirements are PP-SPEC-080, not a revision of this specification.

## 14. Interpretation

Nebulonium, Inc., as maintainer of Proof Protocol, is responsible for the editorial text of this specification. Whether an Engagement or record conforms is determined from its records against the normative text, and is not decided by the maintainer.

## Revision History

| Version | Date | Notes |
|---|---|---|
| 0.1.0 | 2026-10-10 | Initial draft. Engagement layer over PP-SPEC-077, 078, and 013: In-Situ and Independent Lab modes, Provider-Run forbidden, Environment Classes and Parity Declarations, funding per PP-SPEC-025, Engagement Manifest with `CMP-1:engagement` tag, Claim Sheet to Gold canaries, Provider duties, prohibitions, and Right of Reply, Performance Record and Series, Comparability Class, IP-M1 to IP-M5. |
| 0.1.1 | 2026-10-12 | Shared family problem statement at the top of the Introduction. Flock renamed Proof Swarm, following PP-SPEC-077 v0.7.2. 9.6.9 Authorship Disclosure (077 21.15) for components, compositions, Reference Environments, and reports. 9.6.8 humans and machines (077 21.14). 7.3.4 drift during an Engagement covering every 077 15.1 type with the responsible party for each; Performance Record and Series carry SUT, Corpus, Pigtail, and Component Fingerprints and segments; `fragmented` series state. 5.5 Regulatory Regime (declared, in the Comparability Class, sovereign Registry with cross-anchoring); 9.5.5 class versus scale; Section 13 Extension Policy (extension points, what is not extensible, add never relax, declare or it did not happen, Providers, promotion) binding 077 and 078; 2.1 and 13.7 point consumer requirements at PP-SPEC-080. Generalized from vendor products to controls of any provenance: Provider replaces Vendor as the constrained party (Vendor kept only for the commercial case), Control Provenance recorded, 4.4 Self-Provided Engagements with team separation rules, 9.5.4 provenance never affects comparability, Claim Sheet sources widened to READMEs, design documents, runbooks, and policies. Added the Introduction (why this specification exists, scope, what it is not). 9.6 Record form and registration: the Performance Record and the Performance Series are Bundles under 077 Section 21; Holder is the Buyer or the Independent Lab, never the Provider; Engagement Manifest names accepted Registries and the Holder; an Engagement is complete only at the Registered level; Disclosure Level with public summary; revocation. Builds on 077 v0.7.2 and 078 v0.2.1. |
| 0.1.2 | 2026-10-13 | 4.2.3: the Proof Witness MUST be independent of the Lab and its affiliates; a Lab-operated witness no longer conforms. 4.5 Maintainer and Licensor Independence: disclosure of maintainer, patent-holder, or affiliate relationships, and an unrelated Proof Witness in those Engagements; the specification names, prefers, and requires no operator. Abstract no longer names an operator. Section 14 limited to editorial responsibility; conformance is determined from the records. |
| 0.1.3 | 2026-10-13 | 13.6: an extension is adopted by a specification revision published for public review, not by the maintainer; the Proof Protocol License 1.0 Lineage Node sentence is informative. 13.7: reserved items no longer reserved to the maintainer. |
