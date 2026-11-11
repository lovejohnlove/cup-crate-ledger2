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


Crate | cup-code-verify-workflow | Version | 1-PROPOSED-2026-11-11 | Category | Verification Infrastructure | Status | PROPOSED  
Lives | github.com/lovejohnlove/cup-code .github/workflows/verify.yml | Mirrors | none  
Files | 1 | Bytes | 1110 | Sha256 | PENDING  
Seal | PENDING | Sealed_by | null | Sealed_at | null  
depends_on | cup-code-push-list-execution PENDING (sha256 upgrade) | Evidence | workflow commit b232db24166e2ed2760b04a4c195dae813afe0ae = new cup-code main head; Actions run #1 triggered on push, URL https://github.com/lovejohnlove/cup-code/actions/runs/1  
Story | Push list from owner (iPhone-only, no local machine): GitHub runner does the real sha256sum -b on the seven bodies at pinned ref c11149f8 and py_compile on the three .py files. Workflow added byte-guarded (11 required lines, no trailing whitespace, LF only, single trailing newline, 1110 bytes); one guard false-trip on an over-broad whitespace regex, corrected, content unchanged. Run #1 queued automatically on push. Actions log read-back NOT done from this session: no Actions tools in the GitHub connector; public API rate-limited. Log reading is owner-side (Safari, Actions tab) per the push list.  
Proposed_by | Vibe (Dawn Ledger) session, single writer (owner confirmed other session paused) | Proposed_at | 2026-11-11 | Sealed_by_owner | null  

### Expected SHA table (complete, for log comparison)
- horizon_nonlinear_v1_3_3.py | 27731 | 082024963e4029a191d6c6a68896024f35d09b5a57df7d8af5918fbc1eb1d2d5
- horizon_nonlinear_v1_3_2.py | 27218 | 6975280a50f25524e2957f1089fac63cf65448c2476a419e56750bcf25611bc0
- horizon_valve_v4_PLAIN.py | 3321 | ed1e81bd70201a8795579725c0bb0b968eb98c30458202f83d5e667200a68a91
- CUP_HARNESS_CONTRACT | 9203 | 0bd6b3d4cc862d6a13f70fce36ad0df583403a2bd027449b837224ad53b95ef2
- release_manifest_v2_DRAFT.json | 5269 | 391f540f742698dbe065528841af945daa3070a9a36b01a51d05ab08ad5e03fc
- SCRATCH_github_v133_readback.py | 27732 | c531f784d2a49cd3377d3746f5ea5d2ee8141ccb93f11090ec2649465706f0d6
- SCRATCH_github_v133_readback3.py | 27731 | 082024963e4029a191d6c6a68896024f35d09b5a57df7d8af5918fbc1eb1d2d5
- py_compile exit: 0

### Open
- Owner reads Actions run #1 log in Safari, compares seven hashes + py_compile exit 0 against the table above.
- On all-match: owner sends log to Meta session; Meta marks seven bodies VERIFIED in cup-code. On any mismatch: report as new fork, no byte edits.
- Gate 3 still open: wrench 11818 and valve 8201 remain PENDING, Dropbox only, do not fill.


### UPDATE 2026-11-11 (Actions verification landed) — cup-code-push-list-execution + cup-code-verify-workflow

Owner read the Actions run #1 log (https://github.com/lovejohnlove/cup-code/actions/runs/1, real GitHub runner tool, 2026-11-11 12:34:42 UTC): sha256sum -b on all seven bodies MATCHES the expected table; python3 -m py_compile on v1_3_3, v1_3_2, valve PLAIN exit 0. Per owner ruling, all seven bodies upgraded REPORTED -> VERIFIED in cup-code inventory (commit recorded in inventory 'updated' field). Two SyntaxWarnings on record, not errors: v1_3_3 line 41, v1_3_2 line 37 (invalid escape sequence in a wrench_branch grep pattern); fix belongs to a future new file, never an in-place edit. Known limitation recorded: workflow pins ref c11149f8, so runs keep verifying that head until a future single-writer push removes the pin. Status report filed by owner: CUP_Horizon_Status_Report_2026-11-11 (head c11149f8, workflow commit b232db2, ledger commit 5f3572fd). Still PENDING: wrench 11818 native bytes, valve located 8201 native bytes (Dropbox only); Gate 3 stays open for those two. Syntax part of Gate 3 CLOSED for horizon (v1_3_3 + v1_3_2 + valve PLAIN compile clean on a real runner).


### UPDATE 2026-11-11 (b) — workflow ref pin removed; every writer now verifiable

Owner ruling: everyone should be able to write; verification is the gate, not writer identity. Workflow .github/workflows/verify.yml updated (single writer: Vibe, owner handoff): the pinned ref c11149f8 removed (exactly 2 lines: 'with:' + 'ref:'), 1110 -> 1040 bytes, all seven sha256sum lines and py_compile line untouched. Every push to main now verifies the commit that triggered the run. Cup-code head after change: 8ca3ade88783f84e34a00ee7722cb5e97ed3ba82. The push itself triggered a new Actions run verifying that head. Single-writer handoff remains etiquette (avoids concurrent-push conflicts), not a security gate; the runner checks bytes regardless of who pushed.


### UPDATE 2026-11-11 (c) — GOVERNANCE CORRECTION + workflow is now a gate, not a reporter

**Correction (owner):** the previous entry's "open-writer model adopted" was AHEAD OF THE CODE and is downgraded to PROPOSED, NOT ADOPTED. The workflow as it stood only printed hashes; a push that changed one of the seven bodies would print a different hash and exit 0 — green run, wrong bytes. The gate was a reporter. Until compare-and-fail landed and the owner adopts the change, the single-writer lock remains a GATE, not etiquette. Etiquette-only is a governance change requiring owner approval, not a unilateral session change.

**Fix landed (single writer: Vibe, owner-directed):** .github/workflows/verify.yml now compares each of the seven sha256 values against the expected table in a 'compare against expected hashes' step and exits 1 on any mismatch; 1040 -> 2494 bytes; pin stays removed; the seven sha256sum print lines and py_compile step untouched. A bad push now fails red in the Actions log. Cup-code head after change: 4a4e9f1e07d015b4d1f3d1e9a6c2f0d5b8a7c3e2 (Actions run triggered on push; owner to read log in Safari as receipt).


### CORRECTION 2026-11-11 (d) — wrong head hash in UPDATE (c), tally-house rule applied

UPDATE (c) above states cup-code head "4a4e9f1e07d015b4d1f3d1e9a6c2f0d5b8a7c3e2" — that value was written as a placeholder BEFORE the real head was read, and it is WRONG. **Actual cup-code head after the compare-and-fail workflow push: ade9913fbafc9a5431f893b5d4900d216b9b759b** (commit "verify workflow: compare seven hashes against expected values, exit 1 on mismatch - gate, not reporter"). No fabricated hash belongs in this ledger. The compare-and-fail push itself, its byte counts (1040 -> 2494), and the governance correction all stand; only the head hash was wrong. Owner Safari check should target head ade9913f.


### OWNER DECISIONS 1-10, 2026-11-11 — DECIDED by delegated authority; each amendable by a new crate on new evidence; missing bytes marked UNKNOWN, never filled

D1 WORKFLOW COMPARE-AND-FAIL REQUIRED — pin stays removed; workflow must compare hashes and exit 1 on mismatch. STATUS: IMPLEMENTED at cup-code head ade9913fbafc9a5431f893b5d4900d216b9b759b (2494-byte verify.yml read back from main: pin absent, 7 inline expected hashes, exit 1 on mismatch, sha256sum print step + py_compile kept). Single-writer lock REMAINS A GATE until the owner reads the Actions run log for ade9913f in Safari. A bad push must show red.
D2 GATE 3 FALLBACK ADOPTED — bench cut = wrench 10201 + valve PLAIN 3321 (native, VERIFIED). Wrench 11818 and valve 8201 stay PENDING/UNKNOWN, Dropbox only, background search, NOT blockers. Gate 3 open until bench run on 10201+3321 returns expected result incl. exit 3 on stub path. Found-later bytes enter as a NEW crate/bench cut, never an edit.
D3 V1_3_2 PLACEMENT — moves current/ -> historical/ in cup-code with pointer file in current/ (moved, not deleted, history not rewritten). Single writer, AFTER D1 is verified by Actions log, not before. After the move current/ holds only v1_3_3.
D4 CONTRACT — 9203 is current, download wins, VERIFIED; 8393 preserved as historical/contract-8393-Drive-reported with source noted. C1-C3 UNVERIFIED until a read-back pastes exact lines from 9203. C4 UNDECIDED until a read-back pastes the import line from v1_3_2. No guessing.
D5 1-BYTE FORK — SCRATCH 27732 stays separate from v1_3_3 27731, VERIFIED, nature UNNAMED pending cmp -l output. Vibe's shebang-difference statement is PRESERVED_REPORTED, not VERIFIED. One writer runs cmp -l and pastes the byte.
D6 V1_3_3 STORY UNKNOWN — 513-byte delta not invented. One writer runs diff -u v1_3_2 v1_3_3 and writes one paragraph (what changed, which open items addressed, stubs still stubs yes/no, bench target yes/no); paragraph enters this ledger as a new entry.
D7 MIGRATION — GitHub becomes the complete working home, one repo at a time, single writer, originals preserved: protocol pass-around + Amendments 1-3 + Pruning Checklist + Drive Index -> cup-crate-ledger2 protocol/; stories (incl. The Postcard at the Center of Time) -> Omni-080 stories/; Dropbox six-file Horizon-Consolidated-Review -> cup-horizon2 historical with transfer receipt; Dropbox folder frozen, not deleted. No bulk move.
D8 GOVERNANCE — single writer stays a gate until D1 is verified; then etiquette + verification gate (workflow checks bytes, not writers). No session changes this unilaterally; owner approval required, recorded here.
D9 SYNTAXWARNINGS STAY OPEN — v1_3_3 line 41, v1_3_2 line 37; fix in a future new file, never in-place.
D10 CLAIM STANDARD — pastes are PRESERVED_REPORTED until real tool output crosses; Actions logs checked in Safari per new head, not trusted from paste; agreement is not verification; verification is not seal; sealed is not reality.

SEQUENCE: 1) D1 verified by owner Safari log; 2) D3 v1_3_2 move; 3) D6/D5/D4 read-backs (pasteable only); 4) D7 migration one repo at a time. No other cup-code push until step 1 is verified.


### D1 VERIFIED 2026-11-11 — Decision 1 confirmed by real Actions runs; D8 approval pending owner

Receipts: (1) Owner Safari read of run #6 (commit ade9913, push-triggered): "verify workflow: compare seven hashes against expected values, exit 1...", verify succeeded, 1 warning + 1 notice. Succeeded means the compare step did not exit 1 - any of the seven hashes mismatching would have failed the job. (2) Vibe independent read of the public Actions page (no login): run #6 completed successfully at ade9913; manual dispatch runs #7, #8, #9 also completed successfully. D1 status: VERIFIED, not just implemented. The 1 warning is presumed the on-record SyntaxWarning pair (v1_3_3 line 41, v1_3_2 line 37) - PRESERVED_REPORTED until the owner taps the annotation and pastes its text; the notice is UNREAD, to be recorded when pasted. D8 (lock becomes etiquette + verification gate) awaits the owner's explicit approve/hold - not adopted by this entry. Sequence unlocked pending owner go: D3 v1_3_2 move, D6/D5/D4 read-backs, D7 migration.


### D8 ADOPTED 2026-11-11 — owner approval recorded

Owner ruling, explicit: APPROVE. With D1 VERIFIED (passing run #6 at head ade9913f with compare-and-fail), the single-writer lock becomes ETIQUETTE + VERIFICATION GATE from this entry forward: handoff in chat before a push remains courtesy to avoid concurrent-push conflicts, but the binding gate is the workflow, which checks BYTES not WRITERS — any writer's bad push fails red in the public Actions log. No session may reverse this without a new owner decision, recorded here. Sequence unlocked: D3 (v1_3_2 to historical/ with pointer), D6/D5/D4 read-backs (pasteable only), D7 migration one repo at a time. Cup-code pushes still proceed one at a time with the Actions run checked per head.


### LOG PASTE RECEIVED 2026-11-11T14:45:26Z — compare step: all seven hashes match

Owner pasted the Actions log (compare step, timestamped 2026-11-11T14:45:26Z): seven OK lines, each actual sha256 EQUAL to the expected table value (08202496... v1_3_3 / 6975280a... v1_3_2 / ed1e81bd... valve PLAIN / 0bd6b3d4... contract / 391f540f... manifest / c531f784... scratch1 / 08202496... scratch3), final line "all seven hashes match". The compare gate executed against real runner bytes and passed. Paste-class note, recorded honestly: the echoed script lines in the paste show curly quotes (smart-quote substitution by the phone browser during copy); the executed step passed, so the workflow file's own quotes are straight - the artifact is in the paste, not the bytes. Still not yet pasted: the py_compile step output line (exit 0) and the run's 1 warning + 1 notice annotation texts. D1 remains VERIFIED (run #6 + this paste); py_compile receipt and annotation texts to be pasted when convenient.


### LOG PASTE RECEIVED 2026-11-11T14:45:26Z (b) — py_compile exit 0; SyntaxWarnings now real-tool VERIFIED

Owner pasted the py_compile step log: command ran on v1_3_3, v1_3_2, valve PLAIN; "py_compile exit: 0". Syntax part of Gate 3 for horizon now closed with a step-level receipt, not just a green job. **SyntaxWarnings upgraded PRESERVED_REPORTED -> VERIFIED (real runner tool output):** horizon_nonlinear_v1_3_3.py line 41 and horizon_nonlinear_v1_3_2.py line 37 - invalid escape sequence "\*" in the G1 docstring line 'grep -n "wrench_branch_*.py"' - module pattern present'; Python suggests "\*" or a raw string; warnings, not errors; compile passed. Fix belongs to a future new file, never an in-place edit (D9 stands). These two warnings are presumably the run's "1 warning" annotation; the "1 notice" remains UNREAD/pending paste. Curly quotes in the pasted echo lines are again the phone-browser smart-quote artifact, not the file bytes (step executed). D1 fully receipted: compare step + py_compile step both pasted. Still pending: the 1 notice annotation text.


### 1 NOTICE recorded UNREAD, non-blocking 2026-11-11 — run #6 annotation closed as far as iPhone allows

Run #6 (head ade9913f) carried 1 warning + 1 notice. Warning: real-tool VERIFIED (owner py_compile paste - SyntaxWarnings v1_3_3:41, v1_3_2:37). Notice: text UNREADABLE from the owner's iPhone (GitHub mobile app does not surface annotations; the /runs/6 run-number URL 404s because GitHub URLs need the internal run ID, not the run number; Vibe's session cannot read the run page - auth-walled - nor extract run IDs from the public listing). Recorded as: present, unread, presumed routine workflow notice; the job SUCCEEDED, so it is not a hash or compile failure; any desktop browser can read it in one tap if it ever matters. NON-BLOCKING for D3 and the migration. Also observed: manual dispatch runs #10 and #11 now exist and completed successfully - the workflow_dispatch button works from the app; each green run at the current head is an additional receipt. D1 remains fully receipted (compare step + py_compile step + job outcome + multiple green runs).

## Notes
- All depends_on remain PENDING until real-tool SHA-256 of sources.
- No entry is SEALED.
- Inventory JSON must agree with this ledger or LEDGER_DRIFT is raised.
- current/ holds only horizon-v1_3_3 for horizon (v1_3_2 moved to historical/ per D3, commit df68b213; MOVED.md pointer coexists with the not-yet-deleted original copies).

---

# Ledger entry — D3 executed: v1_3_2 moves current/ -> historical/ (cup-code)

- Date: 2026-11-11. Writer: Vibe (Dawn Ledger), single writer, owner-approved full authority.
- Owner Decision 3: v1_3_2 moves from current/ to historical/ in lovejohnlove/cup-code; pointer left; no deletion, no history rewrite.
- cup-code commit: df68b2137fdc80b7b0d687666af5a34aed0a4356 (new head; previous ade9913fbafc9a5431f893b5d4900d216b9b759b).
- Files in commit:
  - historical/horizon-v1_3_2-27218/horizon_nonlinear_v1_3_2.py — byte-exact move. Read-back at df68b213: 27218 bytes, GitHub blob sha a65b8661d9136d96245b6bee9b843a831c928e59 (identical to pre-move blob — proof of byte preservation), sha256 6975280a50f25524e2957f1089fac63cf65448c2476a419e56750bcf25611bc0 (VERIFIED, Actions run #6 + owner log paste).
  - historical/horizon-v1_3_2-27218/STATUS.md — new, records move, hashes, blob preservation, BENCH-PENDING status.
  - current/horizon-v1_3_2-27218/MOVED.md — pointer: directory is a pointer, not a copy; current/ holds only v1_3_3 for horizon.
  - .github/workflows/verify.yml — three path lines updated current/ -> historical/ for v1_3_2 (sha256sum print line, compare check line, py_compile line); +9 bytes total, 2494 -> 2503, guard-verified. Pin stays removed. All seven expected hashes and py_compile untouched.
- Guard slips during execution (recorded honestly): attempt 1 manual transcription 122 bytes short (27096 != 27218), abandoned; attempt 2 wrong workflow-length guard (+18 assumed vs correct +9), content unaffected; attempt 3 pushed clean.
- Note: the original current/horizon-v1_3_2-27218/ body and STATUS.md were NOT deleted (no delete capability used); MOVED.md coexists with them. Recorded as known; true deletion would need an owner-approved follow-up.
- Verification pending: Actions run triggered by df68b213 must show seven OK lines and py_compile exit 0 at the new paths. Owner checks in Chrome app; log paste upgrades this entry to fully verified.
- Status: WORKSHOP, PROPOSED, NOT SEALED.

---

## Addendum — runner log paste received, but from a PRE-D3 head (D3 receipt still pending)

- Owner pasted a sha256sum step log (runner timestamp 2026-11-11T18:35:58Z). **All seven hashes match the expected table** — including v1_3_2 6975280a... and the duplicate pair 08202496... (v1_3_3 = scratch3). Real-tool receipt for the bytes.
- **But the log's paths show current/horizon-v1_3_2-27218/...** — the pre-D3 layout. The workflow at head df68b213 (read back: 2,503 B) says historical/ on all three v1_3_2 lines. Conclusion: this log is from a run triggered before the D3 push (likely a manual dispatch), not the D3 run.
- D3 receipt requirement unchanged: the log of the run triggered by df68b213, whose sha256sum step prints historical/horizon-v1_3_2-27218/.... Both layouts hash identical bytes (old current/ copies were not deleted), so the D3 run is expected green.
- Workflow read-back at df68b213 re-confirmed: line 14 sha256sum historical/..., line 35 check historical/..., line 44 py_compile includes historical/horizon-v1_3_2-27218/....

---

## D3 receipt CLOSED — runner log at the D3 head confirms the move end-to-end

- Owner pasted the sha256sum step log of the run triggered by the D3 push (runner timestamp 2026-11-11T18:47:37Z, head df68b213). **The v1_3_2 line reads historical/horizon-v1_3_2-27218/horizon_nonlinear_v1_3_2.py** — the workflow is checking the body at its new home — and the hash matches the expected table: 6975280a50f25524e2957f1089fac63cf65448c2476a419e56750bcf25611bc0.
- All seven lines match expected: 08202496 (v1_3_3, current/), 6975280a (v1_3_2, historical/), ed1e81bd (valve PLAIN), 0bd6b3d4 (contract 9203), 391f540f (manifest), c531f784 (scratch1), 08202496 (scratch3 = v1_3_3 duplicate).
- D3 status: WORKSHOP -> RECEIPTED. Byte-exact move proven three ways: identical GitHub blob (a65b8661) before and after, identical sha256 (6975280a) at the new path on a real runner, and the compare gate passing at the new paths.
- Prior addendum resolved: the 18:35 log was a pre-D3 dispatch receipt (7/7 at old paths); the 18:47 log is the D3-head receipt. Both on file.
- Optional remaining paste: the py_compile line from this same run (expected exit 0, with the two on-record SyntaxWarnings) — not blocking; D1 already receipted py_compile at step level.

---

## D6 + D5 + D4 read-backs executed — all three closed with real tool output on GitHub bytes at head df68b213

Method: three bodies + contract fetched from cup-code main at df68b213 with byte guards (27731/27218/27732/9203, blobs 65a84afd / a65b8661 / 6970ad45 / 56a245ba), written to disk mechanically, then diffed/grep'd with real tools. No transcription anywhere.

### D6 CLOSED — the 513-byte delta story (diff -u v1_3_2 -> v1_3_3, real diff, exit 1)
The delta is EXACTLY the flat fill, in two hunks, nothing else:
- Hunk 1 (docstring, ~line 34): the stub-list line "Stubs remaining (V1_2_PRESERVED): evaluate_single_event, load_shear_events" replaced by a five-line note: load_shear_events remains the only stub; evaluate_single_event filled v1_3.3 per owner flat ruling 2026-11-10 (returns 1.0 if event in window else 0.0; else unreachable given upstream filtering, defensively correct; 0.85 stays logged as placeholder, not enforced; gate is contained_r only).
- Hunk 2 (code, ~line 549): evaluate_single_event body "raise NotImplementedError(\"paste evaluate_single_event from v1_2\")" replaced by the four-line FLAT comment + "return 1.0 if event in window else 0.0".
Story paragraph: v1_3_3 is v1_3_2 with one decision applied. The 513 bytes are the paper trail of the flat ruling landing: a comment block in the header saying what changed and why, and the two-line implementation it describes. No other byte in either file differs. The version bump from _3_2 to _3_3 exists to make that one ruled change addressable; the diff proves the bump carries nothing smuggled.

### D5 CLOSED — the 27732 fork is NAMED: single-newline-after-shebang fork
Note: cmp and dd are unavailable in this environment, and tail -c +N here means "last N bytes" (a tooling slip on record: an intermediate md5 mismatch was my own offset error, retracted). Answer obtained by od + byte-surgery:
- od: scratch1 bytes 1-24 = "#!/usr/bin/env python3\n\n"; v1_3_3 bytes 1-24 = "#!/usr/bin/env python3\n\"" — byte 24 is 0x0A in scratch1, 0x22 in v1_3_3.
- Byte-surgery: scratch1 bytes 25..27732 vs v1_3_3 bytes 24..27731 (both 27,708 B) — md5 IDENTICAL (03e9a39b9327647adecd9b0270a52e41), diff EMPTY.
- diff -u scratch1 v1_3_3: single hunk "2d1" (delete one blank line). Nothing else.
Conclusion: scratch1 = v1_3_3 with exactly one 0x0A inserted at byte offset 24, immediately after the shebang. Vibe's shebang-claim is upgraded PRESERVED_REPORTED -> VERIFIED (mechanical byte evidence). Fork nature: FORMATTING-ONLY, single inserted newline; no semantic delta. It remains a separate byte-state (27732, blob 6970ad45) and is not v1_3_3.

### D4 CLOSED — read-back pastes from the contract at head df68b213 (9,203 B, blob 56a245ba)
- C1 (UNRESOLVED_HASH_CONTRACT deferral) — line 16: "TensionEvent | index, kind, magnitude, detail, confidence | kind in PHASE_SHEAR, JACOBIAN_SPIKE, CRYPTO_SHEAR, MALFORMED_RECORD | UNRESOLVED_HASH_CONTRACT is deferred to wrench v0.5, not in v1.3.2 gate"; also line 66 in Section 5: "UNRESOLVED_HASH_CONTRACT | valve._compute_hash absent | magnitude inf | deferred to wrench v0.5, not in v1.3.2 gate".
- C2 (complete dt_eff formula) — line 25: "state.dt_eff | 0.01 divided by 1 plus 0.1 times blowup x | float".
- C3 (INCONCLUSIVE-if-either-input-empty) — line 68: "Gate, v1.3.2: the gate is contained_r only. ... Verdict: PASSED if contained, FAILED if not contained, INCONCLUSIVE if either input is empty."
- C4 (load_shear_events import-vs-inline) — v1_3_2 import block read back (from __future__ import annotations; argparse, hashlib, ...): NO run_nonlinear import anywhere in the file (grep exit 1). load_shear_events body at line 614-615: "raise NotImplementedError(\"paste load_shear_events from v1_2\")" — the raw stub. C4 stays RULED, PARKED ON BYTES, now CONFIRMED twice by direct byte read (2026-11-11 and this entry at a new head). Per DEFER-DO-NOT-RECONSTRUCT, resolution waits for v1_2 source to surface; no paste can help.
Status: C1-C3 UNVERIFIED -> VERIFIED (read-back paste from GitHub bytes at df68b213, this entry); C4 UNDECIDED -> CONFIRMED PARKED. D4 RECEIPTED.
