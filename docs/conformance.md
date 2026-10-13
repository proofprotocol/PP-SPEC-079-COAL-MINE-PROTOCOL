# Conformance Checklist

*Informative summary of the MUST requirements in [SPEC.md](../SPEC.md). An engagement that fails any item is non-conforming. Every underlying run must also conform to its own specification.*

## Mode and environment (SPEC 4, 5)

- [ ] Engagement Mode declared: In-Situ or Independent Test Lab; no Provider-Run output labeled Proof of Performance
- [ ] Environment Class declared before first commitment; a class change is a new engagement
- [ ] Parity Declaration published and hashed for every class except production
- [ ] No destructive canaries or 078 runs in production
- [ ] Lab replica has no network path to Implementor production
- [ ] Proof Witness is not the Provider (Provider or internal team)
- [ ] In Independent Test Lab Mode, Proof Witness is not the Lab or its affiliates
- [ ] Maintainer, patent-holder, and affiliate relationships of the Lab, Issuer, or any Integration Point operator disclosed; Proof Witness in such an Engagement has none of them

## Funding (SPEC 6)

- [ ] Sponsor and PP-SPEC-025 funding tier on the manifest and the record
- [ ] Sponsor sees no canaries before reveal, occupies no forbidden seam, cannot delay or veto publication
- [ ] All fees, in-kind contributions, and commercial relationships in disclosed_interests

## Mine Plan (SPEC 7)

- [ ] Engagement Manifest published to the Registry before first commitment, hashed with `CMP-1:engagement`, anchored
- [ ] Manifest contains mode, class, parity hash or Reference Environment, DUT and fingerprint capturer, Claim Sheet hash, composition version, Interface Manifest(s), thresholds, publication commitment
- [ ] At least one 077 Bounded run per claimed technology profile with White, Gray, Red, Black present and Gold for every applicable claim
- [ ] At least one 078 run with escape suite where the product is, protects, or constrains an agent
- [ ] At least one 013 measurement window overlapping Proof Swarm release
- [ ] Production Stream commitment for in-situ production or pre-production
- [ ] Invalid runs published as invalid; incomplete engagements published as incomplete
- [ ] Molts declared in advance; undeclared molts recorded as findings

## Provider (SPEC 8)

- [ ] Claim Sheet submitted before manifest commitment, or its absence recorded
- [ ] Every efficacy or containment claim mapped to a Gold canary; every operational claim to a Performance Specification
- [ ] Provider supplies the control exactly as deployed and cooperates with independent fingerprinting
- [ ] Provider occupies no Integration Point and receives nothing before reveal
- [ ] Provider telemetry attached only as annotation, never as proof of outcome
- [ ] Right of Reply appended separately, record unaltered

## Record (SPEC 9)

- [ ] Performance Record contains every item in 9.1 and is published to the Registry
- [ ] Summary paragraph states what the record proves and what parity prevents it from proving
- [ ] Any report cites the record URI, reproduces the summary verbatim, states no number the record lacks
- [ ] Series shows class and comparability per entry; live or stale state shown wherever cited
- [ ] Comparisons stay within one Comparability Class and state it

## Self-Provided and provenance (SPEC 4.4, 9.5.4)

- [ ] Control Provenance and Provider named in the Engagement Manifest; upstream project named for open source controls
- [ ] Self-Provided Engagements: Issuer, Witness, Fingerprint Capture, and Adjudicator staffed outside the Provider team's reporting line and change responsibility, boundary declared, `self_provided: true` on the record
- [ ] Provenance and self_provided shown in any side-by-side comparison; never used to adjust a rate

## Authorship Disclosure (SPEC 9.6.9, 077 21.15)

- [ ] Disclosure reference for every component, the Mine Plan composition, and any Reference Environment in the Engagement Manifest
- [ ] Narrative reports state AI involvement in their first paragraph, next to the Registry URI
