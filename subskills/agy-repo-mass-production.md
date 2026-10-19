# Sub-Skill 3: AGY Repository Architecture, Best-Practice Assembly & Multi-Channel Mass Production

Use this sub-skill to structure the Antigravity CLI (`agy`) monorepo, manage parallel `/browser` sessions via `browsermcp`, enforce viral video best practices during FFmpeg post-production, and publish across multiple channels with full YouTube Partner Program (YPP) compliance.

## Step 1: Repository Directory Layout

Initialize the `agy` workspace with the following multi-channel fleet structure:

```text
yt-hybrid-empire/
├── .agy/
│   ├── config.yaml                  # Antigravity CLI harness & concurrency settings
│   ├── mcp_config.json              # BrowserMCP (@browsermcp/mcp) + YouTube API MCP servers
│   └── workflows/
│       ├── weekly_batch.md          # Automated fleet production workflow
│       └── daily_telemetry.md       # Daily 06:00 UTC analytics ingestion & winner scoring
├── references/
│   └── proven-channel-templates.md  # 30 battle-tested faceless AI templates (T-01 to T-30)
├── channels/
│   ├── CH-01_subzero_forensics/
│   │   ├── brand_kit.json           # Assigned Template ID, palette, LUTs, voice, Flow Ingredients
│   │   ├── negative_constraints.json# Killed angles/hooks auto-populated by evolution loop
│   │   └── runs/                    # Timestamped production batches
│   ├── CH-02_orbit_and_atom/
│   ├── CH-03_shadow_ledger/
│   ├── CH-04_nocturne_archives/
│   ├── CH-05_alpha_autopsy/
│   ├── CH-06_yield_matrix/
│   ├── CH-07_silicon_pulse/
│   └── CH-08_biohack_mechanics/
├── schemas/
│   ├── production_package.schema.json
│   └── telemetry_winner.schema.json
├── scripts/
│   ├── 01_ingest_metrics.py         # Pulls YouTube Analytics API v2 & executes Promote/Kill rules
│   ├── 02_argon_architect.ts        # Runs /browser on gemini.google.com (Argon High + Critique)
│   ├── 03_flow_visual_factory.ts    # Runs /browser on labs.google/fx/tools/flow (Omni + Veo 3.1)
│   ├── 04_ffmpeg_assembler.py       # Enforces pacing cuts, audio ducking, captions & overlays
│   └── 05_youtube_publisher.py      # Uploads, sets synthetic flags, links Shorts -> Long-Form
└── dashboard/
    └── index.html                   # "Promote Winners, Kill Losers" Command Center UI
```

## Step 2: Configuring `agy` and Parallel `/browser` Execution

Register `browsermcp` in `.agy/mcp_config.json` with isolated persistent Chrome profiles per channel batch so Gemini 4 Argon (High) and Google Flow sessions stay authenticated:

```json
{
  "mcpServers": {
    "browsermcp": {
      "command": "npx",
      "args": ["-y", "@browsermcp/mcp@latest"]
    }
  }
}
```

Execute a fleet-wide mass production batch across channels from the terminal:

```bash
agy run .agy/workflows/weekly_batch.md --channels CH-01,CH-02,CH-03,CH-04,CH-05,CH-06,CH-07,CH-08 --parallel 4
```

## Step 3: Video Best Practices Enforced in `04_ffmpeg_assembler.py`

To pass YouTube Partner Program (YPP) authenticity reviews and maximize algorithmic retention, `04_ffmpeg_assembler.py` programmatically enforces 5 non-negotiable video best practices:

1. **The 2.2s / 4.5s Visual State Reset Law:**
   - **Shorts (`9:16`):** Every **1.8 to 2.5 seconds**, the assembler executes a hard cut, whip-pan transition, `1.08x` dynamic punch-in zoom, or kinetic graphic pop. No single static camera shot may exceed 2.8 seconds.
   - **Long-Form (`16:9`):** Every **4.0 to 6.0 seconds**, the assembler triggers a camera angle cut, vector data overlay, document highlight, or 3D cutaway label.

2. **First-Frame Thumbnail Validation & Cold-Open Velocity:**
   - Frame 1 (`00:00.00`) of every Long-Form video visually resolves or animates the exact focal object from the thumbnail while the narrator delivers the core curiosity hook within the first 4.5 seconds—zero channel logo intros.

3. **Broadcast-Grade Multi-Stem Audio Mastering (`-14 LUFS`):**
   - Mixes 3 discrete audio stems: (1) Niche-matched Voiceover (165-185 WPM with breaths trimmed above `0.25s`), (2) Tension/Atmospheric Score ducked by `-14dB` under voiceover via FFmpeg `sidechaincompress`, and (3) Sub-bass risers, mechanical clicks, and whooshes synced to every visual state transition.

4. **Kinetic Safe-Zone Captions & Vector Data Callouts:**
   - Renders word-by-word highlighted mobile captions (`2 to 3 words per line`, Montserrat ExtraBold / Inter Black with `4px` stroke and drop shadow) positioned strictly at `Y = 72%` on `9:16` Shorts so they never collide with YouTube's bottom title/Related Video link bar (`Y = 78%–100%`).

5. **Post-Render Automated Final Audit:**
   - Before queuing for upload, `04_ffmpeg_assembler.py` runs `ffprobe` and silence/scene-change detection (`select='gt(scene,0.3)'`) to verify:
     - Zero audio dead air `> 0.4s`
     - Integrated loudness within `-14.0 ± 1.0 LUFS`
     - Scene cut frequency meets the assigned template's target cadence

## Step 4: YouTube API Upload, Thumbnail A/B Testing & Funnel Linking (`05_youtube_publisher.py`)

1. Upload the Long-Form anchor video first and capture its `LONG_FORM_VIDEO_ID`.
2. Queue the 3 Nano Banana 2 thumbnail variants (`Thumb_A_Curiosity`, `Thumb_B_Contrast`, `Thumb_C_Stat`) into YouTube Studio's **Test & Compare** A/B/C testing slot.
3. Explicitly set `"containsSyntheticMedia": true` and `"selfDeclaredMadeForKids": false` in the `status` payload of every upload.
4. Schedule the 4 companion Shorts across the next 96 hours and set `relatedVideoId: LONG_FORM_VIDEO_ID` on each Short so every vertical view becomes a 1-click bridge into your high-RPM Long-Form video.
