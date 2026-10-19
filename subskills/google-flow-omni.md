# Sub-Skill 2: Prompting Gemini Flash 1.1 Omni in Google Flow (`labs.google/fx/tools/flow`) + Visual Critique Gate

Use this sub-skill during Stage 3 (`scripts/03_flow_visual_factory.ts`). It automates **Google Flow** via the `agy` `/browser` subagent (`browsermcp`), using **Gemini Flash 1.1 Omni** to translate Argon's verified scene blocks into camera-accurate prompts, generate consistent "Ingredients" (Nano Banana 2 / Imagen reference frames), render video clips with **Veo 3.1** (Lite, Fast, and Quality), and execute an automated **Visual Frame Critique** before export.

## Why Gemini Flash 1.1 Omni + Google Flow

Google Flow unifies three specialized models in a single browser workspace:
- **Gemini Flash 1.1 Omni:** Multimodal natural-language prompt expander, cinematography director, and visual frame auditor inside Flow.
- **Nano Banana 2 / Imagen:** Generates consistent character, cutaway, and environment reference images ("Ingredients") locked as Start and End frames so 10-minute videos never suffer visual style drift.
- **Veo 3.1 (Lite, Fast, Quality):** Renders 16:9 landscape clips for Long-Form and 9:16 portrait clips for Shorts with native camera control and SynthID watermarking.

## Step 1: Browser Automation Workflow in Google Flow (`/browser`)

1. **Open Project Workspace:**
   - Navigate via `/browser` to `https://labs.google/fx/tools/flow`.
   - Click `"New Project"` and name it `{{CHANNEL_ID}}_{{TEMPLATE_ID}}_{{RUN_DATE}}_{{VIDEO_SLUG}}`.

2. **Generate Master Visual Ingredients (Consistency Lock):**
   - Open the **Ingredients / Frames** panel (`Nano Banana 2`).
   - Generate 4 to 6 anchor reference images matched to the channel's assigned template from `references/proven-channel-templates.md` (e.g., recurring narrator avatar, isometric cutaway vehicle/structure, primary color LUT reference).
   - Pin these Ingredient IDs across all scene prompts so every Veo 3.1 clip shares identical lighting, geometry, and color grading.

3. **Expand Scene Prompts with Gemini Flash 1.1 Omni:**
   - Invoke the **Gemini Flash 1.1 Omni** prompt assistant inside Flow to transform each scene block from `production_package.json` into a structured cinematography prompt.

## Step 2: Prompting Protocol for Gemini Flash 1.1 Omni in Flow

Inject this prompt template into Gemini Flash 1.1 Omni inside Google Flow for every scene batch:

```text
[FLOW OMNI 1.1 FLASH CINEMATOGRAPHY EXPANDER]
Convert the following verified Scene Block into a production-ready Veo 3.1 prompt and Start/End Frame pair.

INPUT SCENE DATA:
- Channel Template: {{TEMPLATE_ID}} - {{TEMPLATE_NAME}} ({{TEMPLATE_STYLE_GUIDE}})
- Aspect Ratio: {{ASPECT_RATIO}} (16:9 for Long-Form | 9:16 for Shorts)
- Scene Narration: "{{NARRATION_LINE}}"
- Visual Action: "{{VISUAL_ACTION}}"
- Locked Ingredient IDs: {{INGREDIENT_REFS}}

STRICT PROMPTING RULES FOR VEO 3.1:
1. Physical Camera Language Only: Replace vague verbs ("zoom in", "show") with explicit lens and rig terms ("slow motorized macro dolly-in on 50mm lens", "isometric 45-degree orthographic cutaway pan", "low-angle tracking shot at 24fps").
2. Sensory & Surface Micro-Textures: Include 2 physical light/surface details ("volumetric tungsten dust motes", "subsurface scattering on translucent polymer", "rain streaking across anodized aluminum").
3. Safe-Zone Composition by Aspect Ratio:
   - If 9:16 (Shorts): Keep the primary kinetic subject inside the vertical center 55% of the frame (Y: 20% to 75%, X: 10% to 85%) so the bottom 25% and right 15% remain completely clear for dynamic mobile captions, YouTube UI icons, and the Related Video funnel link.
   - If 16:9 (Long-Form): Use rule-of-thirds wide staging with clean negative space on the left or right for kinetic data callouts.
4. Zero Gibberish Text Rule: Never ask Veo 3.1 to render complex multi-word paragraphs inside the raw video frame; render clean geometric plates and let `04_ffmpeg_assembler.py` composite crisp vector typography overlays.
5. Output Format:
   - START_FRAME_PROMPT (for Nano Banana 2): <1-sentence exact geometric state at t=0.0s>
   - END_FRAME_PROMPT (for Nano Banana 2, if state transition required): <1-sentence exact geometric state at t=5.0s>
   - VEO_3_1_MOTION_PROMPT: <65-85 word continuous prompt ordered as: [Template Style & Palette] + [Subject & Action] + [Camera Movement & Lens] + [Lighting & Atmosphere]>
```

## Step 3: Tiered Credit Optimization & Automatic Visual Critique Gate

To prevent burning Google Flow credits on hallmarked AI glitches, `agy` enforces a 3-tier rendering and critique loop:

1. **Tier 1 Pre-Flight (`Veo 3.1 Lite`) + Automated Frame Critique:**
   - Select model `Veo 3.1 Lite` in the Flow dropdown and render a draft pass using the Start Frame ingredient.
   - Have `agy` `/browser` capture keyframes at `t=0.5s`, `t=2.5s`, and `t=4.5s` and pass them through **Gemini Flash 1.1 Omni Visual QA**:
     - **Check A (Anatomy & Geometry):** Zero extra limbs, warped mechanical gears, or melting faces.
     - **Check B (Motion Continuity):** Camera movement matches the requested dolly/pan direction without sudden horizon flips.
     - **Check C (Safe-Zone Clearance):** For `9:16` clips, confirm the focal subject does not collide with the bottom 25% caption/funnel zone.
   - If any check fails, automatically mutate the seed and refine the motion prompt before escalating to Tier 2.

2. **Tier 2 Production Render (`Veo 3.1 Quality` for Hooks / `Veo 3.1 Fast` for Body):**
   - For the **first 30 seconds of Long-Form** and **all 4 Shorts hooks (00:00 to 00:12)**, switch model to `Veo 3.1 Quality` with Start + End Frame interpolation enabled.
   - For standard B-roll body scenes (00:30+ in Long-Form), use `Veo 3.1 Fast` to reduce credit burn by 60% while preserving 1080p visual fidelity.

3. **Scene Builder Sequencing & Export:**
   - Select all approved tiles (`Shift + Click` via CDP), add them to **Scene Builder**, verify cut continuity, and export master MP4s into `channels/{{channel_id}}/runs/{{run_id}}/raw_clips/`.
