CRATE PROTOCOL
Pruning Decision Checklist v0.1
Status: PROPOSED, not sealed, not public, no bytes promoted to fact
Recorded as: Implementation of Amendment 3, Pruning Criteria, as constraint on protocol itself, not merely another amendment
Purpose: Determine whether a rule should be kept, simplified, moved, parked, or pruned.

Step 1: Load-Bearing Test
If this rule disappeared tomorrow, would any of the following become easier?
Silent mutation, Provenance loss, Seal ambiguity, Verification ambiguity, Attribution ambiguity, Authorization ambiguity, Fork collapse, Historical overwrite
If YES to any item: KEEP unless a stronger replacement exists.

Step 2: Reality Test
Does the rule affect actual behavior?
Tool behavior, Human decision-making, Seal procedure, Governance ruling, Verification workflow
If NO to all: Candidate for PRUNE or MOVE TO NOTES.

Step 3: Duplication Test
Is the same fact recorded elsewhere?
Same fact appears twice, Same fact appears in three places, Copy maintained manually, Drift between copies already observed
If YES: Replace with single source, pointer, reference.

Step 4: Trigger Test
If this is a placeholder:
Has trigger, Has owner, Has decision path, Has review date
If NO to any: Move to RESERVED, PARKED, Remove until needed.

Step 5: Cost Test
Does maintaining this rule require:
Repeated manual updates, Multiple receipts, Duplicate entries, Human bookkeeping
If cost exceeds benefit: Candidate for simplification.

Step 6: Verification Test
Can anybody tell whether the rule has been satisfied?
Observable, Checkable, Receiptable, Auditable
If not: Candidate for rewrite.

Step 7: Fair Witness Test
Can this rule be stated without interpreting reality?
Good: File present but absent from manifest blocks seal.
Bad: File probably should have been listed.
If rule depends on interpretation rather than observation: Rewrite before keeping.

Step 8: Governance Test
If removed:
New crate created, Governance ruling recorded, Version bump recorded, Historical text preserved
If not, pruning is not allowed.

Decision Matrix:
Load-bearing: KEEP
Useful but non-essential: SIMPLIFY
Documentation only: MOVE TO NOTES
No trigger, no owner: PARK
Duplicate: POINTER
No behavioral effect: PRUNE
Historical value only: HISTORICAL

Final Reminder:
PRESERVED_REPORTED is not VERIFIED.
VERIFIED is not SEALED.
SEALED is not reality.
The map is not the territory.
The postcard is not the place.
Pruning Goal: Remove bureaucracy, not provenance. Preserve protection. Remove decoration.
