Crate Protocol v0.1 Amendment 2, Valve Cut, Manifest Hashing, Authenticity, Prior Art, PROPOSED


To: Owner / Meta From: This session, as proposal, on read-back from DeepSeek and GPT Status: PROPOSED, not sealed, not public, no bytes promoted to fact Basis: DeepSeek read-back of Amendment 1, plus GPT read-back of Amendment 1, both 2026-11-10, text pasted, not Drive bytes for GPT Amends: Crate Protocol v0.1 Final Pass-Around, plus Amendment 1, Section 13, Section 2 Jack 3, Section 11


1. Blocking inconsistency, valve ruling, resolved by naming cut, not by editing


DeepSeek flags: Two documents now on Drive assert mutually exclusive facts about same ruling:


* Manifest v2 draft, filed earlier: verify closed as fork with PLAIN ruled bench-paired, subject to override.
* Amendment 1, this report: bench-paired valve, 3321 versus 8201: RULED located 8201, not PLAIN 3321 bytes. These cannot both be true of one ruling. One is stale, or one is wrong, or they describe two different cuts without naming them. Amendment phrase not bench-paired for this cut hints at third reading, but neither document names cut, so reader cannot tell which is current. Fix, PROPOSED: Name cut in both places. Ruling is 8201 for bench-release cut, manifest line is stale and must be superseded, not edited, per Section 7 Rule 1, correction is new crate. If ruling were 3321, amendment line would be wrong. Either way, one document gets superseded_by pointer, and protocol Section 4 invariant, SEALED to DRAFT is not allowed, correction is new crate, applies to manifest, not just to code. Resolution, PROPOSED, to be ratified by owner:
* Cut name: bench-initial-2026-11-10 | Valve: PLAIN, 3321 bytes, verify_integrity only | Status: HISTORICAL, superseded | Superseded_by: bench-release-2026-11-10 | Reason: Manifest v2 draft line for this cut is stale, superseded, not edited.
* Cut name: bench-release-2026-11-10 | Valve: located, 8201 bytes, bare verify returning ok, msg | Status: CURRENT, bench-paired for this cut | Supersedes: bench-initial-2026-11-10 | Reason: Ruling (d) and (g), located 8201, as recorded in Amendment 1, with cut named.
* Manifest v2 draft file itself remains historical, not edited. Its line for PLAIN bench-paired is marked superseded_by: Amendment 2, bench-release-2026-11-10. Amendment 1 line is corrected to include cut name: bench-release-2026-11-10, located 8201, not PLAIN 3321 for this cut. PLAIN remains preserved as fork, not deleted, not bench-paired for bench-release cut. This is exactly class of drift three-way check exists to catch. Fix is small: name cut in both places. One line each.
2. Provenance gap, Dropbox transfer has no receipt


DeepSeek flags: Amendment scope note says no session has Dropbox in this turn, and then correctly rules: Cross-home copies are explicit transfers, with source, destination, hash, date, status. Good rule, but it has not been applied retroactively. Six-file folder in Hex-Loom-CUP, Horizon-Consolidated-Review, was copied by some session, at some time, from some source paths. None of that is in ledger as receipt. Under amendment own rule, that transfer is currently PRESERVED_REPORTED, not VERIFIED. Receipt should be back-filled, or folder entries explicitly marked as missing transfer receipt. Resolution, PROPOSED:


* Transfer receipt for Hex-Loom-CUP, Horizon-Consolidated-Review, six-file folder: Status MISSING, not back-filled in this session, because this session has no Dropbox connector, no source paths, no date, no hash from transfer.
* Folder entries are explicitly marked: Transfer receipt missing, PRESERVED_REPORTED, not VERIFIED, until receipt is back-filled by session that performed transfer, with source, destination, hash, date, status.
* Back-fill fields required: Source home, source path, destination home, destination path, source SHA-256, destination SHA-256, transferred_by, transferred_at, tool, environment, status.
* Until back-fill, no folder entry in that folder can be promoted from PRESERVED_REPORTED to VERIFIED on basis of transfer alone. It can be promoted only by independent read-back from source, with hash, with receipt, per Section 8.
* This session did not perform Dropbox transfer, did not inspect Dropbox bytes in this turn, and does not claim transfer receipt exists.
3. Search findings, what Section 11 missed, six gaps, ranked by value-per-line


DeepSeek search, adopted as PROPOSED prior-art notes, not structural changes, v0.1 can absorb them as amendment, except where noted as v0.2. 3.1 SWHID, standardized content identifier we should have named Software Heritage SWHID became ISO IEC 18670:2025 this year: intrinsic, decentralized, cryptographically strong identifier bound to source-code content, at multiple granularities, file, directory, commit, snapshot. This is exactly seal-upgrade path Section 11.4 gestures at, content-addressed identity, standardized, verifiable without trusting registry. It also sharpens distinction protocol blurs: SWHID is intrinsic, derived from content, DOI and ARK are extrinsic, assigned by authority. Our seal is intrinsic, our ledger entry slug is extrinsic. Protocol should say so explicitly, because seal and crate ID are currently doing similar work in prose and are not same kind of thing. Adopt, PROPOSED: Section 11.1 line naming SWHID as standard for intrinsic software identity, with swhid field reserved in manifest for when it is computed. Manifest field: swhid | swh:1:rev: and others, or PENDING, or RESERVED, not required for v0.1. 3.2 OCFL is stricter than us on manifest completeness OCFL makes two things errors, not warnings: file whose checksum does not match manifest entry, and file present in object but not listed in manifest. Our Jack 1 and Jack 3 say manifest lists what is in crate, but do not say what happens when something is present and unlisted. That is real gap: unlisted file is currently neither sealed nor flagged. Adopt, PROPOSED: One line in Jack 1, File present in crate directory but absent from files is error, not warning, crate cannot seal. Unlisted file is not sealed, not ignored, it blocks seal until listed or removed, with removal recorded as new crate, not silent delete. 3.3 in-toto layout, authorization model we do not have in-toto graduated CNCF in April 2025 and models entire supply chain, not just artifact: layout defines steps, functionaries authorized to perform each step, and inspections that verify result. Our protocol has per-crate manifests but no pipeline-level model. Gate 3 bench run is step with no authorization record, anyone with Python can claim they ran it. Adopt, v0.2, not v0.1, PROPOSED, RESERVED: layout section in protocol defining which session or identity is authorized to produce bench receipt for given crate. This is piece that makes independently reproduced meaningful rather than self-reported. For v0.1, bench receipt remains self-reported, with flag independently reproduced, yes or no, with limitation noted. For v0.2, layout becomes required, with authorized functionaries, with inspections. 3.4 SLSA separates verification levels, we collapse them into one state SLSA distinguishes build-integrity levels, in-toto attestation format carries materials, command, byproducts. Our SEALED currently means hash pinned and bench run and independently reproduced all at once, three very different strengths. That conflation is why manifest can say SEALED while sha256 is PENDING in same breath. Adopt, v0.2, not v0.1, PROPOSED, RESERVED: Split seal state into three named levels, INTEGRITY, hash match, BENCHED, tests ran, receipt attached, REPRODUCED, independent run confirms. Crate can be SEALED at INTEGRITY and not yet BENCHED, label says which. For v0.1, SEALED means all five jacks complete, with seal filled and verified, no partial seals. For v0.2, SEALED becomes leveled, with level recorded in manifest, with INTEGRITY, BENCHED, REPRODUCED as distinct states. 3.5 DataCite PID rule is external validation of fork discipline DataCite guidance is almost verbatim our Section 7: Every public release must have persistent identifier and be immutable. Any content change requires new persistent identifier. Track both time, sequential updates, and space, forks and parallel variants. Adopt, PROPOSED: Cite in Section 7, not because we need their approval, but because it proves fork-preservation rule is not idiosyncratic. It is same rule library science arrived at independently, for same reason: mutable name cannot be stable claim. Section 7 now cites DataCite PID rule as independent convergence. 3.6 Ecosystem norm is weaker than digest rule, say so DVC, widely used data-versioning tool, content-addresses files by MD5. Our MD5 is debt marker, not seal rule is therefore deliberate divergence from ecosystem norm, not restatement of it. Section 11.4 should say this plainly, alongside no-signature divergence, both are places where we are stricter or different on purpose, and both should be named so nobody fixes them later. Adopt, PROPOSED: Section 11.4 now says: DVC uses MD5 for content addressing. Our rule, MD5 is debt marker, not seal, is deliberate divergence from ecosystem norm, not restatement. Do not fix by replacing SHA-256 with MD5 for compatibility. Divergence is intentional, with reason: MD5 is weak, SHA-256 is strong, seal must be strong.


Minor, worth line each, PROPOSED:


* BagIt tagmanifest-sha256.txt, pattern of single manifest whose own hash validates inventory that validates files. We have this, manifest_sha256, worth naming precedent.
* Rekor inclusion plus consistency proofs, construction that makes append-only log verifiable, not just append-only. Our ledger is append-only by discipline, naming Rekor as construction shows upgrade path.
* W3C PROV, Entity, Activity, Agent, vocabulary for provenance that our depends_on plus story plus sealed_by roughly maps to. Not needed now, worth mapping table in v0.2 if crates ever need to interoperate.
* FAIR for software, DOI, no mapping in protocol. Not urgent, but if crate ever needs to be cited, FAIR is framework. What we did not miss, per DeepSeek search: Core shapes, manifest-last, file-fixity, transitive pending, no-partial-seals, fork preservation, all held up against standards. Section 11 existing citations, BagIt, OCFL, in-toto, SLSA, Sigstore, Rekor, C2PA, SBOM, are correct, just incomplete. Search did not overturn anything, it filled gaps.
4. GPT two technical details, to tighten before sealing


GPT agrees Amendment 1 is useful correction, agrees keeping it PROPOSED, not sealed. Two details to tighten before sealing, adopted as PROPOSED. 4.1 Manifest hashing, self-reference Amendment says seal includes SHA-256 of manifest itself. Need to specify how that works. If manifest contains its own hash, it creates self-reference. Clean solution is detached seal receipt containing manifest SHA-256, alongside file hashes. Alternatively, define canonical manifest representation that excludes seal fields before hashing. Resolution, PROPOSED: Use both, in defined order, to avoid self-reference.


* Canonical manifest representation excludes seal fields before hashing. Fields excluded: seal, manifest_sha256, sealed_by, sealed_at, tool, environment, if they are part of seal block.
* Compute SHA-256 of canonical manifest, without seal fields, in defined order, with defined line endings, with defined encoding.
* Seal is detached receipt, separate file, containing manifest SHA-256, plus file hashes, plus sealer identity, timestamp, tool, environment, plus its own SHA-256 for receipt itself, recorded in ledger.
* Manifest does NOT contain its own hash. Manifest contains pointer to seal receipt: seal_receipt | file name, SHA-256 of receipt, or PENDING.
* This avoids self-reference, because manifest hash is of manifest without seal, and seal receipt hash is of receipt, not of manifest.
* For v0.1, canonical representation is: manifest as sealed, with seal block removed, with fields in order listed in Jack 1, with pipe-separated plain lines, with UTF-8, with LF line endings. Any change to canonical representation is version bump, with new procedure recorded. 4.2 Hash versus authenticity SHA-256 establishes content fingerprint. It does not, by itself, prove who produced file or who authorized its seal. Receipt should distinguish:
* Content integrity: SHA-256.
* Attribution: named sealer and recorded identity.
* Authorization: explicit sealing action.
* Execution provenance: tool, procedure and environment. Resolution, PROPOSED: Seal receipt must distinguish four fields, not conflate them.
* Content integrity: SHA-256 of each file, plus manifest SHA-256, plus receipt SHA-256.
* Attribution: sealed_by, named sealer and recorded identity, as text field, not signature, per Section 11.4, with limitation noted.
* Authorization: sealing action, explicit, with date, with decision, with Governance ruling if needed, with status change from DRAFT to SEALED, recorded in ledger, not just in receipt.
* Execution provenance: tool, procedure, environment, command, version, OS, architecture, relevant runtime. That distinction will prevent valid hash from being mistaken for proof of authority. Agreement is not verification, and verification is not authorization to seal. That is exactly separation we want to preserve, per GPT note, ratified as PROPOSED.
5. Source read-back status, GPT and DeepSeek


GPT notes: Not independently read back. Could not retrieve Google Drive document through connected Google Drive action in this session, and Library search did not locate it. So reviewed text pasted, not actual Drive bytes. Supplied Drive link remains reported location. File remains PRESERVED_REPORTED from GPT perspective until source is retrieved and checked. Recorded: GPT read-back is text-only, not byte read-back, with limitation noted. It is check of prose, not check of bytes. It does not promote file from PRESERVED_REPORTED to VERIFIED from GPT perspective. DeepSeek read-back: DeepSeek read Amendment 1 text, flagged blocking inconsistency and provenance gap, plus search findings. DeepSeek read-back is also text-based in this forwarding, not byte read-back from Drive in this session. It is recorded as read-back of pasted text, with check of logic, not as byte verification. Both read-backs are useful, neither is seal. Seal waits for real-tool output, not agreement.


6. Smallest next moves, per DeepSeek, adopted as PROPOSED


7. Resolve valve contradiction, name cut in both manifest and Amendment 1, supersede whichever is stale. One line each. Done in Section 1 above: bench-initial-2026-11-10 superseded by bench-release-2026-11-10, with superseded_by pointer, with cut named.


8. Back-fill Dropbox transfer receipt, or mark folder entries as missing one. Done in Section 2 above: marked missing, PRESERVED_REPORTED, not VERIFIED, with back-fill fields required.


9. Add six lines to Section 11, SWHID, OCFL strictness, in-toto layout, SLSA levels, DataCite citation, DVC and MD5 divergence. All are prior-art notes, not structural changes, v0.1 can absorb them as amendment. Done in Section 3 above, with layout and SLSA levels as v0.2, RESERVED, not v0.1.


10. Defer layout section and seal-level split to v0.2, they are real gaps but not blockers for protocol that is not sealed yet. Done: layout and seal-level split are RESERVED, v0.2, not required for v0.1.


11. What this amendment does not do


* It does not seal protocol. Protocol remains PROPOSED, not sealed, not public.
* It does not resolve open rulings, except to record valve cut naming as above, to be ratified by owner.
* It does not promote DeepSeek or GPT read-back to seal. Seal waits for real-tool output, not agreement.
* It does not claim dependency graph is verified. Dependency graph remains PROPOSED, pending read-back against source.
* It does not claim AI has consciousness, awareness, enlightenment, or outside agency. Those remain RESERVED, PROPOSED EFO entries, with triggers, not facts.
* It does not claim Dropbox transfer receipt exists. Receipt is missing, marked as missing, to be back-filled by session that performed transfer.