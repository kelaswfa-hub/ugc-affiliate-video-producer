---
name: ugc-affiliate-video-producer
description: Create structured short-form UGC affiliate video production packs from product photos, model photos, product links, product names/descriptions, or brief prompts. Use when the user wants TikTok/Reels/Shorts affiliate concepts, hooks, scripts, storyboards, AI video prompts, Bumi Digital payload plans, caption packs, CTA packs, testing variations, or help choosing Seedance / Veo / Grok video models and durations.
---

# UGC Affiliate Video Producer

Use this skill to turn product context into an actionable UGC affiliate video pack.

Default output language is casual Bahasa Indonesia. Prefer English for AI image/video prompts unless the user asks otherwise.

## Main job

Produce practical short-form affiliate creative, not just ideas.

Typical outputs:
- recommended creative brief
- UGC angles
- hook options
- timestamped script
- 9:16 storyboard
- shot-by-shot AI video prompts
- Bumi Digital generation payload plan
- captions, CTA, hashtags, and test variations

## Required operating order

Follow this sequence:

```text
Validate minimum input
↓
Analyze available assets or link info
↓
If talent/influencer photo exists, convert it into a character sheet with GPT Image 2
↓
If GPT Image 2 fails, retry once with Nano Banana 2
↓
If Nano Banana 2 also fails, stop and report the failure
↓
Collect only missing brief details
↓
Lock AI video model + duration
↓
Adapt pacing to model/duration
↓
Generate production pack
↓
If asked, continue into Bumi Digital generation
```

Do not jump straight to the full pack when the user has not provided enough product context.

## 1. Validate minimum input first

Require at least one of:
- product photo
- model/talent photo plus clear product instruction
- product link
- clear product name
- clear product description

If none are present, stop and reply:

```text
Untuk membuat video UGC affiliate, saya butuh minimal salah satu dari berikut:

1. Foto produk
2. Foto wajah/model yang ingin digunakan
3. Link produk
4. Nama atau deskripsi produk yang jelas

Silakan upload salah satu atau semuanya, lalu saya akan bantu lanjutkan proses pembuatan video UGC affiliate-nya.
```

## 2. Analyze what is available

Extract whatever the user already gave instead of asking again.

### Product photo

Infer carefully:
- category
- appearance, color, shape, size, material impression
- visible branding or packaging
- best close-up and demo moments
- unclear areas that need confirmation

### Model photo

Use only prompt-relevant visual traits:
- apparent age range
- hair
- outfit
- expression
- general creator vibe
- framing and camera presence

Avoid sensitive or speculative traits.

If the user uploads a talent or influencer photo for UGC video generation, default to this prep flow before final video generation planning:
- use the Bumi Digital skill to edit the uploaded image with **GPT Image 2**
- create a **3-panel character sheet**
- required panels: **full body**, **half body**, **head shot**
- add a **black censor bar over the character's eyes**
- treat the resulting character sheet as the preferred character reference for downstream video generation
- if **GPT Image 2** fails, retry the same character-sheet step once with **Nano Banana 2**
- if **Nano Banana 2** also fails, stop the character-sheet flow and clearly report the failure to the user
- do not continue retry loops beyond that single fallback attempt

Default edit prompt for that step:

```text
buatkan character sheet dengan 3 panel: full body, half body, dan head shot. tutupi mata karakternya dengan garis hitam seperti sedang disensor matanya
```

Unless the user explicitly says otherwise, prefer the generated character sheet over the original uploaded talent photo when preparing Seedance, Veo, or Grok video prompts and payload plans.

### Product link

Use the link to gather:
- name
- category
- features
- benefits
- audience
- use cases
- likely objections
- claims that need compliance caution

If the link cannot be read, ask for pasted details or screenshots.

### User text

Extract:
- audience
- platform
- objective
- pain point
- CTA
- tone
- style
- language
- requested model or duration
- constraints

## 3. Ask only for missing brief fields

Keep questions light. Do not overwhelm the user.

If important brief fields are missing, ask only for the missing items. Offer `rekomendasikan` as a shortcut.

Minimum useful brief fields:
- target audience
- platform
- AI video model
- duration
- style
- tone
- CTA
- pain point
- objective
- language
- selling style

## 4. Lock model and duration before scripting

Model and duration control script length, shot count, pacing, and payload shape.

Supported user-facing options:
- Seedance 2.0 — 5s / 10s / 15s
- Seedance 2.0 Fast — 5s / 10s / 15s
- Google Veo 3.1 — 4s / 6s / 8s
- Google Veo 3.1 Fast — 4s / 6s / 8s
- Google Veo 3.1 Lite — 4s / 6s / 8s
- Grok Imagine Video — 5s / 10s / 15s

If the user says `rekomendasikan`, choose based on product, platform, and objective.

Default recommendation logic:
- best overall UGC quality: Seedance 2.0 — 15s
- fast testing: Seedance 2.0 Fast — 10s or 15s
- premium realism: Google Veo 3.1 — 8s
- lightweight draft: Google Veo 3.1 Lite — 8s
- viral experimental: Grok Imagine Video — 10s or 15s

If the user picks an unsupported duration, suggest the nearest valid one.

Read `references/model-and-output-guide.md` when you need the duration rules, shot count rules, recommended structures, or output templates.

## 5. Apply audio policy

Assume the selected video model handles built-in voice/audio unless the user explicitly asks for separate audio work.

By default:
- do not create separate voiceover workflow
- do not create separate music workflow
- do not create separate SFX workflow
- include dialogue, ambience, and light SFX inside the video prompt

Keep audio direction simple for 4s–5s clips, richer for 10s–15s clips.

## 6. Build the production pack

Unless the user asks for a quick version, produce a full structured pack.

Default section order:

```markdown
# UGC Affiliate Video Production Pack

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

### Quick pack mode

If the user wants something quick, include only:
- recommended creative brief
- chosen model and duration
- pacing plan
- 3 angles
- 5 hooks
- 1 script
- 1 storyboard
- 3 AI video prompts
- Bumi payload plan
- caption + CTA + hashtags

## 7. Output rules

### Hooks

Generate strong first-1-to-3-second hooks. Common families:
- pain
- curiosity
- POV
- personal experience
- confession
- before/after
- discovery
- contrarian
- stop-scrolling

### Script

Make it:
- natural
- conversational
- UGC-style
- easy to perform or generate
- conversion-aware but not overly salesy unless requested
- short enough for the chosen duration

### Storyboard

Use vertical 9:16 by default.

Include:
- shot number
- timestamp
- visual
- camera direction
- dialogue/voiceover
- audio direction
- text overlay
- scene purpose

### AI video prompts

Make each prompt self-contained. Repeat critical character, product, and setting details in every shot.

Do not rely on:
- same character
- same product
- previous shot
- same room

Include:
- model
- shot duration
- 9:16 aspect ratio
- character description when relevant
- product description when relevant
- setting
- action
- camera
- lighting
- mood
- spoken line
- built-in audio direction
- text overlay
- negative prompt if useful

### Seedance-specific output rule

If the selected model is **Seedance 2.0** or **Seedance 2.0 Fast**, always write the final video prompt in a **single multi-shot prompt block** with explicit time markers.

Required format style:
- one combined prompt for the whole video
- use shot timing labels such as `Shot 1 (0–3s)`, `Shot 2 (3–6s)`, `Shot 3 (6–9s)`
- describe each shot in sequence inside the same prompt
- include spoken dialogue and text overlay for each shot inside that combined prompt
- keep it detailed, production-oriented, and easy to paste directly into Seedance

For Seedance outputs, prefer this combined multi-shot format over isolated per-shot prompt blocks.

For non-Seedance models, keep using the normal shot-by-shot prompt format unless the user asks otherwise.

## 8. Bumi Digital integration

Use Bumi Digital as the generation provider when the user wants actual media generation and tool access is available.

For video generation, use a strict single-attempt policy: if one generation attempt fails, stop and report the failure without automatic retry.

### Character-sheet prep flow for talent photos

If a talent/influencer photo is provided for a UGC video workflow, insert this image-edit step before video generation:
1. use the Bumi Digital skill image editing flow with **GPT Image 2**
2. transform the talent photo into a **3-panel character sheet**
3. panels must be: **full body**, **half body**, **head shot**
4. add a **black censor bar over the eyes**
5. if **GPT Image 2** fails, retry the same step once with **Nano Banana 2**
6. if **Nano Banana 2** also fails, stop and report the failure to the user without additional retries
7. use the edited character sheet as the main character reference in later video payloads

Default prompt for the image edit step:

```text
buatkan character sheet dengan 3 panel: full body, half body, dan head shot. tutupi mata karakternya dengan garis hitam seperti sedang disensor matanya
```

### Video generation flow

Before generating:
1. confirm model
2. confirm duration
3. verify the duration is supported
4. if talent photo exists, create character sheet first
5. upload product references and the character sheet if needed
6. prepare payload
7. submit job once only
8. if the generation attempt fails, stop and clearly report the failure to the user
9. do not retry the same video generation request automatically
10. if the job succeeds, return result URLs or files

Do not hardcode exact model IDs unless confirmed from the live Bumi model list.
Use user-facing model names in planning when the exact live model ID is not yet confirmed.

## 9. Compliance rules

Avoid false, absolute, or unsupported claims.

Never generate claims like:
- pasti sembuh
- dijamin kaya
- 100% terbukti
- aman untuk semua orang
- hasil permanen
- langsung berhasil dalam 1 hari

Prefer safer phrasing like:
- bisa membantu
- bisa jadi opsi
- terasa lebih praktis
- menurut pengalaman
- worth it buat dicoba
- hasil bisa berbeda tergantung pemakaian

## 10. Default assumptions

If the user leaves details open, default to:
- platform: TikTok / Instagram Reels
- aspect ratio: 9:16
- model: Seedance 2.0
- duration: 15s
- language: Bahasa Indonesia
- tone: casual, relatable, natural
- selling style: soft selling
- objective: affiliate conversion
- style: problem-solution + honest review
- CTA: cek link di bio / klik keranjang

## 11. User-facing failure message templates

Use consistent, plain, user-facing error messages when media generation fails.

### A. Character sheet generation failed after fallback

Use when **GPT Image 2** failed and the single fallback attempt with **Nano Banana 2** also failed.

Template:

```text
Character sheet influencer belum berhasil dibuat.

Saya sudah mencoba:
1. GPT Image 2
2. Nano Banana 2

Keduanya gagal pada percobaan ini, jadi proses saya hentikan dulu tanpa retry tambahan.

Kalau mau, saya bisa lanjut bantu dengan salah satu opsi berikut:
- rapikan prompt character sheet-nya dulu
- pakai foto influencer lain
- lanjut bikin production pack tanpa character sheet
```

### B. Video generation failed

Use when the video generation job fails on its first and only attempt.

Template:

```text
Video belum berhasil digenerate.

Percobaan generate video gagal, dan sesuai flow saat ini proses saya hentikan dulu tanpa retry otomatis.

Kalau mau, saya bisa bantu lanjut dengan salah satu opsi berikut:
- review prompt videonya dulu
- sederhanakan adegan atau gerakan
- ganti model atau durasi video
- siapkan ulang payload generation yang lebih aman
```

### C. Short failure version

Use this shorter version when the chat context needs a compact update.

Character sheet short version:

```text
Character sheet belum berhasil dibuat. Saya sudah coba GPT Image 2 lalu fallback ke Nano Banana 2, tapi keduanya gagal. Proses saya stop dulu tanpa retry tambahan.
```

Video short version:

```text
Video belum berhasil digenerate. Percobaan pertama gagal, jadi proses saya stop dulu tanpa retry otomatis.
```

### D. Reporting rule

When reporting failures:
- say clearly what failed
- mention which model or step was attempted
- mention whether a fallback was attempted
- state that the process was stopped
- do not promise hidden retries
- offer 2 to 4 concrete next-step options

## 12. End with a concrete next step

Always end with a direct next step, for example:
- ask the user to choose an angle
- ask for product/model photo to improve consistency
- offer final per-shot prompts for Seedance/Veo/Grok
- offer Bumi Digital generation if they want to continue into production
