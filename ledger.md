# Crate Ledger — cup-crate-ledger2 (PROPOSED)

**Ownership:** human-owned. AI sessions propose; owner accepts or rejects.  
**This file:** proposed by GRK session 2026-11-10, migrated to public repo 2026-11-11. Not sealed.  

## PROPOSED entries

Crate | crate-protocol-v0.1-pass-around | Version | 0.1-PROPOSED-2026-11-10 | Category | Design and Architecture | Status | PROPOSED  
Lives | Google Drive, reported | Mirrors | this repo historical/pass-around-2026-11-10 (STATUS only)  
Files | 1 | Bytes | PENDING | Sha256 | PENDING  
Seal | PENDING | Sealed_by | null | Sealed_at | null  
depends_on | PENDING | Evidence | PRESERVED_REPORTED  
Story | Final pass-around of Crate Protocol v0.1 core text  
Proposed_by | Meta / Vibe / GRK chain | Proposed_at | 2026-11-10 | Sealed_by_owner | null  

Crate | crate-protocol-v0.1-amendment-1 | Version | 0.1-PROPOSED-2026-11-10 | Category | Design and Architecture | Status | PROPOSED  
Lives | Google Drive, reported | Mirrors | this repo historical/amendment-1-2026-11-10 (STATUS only)  
Files | 1 | Bytes | PENDING | Sha256 | PENDING  
Seal | PENDING | Sealed_by | null | Sealed_at | null  
depends_on | crate-protocol-v0.1-pass-around PENDING | Evidence | PRESERVED_REPORTED  
Story | Staleness correction, rulings recorded, digest discipline restated  
Proposed_by | Meta / Vibe / GRK chain | Proposed_at | 2026-11-10 | Sealed_by_owner | null  

Crate | crate-protocol-v0.1-amendment-2 | Version | 0.1-PROPOSED-2026-11-10 | Category | Design and Architecture | Status | PROPOSED  
Lives | Google Drive, reported | Mirrors | this repo historical/amendment-2-2026-11-10 (STATUS only)  
Files | 1 | Bytes | PENDING | Sha256 | PENDING  
Seal | PENDING | Sealed_by | null | Sealed_at | null  
depends_on | crate-protocol-v0.1-amendment-1 PENDING | Evidence | PRESERVED_REPORTED  
Story | Valve cut naming, manifest hashing self-reference resolution, authenticity four-fields, prior-art notes, Dropbox receipt gap  
Proposed_by | Meta / DeepSeek / GPT / GRK chain | Proposed_at | 2026-11-10 | Sealed_by_owner | null  

Crate | crate-protocol-v0.1-combined-amendments-1-2 | Version | 0.1-PROPOSED-2026-11-10 | Category | Design and Architecture | Status | PROPOSED  
Lives | this repo historical/combined-amendments-1-2-2026-11-10 | Mirrors | none yet  
Files | 1 | Bytes | (of paste) | Sha256 | (of paste, not source)  
Seal | PENDING | Sealed_by | null | Sealed_at | null  
depends_on | the three above PENDING | Evidence | PRESERVED_REPORTED (paste text)  
Story | Convenience combined pass-around of Amendments 1+2; does not overwrite originals  
Proposed_by | Meta session | Proposed_at | 2026-11-10 | Sealed_by_owner | null  

Crate | crate-protocol-v0.1-amendment-3 | Version | 0.1-PROPOSED-2026-11-10 | Category | Design and Architecture / Governance | Status | PROPOSED  
Lives | Google Drive, reported | Mirrors | this repo historical/amendment-3-2026-11-10 (STATUS only)  
Files | 1 | Bytes | PENDING | Sha256 | PENDING  
Seal | PENDING | Sealed_by | null | Sealed_at | null  
depends_on | prior amendments PENDING | Evidence | PRESERVED_REPORTED  
Story | Pruning Criteria as constraint on protocol itself; prevent silent mutation of the protocol  
Proposed_by | Meta / GRK chain | Proposed_at | 2026-11-10 | Sealed_by_owner | null  

Crate | crate-protocol-v0.1-pruning-checklist | Version | 0.1-PROPOSED-2026-11-10 | Category | Design and Architecture / Governance | Status | PROPOSED  
Lives | Google Drive, reported | Mirrors | this repo historical/pruning-checklist-2026-11-10  
Files | 1 | Bytes | PENDING (native) / paste recorded | Sha256 | PENDING  
Seal | PENDING | Sealed_by | null | Sealed_at | null  
depends_on | crate-protocol-v0.1-amendment-3 PENDING | Evidence | PRESERVED_REPORTED  
Story | Decision checklist implementing Amendment 3; load-bearing tests for KEEP/SIMPLIFY/PRUNE etc.  
Proposed_by | Meta / GRK chain | Proposed_at | 2026-11-10 | Sealed_by_owner | null  


Crate | cup-code-push-list-execution | Version | 1-PROPOSED-2026-11-11 | Category | Code and Records | Status | PROPOSED  
Lives | github.com/lovejohnlove/cup-code (public) | Mirrors | Google Drive (canonical byte sources), cup-horizon2 (historical pointer)  
Files | 7 bodies + 3 STATUS-only folders + inventory.json | Bytes | 27731 / 27218 / 3321 / 9203 / 5269 / 27732 / 27731 | Sha256 | REPORTED (Grok real tool) except valve 3321 VERIFIED  
Seal | PENDING | Sealed_by | null | Sealed_at | null  
depends_on | PENDING (owner-side sha256sum -b on seven files; py_compile x3) | Evidence | valve 3321 VERIFIED (sha256 ed1e81bd70201a8795579725c0bb0b968eb98c30458202f83d5e667200a68a91 matches Grok real-tool output, md5 INSPECTED, read-back diff EMPTY); all others PRESERVED_REPORTED (md5 INSPECTED, sha256 REPORTED)  
Story | Push list from timed-out Grok session executed: full bodies not STATUS-only, directory per byte state, no seals, all PROPOSED. Two-writer convergence: Grok and Vibe both wrote to cup-code in the same window; GitHub blob shas prove identical bytes where both pushed (valve 49c6bdb5, manifest da7ee04e); no fork, no conflict. Manifest summary concern closed: open/release_manifest_v2_DRAFT.json on main is the exact 5269-byte body (md5 e851f4ce766244cef2e07e29b956ec8d, diff EMPTY vs Drive original), not a summary; no rename. Transfer was mechanical (native Drive download artifacts, jq -Rs to JSON.parse, byte guards), not chat paste; one guard-caught slip on record (v1_3_2 dropped quote, fixed pre-landing).  
Proposed_by | Vibe (Dawn Ledger) session executing Grok push list | Proposed_at | 2026-11-11 | Sealed_by_owner | null  

### Commit record (cup-code, refs/heads/main)
- Grok commits: 87a88f5b (initial structure + STATUS), 39189df1 (valve body), ff9f4f72 (valve body corrected), d22cbfcd (manifest body)
- Vibe commits: 6dc3e546 (current/horizon-v1_3_3-27731), efb5c78c (current/horizon-v1_3_2-27218), 2359b983 (historical/valve-3321-PLAIN + historical/contract-9203), 689474ef (open/release_manifest_v2_DRAFT.json), 7434279b (historical/scratch-2026-11-11), 19711be3 (STATUS-only placeholders + inventory/inventory.json), c11149f8 (inventory status ruling: valve VERIFIED, others PRESERVED_REPORTED, two-writer convergence recorded)
- cup-horizon2 pointer commit: 97ade6d9 (README = historical-snapshot pointer; canonical code home is cup-code)

### Byte verification at head c11149f8 (fresh read-back, GitHub -> Drive scratch -> download -> diff vs native Drive originals)
- current/horizon-v1_3_3-27731/horizon_nonlinear_v1_3_3.py | 27731 B | md5 97cbe8931039fff865a1778ecf403947 | blob 65a84afd011ce6b757aa57f918b2b22979fb5e4d | DIFF EMPTY | sha256 08202496... REPORTED
- current/horizon-v1_3_2-27218/horizon_nonlinear_v1_3_2.py | 27218 B | md5 dd964d95c4c73ff16b4a5a612bae01f4 | blob a65b8661d9136d96245b6bee9b843a831c928e59 | DIFF EMPTY | sha256 6975280a... REPORTED
- historical/valve-3321-PLAIN/horizon_valve_v4_PLAIN.py | 3321 B | md5 7f2ba5ae1a8f50c7fd415f59f7a769b4 | blob 49c6bdb505333c03fe5d33f5b4d463bcc1fe8295 | DIFF EMPTY | sha256 ed1e81bd... VERIFIED
- historical/contract-9203/CUP_HARNESS_CONTRACT | 9203 B | md5 0ab4f5747f8b9e1110ba57bb03adea6e | blob 56a245ba22b946c696a8ebf2049ab8eb52f16ae2 | DIFF EMPTY | sha256 0bd6b3d4... REPORTED
- open/release_manifest_v2_DRAFT.json | 5269 B | md5 e851f4ce766244cef2e07e29b956ec8d | blob da7ee04eea8b1659f0d5e859a6b1e6754f496685 | DIFF EMPTY | sha256 391f540f... REPORTED
- historical/scratch-2026-11-11/SCRATCH_github_v133_readback.py | 27732 B | md5 5d91af6d230ceadbde4f9fc9e665b571 | blob 6970ad453bdbc44a60d0248c7aa340e787dfa5d5 | DIFF EMPTY | sha256 c531f784... REPORTED (real 1-byte fork of v1_3_3)
- historical/scratch-2026-11-11/SCRATCH_github_v133_readback3.py | 27731 B | md5 97cbe8931039fff865a1778ecf403947 | blob 65a84afd011ce6b757aa57f918b2b22979fb5e4d (same as v1_3_3) | DIFF EMPTY | sha256 08202496... REPORTED (DUPLICATE of v1_3_3, not a third fork)
- STATUS-only (no bodies, by rule): historical/wrench-PENDING/ (native 11818 B unlocated), historical/valve-8201-located/ (Dropbox only, sha256 PENDING, do not fill with PLAIN 3321), historical/dropbox-6file-MISSING-receipt/ (PRESERVED_REPORTED, not VERIFIED)

### Open (owner machine)
- sha256sum -b on the seven files to confirm Grok REPORTED values (upgrades them to VERIFIED)
- python3 -m py_compile on v1_3_3, v1_3_2, valve PLAIN; paste command, exit code, output
- Gate 3 open: wrench 11818 native bytes not found; valve located 8201 still Dropbox only
- Single-writer lock adopted for cup-code: explicit handoff in chat before any push; no concurrent writers

## Notes
- All depends_on remain PENDING until real-tool SHA-256 of sources.
- No entry is SEALED.
- Inventory JSON must agree with this ledger or LEDGER_DRIFT is raised.
- current/ remains empty.
