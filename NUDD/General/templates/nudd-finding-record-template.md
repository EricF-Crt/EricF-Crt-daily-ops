# NUDD Finding Record Template

Use this template for every meaningful NUDD finding that could drive engineering investigation, validation effort, design change, or cross-functional support.

## Writing principles
- Separate **observation**, **risk hypothesis**, **evidence**, and **action**.
- Use measurable conditions and variables whenever possible.
- Avoid vague wording such as "should be okay", "normal", "acceptable", or "needs attention" without criteria.
- Every finding must have an owner, status, and closure path.
- If the finding does **not** justify action yet, explicitly document why.

## Evidence quality scale
- **E0** — intuition / expert concern only
- **E1** — prior-generation learning or analogous field issue
- **E2** — simulation / theoretical analysis / first-principles reasoning
- **E3** — bench measurement on early sample or limited setup
- **E4** — repeatable controlled test result
- **E5** — statistically significant validation across builds / lots / conditions

## Priority guide
- **P0** — launch blocker, safety, regulatory, or catastrophic field risk
- **P1** — major user experience, reliability, or architectural risk requiring immediate action
- **P2** — important but manageable risk requiring planned investigation or mitigation
- **P3** — monitor / document / no immediate action

## Status workflow
- **Draft** → initial capture
- **Reviewed** → technically reviewed by owner / peers
- **Accepted** → approved for action or monitoring
- **In Execution** → validation / mitigation in progress
- **Verified** → evidence shows exit criteria met
- **Closed** → formally closed with residual risk documented

---

## Template

### NUDD Finding ID
- **Finding ID:** `NUDD-<Domain>-<NNN>`
- **Title:**
- **Type:** `Risk | Confirmed Issue | Action Item`
- **Category:**
- **Priority:** `P0 | P1 | P2 | P3`
- **Status:** `Draft | Reviewed | Accepted | In Execution | Verified | Closed`

### 1. Strategic traceability
- **Threatened KEI(s):**
- **Related usage scenario(s):**
- **Linked requirement(s):**
- **Linked selling point / product promise:**

### 2. Scope and ownership
- **Affected module(s):**
- **Primary owner (DRI):**
- **Supporting teams / reviewers:**
- **Date opened:**
- **Target decision date:**
- **Target closure date:**

### 3. Observation
- **Observed symptom / concern:**
- **When / where it appears:**
- **Trigger condition(s):**
- **Boundary conditions / assumptions:**

### 4. Risk statement
- **Risk statement:**
  - In the condition(s) above, the design may fail to meet the intended requirement or user experience because:
- **Customer / business impact if true:**
- **Why this matters now:**

### 5. Physics-of-failure hypothesis
- **PoF chain:**
  - `[Victim] + [Stress / Killer] -> [Mechanism / Weapon] -> [Failure site / Symptom]`
- **Suspected root physical mechanism(s):**
- **Why this mechanism is credible:**

### 6. Evidence and confidence
- **Current evidence level:** `E0 | E1 | E2 | E3 | E4 | E5`
- **Evidence summary:**
- **Known data points:**
- **Unknowns / assumptions / blind spots:**
- **Confidence level:** `Low | Medium | High`

### 7. Priority basis
- **Severity rationale:**
- **Likelihood rationale:**
- **Detectability / escape risk:**
- **Reversibility if found late:**
- **Cost of being wrong if ignored:**
- **Cost of false alarm / over-investigation:**

### 8. Required action
- **Immediate next action:**
- **Action owner:**
- **Due date:**
- **Expected output:**
- **Escalation trigger(s):**

### 9. Verification and closure
- **Verification approach:**
- **Test method / analysis method:**
- **Sample size / coverage expectation:**
- **Exit criteria (measurable):**
- **Required evidence level for closure:** `E3 | E4 | E5`
- **Closure evidence:**
- **Residual risk after closure:**
- **Approved by:**
- **Date closed:**

### 10. Decision record
- **Decision:** `Investigate | Mitigate | Monitor | Accept Risk | Defer`
- **Decision rationale:**
- **If no immediate action is taken, justify why:**
- **Re-open trigger(s):**

---

## Example

### NUDD Finding ID
- **Finding ID:** `NUDD-THERM-001`
- **Title:** Surface hot spot risk at top-right frame during gaming + charging
- **Type:** `Risk`
- **Category:** Thermal / User Reality / Interface
- **Priority:** `P1`
- **Status:** `Accepted`

### 1. Strategic traceability
- **Threatened KEI(s):** Surface temperature < 41°C
- **Related usage scenario(s):** User gaming while charging in 35–40°C ambient
- **Linked requirement(s):** Skin temperature requirement, charging performance requirement
- **Linked selling point / product promise:** Premium comfort during high-performance usage

### 2. Scope and ownership
- **Affected module(s):** Thermal, ME, Power, ID
- **Primary owner (DRI):** Thermal lead
- **Supporting teams / reviewers:** ME, Power, HWV
- **Date opened:** 2026-05-19
- **Target decision date:** 2026-05-23
- **Target closure date:** 2026-06-05

### 3. Observation
- **Observed symptom / concern:** Simulation suggests a local frame-edge hot spot near the application processor region.
- **When / where it appears:** Gaming workload + charging at elevated ambient.
- **Trigger condition(s):** High SoC power + charging input + restricted spreading path.
- **Boundary conditions / assumptions:** No thick protective case installed; nominal TIM application; ambient 35–40°C.

### 4. Risk statement
- **Risk statement:**
  - Under gaming + charging + high ambient, local heat spreading may be insufficient near the frame edge, causing surface temperature to exceed the KEI limit.
- **Customer / business impact if true:** User discomfort, poor reviews, possible launch gating.
- **Why this matters now:** Thermal architecture is still changeable; late discovery would be expensive.

### 5. Physics-of-failure hypothesis
- **PoF chain:**
  - `[Frame edge touch point] + [High local power density + charging heat] -> [Insufficient heat spreading / enclosure bottleneck] -> [User-touch hot spot / KEI violation]`
- **Suspected root physical mechanism(s):** Local thermal bottleneck, stack-up contact resistance, insufficient spreading area.
- **Why this mechanism is credible:** Known hotspot region aligns with power map and enclosure geometry.

### 6. Evidence and confidence
- **Current evidence level:** `E2`
- **Evidence summary:** Thermal simulation only; no chamber confirmation yet.
- **Known data points:** Predicted peak exceeds target by ~1.8°C in worst simulated stack-up.
- **Unknowns / assumptions / blind spots:** TIM void sensitivity, case effects, battery contribution, contact resistance variation.
- **Confidence level:** `Medium`

### 7. Priority basis
- **Severity rationale:** Direct threat to top-level comfort KEI.
- **Likelihood rationale:** Condition is realistic for target users.
- **Detectability / escape risk:** Moderate; easy to miss if only nominal ambient is tested.
- **Reversibility if found late:** Low; thermal architecture changes late are expensive.
- **Cost of being wrong if ignored:** Potential launch delay and redesign.
- **Cost of false alarm / over-investigation:** Moderate test and analysis cost.

### 8. Required action
- **Immediate next action:** Run chamber test with worst-case workload and instrument frame hot spot locations.
- **Action owner:** Thermal lead
- **Due date:** 2026-05-28
- **Expected output:** Measured temperature map and comparison to simulated model.
- **Escalation trigger(s):** Any location > 41°C or margin < 1.0°C at defined condition.

### 9. Verification and closure
- **Verification approach:** Controlled thermal chamber test.
- **Test method / analysis method:** Gaming + charging workload at 40°C ambient with calibrated thermocouples and IR correlation.
- **Sample size / coverage expectation:** 5 EVT units, 3 stack-up variants if available.
- **Exit criteria (measurable):** Peak measured user-touch temperature ≤ 41°C at defined condition.
- **Required evidence level for closure:** `E4`
- **Closure evidence:**
- **Residual risk after closure:**
- **Approved by:**
- **Date closed:**

### 10. Decision record
- **Decision:** `Investigate`
- **Decision rationale:** Insufficient evidence to close; thermal margin appears weak and architecture is still mutable.
- **If no immediate action is taken, justify why:** N/A
- **Re-open trigger(s):** Any chamber result exceeding exit criteria or showing margin collapse under accessory use.
