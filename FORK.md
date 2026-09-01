# Credits

This is **utopia-stack**, a maintained fork of [pstack](https://github.com/cursor/plugins/tree/main/pstack) by Lauren Tan ([@poteto](https://x.com/poteto)), MIT.

The original idea is poteto's: go deep first, then parallelize. The principles, playbooks, and quality bar are hers. This tree is adrianvrj's: same machinery, utopia-stack on the door.

User-level copies of the same skill names in `~/.agents` or `~/.claude` win over the patched plugin copy unless you disable them.

Keep `LICENSE` (Copyright (c) 2026 Lauren Tan, Copyright (c) 2026 Adrian Vargas) in every copy.

Upstream: https://github.com/cursor/plugins/tree/main/pstack

## What you got

- `skills/` — 57 SKILL.md files under `skills/` (workflows and principles, the actual stack), including vendored design skills (impeccable, design-taste-frontend, GSAP, and the rest of the UI design set). This fork does not claim those authors.
- `docs/` — the utopia-stack guide
- `agents/` — utopia-agent subagent definition
- `automations/` — optional automation pack
- `.cursor-plugin/` — Cursor plugin manifest if you want to load this folder as a local plugin

## Adapt it for other agents

These files are just markdown. Any agent that can load `SKILL.md` can run them.

### Cursor (already works)

Keep using `/utopia-mode` from this folder, or point Cursor at this directory as a local plugin. `/setup-utopia-stack` writes `~/.cursor/rules/utopia-stack-models.mdc`.

### Grok Bots

Grok Bots do not load this folder automatically. Editable Grok Bot skills live as user skills (one folder per skill). Ask dr eggbot to install selected skills from this fork into your Grok Bot skill library — do not edit the marketplace plugin copies.

Things that are Cursor-shaped and need a rewrite when a Grok Bot runs them:

- `Task` subagents / `utopia-agent` → Grok Bot `executor` / `CloudAgent`
- `AskQuestion` → a Grok Bot question widget
- model slugs (`grok-4.6-fast-xhigh`, `gpt-5.6-sol-max`, …) → `inherit-parent` or `sand-default` on Grok Bot
- merge / publish / deploy still need the human's explicit yes
- `SendToUser` is the only voice; never assume a Cursor composer

The principles (`prove-it-works`, `laziness-protocol`, `unslop`, …) port as-is. The playbooks in `utopia-mode` need the tool names swapped.

### Claude Code, Codex, and others

Drop `skills/*/SKILL.md` into that product's skill path. Same rewrite list as above wherever the host has no Cursor `Task` tool.

## How to customize without making a mess

1. Leave upstream wording in place until you disagree with it.
2. Put your overrides in new files (`skills/your-mode/SKILL.md`, product facts, Grok Bot tool map) rather than silently rewriting the principles.
3. If you change a principle, say so in that skill's frontmatter `description` so agents pick the fork, not a stale copy.

## Do not edit

The installed marketplace cache for upstream pstack (if you still have it) will get overwritten on update. Edit **this** tree.
