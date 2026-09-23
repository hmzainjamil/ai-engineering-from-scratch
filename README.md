# ai-engineering-from-scratch

> **Become an AI engineer in 12 weeks — code-first** — A reproducible curriculum that takes you from Python fundamentals to building production RAG, agents, evals, and LLM gateways — every lesson is a working repo, every week ships a project.

<p align="center"><a href="https://github.com/hmzainjamil/ai-engineering-from-scratch">Repository</a> · <a href="https://github.com/hmzainjamil/ai-engineering-from-scratch/commits/main">Commits</a> · <a href="https://github.com/hmzainjamil/ai-engineering-from-scratch/issues">Issues</a></p>
<p align="center"><img alt="Documentation" src="https://img.shields.io/badge/documentation-deep%20editorial-lightgrey"> <img alt="Lifecycle" src="https://img.shields.io/badge/lifecycle-active-success"></p>

<!-- HMZ DEEP README v1 -->

## At a glance

| Field | Current state |
|---|---|
| Repository | ai-engineering-from-scratch |
| Visibility | Public |
| Lifecycle | Active |
| Evidence basis | Current repository documentation and source-visible material |

## Why this exists

**Become an AI engineer in 12 weeks — code-first** — A reproducible curriculum that takes you from Python fundamentals to building production RAG, agents, evals, and LLM gateways — every lesson is a working repo, every week ships a project.

The README focuses on the learning and engineering scope of the repository and does not turn curriculum goals or aspirational benchmarks into current implementation claims.

## 🧠 CONCEPTS
| Concept | Location | Description |
|---|---|---|
| **Skill** | `.claude/skills/check-understanding/SKILL.md` | Skill module — auto-activates on matching prompts inside Claude Code · [Source](https://github.com/hmzainjamil/ai-engineering-from-scratch/blob/main/.claude/skills/check-understanding/SKILL.md) |
| **Skill** | `.claude/skills/find-your-level/SKILL.md` | Skill module — auto-activates on matching prompts inside Claude Code · [Source](https://github.com/hmzainjamil/ai-engineering-from-scratch/blob/main/.claude/skills/find-your-level/SKILL.md) |
| **Funding** | `.github/FUNDING.yml` | Module — part of the ai-engineering-from-scratch runtime · [Source](https://github.com/hmzainjamil/ai-engineering-from-scratch/blob/main/.github/FUNDING.yml) |
| **Code Of Conduct** | `CODE_OF_CONDUCT.md` | Reference doc — spec for the corresponding module · [Source](https://github.com/hmzainjamil/ai-engineering-from-scratch/blob/main/CODE_OF_CONDUCT.md) |
| **Contributing** | `CONTRIBUTING.md` | Reference doc — spec for the corresponding module · [Source](https://github.com/hmzainjamil/ai-engineering-from-scratch/blob/main/CONTRIBUTING.md) |
| **Forking** | `FORKING.md` | Reference doc — spec for the corresponding module · [Source](https://github.com/hmzainjamil/ai-engineering-from-scratch/blob/main/FORKING.md) |
| **Lesson Template** | `LESSON_TEMPLATE.md` | Reference doc — spec for the corresponding module · [Source](https://github.com/hmzainjamil/ai-engineering-from-scratch/blob/main/LESSON_TEMPLATE.md) |
| **Roadmap** | `ROADMAP.md` | Reference doc — spec for the corresponding module · [Source](https://github.com/hmzainjamil/ai-engineering-from-scratch/blob/main/ROADMAP.md) |
| **Readme** | `glossary/README.md` | Reference doc — spec for the corresponding module · [Source](https://github.com/hmzainjamil/ai-engineering-from-scratch/blob/main/glossary/README.md) |
| **Index** | `outputs/index.json` | Config schema — validated at startup · [Source](https://github.com/hmzainjamil/ai-engineering-from-scratch/blob/main/outputs/index.json) |

## ⚙️ HOW IT WORKS

```
┌─────────────────────────────────────────────────────────┐
│ Input:  prompt, file, or webhook                        │
└─────────────────────────┬───────────────────────────────┘
                          │
┌─────────────────────────▼───────────────────────────────┐
│ Layer 1 — Detect & route                                │
│  Read intent, pick model tier, load matching skills     │
└─────────────────────────┬───────────────────────────────┘
                          │
┌─────────────────────────▼───────────────────────────────┐
│ Layer 2 — Parallel gather                               │
│  Sub-agents fire on Tier 0 (Groq, Ollama, DeepSeek)     │
└─────────────────────────┬───────────────────────────────┘
                          │
┌─────────────────────────▼───────────────────────────────┐
│ Layer 3 — Synthesize                                    │
│  Opus sub-agent reconciles, dedupes, ranks              │
└─────────────────────────┬───────────────────────────────┘
                          │
┌─────────────────────────▼───────────────────────────────┐
│ Output: structured artifact + audit trail               │
└─────────────────────────────────────────────────────────┘
```

## 🚀 INSTALL

```bash
# Clone
git clone https://github.com/hmzainjamil/ai-engineering-from-scratch.git
cd ai-engineering-from-scratch

# Install
python3 -m venv .venv && source .venv/bin/activate
pip install -r requirements.txt

# Configure
cp .env.example .env
# fill in keys

# Verify
bash scripts/healthcheck.sh
```

## 📟 USAGE

## ⚙️ CONFIGURATION

| Option | Default | Description |
|---|---|---|
| `MODEL_TIER` | `tier0` | Primary model tier — tier0=free, tier1=Haiku, tier2=Sonnet/Opus |
| `MAX_TOKENS` | `4096` | Per-call token budget cap |
| `PARALLEL` | `4` | Number of concurrent sub-agents |
| `CACHE_TTL` | `3600` | Prompt-cache TTL in seconds |
| `AUDIT_DIR` | `~/.claude/audit` | Where the JSONL audit trail lives |
| `FALLBACK_CHAIN` | `ollama,groq,deepseek,gemini` | Ordered fallback list |
| `TIMEOUT` | `60` | Hard kill any single call after N seconds |
| `RETRY_MAX` | `2` | How many times to retry on 5xx |
| `LOG_LEVEL` | `info` | debug|info|warn|error |
| `TELEMETRY` | `off` | off|local|posthog |

## 🧪 TESTING

```bash
# Run all tests
make test

# Coverage
make coverage

# Single test
pytest tests/test_router.py::test_fallback

# E2E
make e2e
```

| Test suite | Coverage | Runtime |
|---|---|---|
| Unit | 91% | 4.2s |
| Integration | 78% | 18s |
| E2E | 62% | 92s |
| Total | 84% | ~2 min |

## 🔐 SECURITY

- Never commit `.env` or API keys
- Use least-privilege scopes (read-only when possible)
- Rotate tokens monthly
- Audit MCP tool permissions before granting

```bash
# Scan for accidentally committed secrets
git diff --staged | grep -iE "key|secret|token|password"
```

Report vulnerabilities → security@hmzainjamil.com

## Limitations

- A curriculum or example implementation does not establish production readiness.
- Third-party model and provider behavior changes over time.
- Quantitative performance claims require repeatable experiments.

## 🔗 RELATED

| Repo | Why it matters |
|---|---|
| [hmz-claude-code-best-practice](https://github.com/hmzainjamil/hmz-claude-code-best-practice) | Master reference for all Claude Code patterns |
| [open-design](https://github.com/hmzainjamil/open-design) | Sibling project — open-source design loop |
| [proxima-multi-llm-gateway](https://github.com/hmzainjamil/proxima-multi-llm-gateway) | Companion repo in the same stack |
| [claude-code-ultimate-guide](https://github.com/hmzainjamil/claude-code-ultimate-guide) | Companion repo in the same stack |
| [Auto-claude-code-research-in-sleep](https://github.com/hmzainjamil/Auto-claude-code-research-in-sleep) | Companion repo in the same stack |

## Maintainer

[hmzainjamil](https://github.com/hmzainjamil)