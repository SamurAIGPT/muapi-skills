# 🎭 Generative Media Skills for AI Agents

**The Ultimate Multimodal Toolset for Claude Code, Cursor, and Gemini CLI.**
A high-performance, schema-driven architecture for AI agents to generate, edit, and display professional-grade images, videos, and audio — powered by the [muapi-cli](https://github.com/SamurAIGPT/muapi-cli).


[🚀 Get Started](#-quick-start) | [🎬 Recipe Pack](#-recipe-pack) | [🎨 Expert Library](#-expert-library) | [⚙️ Core Primitives](#-core-primitives) | [🤖 MCP Server](#-mcp-server) | [📖 Reference](#-schema-reference)

---

## Related Projects

- [MuAPI](https://muapi.ai) — Unified API for image, video, and audio generation across hundreds of AI models.
- [Agent Skills guide](https://muapi.ai/agent-skills) — How coding agents discover, price and run MuAPI models, plus the MCP server and CLI.
- [MuAPI MCP Server](https://muapi.ai/docs/mcp) — Use the same models as tool calls in Claude Code, Cursor and Windsurf.

## ✨ Key Features

- **🤖 Agent-Native Design** — CLI-powered scripts with structured JSON outputs, semantic exit codes, and `--jq` filtering for seamless agentic pipelines.
- **🧠 Expert Knowledge Layer** — Domain-specific skills that bake in professional cinematography, atomic design, and branding logic.
- **⚡ CLI-Powered Core** — All primitives delegate to [`muapi-cli`](https://www.npmjs.com/package/muapi-cli) — no curl, no JSON parsing, no boilerplate.
- **🖼️ Direct Media Display** — Use the `--view` flag to automatically download and open generated media in your system viewer.
- **📁 Local File Support** — Auto-upload images, videos, faces, and audio from your local machine to the CDN for processing.
- **🌈 100+ AI Models** — One-click access to **Midjourney v7, Flux Kontext, Seedance 2.0, Kling 3.0, Veo3**, and more.
- **🔌 MCP Server** — Run `muapi mcp serve` to expose all 19 tools directly to Claude Desktop, Cursor, or any MCP-compatible agent.

---

## 🏗️ Scalable Architecture

This repository uses a **Core/Library** split to ensure efficiency and high-signal discovery for LLMs:

### ⚙️ Core Primitives (`/core`)
Thin wrappers around [`muapi-cli`](https://github.com/SamurAIGPT/muapi-cli) for raw API access.
- `skills/core/media/` — File upload
- `skills/core/edit/` — Image editing (prompt-based)
- `skills/core/platform/` — Setup, auth & result polling

### 📚 Expert Library (`/library`)
High-value skills that translate creative intent into technical directives.
- **Cinema Director** (`skills/library/motion/cinema-director/`) — Technical film direction & cinematography.
- **Nano-Banana** (`skills/library/visual/nano-banana/`) — Reasoning-driven image generation (Gemini 3 Style).
- **UI Designer** (`skills/library/visual/ui-design/`) — High-fidelity mobile/web mockups (Atomic Design).
- **Logo Creator** (`skills/library/visual/logo-creator/`) — Minimalist vector branding (Geometric Primitives).
- **Seedance 2 (Doubao Video)** (`skills/library/motion/seedance-2/`) — Director-level cinematic video generation with text-to-video, image-to-video, and video extension with native audio-video sync.
- **AI Clipping** (`skills/library/edit/ai-clipping/`) — Long video → ranked vertical short clips in one managed API call. Server-side transcription, virality ranking, dedupe, and face-tracked auto-crop — no local Whisper or LLM.
- **YouTube Shorts** (`skills/library/social/youtube-shorts/`) — Platform-aware preset over AI Clipping (Shorts / TikTok / Reels / Feed defaults).

Plus **41 ready-to-run workflow recipes** organized by output type — see [🎬 Recipe Pack](#-recipe-pack) below.

---

## 🎬 Recipe Pack

Forty-one LLM-orchestrated workflow recipes that combine multiple `muapi-cli` calls into named end-to-end pipelines (e.g. *photo of person → 3D action figure*, *product photo → cinematic 10s ad*). Each skill is a SKILL.md the agent reads and follows; bring your own consuming agent (Claude Code, Cursor, MCP) — these are recipes, not bash wrappers.

**Motion / Video (16)**

| Skill | Description |
|:---|:---|
| [3D Logo Animation](skills/library/motion/3d-logo-animation/) | Transform a 2D logo into a premium 3D version and animate it with professional cinematic effects |
| [AI Fight Scene Generator](skills/library/motion/ai-fight-scene/) | High-cut-density action / fight scene — 16-cell storyboard image drives Seedance 2.0 i2v for shot-by-shot choreography |
| [Animal Vlogger Video](skills/library/motion/animal-video-generator/) | Hilarious, ultra-realistic anthropomorphic-animal vlogger acting like a human in a real-world setting |
| [Cartoon Dance Animation](skills/library/motion/cartoon-dance-animation/) | Convert a photo into a Pixar-style 3D cartoon, then animate using a reference dance/motion video |
| [Character Story Video](skills/library/motion/character-story-video/) | Multi-part animated story video — establish a consistent character then animate sequential scenes |
| [Drone-Style Video](skills/library/motion/drone-style-video/) | Aerial drone-perspective footage — bird's-eye sweeps, orbit shots, and flyover sequences |
| [Giant Product Showcase](skills/library/motion/giant-product-showcase/) | Dramatic giant-scale product visual (building-sized object next to a person), optionally animated |
| [Jewelry Product Video](skills/library/motion/jewelry-product-video/) | Luxury jewelry ad with high-end commercial cinematography and detailed macro animation |
| [Music Video](skills/library/motion/music-video/) | Short music video from a song theme — keyframes, animation per beat, matching music track |
| [One-Shot Video](skills/library/motion/one-shot-video/) | Single continuous cinematic shot — no cuts, one seamless flowing scene |
| [Cinematic Product Ad](skills/library/motion/product-ad-cinematic/) | Cinematic 5–10s product ad from a product photo + brand brief |
| [Product Showcase Video](skills/library/motion/product-showcase-video/) | Dynamic product showcase with explosive ingredient arrangement + realistic motion animation |
| [Product Video Ad Maker](skills/library/motion/product-video-ad-maker/) | High-end cinematic product video ad starting from a simple product photo |
| [Talking Baby Video](skills/library/motion/talking-baby-video/) | Viral-style talking-baby video with custom costumes and scripts |
| [UGC Lifestyle Try-On](skills/library/motion/ugc-lifestyle-try-on/) | UGC-style lifestyle photos & video of a person using your product — authentic, social-native |
| [UGC Video Factory](skills/library/motion/ugc-video-factory/) | Person photo + product photo + script → 10s vertical 9:16 UGC video ad with native dialogue (Nano-Banana Pro Edit → Seedance 2.0 VIP i2v) |

**Social (5)**

| Skill | Description |
|:---|:---|
| [Instagram Post](skills/library/social/instagram-post/) | Polished on-brand Instagram post — hero image + caption + hashtags |
| [Product Campaign Pack](skills/library/social/product-campaign/) | Full multi-channel campaign — hero visuals, social assets, short ad video, platform crops |
| [RedNote Cover](skills/library/social/rednote-cover/) | Xiaohongshu (小红书) cover image — vibrant lifestyle aesthetic with typography overlay |
| [Social Media Pack](skills/library/social/social-pack/) | Re-render a hero image into Instagram / TikTok / Shorts / X aspect ratios |
| [UGC Ads Workflow](skills/library/social/ugc-ads-workflow/) | UGC video ad pipeline — combine selfie + product image, write script, animate |

**Visual / Images & Design (21)**

| Skill | Description |
|:---|:---|
| [Action Figure Generator](skills/library/visual/action-figure-generator/) | Convert a photo of a person into a custom 3D action figure with collectible toy packaging |
| [Ad Creative Set](skills/library/visual/ad-creative/) | High-converting ad set — hero image, copy variations, platform crops for Meta / Google / LinkedIn |
| [Amazon Product Listing Pack](skills/library/visual/amazon-product-listing/) | Full Amazon listing image set — hero, lifestyle, infographic, comparison/detail closeups |
| [Blog Header](skills/library/visual/blog-header/) | Professional 1200×628 blog header image with optional title composition guidance |
| [Brand Kit](skills/library/visual/brand-kit/) | Cohesive brand visual kit — logo concept, color palette, typography pairings |
| [Brochure Designer](skills/library/visual/brochures/) | Multi-page brochure — cover, inner spread, back — for business, real estate, events, launches |
| [Couple Grid Creator](skills/library/visual/couple-grid-creator/) | Stylized 6-box grid of a couple in romantic poses, each pose framed inside cardboard packaging |
| [Brand Design Guide](skills/library/visual/design-guide/) | Comprehensive design guide — palette, typography, UI components, visual identity rules |
| [Fashion Try-On](skills/library/visual/fashion-try-on/) | Virtually try outfits by combining a person's photo + clothing item, optional fashion model video |
| [Floor Plan Rendering](skills/library/visual/floor-plan-rendering/) | Design a 2D floor plan and convert into a realistic 3D architectural rendering |
| [Interior Design](skills/library/visual/interior-design/) | Pro interior design visualizations — redesign rooms, generate concepts, visualize furniture styles |
| [Interior Design Visualizer](skills/library/visual/interior-design-visualizer/) | Generate an empty room and fill it with stylish furniture / decor; or redesign an existing room |
| [Keyboard Art Maker](skills/library/visual/keyboard-art-maker/) | Artistic top-down photos of keyboard keycaps arranged to spell custom messages |
| [Logo + Branding Package](skills/library/visual/logo-branding/) | Logo + full branding package — variations (dark/light/icon), palette, mockups |
| [Logo Generator](skills/library/visual/logo-generator/) | Quick single-shot polished logo — fast, clean vector aesthetic with accurate brand-name text |
| [Multi-Angle Reshoot](skills/library/visual/multi-angle-reshoot/) | Re-render a subject from dramatic camera angles (fish-eye, bird's-eye, low, macro) — identity preserved |
| [Multi-Angle Shots](skills/library/visual/multi-angle-shots/) | Full multi-angle product shot set — front, side, back, top-down, 45° |
| [Selfie with Celebrities](skills/library/visual/selfie-with-celebrities/) | Realistic behind-the-scenes selfie of the user with a celebrity; optional cinematic long-take |
| [Storyboard Generator](skills/library/visual/storyboard/) | Generate N keyframes for a short story or scene sequence (image only, no video) |
| [URL to Design](skills/library/visual/url-to-design/) | Analyze a website URL and generate a redesigned, improved UI with modern aesthetics |
| [YouTube Thumbnail](skills/library/visual/youtube-thumbnail/) | High-CTR YouTube thumbnail — striking imagery, bold text placement, emotional face/subject |

Each recipe declares its `inputs` and a `Steps` body. Pass the inputs and let your agent execute the steps via `muapi` CLI calls (or raw API for endpoints that don't yet have a CLI alias — see the per-skill *Notes for the Executing Agent* footer).

---

## 🚀 Quick Start

> **Fastest path:** [`muapi-models`](skills/muapi-models/SKILL.md) is a single skill that lets your coding agent discover, price and run any [Muapi](https://muapi.ai) model. Install it with `npx skills add https://muapi.ai`, set `MUAPI_API_KEY`, and ask in plain language. See the [install guide](https://muapi.ai/docs/ai-agent-overview). The steps below set up the script library in this repo.

### 1. Install the muapi CLI

The core scripts require [`muapi-cli`](https://www.npmjs.com/package/muapi-cli). Install it once:

```bash
# via npm (recommended — no Python required)
npm install -g muapi-cli

# via pip
pip install muapi-cli

# or run without installing
npx muapi-cli --help
```

### 2. Configure Your API Key

```bash
# Interactive setup
muapi auth configure

# Or pass directly
muapi auth configure --api-key "YOUR_MUAPI_KEY"

# Get your key at https://muapi.ai/dashboard
```

### 3. Install the Skills

```bash
# Install all skills to your AI agent
npx skills add SamurAIGPT/muapi-skills --all

# Or install a specific skill
npx skills add SamurAIGPT/muapi-skills --skill muapi-media-generation

# Install to specific agents
npx skills add SamurAIGPT/muapi-skills --all -a claude-code -a cursor
```

### 4. Generate Your First Image

```bash
muapi image generate "a cyberpunk city at night" --model flux-dev

# Download the result automatically
muapi image generate "a sunset over mountains" --model hidream-fast --download ./outputs

# Extract just the URL (agent-friendly)
muapi image generate "product on white bg" --model flux-schnell --output-json --jq '.outputs[0]'
```

### 5. Run an Expert Skill

```bash
# Use Nano-Banana reasoning to generate a 2K masterpiece
bash skills/library/visual/nano-banana/scripts/generate-nano-art.sh \
  --file ./my-source-image.jpg \
  --subject "a glass hummingbird" \
  --style "macro photography" \
  --resolution "2k" \
  --view
```

### 6. Direct a Cinematic Scene

```bash
cd skills/library/motion/cinema-director

# Create a 10-second epic reveal
bash scripts/generate-film.sh \
  --subject "a cybernetic dragon over Tokyo" \
  --intent "epic" \
  --model "kling-v3.0-pro" \
  --duration 10 \
  --view

# Animate a reference image into video
bash skills/library/motion/seedance-2/scripts/generate-seedance.sh \
  --mode i2v \
  --file ./concept.jpg \
  --subject "camera slowly pulls back to reveal the full landscape" \
  --intent "reveal" \
  --view

# Extend an existing video
bash skills/library/motion/seedance-2/scripts/generate-seedance.sh \
  --mode extend \
  --request-id "YOUR_REQUEST_ID" \
  --subject "camera continues pulling back to reveal the vast city" \
  --duration 10
```

---

## 🤖 MCP Server

Run muapi as a **Model Context Protocol server** so Claude Desktop, Cursor, or any MCP-compatible agent can call generation tools directly — no shell scripts needed.

```bash
muapi mcp serve
```

**Claude Desktop config** (`~/Library/Application Support/Claude/claude_desktop_config.json`):

```json
{
  "mcpServers": {
    "muapi": {
      "command": "muapi",
      "args": ["mcp", "serve"],
      "env": { "MUAPI_API_KEY": "your-key-here" }
    }
  }
}
```

This exposes **19 structured tools** with full JSON Schema input/output definitions:

| Tool | Description |
|------|-------------|
| `muapi_image_generate` | Text-to-image (14 models) |
| `muapi_image_edit` | Image-to-image editing (11 models) |
| `muapi_video_generate` | Text-to-video (13 models) |
| `muapi_video_from_image` | Image-to-video (16 models) |
| `muapi_audio_create` | Music generation (Suno) |
| `muapi_audio_from_text` | Sound effects (MMAudio) |
| `muapi_enhance_upscale` | AI upscaling |
| `muapi_enhance_bg_remove` | Background removal |
| `muapi_enhance_face_swap` | Face swap image/video |
| `muapi_enhance_ghibli` | Ghibli style transfer |
| `muapi_edit_lipsync` | Lip sync to audio |
| `muapi_edit_clipping` | AI highlight extraction |
| `muapi_predict_result` | Poll prediction status |
| `muapi_upload_file` | Upload local file → URL |
| `muapi_keys_list` | List API keys |
| `muapi_keys_create` | Create API key |
| `muapi_keys_delete` | Delete API key |
| `muapi_account_balance` | Get credit balance |
| `muapi_account_topup` | Add credits (Stripe checkout) |

---

## ⚡ Agentic Pipeline Examples

```bash
# Submit async, capture request_id, poll when ready
REQUEST_ID=$(muapi video generate "a dog running on a beach" \
  --model kling-master --no-wait --output-json --jq '.request_id' | tr -d '"')

# ... do other work ...

muapi predict wait "$REQUEST_ID" --download ./outputs

# Pipe a prompt from another command
generate_prompt | muapi image generate - --model flux-dev

# Chain: upload → edit → download
URL=$(muapi upload file ./photo.jpg --output-json --jq '.url' | tr -d '"')
muapi image edit "make it look like a painting" --image "$URL" \
  --model flux-kontext-pro --download ./outputs
```

---

## 📖 Schema Reference

This repository includes a streamlined `skills/schema_data.json` that core scripts use at runtime to:
- **Validate Model IDs**: Ensures the requested model exists.
- **Resolve Endpoints**: Automatically maps model names to API endpoints.
- **Check Parameters**: Validates supported `aspect_ratio`, `resolution`, and `duration` values.

Discover all available models via the CLI:

```bash
muapi models list
muapi models list --category video --output-json
```

---

## 🔧 Compatibility

Optimized for the next generation of AI development environments:
- **Claude Code** — Direct terminal execution via tools + MCP server mode.
- **Gemini CLI / Cursor / Windsurf** — Seamless integration as local scripts.
- **MCP** — Full Model Context Protocol server with typed input/output schemas.
- **CI/CD** — `--output-json`, `--jq`, semantic exit codes for scripting.

---

## 📄 License
MIT © 2026
