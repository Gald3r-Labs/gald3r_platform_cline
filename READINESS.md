# gald3r Readiness Report — Cline

> An honest accounting of how much of the gald3r framework installs natively on this
> platform, what degrades to an approximation, and what has no native home yet.
> Generated from a live documentation crawl on 2026-06-02.

**Overall readiness: ✅ Full.** Cline is an open-source autonomous coding agent (VS Code /
JetBrains extension, CLI, and SDK runtime). As of mid-2026 it natively hosts every
gald3r-relevant mechanism — commands, rules, agents, skills, and hooks — plus full MCP. Two
caveats only: Hooks are macOS/Linux-only at time of research, and native sub-agents/teams
require the Cline SDK or CLI runtime rather than the bare IDE chat.

## C.R.A.S.H. capability grid

| | Capability | Native? | What gald3r gets here | The gap |
|---|---|:---:|---|---|
| **C** | Commands | ✅ | Any markdown file in `.clinerules/workflows/` becomes a `/`-invoked slash command; built-ins (`/newtask`, `/newrule`, `/deep-planning`) alongside | None — gald3r's `@g-*` set installs natively as Workflow slash commands |
| **R** | Rules | ✅ | `.clinerules` (single file or folder) — always-on persistent rules, toggleable per-file; YAML frontmatter scopes rules to file paths | None — gald3r rules load here as first-class always-on rule files |
| **A** | Agents | ✅ | Subagents + multi-agent teams via the Cline SDK; each gets its own model, tool set, and system prompt; teams share a task board | Needs the SDK/CLI runtime — the bare IDE chat can't run gald3r's `g-agnt-*` roles |
| **S** | Skills | ✅ | Native Agent Skills — `SKILL.md` folders with progressive disclosure (3-tier load), discovered from `.cline/skills/`, run via `use_skill` | None — gald3r skills install verbatim as native `SKILL.md` packages |
| **H** | Hooks | ✅ | 6 lifecycle events (PreToolUse, PostToolUse, UserPromptSubmit, TaskStart/Resume/Cancel); executable scripts in `.clinerules/hooks/`, JSON over stdin | macOS/Linux only at research time — gald3r's `g-hk-*` wiring won't fire on Windows yet |

_Legend: ✅ native · ⚠️ partial / approximated · ❌ no native mechanism · ❓ unverified_

**Beyond C.R.A.S.H. — MCP: ✅** Full native Model Context Protocol support — STDIO (local)
and Remote HTTP/SSE transports, one-click install via the built-in MCP Marketplace, config in
`cline_mcp_settings.json` (IDE) or `~/.cline/mcp.json` (CLI). gald3r's MCP backend connects directly.

## Adoptable extras (non-C.R.A.S.H.)

Platform-native strengths gald3r can lean on, and which need wiring:

| Feature | Status | gald3r fit |
|---|:---:|---|
| Cline SDK plugin system (register tools, observe lifecycle, add rules + commands in code) | ✅ present | A second, code-driven path to every gald3r primitive |
| AGENTS.md cross-tool source (project root + `~/.agents/AGENTS.md`) | ✅ present | gald3r's shared instruction file is read natively, no per-tool duplication |
| Cron-driven coordinator agents (per SDK docs) | ⚙️ needs customization | Could drive gald3r scheduled / heartbeat workflows |
| Community library (`github.com/cline/clinerules`) for shared rules / skills / workflows | ✅ present | A distribution channel gald3r tiers could publish into |
| `.cursorrules` / `.windsurfrules` auto-detection | ➖ n.a. | Cross-tool compat; no gald3r work required |

## The ceiling, and what's beyond it

gald3r runs at full strength on this platform — commands, rules, agents, skills, and hooks all map onto native mechanisms, so the framework installs without compromise. As third-party adaptation goes, this is the high end: nothing here has to be approximated.

But adaptation, however clean, is still gald3r living as a guest inside someone else's tool. The native build goes further — **gald3r_agent**, running on the **gald3r throne** over the **gald3r_world_tree** — where these primitives aren't mapped onto a host, they *are* the substrate. Same framework, no host in between.

> ### gald3r_agent — coming soon. 🌳

---

<sub>Capabilities verified against the platform's official documentation on 2026-06-02, and
re-verified each release via the gald3r platform-docs crawl. This report describes gald3r's
third-party adaptation surface; it is not an endorsement or critique of the platform itself.</sub>
