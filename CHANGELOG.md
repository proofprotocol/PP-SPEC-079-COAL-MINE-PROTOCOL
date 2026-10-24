# Changelog

## 0.1.4 (2026-10-23)
- 2.1: PP-SPEC-081 Reproof row.
- 7.1: `reproof_of` in the Engagement Manifest for Check and Umpire Engagements.
- 9.1: Reproof Status, scope, count, and history on every Performance Record.
- 9.5.6: reproof and Comparability Class.
- 10.4: Implementors may require reproof; no contract may prevent a Check Engagement.
- License: Proof Protocol License 1.1. Specification text is CC BY 4.0 from this version (LICENSE-CC-BY-4.0.md), which grants no patent rights; patents only under LICENSE.md Part A2 and PATENT-SCHEDULE.md. Earlier versions remain Apache-2.0 (Part A6).

## 2026-10-20 (licensor)

- Licensor, copyright holder, maintainer and author changed from Nebulonium, Inc. (dba HACKERverse) to Craig Thomas Ellrod. Contact: CraigEllrod@gmail.com. Historical statements of what HACKERverse published and when are unchanged.
- LICENSE.md: ProofStamp named as a Mark; new C9 makes ProofStamp issuance exclusive to the Licensor and excludes it from any transfer to PESA. ETHICS.md section 4 states the same.

## 2026-10-19

- Adopted the Proof Protocol License 1.0 (LICENSE.md). Specifications: Apache-2.0. Software: proprietary.
- Added ETHICS.md (Proof Economy Code of Ethics).
- All prior versions of the specifications are relicensed under Apache-2.0 (see NOTICE.md).

## 0.1.3 (2026-10-13)
- 13.6: extensions adopted by a specification revision published for public review, not by the maintainer; Lineage Node sentence made informative
- 13.7: reserved items no longer reserved to the maintainer

## 0.1.2 (2026-10-13)
- 4.2.3: Proof Witness MUST be independent of the Lab and its affiliates; Lab-operated witness no longer conforms
- 4.5 Maintainer and Licensor Independence: maintainer, patent-holder, and affiliate relationships disclosed in `disclosed_interests`; such Engagements use an unrelated Proof Witness; no operator named, preferred, or required
- Abstract no longer names an operator
- Section 14: maintainer responsible for editorial text only; conformance determined from the records
- CONTRIBUTING.md, docs/conformance.md, and docs/faq.md updated to match
- Proof, not evidence: wherever the text meant what the protocol produces, relies on, accepts, or prices, "evidence" is now "proof". Evidence remains the word for inputs inside a proof record (liveness, cause, differential, verification evidence). Evidence is not proof; proof contains evidence.

## 0.1.1 (2026-10-11)
- Role terms: Provider replaces Vendor everywhere (the separate Vendor definition is removed); Implementor replaces Buyer; funding tiers Provider-Funded and Implementor-Funded (`provider_funded`, `implementor_funded`); Engagement Manifest field `implementor`. Environments: Production, Pre-Production, QA, Dev (`dev` replaces `development`), and/or Independent Test Lab (replaces Independent Lab)
- FUNDING.md funding disclosure ([FUNDED] Yes or No, [FUNDED BY] name and URL per funder); Proof Economy Code of Ethics applies
- 9.6 Record form and registration: Performance Record and Performance Series are Bundles under PP-SPEC-077 Section 21, with Record ID, envelope, receipt, Comparability Class as a field
- Holder is the Buyer (or the Independent Lab for Reference Environment Engagements), named in the Engagement Manifest, never the Vendor
- Engagement Manifest names the accepted Registries; records registered elsewhere are not part of the Engagement
- An Engagement is complete only at the Registered level; IP-M5 may not assemble from Executed or Conformant runs
- Disclosure: public by default; In-Situ may use holder_only with the summary, Record ID, receipt, Holder, class, and series state always public
- Revocation by Issuer, Witness, or Registry; Vendor remedy is Right of Reply
- Schema: record_id, bundle_root, holder, registries, registry_receipt, disclosure, conformance_level, signatures
- Builds on 077 v0.7.2 and 078 v0.2.1

## 0.1.0 (2026-10-10)
- Initial draft of the Coal Mine Protocol: the engagement layer over PP-SPEC-077, 078, and 013
- Two Engagement Modes, In-Situ and Independent Lab; Vendor-Run forbidden
- Environment Classes (production, pre-production, qa, development, lab-replica) and Parity Declarations; Reference Environments for Lab Mode
- Funding and Sponsor rules per PP-SPEC-025; Sponsor has no seam
- Engagement Manifest, hashed with `CMP-1:engagement`, anchored, with a publication commitment
- Mine Plan: per-profile Bounded runs, 078 where an agent is involved, 013 windows during flock load, Production Stream for in-situ production
- Claim Sheet: every vendor claim becomes a Gold canary or a Performance Specification
- Vendor duties, prohibitions, Right of Reply
- Performance Record, Performance Series, Comparability Class
- Integration Points IP-M1 to IP-M5
