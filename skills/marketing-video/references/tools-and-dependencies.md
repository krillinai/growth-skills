# Marketing Video Tools And Dependencies

Use this reference when selecting a production path or explaining API, Key, account, network, runtime, budget, market, and delivery dependencies. Verify current provider capabilities, model names, regional availability, pricing, limits, terms, and API documentation from dated official sources before making a recommendation.

## Contents

- Production paths
- Provider and framework families
- Capability questions
- Credential report
- Local runtime
- KrillinAI routing
- Deterministic media tools
- Selection logic
- Freshness record

## Production Path Matrix

| Path | Good fit | Required configuration | Main limitations |
| --- | --- | --- | --- |
| Agent-provided video capability | Fast generation or editing inside the current agent environment | Confirm the tool exists, accepts the required inputs, and returns inspectable local artifacts | User may not control exact model, queue, region, retention, or settings |
| Direct provider API | Automated generation, editing, avatars, voice, or batch workflows | Provider account, API Key or OAuth, billing or credits, network, SDK or HTTP client | Cost, asynchronous jobs, rate limits, content rules, retention, and version changes |
| Hosted inference provider | Multiple hosted video or audio models through one service | Provider account, Token, credits, network, selected model and version | Additional provider layer, changing catalog, queue, and output retention |
| Hosted editing or avatar application | Human-directed editing, captions, dubbing, presenter, or design work | Third-party account, subscription or credits, browser | Manual handoff, limited automation, export limits, identity and workspace controls |
| Programmatic renderer | Templates, data-driven videos, exact text, repeatability, and batch output | Code, assets, fonts, renderer, browser engine where used, FFmpeg, Node.js or framework runtime | Requires implementation, testing, and render capacity |
| Local or self-hosted inference | Private, controllable, experimental, or high-volume generation | GPU, model weights, storage, Python, inference graph or service, FFmpeg | Installation, model licensing, long renders, quality tuning, and maintenance |
| KrillinAI pipeline | Subtitle, translation, dubbing, horizontal or vertical rendering, and chained localization | Installed CLI, supported source, configured upstream services, local media dependencies | Stage-specific configuration, source quality, and review requirements |
| Deterministic media pipeline | Screen capture, edit, transcode, crop, pad, overlay, captions, audio, packaging, and QA | Rights-cleared sources, project instructions, codecs, FFmpeg or equivalent | Does not synthesize original footage or secure missing rights |

## Provider And Framework Families To Evaluate

International candidates may include OpenAI video capabilities, Google video generation, Runway, Luma, Pika, HeyGen, Synthesia, Adobe or other editing services, and authorized hosts for current video or audio models. Programmatic options may include Remotion, HTML/CSS/JavaScript video renderers, browser-based capture, motion-graphics templates, or a custom FFmpeg pipeline. Treat every name as a candidate to verify, not a required or permanently available choice.

For China, evaluate current official options such as Kuaishou Kling, Volcano Engine or ByteDance video services, MiniMax or Hailuo, Tencent Hunyuan video capabilities, Alibaba Cloud Bailian or Wan video models, ModelScope-hosted or downloadable models, KrillinAI workflows, ComfyUI-compatible local models, and authorized domestic editing, avatar, voice, or inference platforms. Separate service availability, account eligibility, real-name or business verification, payment, invoice, region, data location, content review, watermark or disclosure, API access, voice and likeness terms, and commercial-use rights.

Do not assume the reference project's model versions, maximum duration, resolution, native audio, API support, price, or regional access remain current.

## Capability Questions

Check the task against:

- text-to-video, image-to-video, video-to-video, keyframe, storyboard, reference, character, object, and style consistency;
- inpainting, outpainting, background, relighting, motion transfer, extension, interpolation, restyle, and lip sync;
- prompt and camera control, shot duration, continuity, frame rate, ratio, resolution, native audio, transparency, and export formats;
- presenter, avatar, voice, voice clone, pronunciation, emotion, language, translation, dubbing, and disclosure support;
- transcript, captions, subtitles, speaker detection, music, sound effects, stems, and audio cleanup;
- exact text, logo, product UI, screen capture, charts, templates, overlays, and brand-system control;
- batch, asynchronous jobs, callbacks, retries, cancellation, seeds, templates, personalization, and reproducibility;
- project files, source retention, output expiry, provenance, watermark, metadata, deletion, and training-use controls;
- latency, queue, rate limit, cost per second or minute, subscription, credits, failed-job billing, and render infrastructure.

No generative model is automatically suitable for exact product UI, approved logos, legal copy, attributable charts, customer testimony, real events, or identity evidence. Use real captures and deterministic layers for those elements.

## Credential And Configuration Report

Report dependencies without exposing secrets:

```text
Primary mode:
Production path:
Provider or local tool:
Interface: built-in tool | API | hosted app | local service | CLI | programmatic renderer
Video capability available: yes | no | unknown
Audio or voice capability available: yes | no | not required | unknown
Subtitle or translation capability available: yes | no | not required | unknown
Render and inspection capability available: yes | no | unknown
API connection: required | optional | not required
Credential type: API Key | OAuth | Token | account login | none
Credential configured: yes | no | unknown
Third-party account: required | optional | not required
Billing or credits: required | optional | not required | unknown
Network access: required | optional | not required
Queue, quota, duration, and resolution limits:
Local runtime and packages:
GPU, memory, disk, model, and render requirements:
Market or regional constraints:
Data, retention, identity, voice, music, and rights constraints:
Fallback for each unavailable stage:
```

Do not request the secret value. Prefer an environment variable, secret manager, provider-specific credential store, or already authorized tool. Do not print environment variables, configuration files, tokens, cookies, authorization headers, or signed media URLs. A successful credential check proves only technical access.

## Local And Self-Hosted Runtime

For local generation or rendering, verify:

- operating system and supported GPU or accelerator;
- GPU or unified memory for the selected model, resolution, frame count, batch, and workflow;
- Python, Node.js, package manager, browser runtime, FFmpeg, ffprobe, ComfyUI or equivalent versions;
- model weights, text encoders, VAE, adapters, control models, nodes, plugins, fonts, and licenses;
- source and output codecs, hardware encoding support, disk capacity, cache, temp space, and cleanup policy;
- local HTTP endpoint, CLI, render command, queue behavior, failure handling, and output location;
- workflow, model hash, seed, sampler, steps, frame settings, interpolation, and encode settings where relevant.

Do not claim a model or template will render from its name alone. Verify the actual hardware, workflow, fonts, codecs, source media, and dependencies.

## KrillinAI Routing

When installed, authorized, and suitable:

- use `krillinai-subtitle` for transcription and subtitle generation;
- use `krillinai-tts` for target-language dubbing from reviewed subtitle input;
- use `krillinai-render-horizontal` for landscape rendering;
- use `krillinai-render-vertical` for portrait rendering and reframing;
- use `krillinai-pipeline` for multi-stage subtitle, translation, dubbing, and render workflows.

Check the selected KrillinAI workflow's actual source, target language, provider, model, credentials, media tools, output paths, and review requirements. Installing KrillinAI does not establish voice, music, footage, product, translation, platform, or publication rights.

## Deterministic Media And QA Tools

Useful categories include:

- FFmpeg for transcode, trim, concat, crop, pad, scale, overlay, audio, captions, and packaging;
- ffprobe or equivalent metadata inspection for duration, streams, codecs, dimensions, frame rate, audio, and file integrity;
- programmatic video frameworks for exact text, brand templates, data-driven scenes, and batch rendering;
- browser or device capture for real product workflows;
- waveform, loudness, subtitle, transcript, and caption inspection tools;
- ImageMagick or image utilities for frames, thumbnails, contact sheets, and overlays;
- media players and representative destination players for visual, audio, caption, and safe-area QA.

Check installation and supported codecs before use. Preserve masters, work in versioned outputs, and inspect the complete rendered result after every transcode, dub, caption, crop, or automated edit.

## Selection Logic

```text
Need only a brief or script?
|- Yes -> no generation API, video provider account, or renderer is required.
`- No -> identify the actual production or adaptation stages.
   |- Built-in video capability available -> use it; user-managed Key may not be required.
   |- External provider selected -> verify account, Key or OAuth, billing, queue, network, rights, and region.
   |- Programmatic renderer selected -> verify code runtime, fonts, assets, browser engine, FFmpeg, and render capacity.
   |- Local model selected -> verify model, GPU, memory, storage, workflow, license, and encode tools.
   |- KrillinAI stage selected -> verify the relevant installed skill, provider configuration, source, language, and local media tools.
   `- Required stage unavailable -> return the script, prompts, edit list, project specification, and handoff.

Need exact product UI, text, logo, chart, captions, or repeatable layout?
|- Yes -> use real capture or deterministic composition for that layer.
`- No -> generation may create the supporting visual layer.
```

## Freshness Record

When recommendations depend on current tools, record:

- provider, framework, model, and product name;
- official source URL;
- source publication or update date when available;
- access date;
- verified input, output, API, account, price basis, queue, limit, region, retention, and terms;
- facts still unavailable or inferred.

Do not copy an old provider comparison table forward without revalidation.
