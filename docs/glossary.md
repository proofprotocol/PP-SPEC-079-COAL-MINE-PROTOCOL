# Glossary

*Informative. Normative definitions are in [SPEC.md](../SPEC.md), Section 2. Terms from PP-SPEC-077 and 078 are not repeated.*

| Term | Meaning |
|---|---|
| **Mine Plan** | The committed set of runs in an engagement: which 077 profiles and modes, whether 078 applies, which 013 windows, how many of each. Versioned. |
| **Engagement** | One commissioned Mine Plan against one product, manifest to record. |
| **In-Situ Mode** | The Mine Plan runs in the Implementor's own environment; the Implementor's infrastructure is the testing equipment. |
| **Independent Test Lab Mode** | The Mine Plan runs in a lab replica with no path to Implementor production. The old lab model with the Provider removed from every seam. |
| **Provider-Run Mode** | Forbidden. A test operated by whoever built or runs the control, Provider or internal team, is verification, not proof. |
| **Provider** | Whoever built, maintains, sells, or operates the control: Provider, open source project, managed service, platform, or internal team. |
| **Control Provenance** | commercial, open_source, custom, managed_service, platform_native, configuration. Recorded, never a comparability factor. |
| **Self-Provided** | Implementor and Provider are the same organization; team separation rules apply (4.4). |
| **Environment Class** | production, pre-production, qa, dev, or lab-replica. |
| **Parity Declaration** | How an environment matches or differs from production: topology, scale, data, identity, DUT config, dependencies, traffic. Hashed into the manifest. |
| **Reference Environment** | A published, versioned, fingerprinted SUT description for one technology profile, used by labs with no specific Implementor. |
| **Engagement Manifest** | Published before the first commitment: who, where, how funded, what Mine Plan, what claims, and the promise to publish everything. Hashed with `CMP-1:engagement`, anchored. |
| **Claim Sheet** | The Provider's own claims with provenance. Each becomes a Gold canary or a Performance Specification. |
| **Right of Reply** | The Provider's signed comment appended to a record, visibly separate, never altering it. |
| **Molt (during engagement)** | A DUT fingerprint change. Must be declared in advance; undeclared is a finding. |
| **Performance Record** | The published result of one engagement: every run's URIs, all outcomes and rates, claims graded, operational metrics under load, fingerprints, parity, funding, reply, and a one-paragraph summary of what it does and does not prove. |
| **Performance Series** | A product's records over time, keyed by fingerprint, marked live or stale. |
| **Comparability Class** | Profile + Mine Plan version + environment class + parity class. Records compare only within one. |
| **Sponsor** | Whoever pays. Disclosed per PP-SPEC-025. Has no seam. |
| **IP-M1 to IP-M5** | The seams CMP adds: Commissioning Party, Environment Provider, Claim Sheet Intake, Operational Meter, Record Assembler. |
