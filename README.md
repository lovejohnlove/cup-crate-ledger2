# cup-crate-ledger2

**Status:** DRAFT / PROPOSED, not SEALED  
**Owner:** human (lovejohnlove)  
**Public mirror of the canonical ledger materials**  
**Source of this content:** Migrated from private `cup-crate-ledger` on 2026-11-11  

This is the public working home for Crate Protocol v0.1 ledger and framework materials.  
It is not Omni-080 (stories). It is not Toolbox code.

## Directory structure

- `current/` — only SEALED, bench-paired byte-states. Currently empty: nothing is SEALED.
- `historical/` — every fork, named by byte-state / revision, never overwritten. Pass-around, Amendments 1–3, combined object, and Pruning Checklist live here as PROPOSED / PRESERVED_REPORTED.
- `open/` — unresolved questions, draft fragments, undecided semantics, valve cut naming note, Dropbox receipt missing note, open rulings.
- `promise/` — manifests and claims about unexecuted runs. Status PROMISE.
- `inventory/` — machine-readable inventory (JSON), parallel to ledger. PROPOSED.
- `ledger.md` — human-owned ledger entries. Proposed by session, accepted/rejected by owner. Not sealed by AI.

## Critical limitations (carried forward)

- No native Google Docs bytes were retrieved. Only reported Drive links and text exports / pastes exist.
- All SHA-256 values for the source documents remain PENDING or are hashes of Markdown exports only. Export hashes are not seals of the Drive source.
- No Dropbox access was available in the originating session. No assumption of full Meta access beyond the handoff text.
- Nothing has been sealed. No promotion of draft to fact.
- Valve cuts named as instructed: bench-initial-2026-11-10 (PLAIN 3321, HISTORICAL) superseded by bench-release-2026-11-10 (located 8201, CURRENT for this cut). PLAIN preserved as fork.
- MD5 remains debt marker, never seal.

Agreement is not verification. Verification is not authorization to seal.

Python / execution files will be handled by collaborating sessions; the human does not need to edit them directly in the app.
