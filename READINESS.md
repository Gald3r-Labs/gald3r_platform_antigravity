# gald3r Readiness Report — Google Antigravity

> An honest accounting of how much of the gald3r framework installs natively on this
> platform, what degrades to an approximation, and what has no native home yet.
> Generated from a live documentation crawl on 2026-06-02.

**Overall readiness: ✅ Full.** Antigravity is an agent-first IDE/CLI/SDK sharing one harness.
gald3r's command, rules, skills, hooks, and MCP layers all map onto native mechanisms; the
only nuance is agents — subagents are dynamic and orchestrator-spawned, so gald3r's static
role files fold into rules/skills rather than installing as discrete agent files.

## C.R.A.S.H. capability grid

| | Capability | Native? | What gald3r gets here | The gap |
|---|---|:---:|---|---|
| **C** | Commands | ✅ | Workflows — saved-prompt slash commands (`/workflow-name`), markdown title/description/steps, global or workspace scope | None — gald3r's `@g-*` set installs as native Workflows (12,000-char file cap) |
| **R** | Rules | ✅ | Markdown Rules (`.agents/rules/`) with Always On / Manual / Model Decision / Glob activation, plus `AGENTS.md` / `GEMINI.md` | None — true always-on guarantee; gald3r rules load first-class (12,000-char cap per file) |
| **A** | Agents | ⚠️ | Dynamic Subagents — the Orchestrator decomposes goals and spawns parallel async subagents with isolated context | No file-based static-role discovery; gald3r's `g-agnt-*.md` roles don't auto-map — fold guidance into rules/skills |
| **S** | Skills | ✅ | Native Agent Skills (`SKILL.md`, Anthropic open format, progressive disclosure), loaded on-demand | None — gald3r `g-skl-*` files are directly compatible; exact skills dir should be pinned by install test |
| **H** | Hooks | ✅ | Lifecycle Hooks (`hooks.json`, shell scripts, stdin/stdout JSON): before/after tool & model call, on_loop_stop, on_error | None — gald3r `g-hk-*.ps1` wire as executed scripts; payload schemas to be pinned by install test |

_Legend: ✅ native · ⚠️ partial / approximated · ❌ no native mechanism · ❓ unverified_

**Beyond C.R.A.S.H. — MCP: ✅** Native Model Context Protocol via `mcpServers` JSON
(`.antigravity/mcp.json` project / `~/.gemini/antigravity/mcp_config.json` global) plus a GUI
MCP Store; gald3r MCP servers (e.g. gald3r_valhalla) integrate directly, with trusted-workspace
gating on write-capable servers.

## Adoptable extras (non-C.R.A.S.H.)

Platform-native strengths gald3r can lean on, and which need wiring:

| Feature | Status | gald3r fit |
|---|:---:|---|
| Scheduled Tasks (cron-style agent invocations, Antigravity 2.0) | ⚙️ needs customization | Drives gald3r heartbeat / scheduled jobs |
| Antigravity SDK / shared harness (CLI + IDE one harness) | ✅ present | Programmatic automation entry point; common config across the suite |
| Orchestrator self-handoff (state dump + successor subagent on spawn limit) | ✅ present | Sustains gald3r long-running autonomous loops |
| `AGENTS.md` cross-tool instruction file (global + project) | ✅ present | gald3r already emits it — primary integration point, no bespoke work |
| Hosted Gemini API "Managed Agents" surface | ➖ n.a. | Separate SDK; custom tools + subagent delegation "not yet supported" — not the IDE/CLI harness |

## The ceiling, and what's beyond it

gald3r runs at full strength on this platform — commands, rules, agents, skills, and hooks all map onto native mechanisms, so the framework installs without compromise. As third-party adaptation goes, this is the high end: nothing here has to be approximated.

But adaptation, however clean, is still gald3r living as a guest inside someone else's tool. The native build goes further — **gald3r_agent**, running on the **gald3r throne** over the **gald3r_world_tree** — where these primitives aren't mapped onto a host, they *are* the substrate. Same framework, no host in between.

> ### gald3r_agent — coming soon. 🌳

---

<sub>Capabilities verified against the platform's official documentation on 2026-06-02, and
re-verified each release via the gald3r platform-docs crawl. This report describes gald3r's
third-party adaptation surface; it is not an endorsement or critique of the platform itself.</sub>
