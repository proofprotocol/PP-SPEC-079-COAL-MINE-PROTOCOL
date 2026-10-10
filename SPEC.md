# Proof of Performance Engagement: The Coal Mine Protocol (CMP)

*A Proof Protocol specification*

> **Ownership and Attribution Notice**
>
> This specification is authored by **Craig Ellrod** (Nebulonium, Inc., dba HACKERverse) and is published as part of **Proof Protocol**. Copyright (c) 2026 Nebulonium, Inc.
>
> Any use, implementation, derivative, citation, or incorporation of this specification, in whole or in part, MUST attribute **Craig Ellrod, Nebulonium, Inc., and Proof Protocol**. This requirement applies to standards bodies, working groups, consortia, testing laboratories, and commercial implementations.
>
> The text of this specification is licensed under the Proof Protocol Public License, Version 1.0, Part A (see LICENSE.md). Attribution is a condition of the license; derivative texts are share-alike; conformance may be claimed only per Integration Point; no patent license is granted.
>
> **Patent rights reserved.** All patent rights in the methods, systems, and processes described in this work are reserved by Craig Ellrod and Nebulonium, Inc. Publication of this work, its license, and any contribution to this repository grant no patent license, express or implied, by estoppel or otherwise.
>
> This specification is related to the Proof Economy Prior Art Declaration, DOI [10.5281/zenodo.21379780](https://doi.org/10.5281/zenodo.21379780).

| Field | Value |
|---|---|
| Spec ID | PP-SPEC-079 |
| Version | 0.1.0 (Draft) |
| Date | 2026-10-10 |
| Status | Draft for public record |
| Maintainer | Nebulonium, Inc. (Proof Protocol) |
| Builds on | PP-SPEC-077 v0.8.0 (Dead Canary), PP-SPEC-078 v0.3.0 (Jailed Canary), PP-SPEC-013 v1.0 (Proof of Performance), PP-SPEC-006 (Proof of Efficacy Score), PP-SPEC-025 (Funding Tier Disclosure), PP-SPEC-004 (ProofRegister API) |

---

## Abstract

For twenty years a security buyer had two ways to learn whether a product worked. An independent laboratory, paid by the vendor, ran a fixed suite of attacks in the laboratory's own environment and published a report. Or the vendor ran a proof of concept inside the buyer's environment, operated by the vendor's own engineers, and reported what the vendor's console showed. The first was comparable but unreal and vendor-funded. The second was realistic but self-attested and unrepeatable. Neither produced proof.

The Coal Mine Protocol replaces both. The vendor's product becomes a Device Under Test inside a Solution Under Test, and its performance is measured by testing equipment the vendor does not touch: the committed, witnessed, anchored runs of PP-SPEC-077 for efficacy, PP-SPEC-078 for agent containment, and PP-SPEC-013 for operational performance under the same load. The testing equipment is operated in one of two places. **In-Situ Mode**: the buyer's own infrastructure, in production, pre-production, QA, or a development lab, where the product produces its own efficacy telemetry while it operates. **Independent Lab Mode**: a laboratory, such as HACKERverse, that performs the same motion in a replica environment never connected to the buyer's live systems. In both, the output is not a report but a Performance Record: Units of Proof, rates, findings, and the vendor's own written claims graded against outcome, published to a Registry.

A vendor-operated test is verification. It is not a Coal Mine Protocol Engagement, and its results MUST NOT be called Proof of Performance.

## 1. Conventions

The key words MUST, MUST NOT, REQUIRED, SHALL, SHALL NOT, SHOULD, SHOULD NOT, RECOMMENDED, MAY, and OPTIONAL are to be interpreted as described in RFC 2119 and RFC 8174.

## 2. Terminology

Terms defined in PP-SPEC-077 Section 2 and PP-SPEC-078 Section 2 have the same meaning here, including SUT, DUT, CUT, AUT, Issuer, Vendor, Proof Witness, Time Anchor, Unit of Proof, Registry, Integration Point, Component Fingerprint, and Interface Manifest. The following terms are added:

- **Buyer:** The party that operates, or intends to operate, the SUT the Vendor's product is deployed in, and whose infrastructure or commission produces the Performance Record.
- **Independent Lab:** A party that operates a Mine Plan in a replica environment on commission, with no commercial interest in the DUT's outcome beyond the fee for the engagement, disclosed under Section 6.
- **Engagement:** One commissioned Mine Plan against one DUT, from Engagement Manifest to Performance Record.
- **Engagement Mode:** In-Situ or Independent Lab (Section 4).
- **Environment Class:** Where the SUT runs: `production`, `pre-production`, `qa`, `development`, or `lab-replica` (Section 5).
- **Parity Declaration:** The published statement of how an environment differs from the Buyer's production environment, and in what it matches (Section 5.3).
- **Mine Plan:** The committed composition of runs in an Engagement: which PP-SPEC-077 technology profiles and operating modes, whether PP-SPEC-078 applies, which PP-SPEC-013 measurement windows, and how many of each (Section 7).
- **Claim Sheet:** The Vendor's written list of what the product stops, contains, or achieves, submitted before the Mine Plan is committed. Every claim becomes a Gold canary (077 5.6.4) or a Performance Specification (013 Section 2) (Section 8.1).
- **Performance Record:** The published result of one Engagement: every run's records, the Claim Sheet graded, operational metrics, the Engagement Manifest, the Parity Declaration, and the funding tier (Section 9).
- **Performance Series:** The ordered Performance Records for one DUT across Engagements and DUT Fingerprints (Section 9.4).
- **Comparability Class:** The tuple that makes two Performance Records comparable: technology profile, Mine Plan version, Environment Class, and Parity Declaration class (Section 9.5).
- **Sponsor:** Whoever pays for the Engagement (Section 6).
- **Right of Reply:** The Vendor's ability to append a signed comment to a Performance Record without altering it (Section 8.4).

### 2.1. Relationship to other specifications

| Specification | What it provides | What CMP adds |
|---|---|---|
| PP-SPEC-077 Dead Canary | Efficacy of a control: Stopped, Missed, False block, Units of Proof | Who commissions the runs, where they run, how the Vendor participates, how results compare across vendors |
| PP-SPEC-078 Jailed Canary | Containment of an agent: JAILED, ESCAPED | Same, when the product is or protects an AUT |
| PP-SPEC-013 Proof of Performance | Operational performance under load: latency, throughput, uptime, SLA | Measures those *during the flock*, so a control's cost is recorded with its efficacy |
| PP-SPEC-006 PES | A score derived from proof records | CMP produces the records the score is computed from; CMP does not define a score |
| PP-SPEC-025 Funding Tier Disclosure | Vendor-Funded, Buyer-Funded, PESA-Governed | CMP requires the tier on every Performance Record and restricts what a Sponsor may do |
| PP-SPEC-009 ProofStamp | Certification mark | A ProofStamp for a product under CMP cites its Performance Series |
| PP-SPEC-004 ProofRegister | Registry API | Every CMP artifact is published there |

CMP does not restate any rule those specifications make. Where CMP states a rule, it binds the Engagement, not the underlying run.

## 3. The Shift

### 3.1. Legacy model A: the independent lab report

A laboratory, usually paid by the vendor, runs a fixed suite of attacks against the product in the laboratory's environment and publishes a report with an opinion score. Comparable across vendors because the suite is fixed. Unreal because the environment is the lab's and the suite is known. Vendor-funded, so publication is negotiable. Periodic, so the result describes a build that is obsolete on publication.

### 3.2. Legacy model B: the vendor-run proof of concept

The vendor deploys its product in the buyer's environment for a trial, operated by the vendor's engineers, and reports what its own console detected. Realistic because the environment is real. Self-attested because the vendor holds the labels, runs the test, and reads the result. Unrepeatable and uncommitted, so nothing stops after-the-fact selection.

### 3.3. What CMP keeps and what it removes

Legacy model A tested the canary in an aviary. Legacy model B let the mine's owner report its own air quality. CMP sends the canaries down the mine and lets someone who does not own the mine or the canary read the result.

| Property | Lab report | Vendor POC | Coal Mine |
|---|---|---|---|
| Environment | Lab's | Buyer's | Buyer's (In-Situ) or declared replica (Lab Mode), with Parity Declaration |
| Who runs the test | Lab | Vendor | Buyer's infrastructure or Independent Lab; never the Vendor |
| Who holds labels | Lab | Vendor | Issuer, never the Vendor (077 4.1) |
| Who observes outcome | Lab | Vendor console | Out-of-band Proof Witness (077 10) |
| Attack set | Fixed, known | Vendor-chosen | Committed, mutated, with holdouts (077 6, 9) |
| Vendor claims | Marketing input | Marketing input | Claim Sheet, every claim a Gold canary, graded (8.1) |
| Publication | Negotiable | None | Every run, favorable or not, to a Registry |
| Result | Opinion score | Vendor slide | Performance Record: Units of Proof and rates |
| Cadence | Periodic | Once | Bounded runs plus Production Stream; a Performance Series |
| Comparability | High | None | Within Comparability Class (9.5) |
| Funding | Vendor | Vendor | Disclosed per PP-SPEC-025; Sponsor has no seam |

## 4. Engagement Modes

### 4.1. In-Situ Mode

4.1.1. The SUT is the Buyer's own environment in a declared Environment Class (Section 5). The Vendor's product is deployed in it as it would be in service.

4.1.2. The testing equipment, meaning every Integration Point of PP-SPEC-077 Section 18 and, where applicable, PP-SPEC-078 Section 16, is operated by the Buyer, by parties the Buyer commissions, or by an Independent Lab acting for the Buyer. The Vendor occupies no seam (077 18.1.6, 078 16.1.2).

4.1.3. The product produces its own efficacy telemetry while it operates: in `production` and `pre-production`, PP-SPEC-077 Production Stream Mode (077 16.2) is the normative form; in `qa` and `development`, Bounded Mode runs (077 16.1) MAY be used alone or with a trickle.

4.1.4. Destructive canary classes and PP-SPEC-078 runs MUST NOT be executed in `production`. They MAY be executed in `pre-production`, `qa`, or `development` under the Parity Declaration.

4.1.5. The Proof Witness in In-Situ Mode SHOULD be the Buyer's security operations function or an auditor the Buyer appoints. It MUST NOT be the Vendor and MUST NOT be the Issuer where another option exists (077 4.2).

### 4.2. Independent Lab Mode

4.2.1. The SUT is a `lab-replica` built by the Independent Lab from a Parity Declaration agreed with the Buyer, or, for a Vendor-sponsored Engagement with no Buyer, from a published Reference Environment (5.4).

4.2.2. The replica MUST have no network path to any Buyer production system. Liveness, egress sinks, and Effect Points are the Lab's.

4.2.3. The Lab MAY occupy IP-1, IP-3, IP-4, IP-5, IP-7, and IP-8. The Proof Witness (IP-6) SHOULD be a party other than the Lab: the Buyer, an auditor, or a second laboratory. Where the Lab also operates IP-6, the Performance Record MUST say so, and this is the weakest conforming configuration (077 docs/faq, "Can the test operator also run the Proof Witness?").

4.2.4. Lab Mode is the modernized form of legacy model A. What changes: the attack set is committed and mutated, the vendor's claims are graded, publication is mandatory, and the Sponsor has no seam.

### 4.3. Forbidden: Vendor-Run Mode

4.3.1. An Engagement in which the Vendor, or any party under the Vendor's direction, generates canaries, holds labels, operates the Proof Witness, operates the Warden, captures fingerprints, adjudicates, or controls publication is not a Coal Mine Protocol Engagement.

4.3.2. Its results are verification evidence (077 Section 3). They MUST NOT be published as a Performance Record, MUST NOT carry the words "Proof of Performance," and MUST NOT be submitted to a Registry as a CMP artifact.

4.3.3. A Vendor MAY run its own PP-SPEC-077 or PP-SPEC-078 runs for internal purposes. Those are the Vendor's business and are outside this specification.

## 5. Environment Classes and Parity

### 5.1. Classes

| Class | Definition | Permitted content |
|---|---|---|
| `production` | The Buyer's live environment serving real users | Non-destructive canaries only; Production Stream Mode; no PP-SPEC-078 |
| `pre-production` | A Buyer environment that mirrors production and receives production-like traffic but no real users | All 077 classes under the Parity Declaration; 078 permitted |
| `qa` | A Buyer test environment | All classes; 078 permitted |
| `development` | A Buyer developer environment | All classes; results carry the lowest In-Situ weight |
| `lab-replica` | An Independent Lab environment built from a Parity Declaration or Reference Environment | All classes; 078 permitted |

5.2. Every Engagement MUST declare its Environment Class in the Engagement Manifest before the first commitment. A change of class is a new Engagement.

### 5.3. Parity Declaration

5.3.1. Every Environment Class other than `production` MUST publish a Parity Declaration: for each of topology, scale, data, identity, DUT configuration, upstream dependencies, and traffic mix, whether it is `identical`, `scaled`, `synthetic`, or `absent` relative to the Buyer's production environment, with a one-line description.

5.3.2. The Parity Declaration MUST be hashed and included in the Engagement Manifest. Changing it is a new Engagement.

5.3.3. A Performance Record's claims extend only as far as the Parity Declaration supports. A record from `development` with `synthetic` data does not prove behavior on production data, and the record MUST say so in its summary.

### 5.4. Reference Environments

5.4.1. For Lab Mode Engagements with no specific Buyer, the Lab MAY use a published Reference Environment: a versioned, hashed description of a representative SUT for one technology profile (077 Section 17).

5.4.2. Reference Environments MUST be published to the Registry before use and MUST carry a Component Fingerprint. Two records built on the same Reference Environment version are in the same Comparability Class.

## 6. Commissioning and Funding

6.1. Every Engagement MUST declare its Sponsor and its funding tier under PP-SPEC-025 (Vendor-Funded, Buyer-Funded, or PESA-Governed) in the Engagement Manifest and on the Performance Record.

6.2. The Sponsor, whoever it is, MUST NOT: select or see canaries before reveal; occupy any seam the Vendor may not occupy; delay, veto, or condition publication; or receive results before the Buyer and Vendor receive them together.

6.3. A Vendor-Funded Lab Mode Engagement is permitted. It is the legacy lab model with the Vendor removed from every seam and publication made mandatory. The Performance Record MUST state "Vendor-Funded" in its title block.

6.4. A Buyer-Funded Engagement, In-Situ or Lab, is the RECOMMENDED form.

6.5. Fees, in-kind contributions, equipment loans, and any commercial relationship between the Lab, the Buyer, and the Vendor MUST be listed in `disclosed_interests` (077 4.4) on every record the Engagement produces.

## 7. The Mine Plan

### 7.1. Engagement Manifest

Before the first commitment, the commissioning party MUST publish an Engagement Manifest to the Registry containing:

- Engagement identifier, Buyer (or "none, Reference Environment"), Vendor, Independent Lab (if any), Sponsor, funding tier
- Engagement Mode and Environment Class
- Parity Declaration hash, or Reference Environment identifier and version
- The DUT: product, version, and the party that will capture its Fingerprint (077 IP-5)
- The Claim Sheet hash (8.1)
- Mine Plan (7.2) and its version
- The PP-SPEC-077 Interface Manifest, and the PP-SPEC-078 one where applicable (077 18.1.3)
- Declared thresholds for every run (077 11.3, 15.4, 15.6)
- Publication commitment: that every committed run will be published, including invalid and unfavorable runs

The Engagement Manifest MUST be hashed with the domain tag `"CMP-1:engagement"` and bound to a Time Anchor pulse.

### 7.2. Mine Plan

7.2.1. A Mine Plan MUST include, for each technology profile the DUT is claimed to serve (077 Section 17): at least one PP-SPEC-077 Bounded Mode run with White, Gray, Red, and Black canaries present, and Gold canaries for every applicable Claim Sheet entry.

7.2.2. A Mine Plan for a DUT that is, protects, or constrains an agent MUST include at least one PP-SPEC-078 run, with the escape test suite (078 Section 13) executed.

7.2.3. A Mine Plan MUST include at least one PP-SPEC-013 measurement window that overlaps a flock release, so that latency, throughput, and resource cost are recorded while the DUT is doing the work it is being credited for. Operational performance measured on an idle DUT is not a CMP artifact.

7.2.4. An In-Situ Mine Plan in `production` or `pre-production` MUST include a Production Stream commitment (077 16.2) of declared minimum duration, and the Performance Record MUST include the resulting series.

7.2.5. The Mine Plan is versioned. Two Engagements are comparable only if they used the same composition version (9.5).

### 7.3. Execution

7.3.1. Runs proceed under their own specifications. CMP adds nothing to the mechanics of a run.

7.3.2. A run that becomes invalid under its own specification is published as invalid. The Engagement continues. An Engagement in which fewer than the Mine Plan's minimum number of runs are valid produces a Performance Record marked `incomplete`, and that record is published.

7.3.3. A DUT Fingerprint change during an Engagement (a molt, 077 15.2.3) marks prior runs stale within the Performance Record and MUST trigger the runs 077 15.3.3 requires. The Vendor MUST declare every update in advance; an undeclared molt is a finding (077 15.4.3) on the Performance Record.

## 8. Vendor Participation

### 8.1. Claim Sheet

8.1.1. Before the Engagement Manifest is committed, the Vendor MUST submit a Claim Sheet: every public or contractual statement about what the product stops, contains, detects, or achieves, each with the document, version, and exact wording it comes from.

8.1.2. Every efficacy or containment claim becomes at least one Gold canary (077 5.6.4) in the Mine Plan. Every operational claim becomes a PP-SPEC-013 Performance Specification. A claim the Vendor does not submit MAY still be tested by the Issuer, as a Gold canary citing the public document.

8.1.3. A Vendor that submits no Claim Sheet has made no claims for CMP purposes, and the Performance Record MUST say so.

### 8.2. Duties

The Vendor MUST: supply the DUT build and configuration as it would be sold or deployed; cooperate with independent fingerprint capture (077 15.2.4), including read access to deployed configuration; declare every update, patch, signature feed change, or model change before it is applied during the Engagement; and refrain from any tuning, rule change, or support intervention that is not also declared and fingerprinted.

### 8.3. Prohibitions

The Vendor MUST NOT: occupy any Integration Point (077 18.1.6, 078 16.1.2); receive labels, colors, the flock, or the release schedule before reveal; access, influence, or receive feeds from the Proof Witness, the Ingress Observer, or the liveness probes; condition the Engagement on a right to review, delay, or veto publication; or present any part of the Engagement's output as its own test result.

### 8.4. Rights

The Vendor: receives every published record at the same time as the Buyer; MAY exercise the Right of Reply, a signed comment of any length appended to the Performance Record, visibly separate from the record, never altering it; MAY request a new Engagement, or additional runs within the Mine Plan, against a new DUT Fingerprint, which produces a new entry in the Performance Series; and MAY cite its Performance Record, in full and with its Registry URI, in any material.

### 8.5. Vendor-side telemetry

The DUT's own logs, alerts, and dashboards are verification evidence (077 Section 3). They MAY be attached to the Performance Record as annotations and MUST NOT be used to establish any outcome, rate, or verdict.

## 9. The Performance Record

### 9.1. Contents

One Performance Record per Engagement, published to the Registry, containing:

- The Engagement Manifest and its anchor
- Engagement Mode, Environment Class, Parity Declaration or Reference Environment, funding tier, Sponsor, disclosed interests
- For every run in the Mine Plan: the Registry URIs of its commitment, witness records, reveal, and result, and whether it was valid
- All Units of Proof, rates per attribution level, Claim Findings, replay and wild findings, black hole rates, witness accuracy, and coverage maps, from PP-SPEC-077
- All bookings, verdicts, escape vectors tested, and rates from PP-SPEC-078, where applicable
- PP-SPEC-013 operational metrics for each measurement window, with the flock load active during it
- The Claim Sheet with each claim's outcome: `held`, `failed`, `not tested`, with the Gold canary or Performance Specification that tested it
- DUT and CUT Fingerprints at start and end, and every molt during the Engagement
- The Vendor's Right of Reply, if any
- A summary that states, in one paragraph, what the record proves and what the Parity Declaration prevents it from proving

### 9.2. What a Performance Record is not

9.2.1. It is not a score. PP-SPEC-006 MAY compute a score from it; the record stands without one.

9.2.2. It is not a pass or fail. It is the outcomes. A Buyer decides what rate is acceptable for its own risk.

9.2.3. It is not a certification. PP-SPEC-009 MAY issue a ProofStamp citing a Performance Series; the stamp is a separate act by a separate authority.

### 9.3. Reports

A narrative report MAY be written from a Performance Record. It MUST cite the record's Registry URI on its first page, MUST NOT state any number the record does not contain, and MUST reproduce the record's summary paragraph (9.1) verbatim. A report without a record is legacy model A and is outside this specification.

### 9.4. Performance Series

9.4.1. Every Performance Record for a DUT joins that DUT's Performance Series, ordered by Engagement date and keyed by DUT Fingerprint.

9.4.2. A Series MUST show, for each entry, the Environment Class and Comparability Class, so that a reader can see which entries are comparable to which.

9.4.3. A Series with a current Production Stream entry is `live`. A Series whose latest entry is stale under 077 15.2.3 is `stale`. The state MUST be shown wherever the Series is cited.

### 9.5. Comparability

9.5.1. Two Performance Records are comparable only within the same Comparability Class: the same technology profile, the same Mine Plan version, the same Environment Class, and the same Parity Declaration class or Reference Environment version.

9.5.2. Any table, ranking, or statement that places two vendors' records side by side MUST state the Comparability Class and MUST NOT include records from different classes in one comparison.

9.5.3. In-Situ records from different Buyers are not comparable to each other except through the Reference Environment they most closely match, and only when the Parity Declaration says so.

## 10. Buyer Use

10.1. **Procurement.** A Buyer MAY require, as a condition of evaluation, that a Vendor participate in a CMP Engagement, and MAY specify the Engagement Mode, Environment Class, and Mine Plan version. Model language is given in docs/procurement.md (informative).

10.2. **Contract.** A Buyer MAY tie contractual remedies to Claim Findings (077 11.6) and to PP-SPEC-013 Performance Specification failures recorded in an In-Situ Production Stream series, since both are independently witnessed and anchored.

10.3. **Operations.** An In-Situ Production Stream series is a continuous Proof of Performance. A Buyer's security operations function MAY treat silent drift and undeclared molt findings as change-control events.

## 11. Security Considerations

- **Lab gaming:** A Vendor that knows the lab's suite tunes for it. Mitigated by committed mutation and holdouts (077 6), Gold canaries drawn from the Vendor's own claims, Reference Environments that are versioned and fingerprinted, and the preference for In-Situ Mode.
- **Sponsor pressure:** The party paying wants a result. Mitigated by the publication commitment in the Engagement Manifest, anchored before the first run, and by the Sponsor's exclusion from every seam (6.2).
- **Parity laundering:** A favorable record from a thin environment presented as if from production. Mitigated by the mandatory Parity Declaration, its hash in the Manifest, the summary paragraph, and the Comparability Class rule (9.5).
- **Buyer and Vendor collusion:** A Buyer that wants a particular vendor to win. Mitigated by the Proof Witness independence rules (077 4, 10), mandatory publication, and the Registry.
- **Replica leakage:** A Lab replica with a path to Buyer production. Prohibited by 4.2.2; detected by the Wall Witness pattern of PP-SPEC-078 where used.
- **Claim dodging:** A Vendor that submits a thin Claim Sheet. Mitigated by 8.1.2, which lets the Issuer test public claims the Vendor omitted, and by 8.1.3, which records the omission.
- **Telemetry substitution:** A Vendor console presented as outcome evidence. Prohibited by 8.5.

## 12. Integration Points

PP-SPEC-077 Section 18 and PP-SPEC-078 Section 16 apply. CMP adds:

| ID | Integration Point | What plugs in | MUST do | MUST emit |
|---|---|---|---|---|
| **IP-M1** | Commissioning Party | Buyer procurement, PESA, a Lab acting for a Buyer | Produce the Engagement Manifest; declare funding tier and Sponsor; commit to publication | Engagement Manifest, anchored |
| **IP-M2** | Environment Provider | IaC pipelines, lab builders, replica orchestration | Build and fingerprint the SUT for the declared class; produce the Parity Declaration or instantiate a Reference Environment | Environment fingerprint, Parity Declaration |
| **IP-M3** | Claim Sheet Intake | Vendor portals, procurement tools | Receive the Vendor's claims with provenance; hash them; hand each to the Issuer for Gold canary or Performance Specification creation | Claim Sheet hash, claim-to-canary mapping |
| **IP-M4** | Operational Meter | APM, load generators, PP-SPEC-013 witnesses | Measure latency, throughput, resource cost during flock release; anchor windows to the same pulses the runs use | PP-SPEC-013 Performance Records tied to run identifiers |
| **IP-M5** | Record Assembler | Reporting tools | Assemble the Performance Record from Registry URIs only; never from unregistered data; compute nothing that a run did not | Performance Record, Series entry |

Separation: the Vendor occupies none of these. IP-M1 and the Proof Witness (077 IP-6) SHOULD differ. IP-M5 MUST NOT alter any number it assembles.

## 13. Reserved

Sections for multi-vendor bake-offs within one Engagement, Buyer consortia sharing a Mine Plan, and insurance and regulatory consumers of Performance Series are reserved for future revisions by the maintainer.

## 14. Interpretation

Nebulonium, Inc., as maintainer of Proof Protocol, reserves final interpretive discretion over this specification and over conformance claims made under it.

## Revision History

| Version | Date | Notes |
|---|---|---|
| 0.1.0 | 2026-10-10 | Initial draft (first drafted under the working name Gauntlet Protocol, renamed before publication). Engagement layer over PP-SPEC-077, 078, and 013: In-Situ and Independent Lab modes, Vendor-Run forbidden, Environment Classes and Parity Declarations, funding per PP-SPEC-025, Engagement Manifest with `CMP-1:engagement` tag, Claim Sheet to Gold canaries, Vendor duties, prohibitions, and Right of Reply, Performance Record and Series, Comparability Class, IP-M1 to IP-M5. |
