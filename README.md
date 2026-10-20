# Civitai Skill

An agent skill for finding and inspecting Civitai models, LoRAs, checkpoints, and ComfyUI workflows with the [official Civitai CLI](https://developer.civitai.com/site/guide/cli).

Uses the standard Agent Skills layout supported by [Vercel's skills CLI](https://github.com/vercel-labs/skills) and [skills.sh](https://skills.sh).

## Install

```bash
npx skills add FrancescoSaverioZuppichini/civitai-skill --skill civitai
```

Install globally across projects:

```bash
npx skills add FrancescoSaverioZuppichini/civitai-skill --skill civitai --global
```

The installer lets you select your agent. To preview available skills:

```bash
npx skills add FrancescoSaverioZuppichini/civitai-skill --list
```

## Set up the Civitai CLI

```bash
npm install -g @civitai/cli
civitai version
```

Searches and metadata reads work anonymously. For model-file downloads, authenticate locally:

```bash
civitai login
civitai whoami
```

You can also run the CLI without installing it: `npx --yes @civitai/cli --help`.

## Example prompts

- “Find popular watercolor LoRAs for SDXL.”
- “Find realism and natural-motion LoRAs for MiniMax H3.”
- “Look up MiniMax H3 Singularity and explain how it differs from a LoRA.”
- “Find Wan 2.2 ComfyUI workflows and check their dependencies.”
- “Inspect this Civitai model URL and list compatible versions.”
- “Download the selected LoRA into my ComfyUI folder.”

## What it covers

- Live catalog searches with architecture, type, creator, and popularity filters
- Version compatibility, trigger words, file sizes, and source-attributed recommendations
- Workflow packages and article/tutorial discovery
- Download previews, authenticated transfers, app-specific folder routing, and SHA256 verification
- Search pitfalls: literal architecture names, model vs. version IDs, and full-model alternatives to LoRAs

The skill does not generate images or spend Buzz as part of discovery.

## Repository layout

```text
skills/
  civitai/
    SKILL.md
```

The skill is instruction-only: no bundled runtime, credentials, model files, or MCP server. See [`skills/civitai/SKILL.md`](skills/civitai/SKILL.md) for commands and guidance.

## Verification

Tested with Civitai CLI **0.1.130** on macOS arm64: anonymous catalog searches, model/version inspection, article retrieval, and download planning. Actual authenticated file transfers and generation quality were not tested.

## License

[MIT](LICENSE). Independent community skill; not affiliated with Civitai or Vercel. Downloaded resources retain their own licenses and terms.
