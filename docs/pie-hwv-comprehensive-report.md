# Report 2 — Comprehensive PIE/HWV Report: Requirements, Cross-Team Alignment, and Open Topics

## 1. Purpose and scope
This report consolidates the PIE ↔ HW leadership discussion (Slack thread, Eric Feng ↔ D. Casner, Oct 10–15) with PIE/HWV materials already in this repository. It is intended to:
- Capture PIE requirements and expectations toward PCE / HW leaders and cross-team leads.
- Record the current state of agreement and disagreement.
- Define follow-ups so the topics can move into official process (CP deliveries) rather than relying on individual engineer recognition.

Companion document: `docs/pie-hwv-key-discussion-points.md` (short discussion list).

## 2. Background
HW/EL leaders have been following Heartbeat Logic planning and driving project meetings. PIE engineers interact with these meetings weekly and depend on:
- Finding the latest meeting page/agenda reliably.
- Clear, official channels for PIE questions and HWV strategy inputs at CP reviews.
- Visibility into process changes (PDP checklist, CP review meetings) that affect cross-team deliveries.

Today, several PIE inputs reach projects only through engineer leads' initiative and per-project recognition, not as official process requirements. The thread with D. Casner is the first step toward formalizing this.

## 3. Topic analysis

### 3.1 Meeting page / Confluence strategy (open disagreement)
**PIE proposal (Eric):**
- Use a fixed Confluence URL that is always live/latest; archive by copying the page and renaming it "LAST Week Page".
- Precedent: all PIE Weekly and PIE-JDM meeting pages use fixed URLs.
- Benefits: one bookmark always works; engineers (and tooling) can rely on a stable URL "even without Claude".

**HW leader position (Daniel):**
- Disagrees with fixed-page + copy/rename archiving: error prone, and hard to trust whether content is current vs. leftover from the previous week.
- Prefers newest page per meeting in a fixed folder.
- Offers a compromise: a Confluence macro that links to the most recent page.
- Requested: specific examples of problems caused by the "most recent page in a fixed folder" approach.

**Assessment:** This is a tooling/UX disagreement with a viable middle ground. The macro-based "latest page" link preserves the single-bookmark benefit without the copy/rename risk. PIE should collect 2–3 concrete incidents (e.g., engineers joining with stale agenda, wrong page used for pre-reads) to either justify the fixed-URL model or accept the macro approach.

**Next steps:**
1. Eric: document concrete examples of discovery/staleness problems. 
2. Jointly evaluate the Confluence macro solution on one meeting series as a pilot.
3. Decide and document the standard in the meeting operating notes.

### 3.2 Regular PIE ↔ HW leader sync (agreed)
- Daniel agreed a regular sync on HWV/PD topics is valuable and will discuss handling with Alexa.
- Eric will prepare a meeting Confluence page covering the topics in this report.
- Open: cadence (monthly vs bi-monthly), participants, and standing agenda.

**Recommended standing agenda:**
1. HWV strategy coverage status (NUDD list, worst-case usage model).
2. PIE open questions needing HW leader / PCT support.
3. Process changes affecting PIE (PDP checklist, CP reviews, workflow optimizations).
4. Roadmap topics raised by either side.

### 3.3 PIE expectations: HWV Strategy inputs as official CP deliveries (highest priority)
PIE requires a valid and comprehensive HWV Strategy. Two deliveries should become **official requirements on the CP review agenda**:

**Delivery A — Unified NUDD list from PCE**
- Purpose: assure HWV Strategy coverage; surface risks; identify whether a NEW PFS is needed.
- Open questions: Who in PCE owns unification? What format and cadence? How is coverage traced back into the HWV strategy?
- Repository support: `NUDD/General/templates/nudd-finding-record-template.md` provides a ready structure (observation / risk / evidence E0–E5 / priority P0–P3 / closure path) suitable for standardizing the unified list across projects (`NUDD/Bear`, `Jaws`, `Maestro`, `Maverick`, `Olympia`, `PCH`, `PIE`, `Stage`).

**Delivery B — In-scope worst-case usage model**
- Purpose: determine if a NEW PFS is needed or current PFS limits require adjustment; drive pass/fail criteria definitions.
- Status: PIE & UX proposal aligned with UX leader Byran, started from gaps; targeting official adoption.
- Open questions: approval path to make it a CP deliverable; who signs off pass/fail criteria; how PFS limit adjustments are governed.

**Gap:** Both deliveries currently depend on engineer leads and per-project recognition rather than official process. The ask to HW leadership/PCT is to anchor them in the official process and CP deliveries.

### 3.4 Process/workflow visibility
PIE needs confirmation on which processes are being optimized and which remain authoritative:
- **PDP checklist** — is it still in use to drive cross-team deliveries? If deprecated, what replaces it?
- **CP Review meetings** — current expectations, required PIE artifacts, and how the two deliveries above fit the agenda.
- Any other workflow changes PIE should attend to and follow up on.

### 3.5 Existing PIE efforts (leverage points)
PIE has already built mechanisms that the formalized process can reuse:
| Mechanism | Function |
| --- | --- |
| HWV Strategy + Overall PIE Questions List | Central register of open HWV questions |
| G-PIE Meeting | Routes CN PIE lead urgent questions to US PIE for PD meeting discussion |
| PIE Weekly Report | Documents weekly critical questions |
| CP PIE Deck Template | Standard CP content: PIE deliveries, readiness, expectations, impacts |

These map naturally onto the PIE Soundstage dashboard structure already specified in this repository (`PFS/pie-soundstage-dashboard-spec.md`, `docs/pie-soundstage-dashboard-delivery.md`): KPI strip (readiness), risk register (NUDD/PFS risks), decision log (CP decisions), dependency tracker (x-team deliveries).

## 4. Risks if not addressed
- **Coverage risk:** Without a unified NUDD list as a CP requirement, HWV strategy coverage depends on individual initiative; NUDD findings may not translate into PFS/validation scope.
- **Criteria risk:** Without an official worst-case usage model, pass/fail criteria and PFS limits may be set inconsistently across projects.
- **Discovery risk:** Engineers using stale or wrong meeting pages lose preparation time and act on outdated agendas.
- **Escalation risk:** PIE open questions without an official channel surface late in PD meetings instead of being pre-staged.

## 5. Consolidated action list
| # | Action | Owner | Depends on |
| --- | --- | --- | --- |
| 1 | Set up regular PIE↔HW leader 1:1 (cadence TBD) | Daniel (with Alexa) + Eric | — |
| 2 | Build meeting Confluence page with these topics | Eric | — |
| 3 | Provide concrete examples of "latest page" discovery problems | Eric | — |
| 4 | Evaluate Confluence macro for latest-page link | Daniel / Confluence admin | 3 |
| 5 | Confirm PDP checklist status and active process changes | HW leader / PCT | — |
| 6 | Propose Unified NUDD list (from PCE) as official CP deliverable | PIE + PCE + PCT | — |
| 7 | Propose in-scope worst-case usage model as official CP deliverable | PIE + UX (Byran) + PCT | — |
| 8 | Define pass/fail criteria and PFS limit adjustment governance | PIE + HWV | 7 |
| 9 | Collect roadmap/process topics from Daniel for future agendas | Daniel | 1 |

## 6. References
- Slack thread: Eric Feng ↔ D. Casner, Oct 10 and Oct 15 (source of sections 2–3).
- `docs/pie-hwv-key-discussion-points.md` — key points list (Report 1).
- `NUDD/PIE/README.md` — PIE exploration notes.
- `NUDD/General/templates/nudd-finding-record-template.md` — NUDD finding record standard.
- `PFS/pie-soundstage-dashboard-spec.md`, `docs/pie-soundstage-dashboard-delivery.md` — PIE dashboard specification for tracking readiness, risks, and decisions.
