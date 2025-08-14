# FreeXR Project Manifesto

*Version 1.0 — August 2025*

## Preamble

Extended Reality (XR) will shape how people learn, work, and play. Today, however, large portions of the XR ecosystem are constrained by closed platforms, limited repairability, and uneven security practices. FreeXR is a community‑driven initiative committed to advancing an open, secure, and repairable XR landscape that benefits end‑users, developers, researchers, and manufacturers alike.

We pursue this mission through collaborative engineering, responsible security research, and constructive dialogue with platform vendors. Our approach is practical, technical, and lawful. We prioritize clarity, evidence, and reproducibility over rhetoric.

---

## Glossary

* **Eureka** — Internal codename commonly used for Meta Quest 3.
* **Panther** — Internal codename commonly used for Meta Quest 3S.
* **XR** — *Extended Reality*: an umbrella term for Virtual Reality (VR) and Mixed/Altered Reality (MR/AR).
* **SoC** — *System‑on‑Chip*: the primary integrated processor in a device responsible for compute, graphics, and specialized accelerators.
* **QFPROM** — *Qualcomm Fuse Programmable Read‑Only Memory*: on‑chip fuses used for secure‑boot configuration (e.g., public keys, eFuse states).
* **Secure Boot / BootROM** — Hardware‑enforced boot chain validating signed firmware images from immutable ROM through subsequent stages.

---

## Mission

Enable an open and sustainable XR ecosystem by:

1. Supporting alternative operating systems and open tooling where lawful and safe.
2. Improving repairability through documentation, open part models, and community manufacturing.
3. Elevating platform security via responsible disclosure and open standards for game security.
4. Fostering a healthy modding culture that clearly opposes cheating and abuse.
5. Building transparent governance where both the community and financial contributors have defined roles.

---

## Principles

* **Openness with Accountability** — Favor open specifications, interfaces, and code; pair openness with clear responsibilities and auditable processes.
* **Right to Repair** — Users should be able to maintain, repair, and extend their devices without undue barriers.
* **Security by Design** — Assume adversarial clients; prefer server‑side validation; follow coordinated vulnerability disclosure.
* **User Safety & Fair Play** — Oppose cheating, fraud, and privacy harms; prefer technical and cultural measures that protect all participants.
* **Legal and Ethical Conduct** — Act within applicable laws and licenses (including FOSS licenses); avoid publishing harmful exploit details that needlessly increase risk.
* **Transparency & Merit** — Decisions are documented; technical merit and community consensus guide priorities.

---

## Program Areas

### 1) Open Ecosystem Access

**Goal:** Reduce lock‑in and enable legitimate research, development, and alternative OS use cases.

**Actions:**

* Advocate for vendor‑supported bootloader unlocking paths that preserve device security (e.g., revocable unlock tokens, clear warranty terms).
* Provide developer documentation for building and testing open components where lawful (kernel, drivers, userspace).
* Offer objective guidance on distribution models that avoid anti‑competitive gatekeeping while respecting safety and content standards.

### 2) Hardware Modding & Repair

**Goal:** Make XR hardware maintainable, modifiable, and safer to service.

**Actions:**

* Publish accurate 3D scans and CAD for non‑infringing parts; provide open licenses compatible with community manufacturing.
* Document materials, tolerances, and assembly notes for injection molding and 3D printing.
* Create repair guides with annotated screw maps, torque/ESD guidance, and part identifiers.
* Maintain a repository of compatible third‑party components and verified substitutions.

### 3) Managing Anti‑Repair Design Patterns (Case Study: “Eureka”/Meta Quest 3)

We document hardware pain points and publish mitigations where lawful. Examples reported by community researchers include:

* **Camera Flex Cable Routing:** Sharp bends behind the face shield may increase work‑hardening risk during repeated disassemblies.
  **Planned Mitigation:** Reverse‑engineer the flex PCB in KiCad and publish alternative routings/strain‑relief guidance.

* **Non‑Ferromagnetic Display Screws:** Certain deep‑set screws are difficult to handle with magnetic drivers.
  **Planned Mitigation:** Specify compatible ferromagnetic screw alternatives and sourcing; provide driver tips and jigs.

* **Thermal Duct Gasket Adhesion:** Weak adhesive can reduce seal integrity after service, potentially degrading airflow and SoC cooling.
  **Planned Mitigation:** Provide a 3D‑printable gasket or replacement duct with better fastening guidance (e.g., TPU/shore rating, adhesive spec).

* **Face‑Guard Clip Stress Point:** Thin plastic near strong clips is prone to early damage (\[video reference]).
  **Planned Mitigation:** Publish a reinforcement insert and service technique to avoid overstressing the clip.

* **Screw Proliferation:** More than 40 screws of varying lengths complicate reassembly.
  **Planned Mitigation:** Color‑coded maps, depth gauges, printable trays, and a comprehensive repair manual (including video walkthroughs).

* **Limited Spare Parts Availability:** Users often cannot obtain spares without purchasing donor headsets.
  **Planned Mitigation:** 3D‑scan non‑infringing plastic parts and publish manufacturable models; identify functional substitutes for commodity components.

* **Lens Durability & Vision Accommodation:** Resin lenses may scratch when used with eyeglasses; optical accommodation options are limited.
  **Planned Mitigation:** Publish a careful, low‑risk lens resurfacing procedure (e.g., micro‑mesh + water), with strong cautions regarding anti‑reflective coatings; encourage prescription inserts and lens‑protector designs.

> **Note:** All design data and guides are provided for educational and repair purposes. Users perform modifications at their own risk; warranties and safety certifications may be affected.

### 4) Platform Lock‑Down & Licensing Concerns

Community members have raised concerns that secure‑boot configurations (e.g., QFPROM/eFuses) on certain XR devices may prevent users from installing modified kernels or systems derived from GPL‑licensed components. Where relevant, this may raise questions of license compliance (e.g., completeness of “scripts used to control compilation and installation”).

**Our Position:**

* We seek clarity and lawful avenues for development. We prefer vendor‑supported unlock procedures that maintain a secure supply chain while enabling research and alternative OS builds.
* We document alleged compliance gaps objectively and refer matters to rights‑holders and competent legal counsel. We refrain from conclusory legal claims in public materials.
* We will continue good‑faith attempts to engage vendors. If engagement fails, we escalate through standard legal and policy channels.

### 5) Support for the Modding Community

**Goal:** Encourage creative, lawful modding; discourage cheating and malicious use.

**Actions:**

* Collaboration with communities such as **Byteus** under a published Code of Conduct.
* Clear non‑cheating policy: FreeXR does not support tools or guides intended to confer unfair in‑game advantages.
* Education on safe modding practices, digital ethics, and privacy.

### 6) Game Security Standard & Developer Support

**Goal:** Reduce the burden on game developers by defining open, practical security baselines for XR titles.

**Actions:**

* Publish a **Game Security Baseline** emphasizing server‑side authority, rate‑limiting, sanity checks, authoritative physics, and telemetry for anomaly detection.
* Document limitations of client attestation on compromised devices; recommend layered defenses and server‑side validation first.
* Coordinate a community bug‑reporting workflow and optional bounty aggregation; offer voluntary code reviews upon request.

**Response to a Common Concern (Developer Feedback):**

> “If bootloaders are unlockable, users could install a custom OS and cheat by changing variables in real time.”

* FreeXR opposes cheating. Unlockability is not a prerequisite for cheating; client compromise (including via public CVEs) has existed since launch on many platforms.
* Security should assume hostile clients. Robust protection comes from server‑side authority, protocol design, and anomaly detection—not from assuming the client is pristine.
* By improving openness and license compliance, we aim to reduce undisclosed, high‑risk privilege‑escalation paths and move toward auditable, hardened stacks.
* We actively cooperate with developers to audit and patch games; contact us for coordinated support.

---

## Governance & Decision‑Making

* **Community First, Structured Input:** Anyone can participate in discussion and RFCs. Sponsors and paying partners may have defined responsibilities (e.g., infrastructure funding, targeted workstreams) but do not control outcomes unilaterally.
* **Maintainership Model:** Technical leads steward specific repositories; decisions are documented with rationale and dissenting views where applicable.
* **Conflict of Interest (COI):** Contributors disclose affiliations; maintainers recuse when necessary.
* **Voting & Consensus:** We prefer rough consensus; for tie‑breakers we use documented votes with clear quorum rules.

### Operational Security (OpSec) Lessons Learned

We have experienced incidents involving premature public disclosures. Corrective actions include:

* Mentorship on OpSec for contributors who inadvertently revealed sensitive information.
* A written embargo policy and review checklist before any public communications.
* Limited‑access handling of active vulnerabilities; post‑mortems for leaks with documented remediation.

### Coordination with Adjacent Communities

Differences in disclosure philosophy led to a split with **BreakXR**. FreeXR prioritizes coordinated disclosure and risk management for active vulnerabilities. For issues already derived from public CVEs and after reasonable developer notice, we generally do not oppose re‑implementations. For novel privilege‑escalation paths, FreeXR follows a vendor‑first disclosure ethic.

---

## Responsible Vulnerability Disclosure Policy

1. **Intake & Triage:** Classify severity and affected versions; avoid sharing weaponized proofs publicly.
2. **Vendor Coordination:** Notify relevant vendors/maintainers; propose remediation and timelines.
3. **Embargo:** Maintain reasonable, finite embargoes to allow patches; extend only with concrete progress.
4. **Public Advisory:** Publish technical details sufficient for defenders after patch availability or after reasonable time if unresolved.
5. **Credit & Reproduction:** Credit reporters and provide reproducibility guidance for defenders.
6. **User Guidance:** Offer mitigations, downgrade/upgrade notes, and detection tips.

*Illustrative examples historically discussed in the community include Android kernel and zygote‑related CVEs and vendor advisories. Our policy is to prioritize upstream reporting to Linux and AOSP where applicable and to avoid avoidable harm to users and developers.*

---

## Near‑Term Roadmap

* Publish v1 repair guide and screw‑map for Eureka, with video walkthrough.
* Release initial CAD pack: gasket replacement, clip reinforcement, screw tray, and lens‑protector designs.
* Draft Game Security Baseline v0.9 and solicit feedback from studios.
* Open an RFC on a vendor‑friendly bootloader unlock blueprint (token‑based, wipe‑on‑unlock, attestation‑aware).
* Establish a public COI registry and voting policy; run the first governance vote.
* Begin legal and policy engag

## Responsible Vulnerability Disclosure Policy

FreeXR practices **defender‑first, coordinated vulnerability disclosure (CVD)**. Our objective is to reduce real‑world risk while advancing openness and license compliance. We avoid publishing details that would meaningfully increase harm before mitigations are available.

### Scope & Goals

* **Scope:** XR headsets and accessories; XR runtimes, kernels, drivers, boot chains; XR applications and network services; build/CI pipelines that produce XR software.
* **Goals:** (1) Timely fixes and mitigations, (2) accurate, reproducible advisories for defenders, (3) minimal collateral risk, (4) upstream hardening and education.

### What We Accept

* Memory‑safety, logic, and cryptographic flaws; secure‑boot/chain‑of‑trust issues; permission/attestation bypasses; sandbox escapes; privacy leaks; supply‑chain and update‑integrity issues; server‑side vulnerabilities impacting XR experiences.

### Out of Scope (examples)

* Social‑engineering without technical vulnerability; denial‑of‑service via unrealistic traffic; vulnerabilities requiring physical access and destructive disassembly unless they break stated security boundaries; issues in unsupported, end‑of‑life software unless widely deployed.

### How to Report

* Email: **[security@freexr.org](mailto:security@freexr.org)** (PGP preferred).
* PGP key: **FINGERPRINT‑HERE** (ASCII‑armored key and `security.txt` will be published in the main repository).
* Include: affected product/firmware, minimal reproducible steps, impact, logs/tracebacks, your contact and preferred credit, and whether the issue appears to be actively exploited.

### Intake & Triage

* **Acknowledgment:** within **3 business days**.
* **Initial severity & scope:** within **7 business days** using CVSS as guidance (we also publish a plain‑language impact summary).
* We assign an internal tracking ID and, where applicable, request a CVE via the relevant CNA (vendor, Linux, Android) or MITRE.

### Severity Levels (guidance)

* **Critical:** Unauthenticated remote code execution; secure‑boot bypass that permits arbitrary firmware; key‑material compromise; cross‑tenant breach.
* **High:** Privilege escalation to persistent root; sandbox escape with sensitive data access; server‑side auth bypass.
* **Medium:** Information disclosure with limited exploitability; spoofing that requires prior access.
* **Low:** Best‑practice deviations with minimal practical impact.

### Coordination & Timelines

* **Standard deadline:** public advisory **within 90 days** of vendor notification.
* **Critical actively exploited:** **7–30 days** with interim mitigations strongly encouraged.
* **Fix‑progress extensions:** possible in **15–30 day** increments if the vendor demonstrates concrete progress and commits to dates.
* **No response:** if a vendor is unresponsive for **21 days**, we may notify users and the wider community with a limited‑detail warning to enable defensive measures.

### Embargo & Exceptions

* Embargoed technical details are shared only with maintainers and directly affected parties under need‑to‑know.
* We may shorten embargoes if widespread harm is ongoing, or lengthen briefly if a coordinated, imminent patch is verifiably scheduled.

### Public Advisory Content

* Affected versions, impact, prerequisites, and practical mitigations.
* Sufficient technical detail for defenders (config deltas, detection heuristics, patch commit IDs) **without** releasing weaponized exploits or turnkey scripts.
* Clear credit to reporters, vendors, and reviewers.

### Proof‑of‑Concept (PoC) Policy

* **Private PoCs** may be shared with maintainers/vendors for validation.
* **Public PoCs**: only after patches are widely available and **only** in a **non‑weaponized** form (e.g., redacted stack traces, pseudocode, unit tests, or differential fuzz harnesses).
* We do **not** publish working exploit chains that meaningfully lower the bar for abuse.

### Credit, Recognition, and Bounties

* We offer public credit (opt‑in), signed acknowledgments, and maintainer references.
* Monetary bounties: not guaranteed; we may pool community funds or vendor‑sponsored rewards on a case‑by‑case basis.
* Duplicate reports receive shared credit; earlier, clearer reports are prioritized.

### Safe Harbor (Good‑Faith Research)

* If you follow this policy, test on devices you own or have permission to test, avoid privacy violations/service disruption, and promptly report findings, **FreeXR will not initiate or support legal action** against you. We will advocate for constructive resolution with vendors. This is not legal advice; local laws apply.

### Data Handling & Retention

* Reports are stored encrypted; access is role‑limited.
* Sensitive artifacts (keys, dumps) are redacted or replaced with synthetic data whenever feasible.
* We target **180‑day** retention post‑resolution, then purge or archive with de‑identification for research statistics.

### Multi‑Party Coordination

* When issues affect upstream (Linux kernel, AOSP) or shared components (SoC vendors), we coordinate with relevant maintainers and CNAs.
* For game‑specific server issues, we contact the publisher and—if necessary—platform security teams to mitigate cross‑title impact.

### Emergency Advisory Flow (Defender‑First)

1. Verify impact and exploitation signals.
2. Publish **interim guidance** (IOCs, config flags, feature gates) without enabling reproduction.
3. Notify trusted defenders and hosting providers if abuse is observed.
4. Publish full advisory once a patch/mitigation is broadly available or after a reasonable window.

### Researcher Code of Conduct

* Obtain consent, minimize data access, respect privacy, avoid lateral movement, and immediately cease testing if instability or user harm is detected.

### Vendor Expectations

* Acknowledge within **7 days**, provide a remediation plan within **21 days**, and deliver patches or mitigations within the agreed window. Credit reporters and share timelines we can relay to users.

### Contact & Keys

* **[security@freexr.org](mailto:security@freexr.org)**
* **PGP:** FINGERPRINT‑HERE (key and `/.well‑known/security.txt` to be published)
* **Preferred channels:** email + Matrix/Signal (on request) for coordinated chats during triage.

### Initial Report Template (Suggested)

```
Title: <concise name>
Affected Product/Version:
Environment: <model, firmware, build>
Impact: <CIA/privilege level>
Prerequisites: <auth/physical access/etc>
Reproduction Steps: <minimal, numbered>
Observed Behavior: <logs, traces>
Expected Behavior:
Workarounds/Mitigations (if any):
Reporter: <name/handle, credit preference>
Active Exploitation Evidence: <yes/no/unknown>
```

### Revision History

* **v1.0 (Aug 2025):** Initial publication of the CVD policy.

---

## Near‑Term Roadmap

* Stand up `security.txt`, publish PGP key, and open a triage mailbox with auto‑acknowledgment.
* Publish **Game Security Baseline v0.9**, including server‑authority patterns, rate‑limit recipes, and cheat‑resilience checklists.
* Release **Eureka Repair Guide v1** with screw map, ESD notes, and video.
* Ship **CAD Pack v1**: thermal‑gasket, clip reinforcement, screw tray, lens protector.
* RFC: **Bootloader Unlock Blueprint** (token‑based, wipe‑on‑unlock, attestation‑aware) for vendor feedback.
* Establish COI registry and voting policy; run inaugural governance vote.

## Participation

* **Developers:** drivers, tooling, repair docs, security hardening.
* **Researchers:** reproduce issues, analyze mitigations, contribute to advisories.
* **Studios/Manufacturers:** request reviews, coordinate fixes, and pilot the security baseline.
* **Users:** test guides on personal devices at your own risk; report issues and improvements.

## Acknowledgments

We thank contributors across the XR ecosystem for responsible reporting, careful reviews, and sustained collaboration. Our aim is an XR landscape where **openness, repairability, and security** reinforce one another—not compete.

## License for This Document

© 2025 FreeXR contributors. You may reuse with attribution under **CC BY‑SA 4.0** unless noted otherwise.

