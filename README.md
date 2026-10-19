# yt-hybrid-funnel-skill

> **End-to-End YouTube AI Hybrid Funnel & Multi-Channel Fleet Production Skill for Antigravity CLI (`agy`)**

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)
[![Antigravity CLI](https://img.shields.io/badge/Antigravity%20CLI-Compatible-indigo.svg)](https://github.com/magebase/yt-hybrid-funnel-skill)
[![Gemini Argon 4 High](https://img.shields.io/badge/Scripting-Gemini%204%20Argon%20High-purple.svg)](subskills/argon-high-scripting.md)
[![Google Flow Veo 3.1](https://img.shields.io/badge/Visuals-Flow%20%7C%20Veo%203.1-orange.svg)](subskills/google-flow-omni.md)
[![Templates](https://img.shields.io/badge/Faceless%20Templates-36%20Proven-brightgreen.svg)](references/proven-channel-templates.md)

---

## 1. Overview

`yt-hybrid-funnel-skill` is an agent-first engineering skill designed to orchestrate an automated, multi-channel YouTube mass-production fleet in Antigravity CLI (`agy`) repositories.

The hybrid funnel architecture pairs **high-discovery YouTube Shorts** (3 to 5 per week) with **high-RPM Long-Form anchor videos** (1 per week) across 36 proven faceless channel templates. The system executes automated browser prompting in the Gemini web app (**Gemini 4 Argon High**) and Google Flow (**Gemini Flash 1.1 Omni** + **Veo 3.1**), validates content through an automated multi-stage quality critique gate, and manages fleet capital via the **"Promote the Winners, Kill the Losers"** evolutionary telemetry engine.

---

## 2. Core Capabilities

### 1. 36 Battle-Tested Channel Templates ([`references/proven-channel-templates.md`](references/proven-channel-templates.md))
- Reverse-engineered from top faceless creators (*Fern, Imperial, Zack D. Films, Kurzgesagt, MelodySheep, MetaBallStudios, MagnatesMedia, ColdFusion, Economics Explained, Wall Street Millennial, Alux, Lemmino, The Why Files, Patrick Boyle, How Money Works, Fireship, Branch Education*, etc.).
- Covers 6 dominant categories with exact pacing laws, visual signatures, and target RPM benchmarks ($8.70 to $24.80).

### 2. Argon 4 High Browser Scripting & Auto-Critique ([`subskills/argon-high-scripting.md`](subskills/argon-high-scripting.md))
- Deterministic DOM selectors and session handling for `https://gemini.google.com/app`.
- Three-phase generation: Winner Synthesis, Full Long-Form + 4 Linked Shorts Generation, and an **Automatic 100-Point Critique & Self-Correction Gate** (rejects and rewrites any script scoring under 85/100).

### 3. Google Flow Omni 1.1 & Veo 3.1 Generation ([`subskills/google-flow-omni.md`](subskills/google-flow-omni.md))
- Browser automation for `https://labs.google/fx/tools/flow`.
- Visual consistency enforcement via Nano Banana 2 Master Ingredients, prompt expansion using Gemini Flash 1.1 Omni, pre-flight motion checks via Veo 3.1 Lite, and high-fidelity rendering with Veo 3.1 Quality/Fast.
- Automated Visual Frame Critique to prevent character morphing, uncanny seams, or text collision.

### 4. Monorepo Architecture & FFmpeg Assembly ([`subskills/agy-repo-mass-production.md`](subskills/agy-repo-mass-production.md))
- Scalable fleet workspace directory layout with parallel `browsermcp` execution.
- FFmpeg video best practices: 1.8–2.5s Shorts cut law, 4.0–6.0s Long-Form visual state-reset law, `-14.0 LUFS` broadcast audio mastering with dynamic voiceover sidechain ducking, and safe-zone kinetic typography.
- YouTube Data API v3 publisher with `containsSyntheticMedia: true` and `relatedVideoId` Shorts-to-Long-Form bridge linking.

### 5. "Promote Winners, Kill Losers" Telemetry Engine & Dashboard ([`subskills/analytics-evolution-loop.md`](subskills/analytics-evolution-loop.md) & [`assets/dashboard.html`](assets/dashboard.html))
- Daily 06:00 UTC ingestion of YouTube Analytics (VVSA, APV, BridgeCTR, 30s Retention, Net RPM, Net AI ROI).
- Normalized Composite Winner Score ($S_w$):
  - **Promote Winners ($S_w \ge 75$):** Double weekly compute credit allocation and spawn mutated sequel branches.
  - **Probation ($45 \le S_w < 75$):** Trigger thumbnail A/B swaps and hook revisions.
  - **Kill Losers ($S_w < 45$):** Deprecate angle into `negative_constraints.json` and hot-swap to a higher-performing template.
- Standalone interactive HTML Command Center UI (`assets/dashboard.html`).

---

## 3. Repository Map

```text
yt-hybrid-funnel-skill/
├── SKILL.md                                 # Canonical AGY router skill definition
├── README.md                                # Repository guide & documentation
├── LICENSE                                  # MIT License
├── .gitignore                               # Production ignore patterns
├── assets/
│   └── dashboard.html                       # Standalone Fleet Command Center UI
├── references/
│   └── proven-channel-templates.md          # 36 battle-tested faceless templates
└── subskills/
    ├── agy-repo-mass-production.md          # Workspace architecture & FFmpeg assembly
    ├── analytics-evolution-loop.md          # Winner scoring & resource reallocation
    ├── argon-high-scripting.md              # Gemini 4 Argon browser prompting & critique
    └── google-flow-omni.md                  # Google Flow browser automation & visual QA
```

---

## 4. Installation & Integration

### Option A: Install into Workspace
Place or symlink this directory into your project's `skills/` folder:

```bash
mkdir -p skills
ln -s /home/aqua/skills/yt-hybrid-funnel-skill skills/yt-hybrid-funnel-skill
```

### Option B: Install Globally into Antigravity (`~/.gemini/config/skills/`)
Link the skill directory into your global Antigravity configuration:

```bash
ln -s /home/aqua/skills/yt-hybrid-funnel-skill ~/.gemini/config/skills/yt-hybrid-funnel
```

### Invoking with Antigravity (`agy`)
When installed, invoke the skill directly in natural language:

```text
Use the yt-hybrid-funnel skill. Review the active fleet telemetry, identify top-performing templates, architect a new batch of 1 Long-Form video and 4 companion Shorts for CH-01, and pass them through the 85-point critique gate.
```

---

## 5. Fleet Production Rules

1. **The Safe Zone Rule:** All vertical Shorts (`9:16`) must keep critical subjects and typography out of the bottom 25% and right 15% to avoid YouTube UI collisions.
2. **The 85/100 Critique Floor:** Never publish or render scripts that score below 85 points on the Argon 4 High retention rubric.
3. **Decisive Pruning:** If a template maintains $S_w < 45$ across 3 consecutive batches, deprecate it and hot-swap to the next highest template in the category.

---

## 6. License

Released under the [MIT License](LICENSE). Copyright &copy; 2026 Magebase / SKEW Bot.
