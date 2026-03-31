# ui-design — Claude Code Skill

Design system + UX intelligence for Claude Code. Creates distinctive, production-grade interfaces with anti-AI-slop aesthetics and structured UX rules.

## What it does

5 modes, zero dependencies, pure markdown:

| Mode | Purpose |
|------|---------|
| **INIT** | Generates a complete design system (palette, typography, spacing, layout) |
| **BUILD** | Implements UI respecting the design system + passive UX checklist + MCP verification |
| **REVIEW** | Audits existing UI with quantitative scoring (0-100) |
| **EXTEND** | Adds page-level overrides without breaking the design system |
| **MIGRATE** | Progressive refactoring of inconsistent UIs |

## What's included

| File | Content | Tokens |
|------|---------|--------|
| `SKILL.md` | Main skill — modes, 99 UX rules, contrast checker, micro-copy, template | ~12k |
| `palettes.md` | ~100 industry-specific color palettes | ~3k |
| `font-pairings.md` | ~40 Google Fonts pairings by mood | ~1k |
| `component-patterns.md` | 15 production-ready component patterns | ~5k |

Files are loaded conditionally — BUILD mode only needs `SKILL.md` (~4k tokens used), INIT loads palettes + fonts on demand.

## Key features

- **99 UX rules** organized in 10 priority levels with Do/Don't format
- **WCAG contrast checker** — formula + JS snippet executable via chrome-devtools MCP
- **Lighthouse / Core Web Vitals** — automated checks (LCP < 2.5s, CLS < 0.1, INP < 200ms)
- **Responsive screenshots** — Playwright or chrome-devtools (desktop 1440px + mobile 375px)
- **Micro-copy guidelines** — buttons, errors, empty states, tooltips, loading (FR + EN)
- **15 component patterns** — button, card, modal, toast, nav, form, table, tabs, accordion, badge, breadcrumbs, avatar, stepper, skeleton, empty state
- **WordPress-native** — wpautop rules, WP Rocket compat, template-only classes, zero inline JS
- **Anti-AI-slop guards** — bans generic fonts in display, purple gradients, cookie-cutter layouts
- **Quantitative audit scoring** — 0-100 scale, trackable across audits

## Comparison

| | frontend-design (Anthropic) | UI UX Pro Max | **ui-design** |
|---|:---:|:---:|:---:|
| Structured modes | 0 | 0 | **5** |
| Component patterns | 0 | 0 | **15** |
| UX rules (Do/Don't) | 0 | 99 (bulk) | **99 (classified)** |
| Micro-copy FR/EN | No | No | **Yes** |
| WCAG contrast auto | No | No | **Yes** |
| Lighthouse / CWV | No | No | **Yes** |
| Responsive screenshots | No | No | **Yes** |
| Audit score 0-100 | No | No | **Yes** |
| Migration mode | No | No | **Yes** |
| WordPress native | No | No | **Yes** |
| Dependencies | 0 | Python + npm | **0** |

## Install

Copy the folder to your Claude Code skills directory:

```bash
# Clone
git clone https://github.com/charlomrt-boop/ui-design-skill.git

# Copy to Claude Code skills
cp -r ui-design-skill ~/.claude/skills/ui-design
```

Or add as a git submodule in your skills folder.

## Usage

The skill activates automatically when you ask Claude Code to build, review, or design UI. The routing logic detects the appropriate mode based on context:

- No `design-system.md` in project? → **INIT**
- Ask to build/modify UI? → **BUILD**
- Ask to audit/review? → **REVIEW**
- Need a different tone for a page? → **EXTEND**
- Inconsistent UI to harmonize? → **MIGRATE**

## License

MIT
