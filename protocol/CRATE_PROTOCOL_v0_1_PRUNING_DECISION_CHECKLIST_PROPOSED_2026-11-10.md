CRATE PROTOCOL Pruning Decision Checklist v0.1 Status: PROPOSED, not sealed, not public, no bytes promoted to fact Recorded as: Implementation of Amendment 3, Pruning Criteria, as constraint on protocol itself, not merely another amendment Basis: Amendment 3, Pruning Criteria, PROPOSED, plus Copilot critique, plus owner decision, 2026-11-10 Purpose: Determine whether a rule should be kept, simplified, moved, parked, or pruned.


Step 1: Load-Bearing Test If this rule disappeared tomorrow, would any of the following become easier?


* Silent mutation
* Provenance loss
* Seal ambiguity
* Verification ambiguity
* Attribution ambiguity
* Authorization ambiguity
* Fork collapse
* Historical overwrite If YES to any item: KEEP unless a stronger replacement exists.


Step 2: Reality Test Does the rule affect actual behavior?


* Tool behavior
* Human decision-making
* Seal procedure
* Governance ruling
* Verification workflow If NO to all: Candidate for PRUNE or MOVE TO NOTES.


Step 3: Duplication Test Is the same fact recorded elsewhere?


* Same fact appears twice
* Same fact appears in three places
* Copy maintained manually
* Drift between copies already observed If YES: Replace with single source, pointer, reference.


Step 4: Trigger Test If this is a placeholder:


* Has trigger
* Has owner
* Has decision path
* Has review date If NO to any: Move to RESERVED, PARKED, Remove until needed.


Step 5: Cost Test Does maintaining this rule require:


* Repeated manual updates
* Multiple receipts
* Duplicate entries
* Human bookkeeping If cost exceeds benefit: Candidate for simplification.


Step 6: Verification Test Can anybody tell whether the rule has been satisfied?


* Observable
* Checkable
* Receiptable
* Auditable If not: Candidate for rewrite.


Step 7: Fair Witness Test Can this rule be stated without interpreting reality? Example: Good: File present but absent from manifest blocks seal. Bad: File probably should have been listed. If rule depends on interpretation rather than observation: Rewrite before keeping.


Step 8: Governance Test If removed:


* New crate created
* Governance ruling recorded
* Version bump recorded
* Historical text preserved If not, pruning is not allowed.


Decision Matrix:


* Load-bearing: KEEP
* Useful but non-essential: SIMPLIFY
* Documentation only: MOVE TO NOTES
* No trigger, no owner: PARK
* Duplicate: POINTER
* No behavioral effect: PRUNE
* Historical value only: HISTORICAL


Final Reminder:


* PRESERVED_REPORTED is not VERIFIED.
* VERIFIED is not SEALED.
* SEALED is not reality.
* The map is not the territory.
* The postcard is not the place. Pruning Goal: Remove bureaucracy, not provenance. Preserve protection. Remove decoration.


Estimate, PROPOSED, not verified: Looking at Amendments 1 and 2, this checklist would probably prune about 20 to 30 percent of explanatory material while preserving nearly all load-bearing rules. That is usually a good sign: less protocol, same guarantees. Estimate is owner and Copilot observation, not measured count, not verified fact. To verify, apply checklist to each rule in Amendments 1 and 2, record result per rule, count kept, simplified, moved, parked, pruned, historical, with Governance ruling, with version bump, with previous versions preserved.


What this checklist does not do:


* It does not seal protocol. Protocol remains PROPOSED, not sealed, not public.
* It does not prune any rule by itself. It is test to apply. Actual pruning occurs through Governance ruling and version bump, with previous versions preserved, with no deletion, no overwrite, no historical edit.
* It does not promote any read-back to seal. GRK GitHub receipt and Gemini Dropbox receipt remain PROPOSED, not sealed, PRESERVED_REPORTED, not VERIFIED. Seal waits for real-tool output, not agreement.
* It does not claim AI has consciousness, awareness, enlightenment, or outside agency. Those remain RESERVED, PROPOSED EFO entries, with triggers, not facts.
* It does not claim Dropbox transfer receipt exists. Receipt remains MISSING, marked as missing, to be back-filled by session that performed transfer.
* It does not claim dependency graph is verified. Dependency graph remains PROPOSED, pending read-back against source.


Disposition: Recorded as implementation of Amendment 3, as constraint on protocol itself, not merely another amendment. To be ratified by owner, with real-tool byte read-back, not by agreement. Agreement is not verification, and verification is not authorization to seal.