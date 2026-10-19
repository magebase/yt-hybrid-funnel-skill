# Sub-Skill 1: Prompting Gemini 4 Argon (High) via `/browser` + Automatic Critique Gate

Use this sub-skill when `agy` executes Stage 2 of the pipeline (`scripts/02_argon_architect.ts`). It drives the Gemini web app (`https://gemini.google.com/app`) via `agy` `/browser` automation (`browsermcp` / CDP) to leverage **Gemini 4 Argon (`thinking_level: high`)** for long-horizon narrative architecture, retention engineering, cross-format synchronization, and a mandatory **100-Point Automatic Critique & Self-Correction Loop**.

## Why Gemini 4 Argon (High)

Gemini 4 Argon in `high` thinking mode maintains structural coherence across 15,000+ tokens, synchronizes 4 vertical Shorts hooks with a single 10-to-15-minute Long-Form narrative across any of the 30 templates in `references/proven-channel-templates.md`, and ruthlessly critiques its own script against YouTube Partner Program (YPP) and retention laws before outputting production JSON.

## Step 1: Browser Automation Sequence (`/browser`)

Execute these deterministic DOM actions via the `agy` browser subagent (`browsermcp`):

1. **Navigate and Authenticate:**
   - Open `https://gemini.google.com/app` using the persistent Chrome profile configured in `.agy/config.yaml`.
   - Wait for selector `div[contenteditable="true"][role="textbox"]` (timeout: `15000ms`).

2. **Select Model Tier (`Gemini 4 Argon - High`):**
   - Click the model selector dropdown button (`button[data-test-id="model-selector-button"]` or aria-label containing `"Model"`).
   - Select `"Gemini 4 Argon"` and toggle Thinking Effort to `"High"` (`[data-value="argon-high"]`).

3. **Three-Phase Prompt Injection (Plan -> Generate -> Auto-Critique & Rewrite):**
   - **Turn 1 (Pre-Flight & Winner Mutation):** Inject Prompt 1 with the latest telemetry from `winner_brief.json` and `negative_constraints.json`.
   - **Turn 2 (Full Production Draft):** Inject Prompt 2 to generate the complete Long-Form script and 4 companion Shorts scripts.
   - **Turn 3 (Automatic Critique & Best-Practices Enforcement Gate):** Inject Prompt 3. Argon (High) must score the draft across 5 strict axes (100 points total). If the total score is `< 85` or any single axis is `< 15/20`, Argon must automatically rewrite every failing scene block before emitting the final validated JSON.

## Step 2: Exact Prompt Templates for Argon (High)

### Prompt 1: Pre-Flight Alignment and Winner Mutation

```text
[SYSTEM ROLE: Principal YouTube Retention Architect & Fleet Showrunner]
We are executing a Weekly Hybrid Funnel Production Run for Channel: {{CHANNEL_NAME}} ({{CHANNEL_ID}})
Assigned Template: {{TEMPLATE_ID}} - {{TEMPLATE_NAME}} (Benchmark Channels: {{BENCHMARK_CHANNELS}})

1. PREVIOUS GENERATION TELEMETRY (PROMOTE WINNERS / KILL LOSERS):
- Active Winner Brief (Mutate & Scale): {{WINNER_TELEMETRY_JSON}}
- Deprecated Angles & Killed Hooks (STRICTLY BANNED): {{NEGATIVE_CONSTRAINTS_JSON}}

2. YOUR OBJECTIVE:
Analyze why the top Parent Winner outperformed the baseline across:
- 3-Second Scroll-Stop Rate (Viewed vs. Swiped Away >= 75%)
- 00:30 Long-Form Hook Retention (>= 72%)
- Shorts-to-Long-Form Bridge Click-Through Rate (CTR >= 4.5%)

Propose 3 mutated video concepts that double down on the winning psychological trigger while introducing a fresh factual angle and strictly avoiding all banned angles in NEGATIVE_CONSTRAINTS_JSON. For each concept, specify:
- Long-Form Title (<55 chars, high curiosity gap, zero clickbait disconnect)
- 3 Thumbnail Variants (3-4 bold words max, high-contrast focal object, emotional/visual tension)
- The 4 Companion Shorts Hooks (Short A: Impossible Question, Short B: Micro-Timeline, Short C: Fatal Error, Short D: Shocking Stat) and the exact cliffhanger bridge line that routes viewers to the Related Video link.

Output the top-ranked concept specification for confirmation.
```

### Prompt 2: Full Script & Timecoded Storyboard Generation

```text
Locking in Concept #1 using Template {{TEMPLATE_ID}} ({{TEMPLATE_NAME}}). Generate the complete production draft.

DELIVERABLE REQUIREMENTS:
1. LONG-FORM ANCHOR SCRIPT (Target: 9 to 12 minutes, ~1,750 words):
   - 00:00-00:05: Instant Cold Open — validate the exact title and thumbnail promise in frame 1. Zero throat-clearing ("Hey guys", "Welcome back", "In today's video").
   - 00:05-00:30: High-Stakes Paradox & Visual Proof — establish the central mystery/mechanism and preview the climax without spoiling the resolution.
   - 00:30-02:30: Act I - The Setup & Mechanism (new visual state reset every 4 to 6 seconds).
   - 02:30-05:45: Act II - Escalation & Forensic Breakdown (plant hard narrative cliffhangers at 02:25 and 05:40 immediately prior to mid-roll ad slots).
   - 05:45-08:30: Act III - The Turning Point & Hidden Consequence (introduce a twist or second-order effect that reframes Act I).
   - 08:30-10:30: Resolution & Systemic Takeaway (end quickly once the climax resolves—no drawn-out sign-off that triggers an end-screen retention cliff).
   - Divide the entire script into numbered 4-to-6-second Scene Blocks with explicit narration, visual camera action, and audio SFX cues.

2. 4 COMPANION SHORTS SCRIPTS (Target: 38 to 48 seconds each, 9:16 vertical):
   - Enforce a visual state change or camera angle flip every 1.8 to 2.5 seconds.
   - 75% of the Short must deliver standalone narrative value; at second 36, hit a high-tension revelation and deliver a 4-second Bridge Hook pointing directly to the YouTube "Related Video" link at the bottom of the Shorts player (never say "Watch Part 2").
   - Also provide an alternate 1.5-second Seamless Loop ending for pure discovery testing where the final sentence grammatically completes the opening 3 words.
```

### Prompt 3: Automatic Critique Gate & Self-Correction Loop (MANDATORY)

```text
[SYSTEM ROLE: Ruthless YouTube Retention Auditor & YPP Compliance Inspector]
Audit the production draft you just generated against our 100-Point Best-Practice Rubric:

1. HOOK VELOCITY & THUMBNAIL SYNERGY (20 pts):
   - Does 00:00-00:05 immediately show the exact visual promised in the thumbnail?
   - Does the first sentence open an irresistible curiosity loop in under 12 words?
2. PACING DENSITY & VISUAL STATE RESETS (20 pts):
   - Do Long-Form scene blocks change camera angle, cutaway state, or data callout every 4-6 seconds?
   - Do Shorts scene blocks change visual state every 1.8-2.5 seconds with zero static talking frames?
3. RETENTION RE-HOOKS & MID-ROLL ARCHITECTURE (20 pts):
   - Is there a pattern interrupt or open-loop question every 60-90 seconds ("But that wasn't the real flaw...")?
   - Do timestamps 02:25 and 05:40 contain unresolved high-tension cliffhangers for mid-roll ad survival?
4. AI ANTI-SLOP & YPP AUTHENTICITY COMPLIANCE (20 pts):
   - Scan for banned AI filler phrases ("delve", "testament", "tapestry", "buckle up", "in conclusion", "it's important to remember", "moreover"). Deduct 5 points per occurrence.
   - Verify the script contains specific dates, named entities, quantitative metrics, and an original analytical thesis that passes YouTube's Inauthentic Content policy.
5. SHORTS-TO-LONG-FORM FUNNEL BRIDGE & LOOP PRECISION (20 pts):
   - Does each Short's bridge line state a high-stakes unresolved question that naturally compels clicking the Related Video link?

EXECUTION RULE:
- Output your itemized Scorecard (0-100) and list every scene block ID that failed a check.
- Automatically rewrite all flagged scene blocks so the final script achieves >= 92/100.
- Emit ONLY the final corrected, verified production package inside a single ```json code block matching `schemas/production_package.schema.json`.
```

## Step 3: DOM Extraction and Schema Validation

1. Wait for the streaming indicator in `gemini.google.com` to finish and locate the final `code.language-json` block in Turn 3.
2. Extract `innerText`, write to `channels/{{channel_id}}/runs/{{run_id}}/production_package.json`, and run:
   ```bash
   npx ajv validate -s schemas/production_package.schema.json -d channels/{{channel_id}}/runs/{{run_id}}/production_package.json
   ```
3. Verify `critique_scorecard.total_score >= 85` in the JSON payload before unlocking Stage 3 (`03_flow_visual_factory.ts`).
