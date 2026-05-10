# Model and Output Guide

Use this reference when you need exact model choices, duration-aware pacing, shot-count guidance, or reusable output templates.

## 1. Supported model families

### Seedance 2.0
- durations: 5s, 10s, 15s
- best for: polished UGC, problem-solution stories, richer demos
- default recommendation: 15s for full affiliate creative

### Seedance 2.0 Fast
- durations: 5s, 10s, 15s
- best for: rapid testing, low-friction variations, hook experiments
- default recommendation: 10s or 15s

### Google Veo 3.1
- durations: 4s, 6s, 8s
- best for: premium realism, beauty, luxury, lifestyle, polished scenes
- default recommendation: 8s

### Google Veo 3.1 Fast
- durations: 4s, 6s, 8s
- best for: quicker premium-style variants

### Google Veo 3.1 Lite
- durations: 4s, 6s, 8s
- best for: drafts, concept validation, lower-cost exploration
- default recommendation: 8s

### Grok Imagine Video
- durations: 5s, 10s, 15s
- best for: bold hooks, viral-native experiments, novelty products
- default recommendation: 10s or 15s

## 2. Duration planning rules

### 4 seconds
- use for: hook only, teaser, beauty shot, micro CTA
- structure: 0–1s hook, 1–3s reveal/use, 3–4s CTA
- shots: 1
- dialogue: 1 short sentence, about 5–8 words

### 5 seconds
- use for: hook testing, teaser, problem + reveal
- structure: 0–2s hook, 2–4s reveal/use, 4–5s CTA
- shots: 1–2
- dialogue: 1 short sentence, about 8–12 words

### 6 seconds
- use for: compact problem-solution or demo
- structure: 0–2s hook, 2–5s use, 5–6s CTA
- shots: 1–2
- dialogue: 1–2 short sentences, about 10–16 words total

### 8 seconds
- use for: compact complete UGC, premium teaser, short problem-solution
- structure: 0–2s hook, 2–5s reveal/demo, 5–7s benefit, 7–8s CTA
- shots: 2–3
- dialogue: 2 short sentences, about 16–24 words total

### 10 seconds
- use for: strong short UGC, quick review, demo, product discovery
- structure: 0–3s hook, 3–6s reveal/use, 6–9s benefit/reaction, 9–10s CTA
- shots: 3–4
- dialogue: 2–3 short sentences, about 24–35 words total

### 15 seconds
- use for: complete affiliate creative with problem, demo, benefit, CTA
- structure: 0–3s hook, 3–6s reveal, 6–10s demo, 10–13s benefit, 13–15s CTA
- shots: 4–5
- dialogue: 3–5 short sentences, about 35–55 words total

## 3. Storyboard guidance by model family

### Seedance family
- default format: 9:16
- camera style: natural handheld UGC
- prompt style: explicit timing and shot purpose
- shot range: 5s = 1–2, 10s = 3–4, 15s = 4–5
- best for multi-shot structure
- final prompt output rule: prefer **one combined multi-shot Seedance prompt** with explicit time markers per shot, not separate isolated shot prompts
- include text overlays and spoken lines inline under each timed shot section

### Veo family
- default format: 9:16
- style: compact, visually clear, realistic, less crowded
- shot range: 4s = 1, 6s = 1–2, 8s = 2–3
- avoid too many actions in one prompt

### Grok family
- default format: 9:16
- style: bold, punchy, social-native pacing
- shot range: 5s = 1–2, 10s = 2–4, 15s = 4–5
- favor surprising hooks and simple stories

## 4. Audio policy

All supported models are treated as built-in audio/voice capable in this workflow.

Default behavior:
- include dialogue in the video prompt
- include room tone or subtle ambience in the video prompt
- include light product handling sounds when useful
- do not make separate voiceover/music/SFX assets unless explicitly requested

Audio prompt heuristic:
- 4s–5s: one spoken line max, minimal ambience
- 6s–8s: one or two short lines, subtle ambience
- 10s–15s: natural dialogue, light ambience, soft handling sound, optional subtle background music

## 5. Fallback duration rules

If the requested duration is unsupported, suggest the closest valid value.

Examples:
- Seedance request 8s → suggest 10s
- Veo request 10s → suggest 8s
- Grok request 8s → suggest 10s

## 6. Recommended creative brief template

```markdown
## Recommended Creative Brief

### Target Audience
...

### Platform
...

### AI Video Model
...

### Duration
...

### Video Style
...

### Tone
...

### CTA
...

### Pain Point
...

### Objective
...

### Language
...

### Selling Style
...

### Audio/Voice/SFX
Use built-in audio/voice from the selected AI video model. Dialogue, ambience, and simple SFX are included directly inside the AI video prompt. No separate audio generation is needed.
```

## 7. Script table template

```markdown
## Main UGC Script

**AI Video Model:** ...
**Duration:** ...
**Platform:** ...
**Tone:** ...
**Style:** ...
**Audio/Voice:** Built into generated video. No separate voiceover or SFX asset needed.

| Time | Visual | Dialogue / Voiceover | Audio / SFX Direction | Text Overlay |
|---|---|---|---|---|
| ... | ... | ... | ... | ... |
```

## 8. Storyboard table template

```markdown
## Storyboard 9:16

**Selected Model:** ...
**Selected Duration:** ...
**Audio/Voice/SFX:** Generated directly by selected AI video model.

| Shot | Time | Visual | Camera | Dialogue / Voiceover | Audio / SFX Direction | Text Overlay | Scene Purpose |
|---|---|---|---|---|---|---|---|
| ... | ... | ... | ... | ... | ... | ... | ... |
```

## 9. AI prompt template

### Default non-Seedance template

```markdown
### Shot X — [Scene Name]

**Selected Model:** ...
**Duration:** ...
**Aspect Ratio:** 9:16
**Audio/Voice/SFX:** Built into generated video. No separate audio generation needed.

**Prompt:**
[A self-contained English prompt with repeated character/product details, setting, action, camera, lighting, mood, spoken line, and built-in audio direction.]

**Text Overlay:**
...

**Camera:**
...

**Negative Prompt:**
Do not make it look like a polished studio commercial. Avoid distorted hands, inconsistent product shape, unreadable text, blurry product details, and robotic speech.
```

### Required Seedance template

Use this format whenever the selected model is **Seedance 2.0** or **Seedance 2.0 Fast**.

```markdown
## Seedance Final Video Prompt

**Selected Model:** Seedance 2.0 or Seedance 2.0 Fast
**Duration:** ...
**Aspect Ratio:** 9:16
**Audio/Voice/SFX:** Built into generated video. No separate audio generation needed.

**Prompt:**
Create a realistic vertical 9:16 multi-shot UGC video ...

Shot 1 (0–3s):
[scene direction]
Dialogue: "..."
Text overlay on screen: "..."

Shot 2 (3–6s):
[scene direction]
Dialogue: "..."
Text overlay on screen: "..."

Shot 3 (6–9s):
[scene direction]
Dialogue: "..."
Text overlay on screen: "..."

Shot 4 (9–10s):
[scene direction]
Dialogue: "..."
Text overlay on screen: "..."

Use smooth realistic motion, natural handheld framing, and detailed continuity across all shots.

**Negative Prompt:**
Do not make it look like a polished studio commercial. Avoid distorted hands, inconsistent product shape, unreadable text overlays, blurry product details, and robotic speech.
```

## 10. Payload planning template

Use user-facing names until the live Bumi model ID is confirmed.

If a talent/influencer photo exists, first create a character sheet through Bumi Digital image editing.

Use this exact default prompt:

```text
buatkan character sheet dengan 3 panel: full body, half body, dan head shot. tutupi mata karakternya dengan garis hitam seperti sedang disensor matanya. Jangan merubah outfit nya
```

Keep that prompt text unchanged unless the user explicitly asks to modify it.

Character-sheet model rules:
- primary model: **OpenAI GPT Image 2**
- GPT Image 2 input image field: **`input_images`**
- GPT Image 2 aspect ratio: **`3:2`**
- fallback model: **Google Nano Banana 2**
- Nano Banana 2 input image field: **`image_input`**
- Nano Banana 2 aspect ratio: **`16:9`**
- upload the source talent/influencer photo first and pass the hosted Bumi file URL into the model-specific image input field

Example payload — GPT Image 2 character sheet:

```json
{
  "model_id": "openai/gpt-image-2",
  "parameters": {
    "prompt": "buatkan character sheet dengan 3 panel: full body, half body, dan head shot. tutupi mata karakternya dengan garis hitam seperti sedang disensor matanya. Jangan merubah outfit nya",
    "input_images": [
      "https://storage.bumi.digital/uploads/source-talent-photo.jpg"
    ],
    "aspect_ratio": "3:2",
    "quality": "high",
    "output_format": "png"
  }
}
```

Example payload — Nano Banana 2 fallback character sheet:

```json
{
  "model_id": "google/nano-banana-2",
  "parameters": {
    "prompt": "buatkan character sheet dengan 3 panel: full body, half body, dan head shot. tutupi mata karakternya dengan garis hitam seperti sedang disensor matanya. Jangan merubah outfit nya",
    "image_input": [
      "https://storage.bumi.digital/uploads/source-talent-photo.jpg"
    ],
    "aspect_ratio": "16:9",
    "resolution": "2K",
    "output_format": "png"
  }
}
```

Then use the resulting character sheet as the preferred character reference in the video payload.

```json
{
  "model_family": "Seedance 2.0",
  "model_variant": "Seedance 2.0",
  "task_type": "text-to-video or image-to-video",
  "duration": 15,
  "aspect_ratio": "9:16",
  "resolution": "720p",
  "prompt": "...",
  "audio_mode": "built-in model audio/voice",
  "separate_audio_generation": false,
  "reference_images": [
    {
      "type": "product_reference",
      "source": "uploaded product photo or generated URL"
    },
    {
      "type": "character_sheet_reference",
      "source": "GPT Image 2 edited character sheet URL"
    }
  ]
}
```

## 11. Default final section order

```markdown
## 1. Input Summary
## 2. Product Analysis
## 3. Asset Analysis
## 4. Selected AI Video Model & Duration
## 5. Recommended Creative Brief
## 6. Duration-Based Pacing Plan
## 7. UGC Angle Ideas
## 8. Selected Main Angle
## 9. Hook Options
## 10. Main UGC Script
## 11. Storyboard 9:16
## 12. AI Video Prompts for Selected Model
## 13. Bumi Digital Generation Payload Plan
## 14. Text Overlay Pack
## 15. Affiliate Copywriting Pack
## 16. CTA Options
## 17. Hashtag Pack
## 18. Variation & Testing Pack
## 19. Compliance Notes
```
