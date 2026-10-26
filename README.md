# Cohort Watch prototype

**Live prototype:** https://usha-pm.github.io/cohort-watch-demo/

A clickable concept prototype for **Cohort Watch**, a proposed extension of SupportLogic's Cohort Summary.

> **Everything in this prototype is illustrative.** All accounts, people, case IDs, quotes and numbers are made up. Cohort Watch is a proposal, not a shipped feature or roadmap commitment.

## Open it

1. Double-click `index.html`, or drag it into Chrome, Safari or Edge.
2. That's it. It's one self-contained file with no server, no install and no network requests.

**Fastest way in:** click **▶ Take the 60-second tour** at the bottom of the page. It walks through the whole story in 8 steps: today's summary → what changed → evidence → confidence → acting with 10.2 features → the upsell moment → MCP → outcome tracking.

**Or explore yourself (about 2 minutes):**
1. **Summary tab** (opens first): the existing Cohort Summary. Click **Watching · Open Cohort Watch**, or click the **9** in the kernel-panic bullet.
2. **Cohort Watch tab:** switch cohorts on the left, change the comparison window, and hover the trend chart.
3. Click the **Kernel panics on Dell PE2650…** insight to open the evidence panel. It has three tabs: Cases (click a row to see its last response; tick or untick cases), Customer quotes, and Why we flagged this.
4. Try the next steps:
   - **Create an alert:** saves a Draft into the mock Alerts Library under the insights.
   - **Send proactive customer updates:** shows per-owner AI drafts (Automated SLA Response draft mode).
   - **Route to a specialist queue:** the **upsell moment**. It previews what Auto Assignment would do with these cases.
   - **Share a cohort brief:** an editable brief you can copy.
5. Rate the insight 👍/👎, or dismiss it (Undo is available).

## Functional vs mocked

| Area | Functional in the prototype | Mocked or illustrative |
|---|---|---|
| Tabs (Overview, Summary, Cohort Watch, Team) | Switching works | The Team tab is a placeholder. The Overview is a simplified static copy |
| *Watch this cohort* (Summary) | Adds the cohort and jumps to Cohort Watch | Saving cohorts doesn't persist; a reload resets everything |
| Watched-cohort list | Selecting a cohort re-renders its KPIs, trend and insights. *Stop watching* works, with Undo | *+ Watch a new cohort* is mocked |
| Comparison window (7/14/30 days) | Recomputes the change shown on each KPI | Longer windows use a made-up scaling, not real data |
| Trend chart | Drawn from the cohort's data, with hover tooltips | 14 days of illustrative values |
| Insight cards | Open the evidence panel; ranked list; dismiss with Undo; feedback state shown | Detection and ranking are not implemented. Insights are hard-coded |
| Evidence: Cases | Select all/clear, per-case checkboxes, rows expand to show the last response; actions use the selected cases | Case links show a "would open" message |
| Evidence: Quotes / Why flagged | Switch per insight | Content is illustrative |
| Create an alert | Pre-filled with 10.2 alert conditions; editable name and type; saves a Draft into the mock Alerts Library; Undo | Not connected to Orchestrate |
| Proactive updates | Groups selected SLA-risk cases by owner; shows a sample AI draft | No drafts are created or sent |
| Route to a specialist queue (upsell) | Preview splits the selected cases across queues; "Ask my CSM" changes state | Queue names, split and CSM request are mocked. Assumes Auto Assignment isn't enabled |
| Share a brief | Builds a brief from the insight and selected cases; editable; **Copy** really copies; weekly toggle | Sharing and scheduling are mocked |
| Guided tour (8 steps) | Drives the real UI: switches tabs, opens the insight, evidence tabs and modals; Back/Next/Exit; Esc exits | Narration is fixed text |
| Weekly digest | Counts high-priority insights, accounts exposed, Premium and churn-risk accounts, actions taken and upsell previews across watched cohorts; updates as you act | Underlying data is illustrative |
| Exposure and confidence | Each insight computes its accounts, Premium-tier and churn-risk counts from its cases; shows a confidence level and reason | Churn-risk accounts and confidence values are illustrative |
| Activity and outcome tracking | Every action is logged on its insight (Activity tab, "actions taken" chip) | Outcome measurement after an action is described, not simulated |
| Ask in an AI assistant (MCP) | Opens a sample assistant exchange built from the selected insight | The tool `get_cohort_insights` and the exchange are a proposal |
| Demo switch: "workspace has Auto Assignment" | Toggles the routing action between the upsell preview and the owned flow (Route now) | Routing is mocked |
| Sidebar, search, help, share/copy icons | Show a "not in prototype" message | Mocked |
| Keyboard | Esc closes a modal, then the panel; focus rings are visible | Not a full accessibility audit |

## Design notes and approximations

- **Taken from the screenshots:** the sidebar items and order, the *SLAs NEW* badge, the yellow sync banner, pill-style tabs, the Cohort Summary layout (*Outdated* + *Update*, share/copy icons, section headings, linked case IDs), the Overview card style (pink titles, large counts, sparklines, selected-card border), the score rings, the churn-risk chip style and the Help button.
- **Approximated (not established by the screenshots):** the font (system sans-serif stands in for the product font), the icons (simple line drawings), exact colors and spacing, and the evidence panel, modals, KPI strip and chart styles, which are new UI. The purple **PROPOSED** chips and the top banner are prototype labels, not product UI.
- **Tested:** the page logic was run against a stand-in for the browser. All views, every insight's tabs and all four actions ran without errors, and no blank or `undefined` values appeared. It has not been checked visually in a real browser yet.

## Files

- `index.html`: the prototype (HTML, CSS and JavaScript in one file)
- `README.md`: this file
