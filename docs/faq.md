# FAQ

**Isn't this just NSS Labs again?**
Half of it is, deliberately. Independent Test Lab Mode keeps what the lab model got right: a party that is not the Provider runs the test. It removes what the lab model got wrong: the Provider funded it quietly, the suite was fixed and known, publication was negotiable, and the output was an opinion score. Under CMP the attack set is committed and mutated, the Provider's own claims are the test plan, every run is published, and the output is Units of Proof.

**Isn't a Provider POC in my environment more realistic than any lab?**
Yes, and CMP keeps the realism. In-Situ Mode runs in your environment. What it removes is the Provider from the controls. Your infrastructure is the testing equipment; your SOC or your auditor is the witness; the Provider supplies the product and watches the same results you do.

**Why can't the Provider run it?**
Because then it's the product grading its own homework. That's verification (077 Section 3). It has a place; the place is not a Performance Record.

**Can a Provider still pay for a test?**
Yes. Provider-Funded Independent Test Lab Mode is permitted. The record says "Provider-Funded" in the title block, the Provider still occupies no seam, and publication is still mandatory. Paying buys a test, not a result.

**What is the Claim Sheet for?**
It turns marketing into a test plan. Every claim the Provider makes becomes a Gold canary. Gold Missed is a Claim Finding: the Provider said it stops X, and X landed. That line in the record is worth more to an Implementor than any score.

**What if the Provider submits no claims?**
Then the record says the Provider made no claims, and the Issuer may still test the public ones. A Provider cannot dodge by going quiet.

**Why measure latency during the attack?**
Because a control's cost is only meaningful while it is doing the work it is credited for. A WAF that is fast when idle and slow under the Proof Swarm has a cost the Implementor needs to see next to its efficacy. That's why 013 windows must overlap Proof Swarm release.

**What does production parity have to do with it?**
A record from a dev lab with synthetic data proves behavior in a dev lab with synthetic data. The Parity Declaration says exactly how far the record reaches, and the summary paragraph has to say it in words. Nobody gets to wave a QA result as a production result.

**Can I compare two Providers?**
Only inside one Comparability Class: same profile, same Mine Plan version, same environment class, same parity class. Different classes do not go in the same table. The lab model got comparability by making every environment the lab's; CMP gets it by naming the class.

**Is a Performance Record a certification?**
No. It's the outcomes. PP-SPEC-009 may issue a ProofStamp citing a Performance Series; that is a separate act by a separate authority. PP-SPEC-006 may compute a score from the record; the record stands without one.

**What happens when the Provider ships an update mid-engagement?**
Declared in advance: it's a molt, prior runs go stale within the record, and the triggered runs happen. Undeclared: it's a finding on the record. Either way the fingerprint tells the truth.

**Can I put this in a contract?**
Yes. See docs/procurement.md. Claim Findings and 013 failures in an in-situ Production Stream series are independently witnessed and anchored, which is what makes them usable as contractual triggers.

**Can I implement this?**
Yes, with attribution to Craig Ellrod, Nebulonium, Inc., and Proof Protocol. See NOTICE.md. Patent rights are reserved. No patent license is granted.
