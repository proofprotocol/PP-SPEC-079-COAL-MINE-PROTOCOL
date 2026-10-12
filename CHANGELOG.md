# Changelog

## Unreleased
- Section 14, Ethics and Fair Dealing: governed by the PESA Code of Ethics, Fair Dealing and Non-Harmful Competitive Practices, adding to the LF Code of Conduct and LF Antitrust Policy (LFDT has no ethics or fair dealing clause); version pinning; conformance claims and PESA marks valid only while compliant, whatever license the text was received under; six minimum duties; PESA enforcement with withdrawal and Revocation records; machine form. Interpretation renumbered to 15.
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
