# UGC Affiliate Video Producer

An OpenClaw skill for turning product context into a structured short-form UGC affiliate video production pack.

This skill is designed for creators, affiliate marketers, and AI-assisted production workflows that need practical outputs such as hooks, scripts, storyboards, video prompts, and Bumi Digital payload planning.

## What this skill does

Given one or more of the following:
- product photo
- model/talent photo
- product link
- product name
- product description
- brief text instruction

this skill helps produce:
- recommended creative brief
- model and duration recommendation
- UGC angle ideas
- hook options
- timestamped UGC script
- 9:16 storyboard
- shot-by-shot AI video prompts
- Bumi Digital generation payload plan
- caption, CTA, hashtag, and testing pack

## Main use cases

Use this skill when you want to create short-form affiliate or UGC-style content for:
- TikTok
- Instagram Reels
- YouTube Shorts
- Facebook Reels
- short-form ads
- product review videos
- product demo videos
- problem-solution videos
- testimonial-style UGC
- marketplace affiliate content

## Input requirements

The skill does **not** jump straight into generating a full production pack without enough context.

Minimum valid input is at least one of:
- product photo
- model/talent photo with clear product instruction
- product link
- clear product name
- clear product description

If the user provides none of the above, the skill is expected to stop and ask for the minimum required source first.

## Workflow summary

The skill follows this order:

1. Validate minimum input
2. Analyze available product/assets
3. Collect only the missing creative brief details
4. Lock AI video model and duration
5. Adapt pacing to model/duration
6. Generate the production pack
7. Continue into Bumi Digital generation only when requested

## Supported video model families

The skill is written to support these user-facing model options:
- Seedance 2.0
- Seedance 2.0 Fast
- Google Veo 3.1
- Google Veo 3.1 Fast
- Google Veo 3.1 Lite
- Grok Imagine Video

It also includes recommendation logic so the agent can choose a sensible default when the user says things like:
- "rekomendasikan"
- "terserah"
- "pilihkan yang terbaik"

## Audio policy

By default, the skill assumes the selected AI video model can generate built-in audio or voice.

That means it prefers:
- dialogue inside the video prompt
- ambience inside the video prompt
- simple SFX inside the video prompt

It does **not** create separate voiceover, music, or SFX workflows unless the user explicitly asks for them.

## Output style

Default response language is Bahasa Indonesia for:
- script dialogue
- CTA
- captions
- text overlays
- hashtags

AI video prompts are generally written in English for better model compatibility unless the user asks otherwise.

## Files in this skill

- `SKILL.md` — main operating instructions
- `references/model-and-output-guide.md` — model guidance, duration rules, templates, and payload planning structure

## Bumi Digital integration

This skill is designed to work well with the Bumi Digital skill as the generation provider.

Typical handoff includes:
- selecting the proper model family
- mapping duration to valid model limits
- preparing prompt structure
- preparing payload-ready planning for image-to-video or text-to-video generation

## Repository

GitHub repo:
- <https://github.com/kelaswfa-hub/ugc-affiliate-video-producer>

## Release artifact

Packaged skill artifact:
- `ugc-affiliate-video-producer.skill`

## Notes

This repository is meant to hold the skill source and release artifact history.

The actual usage instructions for OpenClaw are primarily inside `SKILL.md`.
