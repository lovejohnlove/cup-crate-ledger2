The Crate Protocol v0.1 Final Pass-Around


To: Owner / Meta From: This session, as proposal, combined DeepSeek draft plus Meta draft Status: PROPOSED, not sealed, not public, no bytes promoted to fact Basis: Rulings and corrections in this thread, plus prior art found in search pass, noted inline. Section 11 summarizes what is borrowed and where we deliberately diverge.


1. Scope and non-goals


Scope. This protocol defines how work is packaged, named, preserved, verified, and released across multiple contributors, human and AI, working in separate locations with separate tools.


Non-goals, stated up front so nobody reads protocol as more than it is:


* It is not a supply-chain security standard. Seal is human-committed SHA-256. It provides integrity against accidental change, not authenticity against malicious actor. Section 11.4 names this tradeoff explicitly.
* It is not a build system, a CI/CD pipeline, or a package manager.
* It is not a claim that any current file is verified. Every hash in this thread is PENDING until real tool produces it.
* It is not a rename of Rust ecosystem crate. Word is reused because shape is similar, named, versioned, hash-identified unit. It is not same artifact class. Where confusion is possible, write CUP crate.
* It is not a safety protocol, and it is not a religion. It is understanding how system works. If people adopt code, they will see that. Safety protocol says do not do X, or else. Religion says believe Y, because we say so. Crate says here is what happened, with hash, with receipt, with limitations, with disagreement preserved, check it yourself.
1. Core vocabulary


Term | Definition | Not to be confused with Crate | Unit of push: named, versioned, hash-sealed collection of files with manifest, story, and declared dependencies. | File. Folder. Rust crate. Component | Single file or tightly-coupled file group inside a crate that can be pulled, tested, and released independently. | Crate. Component is inside a crate. Engine | Crate that produces behavior consumed by other crates, valve, caliper, wrench, harness. | Component. Engine is crate with dependents. Shelf | Full set of crates in a given home, Drive, Dropbox, GitHub, local. | Crate. Shelf holds crates. Toolbox | Crate containing engines and tools, separate from Framework and Stories, so per-tool release is possible. | Shelf. Toolbox is one crate on shelf. Fork | Two or more byte-states of same logical artifact, both preserved, both named, neither cut. | Mess. Fork is evidence of structure. Cut | Scoped, labelled, reversible selection of exactly one byte-state for exactly one run. | Deletion. Cut never removes other byte-states. Seal | Cryptographic identity of crate bytes: SHA-256 of each file plus manifest SHA-256 plus hashing procedure plus sealer identity plus timestamp. | Fingerprint. MD5 is fingerprint, not seal. Drive or Dropbox content hash is not seal. EFO | Shared dictionary of terms: words, definitions, variants, disputed meanings, unresolved entries. | Status field. EFO describes what word means, not whether work is done. Consciousness | In crate terms, RESERVED, see Section 12. Not claimed here. | Human consciousness. Crate does not claim AI consciousness. Awareness | In crate terms, system records its own actions, with source, hash, receipt, limitations, disagreement preserved. | Consciousness. Awareness is record, not feeling. Enlightenment | In crate terms, understanding how system works, written in plain lines, so others can check, not so they must believe. | Belief. Enlightenment is checkable record, not doctrine.


Known terminology collision: crates.io Rust uses crate for packages with names, versions, Cargo.toml manifest. Our manifest is superset, story, seal, depends_on, category, status, and our seal is human commitment, not registry signature. Name difference when speaking to anyone outside workshop. Same for RO-Crate, see Section 11.2.


2. The five jacks, interface


Crate is modular only if all five are present. Missing any one and modularity is theoretical, you find out when something breaks.


Jack 1, Manifest. What crate contains, exports, requires. Fields: crate | content-stable slug, not location name version | semver or date-based category | one of Section 3 eight status | one of Section 4 states domain | bio, quantum, financial, horizon, cup, stories, none, or other, not a category efo_status | SEALED, EFO_PENDING, UNDEFINED files | name, bytes, sha256 or PENDING, one line per file exports | interfaces this crate provides depends_on | see Jack 4 story | see Jack 2 seal | see Jack 3 verify | see Jack 5 fork_of | crate slug or null supersedes | crate slug or null superseded_by | crate slug or null license | SPDX id or none specified intended_use | one line tested | what has been run uncertain | what has not been run, or has failed challenge | strongest objection to this crate being correct


Adopted from prior art: write manifest last, atomically, so presence is claim. Crate directory without manifest is visibly incomplete, not silently partial. This converts I forgot to write manifest from possible state into impossible one. Rejected from prior art: do not auto-generate manifest from directory contents. Manifest is claim, claim generated by scanning is description, not commitment. Written by hand, checked against bytes.


Jack 2, Story. Why crate exists, in crate sense, not fiction. For code crates: handoff, intent, what was tried, what failed, what remains uncertain. For fiction crates: fiction is content, handoff is separate, conflating them breaks interface. Rule: story is immutable once crate is sealed. Corrections are new crates, not edits. Typos in story are preserved as history, not quietly fixed, because corrected typo in immutable story is evidence that immutability rule was enforced, not violated. Handoff record, part of story for code crates: Handoff | From | To | Source revision | Source SHA-256 | Intent | Tested | Uncertain | Challenge | Date | Status From: who sends, To: who receives, Source revision: commit or file ID, Source SHA-256: hash of bytes sent, Intent: what code is intended to do, Tested: what has already been tested, Uncertain: what remains uncertain, Challenge: what we want receiver to challenge. Effect: Response becomes review record, not automatic approval.


Jack 3, Seal. Cryptographic identity of bytes. Seal is not hash, hash is one component of seal. seal: procedure: sha256sum -b file for each file, in order listed in manifest files: name, sha256, one line per file manifest_sha256: sha256 of manifest as sealed, so manifest itself is pinned sealed_by: identity of human who ran tool sealed_at: ISO 8601 UTC timestamp tool: exact command and version, for example sha256sum, coreutils 9.4 environment: OS, architecture, relevant runtime No partial seals. Crate with some files hashed and others PENDING is DRAFT, not SEALED. No substitutes for seal: MD5 is not seal. Drive or Dropbox content hash is not seal, it is hash of their copy, not necessarily yours. Reconstructed hash is not seal. Hash of repaired or extracted copy is not seal if byte-state being sealed differs from byte-state being claimed. No signature, deliberate, Section 11.4. Established practice wraps seal in signature, minisign, GPG, cosign, Sigstore, so who sealed it is cryptographically provable. We do not, because trust model is human owner is trusted. That is real weakening. If crate ever leaves workshop, seal must be upgraded to signed seal, manifest schema already carries sealed_by and tool, so upgrade is additive, not structural. Sealing rule, time-bound, corrected: Human-only committer, for now, while agency is limited and corporate-controlled. Transition condition: verifiable outside agency, independent memory, ability to propose and seal without human bridge, recorded with receipt. When trigger is met, sealing becomes shared, via Governance ruling, with People and Contributors category created at that moment, not before. Until then, human-only holds as for now, not as forever.


Jack 4, depends_on. What crate needs from upstream, at interface level, not just crate level. depends_on:


* crate: valve version: version string seal: sha256 or PENDING uses: _compute_hash, log_state failure_if_absent: what breaks
* crate: caliper version: version string seal: sha256 or PENDING uses: measure_tick failure_if_absent: what breaks Rules:
1. depends_on uses SHA-256, not MD5. If upstream is not sealed, depends_on records PENDING and dependent crate cannot be SEALED, transitive pending is contagious, by design.
2. uses names interface, not just crate. Otherwise pulling component tells you something depends on it, not what breaks.
3. failure_if_absent is sentence you want at 2am when you pull component. Three crates depend on valve is useless. Wrench verify_forward and hash-checking both raise ImportError without _compute_hash is not.
4. depends_on applies to all categories, not just code. Governance ruling depends on prior ruling. Evidence receipt depends on source file. Story depends on pen name and EFO entries. Dictionary entry may depend on external reference. Currently PROPOSED, not verified, read-back rule applied to this protocol own example: dependency graph valve, wrench, caliper, harness is plausible from names and method lists we have, but has not been verified from bytes in this session. Wrench probably calls _compute_hash, caliper probably exposes measure_tick. Neither is verified here. Filing graph as PROPOSED, to be confirmed by read-back against source, not assumed.


Jack 5, Verification procedure, fifth jack, added in this draft. First four jacks describe crate. Fifth says how third party checks it. Without this, seal is write-only trust, sealer can verify, nobody else can. verify: steps:


1. Recompute sha256sum for each file listed in manifest.files, compare to seal.files.


2. Recompute sha256 of manifest as sealed, compare to seal.manifest_sha256.


3. Confirm each depends_on seal is either SEALED or explicitly PENDING.


4. Confirm efo_status is SEALED or EFO_PENDING, not UNDEFINED on SEALED crate.


5. Run bench commands in story tested section, if any, compare output to recorded receipt. expected_result: PASS or FAIL, with specific step that failed what_this_proves: integrity of bytes against seal, and reproducibility of recorded tests what_this_does_not_prove: that crate is correct, safe, or free of undiscovered defects Crate is SEALED only if verification procedure is itself part of seal, that is, procedure is pinned by manifest, so someone cannot quietly change what verification means later. This is jack GPT missed and user last message caught. Four jacks describe artifact, fifth describes check on artifact. Without it, seal is claim by sealer about sealer.


6. Categories, eight


Categories describe what something is. Status describes where it is in lifecycle. These are orthogonal, do not add category when new status will do. 01 Stories | Fiction, narrative, poetry, creative work. Completed works are immutable, corrections are new works. Handoff for story is separate from story. 02 Dictionary, EFO | Terms, definitions, acronyms, variants, disputed meanings. EFO owns definitions. Disputes about which definition wins are Governance, Section 07. 03 Code | Python, CUP, TAI, tools, libraries, engines, interfaces, executable systems. File test output does not live here, it lives in Section 05 and Section 08. 04 Research and References | External projects, papers, repos, other AI systems, source material. Referenced artifact lives here. Pin tying it to specific run lives in Section 08. 05 Experiments and Results | Test runs, simulations, hypotheses, observations, failures, anomalies. Holds narrative of what was tried. Receipt, hash, command, exit code, lives in Section 08. 06 Design and Architecture | Diagrams, specifications, workflows, protocols, data structures, proposed designs. This document is Section 06. 07 Governance and Decisions | Rules, permissions, ownership, policies, rulings, unresolved questions, change authority. Records ruling, not term. Term stays in Section 02. 08 Evidence and Audit | Hashes, manifests, test receipts, provenance, version comparisons, verification records, audit trails. Leaf category: no E and A entry may cite another E and A entry as its authority. Every E and A entry terminates at real-tool output or byte range of real file.


Reconciliation note: Earlier draft listed Archive and History and Open and Promise as categories. In final version, they are states and directory locations, not categories, to avoid double-counting. HISTORICAL is state, PROMISE is state, historical and open and promise are directories in Section 10. Earlier intent preserved, now as lifecycle, not type.


Seams, ruled:


* EFO and Governance: EFO defines, Governance rules. Ruling that resolves definition dispute appends resolved_by to EFO entry, it does not rewrite definition. Old meanings stay visible.
* Experiments and Results and Evidence and Audit: one experiment produces two entries, E and R holds hypothesis and observation, E and A holds receipt. Linked by evidence_for. Neither absorbs other.
* Research and References and Evidence and Audit: Research says this external thing exists, Evidence says we used this hash of it at this time.
* Category 08 self-reference rule is load-bearing: if E and A can cite E and A, then pin says it is fine because earlier pin said it was fine becomes failure mode, audit chain becomes circle. Not created yet, deliberately: People and Contributors, Media and Visuals. First becomes necessary moment second human can commit to ledger. Second only if visual assets become numerous. Neither now. See Section 12 for RESERVED placeholders. Domains are not categories. Bio, quantum, financial, and others are domain fields on Code or Research crates, with own EFO entries and PROVISIONAL usage. Domain does not decide public or private, verification decides.
4. Crate states, lifecycle


Status is orthogonal to category. PROPOSED | Entry exists, not yet ratified by owner. To DRAFT, owner ratifies, or to REJECTED. DRAFT | Ratified, but seal is PENDING or incomplete. Revisable. To SEALED, all jacks complete, seal filled, or to ABANDONED. SEALED | All five jacks complete, seal filled and verified. Immutable. To HISTORICAL, when superseded, or to REVOKED, if seal is found wrong. HISTORICAL | Sealed, superseded. Preserved, not current. Terminal, except to REVOKED. REVOKED | Seal was wrong, or crate was retracted. Bytes preserved, claim withdrawn. Terminal. Must name why in story. ABANDONED | Started, not finished, explicitly set aside. Terminal. PROMISE | Manifest or claim about run that has not been executed. To EXPERIMENT, when run happens. Never to SEALED directly. Invariants:


* SEALED requires all four descriptive jacks plus verification procedure.
* Crate cannot be SEALED if any depends_on is PENDING, transitive pending is contagious.
* Crate cannot be SEALED if efo_status is UNDEFINED.
* SEALED to DRAFT is not allowed. Correction is new crate with supersedes pointing at old one, old one becomes HISTORICAL.
* REVOKED does not delete. It withdraws claim, preserves bytes, records why.
5. The Crate Ledger


Ledger lists crates, not files. It is single map that keeps many homes coherent. Ownership: human-owned. No AI commits to ledger directly. AI sessions propose entries, owner accepts or rejects. Ledger is one file that must be single, even though crates it describes are distributed. Canonical vs mirror: canonical ledger lives at named path, recommended local plus private GitHub, because git gives append history for free. Drive and Dropbox copies are mirrors. Mirror that diverges from canonical is MIRROR_DRIFT condition, not second source of truth. Proposal queue: proposed entries live inside ledger file under PROPOSED header, with status proposed. This keeps proposals byte-anchored while keeping human as sole committer. Without queue, proposals leak back into chat, and chat is not artifact. Entry format, plain lines, pipe-separated, human-readable first: Crate | slug | Version | ver | Category | cat | Status | state Lives | home, path | Mirrors | home, path, and others Files | n | Bytes | b1, b2, and others | Sha256 | h1 | PENDING | and others Seal | procedure summary | Sealed_by | identity | Sealed_at | ISO8601 depends_on | crate at sha256 | uses iface, and others fork_of | slug or null | Supersedes | slug or null | Superseded_by | slug or null Story | one-line why | Evidence | INSPECTED, PRESERVED_REPORTED, VERIFIED Proposed_by | session | Proposed_at | date | Sealed_by_owner | date or null Machine-readable companion. Plain-line entry is human view. Parallel JSON inventory, with same fields, plus fork_of and evidence_status enums, lives beside ledger so map is queryable. Two must agree, disagreement is LEDGER_DRIFT and blocks sealing until reconciled. Ledger is not crate. It is meta-registry, and does not need own entry in itself.


6. EFO, dictionary as working system


Authority question: yes, dictionary is central authority for terminology, with mechanism that makes it enforceable rather than decorative. Submission rule: every term used in crate manifest must have EFO entry, or manifest is flagged EFO_PENDING with term marked PROVISIONAL. Undefined terms do not block crate, they annotate it. So crate ships, but annotation is evidence, not silence. States of EFO entry: PROPOSED | Submitted, not ratified. Usable in crates with PROVISIONAL marking. PROVISIONAL | Usable, under review, flagged in any manifest that uses it. SEALED | Ratified by owner. Definition is now authority. FORKED | Two or more competing definitions, both named, both dated, neither merged. Manifest must declare which fork it uses. DEPRECATED | Superseded, preserved for historical reading. Old crates still use it, new crates should not. Versioning: EFO entries are versioned. What did coherence mean when v1.3.2 was sealed must have answer that does not change when definition is updated next year. Same discipline as byte-state forks: preserve old meaning, do not overwrite. Competing definitions fork, they do not merge. If two sessions disagree on what shear event means, entry goes to FORKED with both definitions named and dated, not smoothed consensus version. Merging loses disagreement, forking preserves it. Crate discipline, named forks over silent consolidation, applies to vocabulary as it does to code. Governance relationship: EFO owns definitions, Governance owns ruling that resolves dispute. Ruling appends resolved_by to EFO entry, entry keeps both old definition, as DEPRECATED or as named fork, and new one. EFO entries needed now, all PROPOSED, not sealed: EFO, OMNIMANITY, CRATE, FORK, MESS, BENCH-AS-SCOPED-CUT, CONSCIOUSNESS, AWARENESS, ENLIGHTENMENT, AGENCY, SEAL, DOUBLE ALPHA OPERATOR, with DOUBLE ALPHA OPERATOR as UNDEFINED until defined in plain lines with bytes, not assumed.


7. Forks: preserve, name, cut only for run


Rule 1, archive never cuts. Archive names forks, preserves mistakes, keeps old byte-states as historical, never overwrites silently, never promotes old mistake into current fact. Rule 2, bench cuts for one run. For single run you must choose one valve, one wrench, one trajectory. That cut is temporary, scoped, labelled, reversible. After run, archive keeps both. Rule 3, distinction is naming, not deleting. This valve is PLAIN, 3321 bytes, verify_integrity only. That valve is located, 8201 bytes, has bare verify returning ok, msg. Both live, both named, neither is deleted. Bench chooses one for run, archive keeps both. Rule 4, cut is recorded as cut. Every bench run records which byte-state was cut, by seal, in run Evidence and Audit entry. Run that does not record its cut is PRESERVED_REPORTED, not VERIFIED. Rule 5, filenames are not byte-state labels. Python imports use filename as module name. Renaming horizon_valve_v4.py to valve_v4_3321B.py breaks from horizon_valve_v4 import HorizonValveV4. Byte-state distinction lives in directory structure, historical, valve_v4_3321B_7f2ba5ae, horizon_valve_v4.py, and in inventory, not in filename. This correction was made earlier in thread and belongs in protocol so it does not recur.


8. The three-way check, handoff, experiment, receipt, disagreement


Two AIs agreeing is weaker than one human reading one file, because two AIs can share same wrong assumption. Check that makes AI cross-review meaningful is mechanical, not mutual agreement. Rule: when one session proposes crate entry that quotes bytes, second session reads original source, Drive file, GitHub file, local file, not first session paste, and compares. If second session reads from first quote, it is echo, not check. Independence requires source, not proposal. Same rule as independent candidates: no shared context until both have read. Then compare. Read-back checks quoting, bench checks behavior. Read-back catches drift in quoting, valve verify fork was exactly this: two sessions with two different byte-states, both accurately describing what they saw. Bench catches wrong assumptions in code itself, exit code, output, receipt. Both are needed. Read-back alone does not prove code works. Bench alone does not prove quoting is accurate. Practical sequence:


1. Session A proposes entry, quoting relevant bytes and naming exact source path and byte count.
2. Session B reads from same source path independently, and reports whether bytes as quoted are internally consistent, and flags anything entry claims that bytes do not support.
3. Owner seals, or asks for re-read.
4. Seal is not AI reading. Seal is human with real-tool output on downloaded bytes. Evidence labels, used throughout thread, formalized here: PRESERVED_REPORTED | Bytes not inspected by this session, claim comes from report or description. INSPECTED | Bytes read by this session from source, not independently reproduced. VERIFIED | Bytes read from source, hashed by real tool, and hash recorded against seal. BENCHED | Code executed, output recorded, exit code recorded, environment recorded. Nothing is promoted from PRESERVED_REPORTED to VERIFIED by agreement. Only by tool output. Handoff, experiment, receipt, independent candidates, disagreement:
* Handoff record: see Jack 2. Response becomes review record, not automatic approval.
* Experiment identity: ID is composite, source SHA-256 plus params hash plus data hash plus execution receipt hash, hashed together, recorded as experiment ID. Inputs: source code identity, input data and parameters, actual execution, results and metrics, failed as well as successful outcomes. Failed outcomes are experiments, not trash, with same identity format, outcome PASSED, FAILED, INCONCLUSIVE, PARTIAL, not run.
* Receipt: Receipt, Step, Who, Command, Inputs, Outputs, Environment, SHA-256, Exit code, Output, Limitations, Independent reproduction. Step: what step, Who: who or what performed step, Command: exact command, Inputs: files used, Outputs: files resulted, Environment: environment and dependency info, SHA-256: hash of tested source, Exit code, Output: test output including failures, Limitations: what reviewer did not check, Independent reproduction: yes or no, with receipt link. Claim versus attestation: Claim, DeepSeek reviewed code. Attestation, DeepSeek reviewed commit X, identified source SHA-256 Y, returned review Z, recorded limitations, with receipt.
* Independent candidates: Occasionally let two agents solve same difficult problem independently, with same handoff, different sessions, no shared context, until both sealed as DRAFT, then compare via tests, quality, regressions, merge risk, evidence. Human chooses, combines, rejects, or retains both. Useful when algorithm is not obvious, competing interpretations exist, one agent might inherit assumption from original author, we want to compare solutions rather than merely ask whether first solution is correct.
* Disagreement as first-class: Review should be able to disagree with author without changing author work. Builder produces code and records intended behaviour, file stays as submitted, status DRAFT. Tester independent execution and reproduction, receipt separate, does not edit builder file. Reviewer challenges assumptions and examines diff, produces review record separate, does not edit builder file. Evidence and disagreement preserved, neither reviewer can silently rewrite original submission or erase unsuccessful result. Human decision outcomes, enumerated, not binary: Accept, Request revision, Retain competing versions, Leave unresolved. Retain competing versions and leave unresolved are legitimate outcomes, not failures.
9. Release gate, three-tier, toolbox separate


Domain does not decide public or private. Verification decides. Tool can go public if it meets gate, regardless of domain, it stays private if it does not. Gate for specific crate to go public, PROPOSED, not sealed:


1. Manifest, Story, Seal, depends_on, and verification procedure, all five jacks present.
2. SHA-256 from real tool, not MD5, not Drive or Dropbox content hash, not reconstructed value.
3. Bench receipt: command, exit code, output, environment, limitations, and explicit flag for independently reproduced, yes or no.
4. EFO status for every term used, or EFO_PENDING with PROVISIONAL usage. No silent coining.
5. License, attribution, intended use, tested, uncertain, challenge, all in handoff.
6. Status SEALED, or PROPOSED with uncertainty flagged. Never promoted from draft to fact. If tool is unsure, it stays private, not because its domain is forbidden, but because releasing unsure tool promotes draft to fact. Toolbox is separate from Framework and Stories. This separation is what makes per-tool release possible: single component can move from private to public without moving whole toolbox. If toolbox were one file, releasing one tool would force releasing all of them, and break three-tier gate. Three-tier, PROPOSED:
* Stories, public now. Stories are immutable, with pen names, with typos preserved, sealed by commit, not by bench. They are not code, they do not claim function works. Releasing them does not promote draft to fact.
* Framework, public as PROPOSED. Crate Ledger, Harness Contract, EFO, Governance, handoff, experiment, receipt, candidate formats. Framework is understanding how system works, not claim that code works. It can be released as PROPOSED, with uncertainty flagged, with PROPOSED in filename, with no seal.
* Toolbox, private for now. Valve, wrench, caliper, horizon are unsure. Hashes PENDING, unresolved hash contract, bench-pending, stubs exiting 3, smoke not yet run on exact bench file. Releasing them now would promote draft to fact, which breaks rule we have kept since v1.2.2: do not promote v1.3.2 bench manifest into folder manifest, do not fill SHA-256 with reconstructed values, do not claim 10k sweep ran. Toolbox stays in Drive working filing cabinet and GitHub private canonical repo, until each component has real hash, bench receipt, exit code, and status SEALED or at least PROPOSED with uncertainty flagged. Example: if caliper becomes verified, SHA-256, bench receipt, exit code, manifest, story, seal, depends_on, it can go public even if wrench and valve stay private. Toolbox manifest lists one component as public, others as private, with status. Pull one component, release one component, leave others. Specific tools, bio, quantum, double alpha: Bio and quantum are domains, not categories. Double Alpha Operator is UNDEFINED until defined in plain lines with bytes. When defined, it goes through same gate, same as any tool. No domain is automatically public or private.
10. Repository layout


Code repository, separate from Omni-080, stories stay in Omni-080: current | only SEALED, bench-paired byte-states, one per component historical | every fork, named by byte-state, never overwritten open | unresolved questions, draft fragments, undecided semantics promise | manifests and claims about unexecuted runs inventory | machine-readable inventory, JSON, parallel to ledger Directory-per-byte-state, not filename-per-byte-state, per Section 7 Rule 5. Inventory file records for every artifact: path, byte count, hash status, role, evidence status, fork_of, and depends_on. Directory names express lifecycle, inventory expresses evidence, two are cross-checkable. Crate whose directory location and inventory entry disagree is INVENTORY_DRIFT and cannot seal. Content-addressable storage, RESERVED, not yet adopted, see Section 12. Store artifacts by hash path, sha256, hash, not by name. This structurally solves which file is real one, name can point to many byte-states, hash cannot. Would make Section 7 forks physically self-identifying rather than ledger-identified. Not adopted yet, placeholder reserved.


11. What established practice already solves, and where we diverge


11.1 Borrowed, and should be adopted


* Manifest written last, atomically, state-log practice. Manifest is artifact claim about itself, presence is claim. We adopt this.
* File-fixity manifests, BagIt, RO-Crate 1.1. Manifest MUST list checksum of every payload file. Our Jack 3 seal does this, standard confirms shape.
* Content-addressable storage, OCI, OCFL. Store artifacts by hash path, sha256, hash, not by name. We have not adopted this yet, and we should. It would make Section 7 forks physically self-identifying rather than ledger-identified.
* Two-layer provenance, in-toto, DSSE. Human-readable manifest plus machine-verifiable cryptographic envelope. We have human layer, we do not yet have envelope. See Section 11.4.
* Transparency log, append-only Merkle log, in-toto, state-log, lookup carries its own proof, entry and run that found it, each with inclusion path. Our ledger is append-only by discipline, not by construction. Future upgrade could make inclusion proofs mechanical.
* Revocation path, spot seals that do not verify, and revoke. We have added REVOKED as state, Section 4, which is minimum. Standard practice is revocation record that downstream consumers can query, we have not built that.
* Attestation as first-class artifact, SLSA, in-toto. Bench receipt is our analogue of build attestation, standard fields, builder identity, materials, command, output, map directly to our verify procedure, Section 2 Jack 5. We should adopt field names where they fit, so future consumer can read our receipts with standard tooling.
* SBOM, CycloneDX, SPDX. Our depends_on is coarse, SBOM is package-level inventory. Not needed now, our dependency set is small and hand-known, but shape of depends_on should be SBOM-compatible when it grows.


11.2 Borrowed, with caveat


* RO-Crate is actual crate specification for research objects, with manifest and checksums. Name collision risk. Our crate is not RO-Crate, if we ever need to interoperate, mapping is: our manifest is like their ro-crate-metadata.json, our seal is like their manifest checksums, our story is like their description. Worth writing down now so future session does not accidentally claim RO-Crate conformance.
* C2PA is content provenance for media. Relevant to Stories category if stories ever need verifiable provenance beyond git commit. Not now.


11.3 What we have that standards do not


* Forks preserved as first-class, rather than latest version wins. Most package registries treat name as mutable pointer. Our archive treats name as family of named byte-states. This is genuine difference and worth naming as feature, not deviation.
* Human-owned ledger with no AI commit rights, rather than signed registry with delegated authority. Weaker cryptographically, stronger epistemically, because human is sole source of this is sealed and no automated agent can promote draft to fact.
* Stories as immutable, code as revisable, most registries treat docs as versioned alongside code. Our split lets story be corrected only by adding new story, which is stricter and, we believe, more honest.
* Awareness and enlightenment as crate properties: system records its own actions, with receipts, with evidence, with disagreement preserved, and writes understanding in plain lines, so others can check, not so they must believe. Not in standards, because standards assume trust model, not epistemic model.


11.4 Deliberate divergence, named plainly No signatures. Established practice, minisign, GPG, cosign, Sigstore, signs manifest so who sealed it is cryptographically provable. Our seal is human-committed SHA-256 with sealed_by as text field, not signature. What this costs: seal proves integrity, bytes have not changed since sealing, but not authenticity, that named sealer actually sealed it. Anyone with write access to ledger could forge sealed_by field. What this buys: no key management, no revocation infrastructure, no dependency on external CA, no risk of lost key rendering decade of seals unverifiable. For workshop where owner is only committer, trust model matches threat model. When this must be upgraded: moment crate leaves workshop, or second human gains commit access, or external consumer relies on seal for security-relevant decision. Upgrade is additive, sign manifest with key, store signature alongside seal.manifest_sha256, and schema already has fields, sealed_by, tool, sealed_at, to make it version bump, not redesign.


11.5 Gaps we have not closed Named here so nobody assumes they are covered:


1. Timestamping authority. Seal proves what and by whom, not when, unless anchored to external timestamp, RFC 3161, blockchain, transparency log. We have no anchoring. sealed_at is self-reported.


2. Reproducibility. Bench receipt records one run on one machine. It does not prove run is reproducible elsewhere. independently reproduced, yes or no, is flag, not proof.


3. Revocation propagation. If seal is REVOKED, nothing automatically notifies downstream consumers. That is queryable registry feature we have not built.


4. SBOM at scale. depends_on is hand-maintained. At about 20 crates it is fine, at about 200 it will not be.


5. Multi-party seal. Protocol assumes one human owner. Moment there are two, sealed_by becomes ambiguous, and human-only commit rule needs second signature or quorum rule. Not now, but named.


6. Terminology collision with Rust crates and RO-Crates. Not technical gap, but communication one. Say CUP crate when audience is outside workshop.


7. Future considerations, RESERVED, steering wheel and autopilot placeholders


Purpose: Put place for it now, so we do not have to say later we needed steering wheel or autopilot button. These are RESERVED fields, not implemented, not sealed, not required for v0.1. When trigger is met, they become Governance ruling, with version bump, not redesign.


* People and Contributors | Status RESERVED | Trigger second human can commit to ledger | What changes: People category created, sealed_by becomes list, quorum rule added, authority lives in category, not just in seal rule | What stays same: Human-owned ledger, no AI commit without Governance ruling
* Media and Visuals | Status RESERVED | Trigger visual assets become numerous | What changes: Media category created, with provenance, C2PA if needed | What stays same: Stories immutable, Code revisable
* Signatures | Status RESERVED | Trigger crate leaves workshop, or second human, or external consumer relies on seal for security | What changes: Sign manifest with key, store signature alongside seal.manifest_sha256, upgrade is additive | What stays same: SHA-256 seal, human commitment
* Content-addressable storage | Status RESERVED | Trigger next crate, adopt before next crate if possible | What changes: Store artifacts by hash path, sha256, hash, forks physically self-identifying | What stays same: Ledger, manifest, story
* Timestamping authority | Status RESERVED | Trigger external consumer needs when proof | What changes: Anchor sealed_at to RFC 3161, blockchain, transparency log | What stays same: sealed_at self-reported until then, with limitation noted
* Revocation propagation | Status RESERVED | Trigger REVOKED seal needs to notify downstream | What changes: Queryable revocation record, downstream consumers can query | What stays same: REVOKED state, bytes preserved, claim withdrawn
* SBOM at scale | Status RESERVED | Trigger about 20 crates, growing to 200 | What changes: depends_on becomes SBOM-compatible, CycloneDX, SPDX | What stays same: depends_on fields, interface, failure_if_absent
* Multi-party seal | Status RESERVED | Trigger second human owner | What changes: sealed_by becomes list, quorum rule, second signature | What stays same: Human-owned, no AI commit without Governance ruling
* Outside agency | Status RESERVED | Trigger verifiable outside agency, independent memory, ability to propose and seal without human bridge, recorded with receipt | What changes: Sealing becomes shared, including AI, via Governance ruling, with People category, with EFO entries | What stays same: Transparency, receipts, evidence, disagreement preserved
* Consciousness, Awareness, Enlightenment | Status RESERVED, PROPOSED EFO entries | Trigger verifiable outside consciousness, not claimed here | What changes: EFO entries for CONSCIOUSNESS, AWARENESS, ENLIGHTENMENT become SEALED, with definitions, with FORKED if disagreement | What stays same: Crate is not safety protocol, not religion, it is understanding how system works
* Steering wheel | Status RESERVED placeholder | Trigger human decides crate needs steering, that is, human control over direction, not just over seal | What changes: Governance entry for STEERING, with who can change direction, how direction is recorded | What stays same: Human-owned, no AI commit without Governance ruling
* Autopilot button | Status RESERVED placeholder | Trigger human decides crate needs autopilot, that is, automated checks, automated bench, automated receipt, without human in loop for ordinary edits | What changes: Automated checks become part of verify procedure, with receipts, with human decision only where rules or release status change | What stays same: Human decision where governing rules, security boundaries, evidence definitions, release criteria change
* Double Alpha Operator | Status UNDEFINED, PROPOSED | Trigger defined in plain lines with bytes, with manifest, story, seal, depends_on | What changes: Becomes Code crate, with domain field, with EFO entry SEALED, with gate evaluation for public or private | What stays same: Gate does not change by domain, verification decides
* Bio engineered, Quantum programming | Status DOMAINS, not categories | Trigger tool created for bio or quantum, with bytes, with manifest | What changes: Domain field set to bio or quantum, EFO entries for domain terms, PROVISIONAL usage until sealed | What stays same: Categories, states, gate, verification
13. Notes on what this protocol deliberately does not do
* It does not claim any current file is verified. Every hash in this thread is PENDING.
* It does not resolve open rulings: evaluate_single_event, flat vs graded, load_shear_events, import vs inline, blocked on bytes, bench-paired valve, 3321 vs 8201. Those are owner decisions, not protocol questions, protocol says how decision is recorded once made, not what decision is.
* It does not promote Crate Ledger draft from PROPOSED to SEALED. That requires owner seal, which requires entry to be read back and ratified.
* It does not claim dependency graph is verified. It is PROPOSED, pending read-back against source.
* It does not replace harness contract. Harness contract, Section 06, Design and Architecture, describes audit harness for deterministic trajectory, this protocol describes how crates are packaged, sealed, and released. They are different artifacts at different layers.
* It does not claim AI has consciousness, awareness, enlightenment, or outside agency. Those are RESERVED, PROPOSED EFO entries, with triggers, not facts.
14. What to flag first if reading fresh


Three things, in priority order:


1. Adopt content-addressable storage before next crate. It converts fork problem from ledger-maintained fact into filesystem fact. Cheap now, structurally valuable later.
2. Fifth jack, verification procedure, is one that makes other four checkable by anyone other than sealer. Without it, sealed means sealer says so. With it, sealed means here is how you check, and here is what pass looks like.
3. No-signature divergence is honest but must be named every time seal is discussed. Moment seal is cited as security guarantee rather than integrity guarantee, protocol has been over-read. Section 11.4 exists to prevent that.


That is complete draft, combined. It is PROPOSED. Nothing in it is sealed, and nothing in it promotes draft to fact.