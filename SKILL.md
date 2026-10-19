---
name: yt-hybrid-funnel
description: End-to-end YouTube AI Hybrid Funnel and Mass Production Fleet skill for Antigravity CLI (agy). Orchestrates multi-channel content mass production across 36 real-world faceless video templates, automates Gemini 4 Argon (High) via /browser for scripting and automatic self-critique, automates Gemini Flash 1.1 Omni in Google Flow (Veo 3.1 and Nano Banana) for visual generation, and runs a "Promote the Winners, Kill the Losers" evolutionary telemetry dashboard. Use when the user wants to plan, mass-produce, critique, automate, or optimize faceless YouTube Shorts and Long-Form videos across channels.
---
# YouTube AI Hybrid Funnel & Fleet Manager (yt-hybrid-funnel)

Orchestrate an automated, multi-channel YouTube mass-production pipeline in an Antigravity CLI (`agy`) repository. This skill pairs high-discovery YouTube Shorts (3 to 5 per week) with high-RPM Long-Form anchor videos (1 per week) across 36 proven real-world channel templates, browser-automated prompting in the Gemini web app (`Gemini 4 Argon - High`) and Google Flow (`Gemini Flash 1.1 Omni` + `Veo 3.1`), an automated multi-stage quality critique gate, and a "Promote the Winners, Kill the Losers" evolutionary telemetry engine.

## When to Use

- Building or scaling an `agy` repository to mass-produce YouTube Shorts and Long-Form videos across multiple faceless channels
- Assigning or rotating channels across 36 battle-tested faceless video templates modeled on real top-performing YouTube creators (`references/proven-channel-templates.md`)
- Automating script architecture, storyboard engineering, and **Automatic Pre-Render Critique** via `/browser` in the Gemini web app using **Gemini 4 Argon (`thinking_level: high`)** (`subskills/argon-high-scripting.md`)
- Directing visual asset generation and **Visual Frame Critique** in Google Flow (`labs.google/fx/tools/flow`) using **Gemini Flash 1.1 Omni**, **Nano Banana 2**, and **Veo 3.1** (`subskills/google-flow-omni.md`)
- Ingesting YouTube Analytics telemetry to compute the Composite Winner Score ($S_w$) and execute the **"Promote the Winners, Kill the Losers"** resource allocation protocol and live HTML dashboard (`subskills/analytics-evolution-loop.md` and `assets/dashboard.html`)

## Auxiliary Resources & Sub-Skills

1. **`references/proven-channel-templates.md` (36 Real-World Proven AI Templates):**
   - Full catalog of 36 battle-tested faceless templates modeled on real channels (*Fern, Imperial, Zack D. Films, Kurzgesagt, MelodySheep, MetaBallStudios, MagnatesMedia, ColdFusion, Economics Explained, Wall Street Millennial, Alux, Lemmino, The Why Files, Patrick Boyle, How Money Works, Fireship, Branch Education, JxmyHighroller, JCS*, etc.) with exact pacing, AI tool pairings, and target RPMs.
2. **`subskills/argon-high-scripting.md` (Argon 4 High `/browser` Automation & Auto-Critique Rubric):**
   - Deterministic DOM selectors for `https://gemini.google.com/app`, three-phase prompt templates, and the 100-point **Automatic Script & Retention Critique Gate** (rejects and rewrites any script scoring under 85/100).
3. **`subskills/google-flow-omni.md` (Google Flow Omni 1.1 Flash `/browser` Automation & Visual QA):**
   - Deterministic DOM workflow for `https://labs.google/fx/tools/flow`, Nano Banana 2 Ingredient locking, Veo 3.1 Lite/Fast/Quality tiered rendering, and automated **Visual Frame Critique** to catch morphing or caption collisions.
4. **`subskills/agy-repo-mass-production.md` (AGY Monorepo, FFmpeg Best-Practice Assembly & YPP Compliance):**
   - Complete directory layout, `browsermcp` parallel execution config, FFmpeg pacing/audio mastering laws, and YouTube Data API v3 upload scripts with `relatedVideoId` funnel linking.
5. **`subskills/analytics-evolution-loop.md` & `assets/dashboard.html` ("Promote the Winners, Kill the Losers" Engine & Dashboard):**
   - Daily telemetry ingestion, Composite Winner Score ($S_w$) formula, automated capital/credit reallocation rules, template mutation protocol, and the standalone interactive HTML Command Center (`assets/dashboard.html`).

## Core Fleet Roster (Default Active Cohort)

Channels dynamically draw from the 36 templates in `references/proven-channel-templates.md`. The default fleet spans 8 core channels:

| Channel ID | Channel Name | Niche | Default Assigned Template | Benchmark Real Channels | Target RPM |
| :--- | :--- | :--- | :--- | :--- | :--- |
| `CH-01` | **SubZero Forensics** | Engineering Disasters & Mechanical Failures | `T-01` 3D Isometric Forensics | Fern, Imperial, Neo | $14.50 |
| `CH-02` | **Orbit & Atom** | Existential Physics, Space & Paradoxes | `T-06` Cosmic Flat-Vector | Kurzgesagt, MelodySheep | $11.80 |
| `CH-03` | **Shadow Ledger** | Geopolitics, Megaprojects & Macro-Economies | `T-11` Investigative Map Flyover | Vox, RealLifeLore, Hoser | $18.20 |
| `CH-04` | **Nocturne Archives** | Cold Cases, Internet Mysteries & Conspiracies | `T-17` Cold-Case Vanishing Doc | Lemmino, Barely Sociable, Nexpo | $9.60 |
| `CH-05` | **Alpha Autopsy** | Corporate Collapses, Fraud & Startup Autopsies | `T-12` Noir Corporate Cinema | MagnatesMedia, ColdFusion, Modern MBA | $21.40 |
| `CH-06` | **Yield Matrix** | Personal Finance, Market Cycles & Wealth | `T-13` Sardonic Wealth Charts | How Money Works, Patrick Boyle | $24.80 |
| `CH-07` | **Silicon Pulse** | AI Model Breakdowns & Semiconductor Tech | `T-23` 100s Hyper-Dense Code/AI | Fireship, Branch Education | $16.50 |
| `CH-08` | **BioHack Mechanics** | Cellular Longevity, Neuroscience & Performance | `T-03` Cellular Bio-Simulation | Institute of Human Anatomy, Zack D. Films | $13.90 |

## End-to-End Execution Pipeline

1. **Ingest Telemetry & Execute "Promote Winners, Kill Losers" (`subskills/analytics-evolution-loop.md`)**
   - Pull trailing 48-hour and 7-day YouTube Analytics metrics into `data/telemetry.json` and render `assets/dashboard.html`.
   - Score every video, template, and channel using $S_w$. Automatically promote **Alpha Winners ($S_w \ge 75$)** by doubling weekly credit allocation and spawning 3 mutated sequels. Place **Underperformers ($45 \le S_w < 75$)** on thumbnail/hook A/B probation. **Kill Losers ($S_w < 45$)** after 3 consecutive failed batches by deprecating the angle into `negative_constraints.json` and hot-swapping the channel to a higher-ranked template from `references/proven-channel-templates.md`.

2. **Architect & Critique Scripts via Argon 4 High (`subskills/argon-high-scripting.md`)**
   - Launch `agy` `/browser` (`browsermcp`) on `https://gemini.google.com/app` with **Gemini 4 Argon (High)**.
   - Run Phase 1 (Winner Synthesis), Phase 2 (Full Long-Form + 4 Linked Shorts Generation), and Phase 3 (**Automatic 100-Point Critique & Self-Correction Loop**). Only export `production_package.json` once every retention, pacing, and YPP authenticity check scores $\ge 85/100$.

3. **Generate & Critique Visuals in Google Flow (`subskills/google-flow-omni.md`)**
   - Launch `agy` `/browser` on `https://labs.google/fx/tools/flow`.
   - Lock visual consistency with **Nano Banana 2** Master Ingredients, expand cinematography prompts with **Gemini Flash 1.1 Omni**, run pre-flight motion checks in **Veo 3.1 Lite**, and render final 16:9 and 9:16 masters in **Veo 3.1 Quality/Fast**.

4. **Assemble with Best-Practice Pacing & Publish (`subskills/agy-repo-mass-production.md`)**
   - Run `04_ffmpeg_assembler.py` enforcing the 1.8-2.5s Shorts cut law, 4.0-6.0s Long-Form state-reset law, `-14dB` sidechain audio ducking, and mid-roll ad cliffhangers.
   - Upload via `05_youtube_publisher.py` with `containsSyntheticMedia: true` and `relatedVideoId` linking all 4 Shorts to the parent Long-Form video.

## Gotchas

- **Never bypass the Automatic Critique Gate:** Submitting un-critiqued scripts or raw Veo 3.1 Lite clips without passing the 85/100 rubric causes early viewer drop-off and wastes Google Flow compute credits.
- **Enforce ruthless template pruning:** Do not emotionally attach to a losing template. If a template's $S_w$ stays below 45 across 3 batches, let the evolution loop kill it and reassign a top-performing template from `references/proven-channel-templates.md`.
- **Keep 9:16 Safe Zones Clean:** Never place crucial visual subjects in the bottom 25% or right 15% of Shorts frames where YouTube overlays captions, channel handles, and the Related Video funnel link.
