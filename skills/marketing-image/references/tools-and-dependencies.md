# Marketing Image Tools And Dependencies

Use this reference when selecting a production tool or explaining API, Key, account, network, runtime, budget, and market dependencies. Verify current provider capabilities, model names, regional availability, pricing, limits, terms, and API documentation from dated official sources before making a recommendation.

## Production Path Matrix

| Path | Good fit | Required configuration | Main limitations |
| --- | --- | --- | --- |
| Agent-provided image capability | Fast creation or editing inside the current agent environment | Confirm the tool is available and local file outputs can be inspected | User may not control model, retention, region, quota, or exact settings |
| Direct provider API | Automated or repeatable generation, editing, and batch workflows | Provider account, API Key or OAuth, billing or credits, network, SDK or HTTP client | Cost, rate limits, content policy, data handling, and version changes |
| Hosted inference provider | Access to multiple hosted models through one service | Provider account, Token, credits, network, selected model and version | Additional provider layer, changing catalog, queue, and output retention |
| Hosted web application | Human-directed art exploration or design work | Third-party account, subscription or credits, browser | Weak automation, manual download, uncertain API availability |
| Design platform | Exact brand layout, templates, review, and many size variants | Account and workspace access; OAuth or Token only for authorized automation | Requires a design system and deterministic production work |
| Local or self-hosted inference | Private, controllable, or high-volume workflows | Compatible GPU or accelerator, model weights, storage, runtime, nodes or plugins | Installation, model licensing, quality tuning, maintenance, and compute cost |
| Deterministic renderer | Text, logo, screenshot, chart, layout, resize, crop, and export | Local source assets and installed library or CLI | Does not synthesize an original visual field by itself |

## Provider Families To Evaluate

Examples may include OpenAI image generation, Google Gemini image capabilities, Black Forest Labs FLUX and its authorized hosts, Ideogram, Recraft, Stability AI, Adobe or design-platform generation, and other current providers. Do not assume a named family, model version, API, price, or feature remains available.

For China, evaluate current official options such as Volcano Engine or Doubao image services, Alibaba Cloud Bailian or Tongyi Wanxiang, Tencent Cloud Hunyuan, Baidu AI Cloud Qianfan, ModelScope-hosted or downloadable models, ComfyUI-compatible local models, and authorized domestic design or inference platforms. Treat these only as candidates to verify. Separate service availability, account eligibility, real-name or business verification, payment, invoice, region, data location, content review, watermark or disclosure, API access, and commercial-use terms.

## Capability Questions

Check the specific task against:

- text-to-image, image-to-image, multi-reference, style reference, and product reference support;
- masking, inpainting, outpainting, background removal, object replacement, and relighting;
- reliable text rendering, layout control, logo preservation, and typography;
- aspect ratio, exact dimensions, resolution, upscaling, transparency, vector, and file formats;
- seed, deterministic settings, batch, asynchronous jobs, callbacks, and output retention;
- safety filters, content categories, person and public-figure rules, watermarking, and disclosure;
- model and output commercial terms, source-data treatment, privacy, region, and deletion controls;
- latency, concurrency, rate limit, cost, credits, minimum subscription, and retry behavior.

No model is automatically suitable for exact product UI, approved logos, legal copy, attributable charts, or documentary proof. Use deterministic composition or real captures for those layers.

## Credential And Configuration Report

Report dependencies without exposing secrets:

```text
Production path:
Provider or local tool:
Interface: built-in tool | API | hosted app | local service | CLI
Image capability available: yes | no | unknown
API connection: required | optional | not required
Credential type: API Key | OAuth | Token | account login | none
Credential configured: yes | no | unknown
Third-party account: required | optional | not required
Billing or credits: required | optional | not required | unknown
Network access: required | optional | not required
Local runtime and packages:
GPU, memory, disk, and model requirements:
Market or regional constraints:
Data, retention, and rights constraints:
Fallback if unavailable:
```

Do not request the secret value. Prefer an environment variable, secret manager, provider-specific credential store, or already authorized tool. Do not print environment variables, configuration files, tokens, cookies, or authorization headers. A successful credential check only proves technical access.

## Local And Self-Hosted Runtime

For local generation, verify:

- operating system and supported accelerator;
- GPU or unified memory capacity for the selected model and output size;
- Python, package manager, inference server, ComfyUI or equivalent version;
- model weights, VAE, text encoders, adapters, control models, nodes, and licenses;
- download size, disk capacity, cache location, output location, and cleanup policy;
- local HTTP endpoint or CLI behavior if the agent will invoke the service;
- reproducibility metadata such as workflow, model hash, seed, sampler, steps, and scale where relevant.

Do not claim a local model will run from model name alone. Verify the actual hardware and workflow.

## Deterministic Production And Optimization Tools

Useful categories include:

- ImageMagick for resize, crop, composite, format conversion, metadata, and inspection;
- libvips or Sharp for efficient programmatic pipelines;
- `cwebp` and `avifenc` for web formats;
- `pngquant` or `oxipng` for PNG optimization;
- `jpegoptim` or an equivalent encoder for JPEG optimization;
- HTML/CSS or a design template renderer for exact text and layout;
- browser screenshot tools for real product captures;
- charting libraries for attributable diagrams and data graphics.

Check installation and supported formats before use. Preserve originals, work in a versioned output location, and inspect the result after every lossy conversion or automated crop.

## Selection Logic

```text
Need an actual file now?
|- No -> brief or audit; no generation API is required.
`- Yes -> confirm a production capability exists.
   |- Built-in image capability available -> use it; user-managed Key may not be required.
   |- External provider selected -> verify account, Key or OAuth, billing, network, rights, and region.
   |- Local model selected -> verify runtime, model, hardware, storage, and license.
   `- No generation capability -> use real sources plus deterministic composition, or return a production handoff.

Need exact text, logo, UI, chart, or repeated layout?
|- Yes -> use deterministic composition for that layer.
`- No -> generation or editing may produce the visual field.
```

## Freshness Record

When recommendations depend on current tools, record:

- provider and product name;
- official source URL;
- source publication or update date when available;
- access date;
- verified features, limits, price basis, region, and terms;
- facts still unavailable or inferred.

Do not copy an old model comparison table forward without revalidation.
