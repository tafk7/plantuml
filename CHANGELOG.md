# PlantUML Skill Changelog

## Version 3.0 - SKILL.md Rewrite, tafk7 Fork (2025-02-11)

Forked from [SpillwaveSolutions/plantuml](https://github.com/SpillwaveSolutions/plantuml) at v2.1.0. This is the divergence point.

### SKILL.md — Full Rewrite

Rewrote from scratch following evidence-based prompt engineering practices. The research backing these changes is documented in `docs/effective_prompt_language.md`.

#### Positive framing

Replaced every "NEVER"/"DO NOT" prohibition with an affirmative directive. Zero negative-framing instances remain. This is the single highest-impact change — positive framing improved correctness by ~65% across LLM families in published benchmarks.

#### Primacy/recency structure

Reorganized for how LLMs actually attend to context: identity and core routing at the top (primacy zone), bulk reference tables in the middle, edge cases and fallbacks at the bottom (recency zone).

#### Few-shot orchestration examples

Added three end-to-end examples showing the agent workflow: routing → loading → creating → converting → verifying. These demonstrate decision-making, not PlantUML syntax — the reference files already cover syntax and duplicating them in examples teaches the wrong thing.

#### Specific routing triggers

Replaced vague conditions ("complex features needed", "first-time creation") with concrete keyword matches and step lists.

#### Escape clauses

Explicit fallback behaviors for ambiguous diagram types, missing reference files, and failed conversions. Rigid instructions without escape hatches cause cascading failures on edge cases.

#### Identity framing

Opening statement establishes what the skill does and how it handles errors, giving the agent a behavioral anchor before it reads any routing logic.

### Files Removed

- `SKILL-PDA.md` — Merged into the new SKILL.md. Useful concepts (lazy loading, decision tree routing) kept; token budget tracking framework dropped (unenforceable at runtime, wastes real tokens describing imaginary constraints).

### Files Moved to `docs/`

- `FINAL_SUMMARY.md` — Session recap with no runtime value.
- `PDA_OPTIMIZATION_SUMMARY.md` — Planning document for the optimization effort.
- `docs/effective_prompt_language.md` — Research synthesis backing the SKILL.md rewrite decisions.

### Inherited from Upstream (unchanged)

All files under `references/`, `examples/`, `scripts/`, plus `CLAUDE.md` and `README.md`.

---

## Version 2.0 - Enhanced Code-to-Diagram Conversion (2025-01-13)

*Upstream release — see original CHANGELOG for full details.*

### Major Features

1. Code-to-diagram examples (`examples/`) — Spring Boot, FastAPI, Python ETL
2. Unicode symbol enrichment (`references/unicode_symbols.md`) — 100+ symbols
3. Enhanced markdown processing (`scripts/process_markdown_puml.py`) — embedded blocks + linked `.puml` files
4. Syntax validation (`--validate` flag) for CI/CD pipelines
5. Comprehensive troubleshooting guides (`references/troubleshooting/`) — 215+ errors across 12 categories
6. PDA-optimized architecture (now superseded by v3.0 rewrite)
