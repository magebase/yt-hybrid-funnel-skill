# Sub-Skill 4: "Promote the Winners, Kill the Losers" Evolutionary Engine & Performance Dashboard

Use this sub-skill in Stage 1 (`scripts/01_ingest_metrics.py`) and inside `dashboard/index.html` to evaluate every video, template, and channel in your fleet and automatically reallocate compute credits toward proven winners while killing underperforming templates and channels.

## Step 1: Daily Telemetry Ingestion (`01_ingest_metrics.py`)

Every 24 hours at `06:00 UTC`, query the YouTube Analytics API (`youtubeAnalytics.reports.query`) across all active channels and templates for two windows (48-Hour Rapid Signal and 7-Day Cohort Maturity):

- **Shorts Discovery Metrics:**
  - `VVSA` (Viewed vs. Swiped Away % — Target: `>= 75%`, Kill Floor: `< 58%`)
  - `APV` (Average Percentage Viewed — Target for 45s Short: `>= 98%`, Kill Floor: `< 75%`)
  - `BridgeCTR` (`relatedVideoClickThroughRate` into Long-Form — Target: `>= 4.5%`, Kill Floor: `< 1.8%`)
- **Long-Form Monetization Metrics:**
  - `ThumbCTR` (`impressionsClickThroughRate` — Target: `>= 6.5%`, Kill Floor: `< 3.8%`)
  - `Ret30s` (Alive at 00:30 mark — Target: `>= 72%`, Kill Floor: `< 52%`)
  - `AVD_Pct` (Average View Duration % — Target: `>= 45%`, Kill Floor: `< 28%`)
  - `NetRPM` (Revenue per 1,000 views) & `NetAiROI` = `(GrossAdRevenue - FlowAndApiComputeCost) / FlowAndApiComputeCost`

## Step 2: Composite Winner Score ($S_w$) Formula

Normalize each metric on a 0 to 100 percentile scale against fleet benchmarks and compute the Composite Winner Score ($S_w$) for every **Video**, **Template (`T-01`..`T-30`)**, and **Channel (`CH-01`..`CH-08`)**:

$$S_w = 0.20(\text{Norm}_{\text{VVSA}}) + 0.20(\text{Norm}_{\text{BridgeCTR}}) + 0.20(\text{Norm}_{\text{Ret30s}}) + 0.20(\text{Norm}_{\text{ThumbCTR}}) + 0.20(\text{Norm}_{\text{NetAiROI}})$$

## Step 3: Automated "Promote the Winners, Kill the Losers" Decision Matrix

`01_ingest_metrics.py` automatically classifies every Video, Template, and Channel into one of three action tiers:

| Tier & Score Threshold | Status Badge | Video-Level Action | Template-Level Action (`T-01`..`T-30`) | Channel-Level Fleet Action |
| :--- | :--- | :--- | :--- | :--- |
| **Tier 1: PROMOTE / SCALE**<br>($S_w \ge 75$ and $\text{NetAiROI} \ge 150\%$) | `PROMOTE WINNER` | Extract opening 5s camera prompt, hook cadence, and bridge line into `winner_brief.json`. Spawn **1 Direct Part II Long-Form + 1 Sister Topic + 4 Fresh Shorts**. | Increase weekly Google Flow Veo 3.1 Quality credit allocation by **+100%**. Clone this template to any newly launched or pivoted sister channel. | Upgrade channel concurrency to **2x weekly Long-Form + 8x Shorts** (`Priority Queue 1`). |
| **Tier 2: OPTIMIZE / PROBATION**<br>($45 \le S_w < 75$) | `OPTIMIZE / HOLD` | If `ThumbCTR < 5.5%`, auto-swap to Thumbnail Variant B/C. If `BridgeCTR < 3.0%`, generate 2 replacement Shorts with sharper cliffhangers. | Keep template active at baseline budget (`1x weekly batch`), but require Argon 4 High to test an alternate hook archetype from `references/proven-channel-templates.md`. | Hold steady at baseline 1 Long-Form + 4 Shorts per week. |
| **Tier 3: KILL / DEPRECATE**<br>($S_w < 45$ or $\text{NetAiROI} < 0\%$ across 3 batches) | `KILL LOSER` | Immediately halt further companion Shorts for this video. Append topic angle, hook syntax, and visual prompt tokens to `negative_constraints.json`. | **Kill Template Assignment:** Retire the failing template on this channel and auto-assign the highest-scoring template from `references/proven-channel-templates.md` in the same RPM tier. | If a channel fails across **2 consecutive template swaps (6 weeks total)** with $S_w < 40$, **Pause/Sunset Channel** and reallocate 100% of its compute budget to the top Tier 1 channel. |

## Step 4: Standalone Fleet Command Center (`dashboard/index.html`)

Generate or update `dashboard/index.html` in the repository root so it reads `data/telemetry.json` and provides:
1. **Fleet KPI Header:** Total Weekly Views, Gross AdSense Revenue, Google Flow + API Compute Spend, Net Fleet Profit, and Active Winner Ratio.
2. **Retention vs. RPM Quadrant Matrix:** Plots every active channel/template by 30s Retention (X-axis), Net RPM (Y-axis), and Net AI ROI (Bubble Size), clearly demarcating the **Scale Zone (Top-Right)** and **Kill Zone (Bottom-Left)**.
3. **One-Click Promote / Kill Action Table:** Filterable by `All`, `Promote Winners (Sw >= 75)`, `Probation (45-74)`, and `Kill Losers (< 45)`, exporting `winner_brief.json` and `negative_constraints.json` directly into the next `agy run` cycle.
