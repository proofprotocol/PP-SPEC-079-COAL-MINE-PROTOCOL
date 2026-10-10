# License

This specification is licensed under the Proof Protocol Public License, Version 1.0, Part A (Specification Text). The full text follows.

```
PROOF PROTOCOL PUBLIC LICENSE
Version 1.0, 10 October 2026

Copyright (c) 2026 Nebulonium, Inc. (dba HACKERverse). Author: Craig Ellrod.

This license travels with both the specifications and the software of the
Proof Protocol family that carry it, in one document with two parts:

  Part A governs Specification Text: the normative and informative text,
         tables, schemas, diagrams, and documentation of a specification.
  Part B governs Software: source and object code, including the reference
         implementation of the specifications.

Sections 0, 2, 5, 6, 7, 8, 9, 10, and 11 apply to both parts. Sections 1A,
3A, and 4A apply to Specification Text. Sections 1B, 3B, and 4B apply to
Software. A repository states on its first page which part or parts apply.

What each part reaches. Copyright in a specification reaches copies and
derivatives of its text, and conditions on claiming conformance to it. It
does not, by itself, reach an independent implementation of the methods
the text describes. Copyright in software reaches copies, derivatives, and
works that incorporate it. Patent rights, which Licensor reserves (Section
2), reach implementations regardless of how they were written. This
license is drafted with that distinction in view and claims no more.

Versions of a specification published before this license was adopted
remain available under the license they were published under. This
license governs the version it accompanies and later versions.

A commercial license on different terms is available from Nebulonium, Inc.
If You cannot or will not accept the conditions below, do not use the
Specification Text or Software; obtain a commercial license instead.

0. DEFINITIONS

"Licensor" means Nebulonium, Inc. and Craig Ellrod.

"Specification Text" means the text, tables, schemas, diagrams, and
documentation of a Proof Protocol specification that carries this license,
in any form.

"Derivative Text" means any translation, revision, excerpt beyond fair
quotation, profile, annex, mapping, or restatement of Specification Text,
and any specification, standard, or working-group draft that incorporates
any of it.

"You" means any person or entity exercising rights under this license.

"Integration Point" means a seam named in PP-SPEC-077 Section 18 or
PP-SPEC-078 Section 16, including any successor numbering.

"Component" means any software, service, model, configuration, or
hardware that is distributed, deployed, or operated to interoperate with
the Software through an Integration Point, or that implements an
Integration Point against the Software.

"Covered Work" means, under Part B, the Software; any modification of it;
any work based on it; and any Component. Under Part A, "Covered Text"
means Specification Text and any Derivative Text.

"Improvement" means any modification, extension, derivative, adapter,
Component, test vector, Derivative Text, errata, or technique that You
create, use, or distribute in connection with the Software or the
Specification Text.

"Patent Claims" means any patent claim, anywhere in the world, owned or
controlled by a party now or later, that would be infringed by making,
using, selling, offering for sale, importing, or operating the Software,
the Specifications as implemented by the Software, or an Improvement.

"Conforming Run" means a run that satisfies every MUST of the applicable
Specification, including publication to a Registry and the attribution
required by Section 3.

"Convey" means to distribute, make available over a network, deploy for a
third party, or otherwise enable a third party to receive or use a Covered
Work, including as a service.

1A. CONDITIONAL GRANT: SPECIFICATION TEXT

Subject to every condition in Sections 3A, 4A, and 5 through 8, Licensor
grants You a worldwide, royalty-free, non-exclusive, non-transferable
copyright license to read, reproduce, Convey, and quote Specification
Text, to implement the methods it describes (as to copyright only; see
Section 2), and to create and Convey Derivative Text.

1B. CONDITIONAL GRANT: SOFTWARE

Subject to every condition in Sections 3B, 4B, and 5 through 8, Licensor
grants You a worldwide, royalty-free, non-exclusive, non-transferable
copyright license to use, reproduce, modify, and Convey the Software and
Covered Works.

1C. CONDITIONS, NOT COVENANTS

Each condition in Sections 3 through 8 is a condition precedent to and a
limitation on the scope of the grant it attaches to, not a covenant. Any
exercise of rights outside those conditions is unlicensed and infringes
Licensor's copyright, in addition to any other remedy.

2. PATENTS

2.1 No patent license. This license grants no license under any Patent
Claims owned or controlled by Licensor, express or implied, by estoppel,
exhaustion, or otherwise. All patent rights in the methods, systems, and
processes described in the Specifications and embodied in the Software
are reserved by Licensor.

2.2 Limited covenant. Licensor covenants not to assert its Patent Claims
against You solely for Your use of the unmodified Software, or of the
Software with modifications You have Conveyed under Section 4B, to perform
Conforming Runs that are attributed under Section 3 and published to a
Registry under the specifications. This covenant does not extend to any
Component, to any independent implementation, to any other product or
service, or to any use outside a Conforming Run, and it terminates
automatically under Section 8.3. Reading or implementing Specification
Text confers no patent license and no covenant.

3. ATTRIBUTION

3A. Specification Text. You must, in every copy, quotation beyond fair
use, and Derivative Text You Convey, and in every document, standard,
product, or claim that cites or claims conformance to a specification:

(a) retain and reproduce the specification's Ownership and Attribution
Notice and NOTICE.md;

(b) state, in a place a reader will see, the specification identifier and
"authored by Craig Ellrod, Nebulonium, Inc., Proof Protocol"; and

(c) not remove, obscure, or alter any such notice.

3B. Software. You must, in every Covered Work You Convey and in every
report, result, record, publication, user interface, and marketing
material that is derived from or describes a run performed with a Covered
Work:

(a) retain and reproduce the NOTICE.md file and all copyright, patent,
and attribution notices in the Software;

(b) state, in a place a reader will see, that the work implements or is
derived from the named specifications, authored by Craig Ellrod,
Nebulonium, Inc., Proof Protocol; and

(c) not remove, obscure, or alter any such notice.

4. SHARE-ALIKE

4A. Specification Text.

4A.1 Any Derivative Text You Convey must be Conveyed under this license and
no other, in full, with its differences from the Specification Text
clearly marked and a link to the original.

4A.2 Derivative Text must not be presented as the specification, as a
version of it, or as endorsed by Licensor, and must not carry the
specification's identifier (PP-SPEC-nnn) except in the statement
required by 3A(b).

4A.3 A standards body, consortium, or working group that incorporates
Specification Text into its own deliverable Conveys Derivative Text and is
bound by this Part. Licensor may grant such a body different terms by
separate written agreement; absent that agreement, this Part applies.

4B. Software.

4B.1 If You Convey a Covered Work, You must make its complete corresponding
source code available to every recipient, and to every user who interacts
with it over a network, under this license and no other, at no charge
beyond the cost of transfer.

4B.2 "Complete corresponding source code" includes the source of every
Component You Convey or operate with the Software and everything needed
to build and run it, excluding only general-purpose operating systems,
compilers, and runtimes that are not themselves Covered Works.

4B.3 You may not impose any further restriction on recipients' exercise of
the rights this license grants, including by contract, terms of service,
technical measure, or patent assertion.

Note on scope: Section 4B.2 reaches Components that interoperate through
an Integration Point. Whether a share-alike condition reaches across a
defined interface is unsettled in some jurisdictions. Licensor asserts it.
If a court of competent jurisdiction holds that it does not reach a
particular Component, Sections 3, 5, 6, and 8 continue to apply to that
Component in full. Part A does not claim to reach independent
implementations; Section 2 does.

5. GRANT-BACK

5.1 Improvements. You grant Licensor, and every other licensee of the
Software, a perpetual, irrevocable, worldwide, non-exclusive,
royalty-free, fully paid-up license, with the right to sublicense, to
make, use, sell, offer for sale, import, reproduce, modify, and Convey
Your Improvements, and to practice any method they embody.

5.2 Patents. You grant Licensor, and every other licensee of the Software,
a perpetual, irrevocable, worldwide, non-exclusive, royalty-free license
under Your Patent Claims to make, use, sell, offer for sale, import, and
operate the Software, the Specifications as implemented, and
Improvements.

5.3 These grants are non-exclusive. You keep title to Your Improvements
and Patent Claims. They take effect on the earliest of Your first use of
the Software, Your first Conveyance of a Covered Work, or Your first
Conveyance of Derivative Text, and they survive termination of this
license as to anything created or Conveyed before termination.

6. CONFORMANCE, MARKS, AND MISREPRESENTATION

6.1 You may claim conformance to a specification only per Integration
Point, in the form and under the conditions the Specification states, and
only if the claim is true. A claim of adjudicator conformance (IP-8,
IP-J8) requires output identical to the Software's on the published
conformance vectors.

6.2 "Prooflock", "Dead Canary Protocol", "No Bros Jail Mode Protocol",
"Jailed Canary Protocol", "Coal Mine Protocol", "Proof Protocol",
"ProofRegister", and "HACKERverse" are marks of Licensor or its licensors. This license grants
no right to use them except to make truthful statements of fact under
Section 3 and 6.1.

6.3 You may not represent a modified Software, or any Component, as the
reference implementation, as Licensor's work, or as endorsed by Licensor.

7. RECORDS AND VERIFICATION

For three years after each Conveyance, You must keep records sufficient to
show compliance with Sections 3 through 6, and on thirty days' written
notice You must make them available to Licensor or an independent auditor
bound by confidentiality, no more than once per calendar year unless a
prior audit found non-compliance.

8. ENFORCEMENT AND TERMINATION

8.1 Automatic termination. Your rights under Sections 1A and 1B terminate
automatically on any breach of Sections 3 through 7. If it is Your first
breach and You cure it within thirty days of becoming aware of it, Your
rights are reinstated as of the date of cure, unless Licensor has given
You notice of the breach before cure, in which case reinstatement requires
Licensor's written consent.

8.2 Infringement. Because the conditions of this license limit the scope
of the grant, any use outside them is copyright infringement. Licensor
may seek injunctive relief, actual or statutory damages, impoundment, and
any other remedy available at law or equity, without posting bond and
without proof of irreparable harm, which You acknowledge would result.

8.3 Patent retaliation. If You, or any entity You control, assert a Patent
Claim against Licensor or against any licensee alleging that the Software,
the Specifications as implemented, or an Improvement infringes, then on
the date of that assertion every license and covenant granted to You under
this license, including Section 2.2, terminates, and the grant-backs in
Section 5 remain in force.

8.4 Fees. In any action to enforce this license, the prevailing party is
entitled to recover its reasonable attorneys' fees and costs.

8.5 Survival. Sections 2.1, 3, 5, 6, 7, 8, 9, 10, and 11 survive
termination. Termination does not affect licenses Licensor granted to
third parties for Covered Works or Derivative Text You Conveyed before
termination; those recipients keep their rights if they remain in
compliance.

9. DISCLAIMER OF WARRANTY

THE SPECIFICATION TEXT AND THE SOFTWARE ARE PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR
PURPOSE, TITLE, AND NON-INFRINGEMENT. YOU BEAR THE ENTIRE RISK OF ITS
QUALITY AND PERFORMANCE. A RESULT PRODUCED WITH THE SOFTWARE IS PROOF ONLY
TO THE EXTENT THE APPLICABLE SPECIFICATION WAS FOLLOWED; LICENSOR MAKES NO
REPRESENTATION ABOUT ANY PARTICULAR RUN.

10. LIMITATION OF LIABILITY

TO THE MAXIMUM EXTENT PERMITTED BY LAW, LICENSOR IS NOT LIABLE FOR ANY
INDIRECT, INCIDENTAL, SPECIAL, CONSEQUENTIAL, OR PUNITIVE DAMAGES, OR FOR
LOST PROFITS, DATA, OR GOODWILL, ARISING FROM THE SOFTWARE OR THIS
LICENSE, EVEN IF ADVISED OF THE POSSIBILITY. LICENSOR'S TOTAL LIABILITY
UNDER THIS LICENSE SHALL NOT EXCEED ONE HUNDRED UNITED STATES DOLLARS.

11. GENERAL

11.1 Governing law and venue. This license is governed by the laws of the
State of Delaware, without regard to conflict-of-laws rules. Exclusive
venue for any dispute lies in the state or federal courts located in
Denver, Colorado, and You consent to their personal jurisdiction. The
United Nations Convention on Contracts for the International Sale of Goods
does not apply.

11.2 Severability. If any provision is held unenforceable, it is to be
enforced to the maximum extent permitted and the remainder stays in force.
Section 4.2's note states the parties' intent for one such case.

11.3 Entire agreement; no waiver. This license is the entire agreement
about the Specification Text and the Software between You and Licensor unless You hold a separate
written commercial license. Failure to enforce is not a waiver.

11.4 Versions. Licensor may publish revised versions of this license. You
may use the Specification Text or Software under the version You received
it under or any later version Licensor publishes.

11.5 Acceptance. You accept this license by using, modifying, Conveying,
or quoting beyond fair use the Specification Text or the Software, by
Conveying Derivative Text or a Covered Work, or by claiming conformance.
If You do not accept it, You have no rights in either.

END OF TERMS
```
