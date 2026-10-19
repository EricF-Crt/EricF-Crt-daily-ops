# Report 1 — PIE/HWV Important Topics & Key Points for Discussion

Source: Slack thread between Eric Feng (PIE) and D. Casner (HW leader), Oct 10–15, plus repository PIE/HWV materials (`NUDD/PIE/`, `PFS/`, `NUDD/General/`).

Finalized meeting plan and action tracker: `docs/pie-hwv-future-meeting-plan.md`.

Status legend: 🔴 needs decision · 🟡 in progress / partially aligned · 🟢 agreed, pending execution

## 1. Confluence page & meeting management (🔴 — open disagreement)
- **Key point:** Resolving the disagreement on document versioning for Project/Heartbeat meetings.
- **PIE position (Eric):** Fixed, overwritten Confluence URL — always live and latest — for ease of bookmarking, with a renamed "LAST Week" copy as the historical record (precedent: all PIE Weekly and PIE-JDM meeting pages are fixed URLs). A stable URL can also be leveraged by tooling, even without Claude.
- **HW position (Daniel):** Copy/rename archiving is error prone and makes it hard to trust whether content is current vs. leftover from the previous week; prefers chronological folders with a Confluence Macro that auto-surfaces the latest page.
- **To discuss / actions:** Eric to supply specific examples of problems caused by "take the most recent page from a fixed folder"; jointly pilot the Macro approach on one meeting series before standardizing.

## 2. Process & workflow optimization (🟡)
- **Key point:** Assessing active processes to ensure PIE alignment with current workflows.
- **Specifics:**
  - **PDP checklist** — confirm whether it is still the standard mechanism for driving cross-team deliveries; if deprecated, identify the replacement.
  - **CP Review meetings** — clarify structure, expectations, and where PIE artifacts fit on the agenda.
- **To discuss:** Obtain an authoritative list of processes under optimization that PIE must attend to and follow up on.

## 3. Official CP Review deliverables — HWV Strategy (🔴 — top PIE expectation)
- **Key point:** Integrate PIE expectations into the official CP review agenda to ensure a valid and comprehensive HWV Strategy. Two mandatory deliveries are required (today they rely on individual engineer leads and per-project recognition):
  1. **Unified NUDD list** — provided by PCE to ensure HWV strategy coverage, identify risks, and determine if NEW PFS (Product Functional Specifications) are needed.
  2. **In-scope worst-case usage models** — define in-scope usage limits to verify whether NEW PFS are needed or current PFS limits require adjustment, and to establish clear pass/fail criteria definitions.
- **To discuss:** Path and owner (HW leader / PCT side) to anchor both deliveries in the official process and CP deliveries.

## 4. Cross-functional alignment — UX & PCE (🟡)
- **Key point:** Transition the drafted pass/fail criteria proposal — currently aligned with UX leader Bryan, started from identified gaps — into an official process to close operational gaps.
- **To discuss:** Approval path, sign-off owners, and governance for PFS limit adjustments.

## 5. Help needed from HW leader / PCT (🔴)
- **Key point:** PIE has open questions on process and cross-team deliveries that need HW leader / PCT support to resolve.
- **To discuss:** Review the PIE Open Questions List and assign owners and dates.

## 6. Leadership sync cadence & agenda (🟢)
- **Key point:** Formalize the newly agreed regular NPI/HWV sync between Eric, Daniel, and Alexa (monthly or bi-monthly, cadence TBD).
- **To discuss:** Standing agenda, meeting page ownership, and soliciting ongoing roadmap or process topics from HW Leaders for future sessions.

## 7. Monthly per-project urgent issues for PCE / HW lead (🔴 — standing agenda item)
- **Key point:** Each month, collect from every project the most important and most urgent issues that require PCE or HW lead resolution, and bring them to the leadership sync / CP review as a standing agenda item.
- **Current month (October) register:** see Report 2 §6.1 for the per-project table (Bear, Jaws, Maestro, Maverick, Olympia, PCH, Stage). Project folders in `NUDD/` are the collection source; entries pending input from project PIE leads.
- **To discuss:** Confirm collection cadence (by PIE Weekly Report roll-up), escalation SLA, and who on PCE / HW lead side owns disposition of each item.

## 8. Monthly per-project feedback-into cases (🟡 — standing agenda item)
- **Key point:** Each month, collect per-project "feedback into" cases — findings fed back into design, PFS, NUDD list, process, or checklists — to demonstrate PIE value and close the learning loop.
- **Current month (October) register:** see Report 2 §6.2 for the per-project table; entries pending input from project PIE leads.
- **To discuss:** Standard case format (finding → feedback target → change made → evidence), and whether accepted cases should feed the Unified NUDD list and CP PIE Deck automatically.

## 9. Existing PIE mechanisms to leverage (🟢 — for awareness)
- HWV Strategy with Overall PIE Questions List.
- G-PIE Meeting: CN PIE lead urgent questions escalated to US PIE for PD meeting discussion.
- PIE Weekly Report documenting weekly critical questions.
- CP PIE Deck Template defining PIE deliverables, readiness, expectations, and impacts.

## Repository cross-references
- `NUDD/PIE/README.md` — PIE exploration notes; reconcile with Soundstage source when accessible.
- `PFS/pie-soundstage-dashboard-spec.md` — candidate vehicle for tracking PIE readiness/risks/decisions (topics 3, 5, 7, 8, 9).
- `NUDD/General/templates/nudd-finding-record-template.md` — ready template to standardize the unified NUDD list (topic 3.1) and feedback-into case records (topic 8).
- `NUDD/<Project>/` folders (Bear, Jaws, Maestro, Maverick, Olympia, PCH, Stage) — collection source for monthly urgent issues and feedback-into cases (topics 7, 8).
