# Proof of Performance Engagement: The Coal Mine Protocol

> **Ownership and Attribution Notice**
>
> The Coal Mine Protocol (PP-SPEC-079) is authored by **Craig Ellrod** (Nebulonium, Inc., dba HACKERverse) and published as part of **Proof Protocol**. Copyright (c) 2026 Nebulonium, Inc.
>
> Any use, implementation, derivative, citation, or incorporation of this work, in whole or in part, MUST attribute **Craig Ellrod, Nebulonium, Inc., and Proof Protocol**. See [NOTICE.md](NOTICE.md).
>
> Text licensed under the Proof Protocol Public License 1.0, Part A (see LICENSE.md). 
>
> **Patent rights reserved.** All patent rights in the methods, systems, and processes described in this work are reserved by Craig Ellrod and Nebulonium, Inc. Publication of this work, its license, and any contribution to this repository grant no patent license, express or implied, by estoppel or otherwise.

---

**The control goes into the Mine Plan. Whoever built it doesn't get to hold the stopwatch.**

For twenty years an Implementor had two ways to find out whether a product worked: pay-to-play lab reports, or a proof of concept run by the Provider's own engineers in the Implementor's environment. The first was comparable and unreal. The second was real and self-attested. Neither was proof.

The Coal Mine Protocol replaces both, for every control: commercial, open source, custom-built, managed, or platform-native, in legacy security stacks and agentic AI systems alike. The control becomes a Device Under Test inside the Implementor's Solution Under Test. Its efficacy is measured by [PP-SPEC-077](https://github.com/proofprotocol/PP-SPEC-077-DEAD-CANARY-PROTOCOL) (Dead Canary), its containment by [PP-SPEC-078](https://github.com/proofprotocol/PP-SPEC-078-NO-BROS-JAIL-MODE-PROTOCOL) (Jailed Canary), and its operational cost by PP-SPEC-013 (Proof of Performance), all under the same committed, witnessed, anchored runs. The testing equipment is operated by one of two parties, and never by the Provider, whether that is a Provider or the team that built the control.

## Two modes

```
  In-Situ Mode                                 Independent Test Lab Mode
  ------------                                 --------------------
  Implementor's environment:                         Lab replica built from a
  production | pre-prod | qa | dev             Parity Declaration or a
                                               Reference Environment.
  Product deployed as sold.                    No path to Implementor production.
  Implementor's infrastructure is the                Lab operates the testing
  testing equipment. Product                   equipment. Witness SHOULD be
  emits its own efficacy telemetry             someone other than the lab.
  while it operates (Production
  Stream, 077 16.2).                           This is the old lab model with
                                               the Provider removed from every
  Witness: Implementor SOC or auditor.               seam and publication mandatory.

                      Forbidden: Provider-Run Mode
                      A Provider-operated test is verification, not proof.
                      It MUST NOT be called Proof of Performance.
```

## What changes for the Provider

- **Claim Sheet.** Every public or contractual claim the Provider makes becomes a Gold canary (077 5.6.4) or a Performance Specification (013). Claims are graded against outcome, and the result is published.
- **No seam.** The Provider supplies the product and cooperates with fingerprinting. It occupies no Integration Point, sees no labels, touches no witness, and cannot veto publication.
- **Right of Reply.** The Provider may append a signed comment to the Performance Record. It cannot change the record.
- **Molt rule.** Every update during an engagement is declared in advance and fingerprinted. An undeclared change is a finding.

## What the Implementor gets

A **Performance Record**: Units of Proof, rates per attribution level, Claim Findings, operational metrics under Proof Swarm load, fingerprints, parity, funding tier, all published to a PP-SPEC-004 registry. Not a score, not a pass/fail, not a certification. The outcomes. A **Performance Series** across engagements and fingerprints, marked live or stale. **Comparability Classes** so that two Providers are only ever compared on the same Mine Plan in the same environment class.

## Repository

| Path | Contents |
|---|---|
| [SPEC.md](SPEC.md) | The normative specification, PP-SPEC-079 |
| [docs/procurement.md](docs/procurement.md) | Model RFP and contract language (informative) |
| [docs/glossary.md](docs/glossary.md) | Terms |
| [docs/conformance.md](docs/conformance.md) | Conformance checklist |
| [docs/faq.md](docs/faq.md) | Common questions |
| [schemas/engagement-manifest.schema.json](schemas/engagement-manifest.schema.json) | Engagement Manifest schema |
| [schemas/performance-record.schema.json](schemas/performance-record.schema.json) | Performance Record schema |
| [CHANGELOG.md](CHANGELOG.md) | Version history |
| [NOTICE.md](NOTICE.md) | Attribution requirements |
| [CITATION.cff](CITATION.cff) | Citation metadata |
| [AI_DISCLOSURE.md](AI_DISCLOSURE.md) | What was human-authored and what was AI-drafted |
| [LICENSE.md](LICENSE.md) | License terms |

## Status

Draft, version 0.1.1, 2026-10-11. Maintained by Nebulonium, Inc. as part of Proof Protocol. Builds on PP-SPEC-077 v0.7.2, PP-SPEC-078 v0.2.1, PP-SPEC-013 v1.0, PP-SPEC-006, PP-SPEC-025, PP-SPEC-004.

Related: Proof Economy Prior Art Declaration, DOI [10.5281/zenodo.21379780](https://doi.org/10.5281/zenodo.21379780).

## Cite

```
Ellrod, C. (2026). Proof of Performance Engagement: The Coal Mine Protocol (PP-SPEC-079), v0.1.1.
Nebulonium, Inc., Proof Protocol.
```
