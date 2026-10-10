# AI Disclosure

*How this specification was made, and by whom.*

This file states what in PP-SPEC-079 came from a human and what came from an AI assistant. It is published so that readers, implementers, standards bodies, and examiners can judge the provenance of the work for themselves.

## Summary

The method is Craig Ellrod's. The words were drafted with Claude.

The Coal Mine Protocol, PP-SPEC-079, was conceived, designed, and decided by Craig Ellrod, a human. Claude, an AI assistant made by Anthropic, was used as a drafting, structuring, and editing tool under his direction. No part of the protocol's concept or purpose originated with the AI. Structural proposals listed below were drafted by Claude and are pending Craig Ellrod's acceptance as of this 0.1.0 draft; every section is subject to his review before any release is tagged.

## Ratio

One number would misstate it, because the work splits along more than one line.

| Dimension | Human (Craig Ellrod) | Machine (Claude) |
|---|---|---|
| Conception, method, every normative decision | 100% | 0% |
| Design details and naming | 70% | 30% (section structure, Environment Classes, Parity Declaration, Claim Sheet, Comparability Class, the name Coal Mine, proposed by Claude; pending acceptance) |
| Words on the page, as typed | 5% | 95% |
| Review, direction, acceptance, decision to publish | 100% | 0% |

In short: substance 85% human, 15% machine pending review; expression 5% human, 95% machine.

## Human: Craig Ellrod

The following originated with Craig Ellrod and reflect his judgment, experience, and decisions:

- The diagnosis: that the two legacy models, the vendor-funded independent lab report and the vendor-run proof of concept, are respectively unreal and self-attested, and that neither is proof. This comes from his own career on both sides of those models, including co-authoring the 2007 WAF Test Methodology and the DUT and SUT competitive test method in *Technical Marketing* (2008).
- The shift: that the vendor product becomes part of the SUT, DUT, CUT, and AUT, and that its performance is measured by the buyer's infrastructure rather than by the vendor or by a lab the vendor pays.
- The two engagement modes: in the customer's environment (production, pre-production, QA, development), where the product produces its own efficacy telemetry while it operates; and an independent lab such as HACKERverse performing the same motion with no connection to the customer's live environment.
- That a vendor-operated test is not proof of performance.
- The ownership position: sole authorship, CC BY 4.0 for the text, patent rights reserved, mandatory attribution.
- All review, acceptance, rejection, and revision direction.

## AI: Claude (Anthropic)

Claude was used on 2026-10-10 through claude.ai (model Claude Fable 5.1). Its contributions were:

- Drafting the specification text from Craig Ellrod's description of the shift and the two modes, and from the published text of PP-SPEC-077, 078, 013, 006, 025, and 004.
- Proposing the structure: Environment Classes, Parity Declarations, Reference Environments, the Engagement Manifest, the Claim Sheet mapping to Gold canaries, the Right of Reply, the Performance Record and Series, Comparability Classes, and Integration Points IP-M1 to IP-M5. These are drafting proposals pending his review.
- Proposing the name "The Coal Mine Protocol" from his phrase "run the Mine Plan."
- Drafting the README, glossary, FAQ, conformance checklist, model procurement language, schemas, citation metadata, and this disclosure.

Claude did not originate the shift, the two modes, or the prohibition on vendor-run testing, and made no normative decision that Craig Ellrod has not reviewed.

## Working method

The work was directed and iterative. Craig Ellrod stated what the protocol must do and why; Claude drafted; Craig Ellrod read, corrected, redirected, renamed, and in several cases rejected drafts outright and restated the requirement. The same-day sequence of versions in the Revision History reflects this process. Where the AI drafted text that Craig Ellrod did not change, that is because he read it and agreed with it, not because it went unread.

## What this means for authorship

Craig Ellrod claims authorship of this specification on the basis of its conception, design, every normative decision in it, and the selection, direction, review, and arrangement of all drafted text. AI output was used as a tool in the same way a human technical writer or editor would be used, with the difference that the tool is disclosed here.

Nothing in this file changes the terms in NOTICE.md or LICENSE.md.

## Maintenance

This file will be updated with each release. If a future version contains material drafted without AI assistance, or AI contributions of a different kind, this file will say so.

Craig Ellrod
Nebulonium, Inc., Proof Protocol
2026-10-10
