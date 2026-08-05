# Arta AI - Private Art Curator

**Important: ARTA AI is still in the BUILDING THE PROTOTYPE STAGE!!**

Arta AI is a personal, locally hosted cultural desk for cinema and literature. Arta learns from your viewing history (watch logs, reading notes, saved works) and builds a private taste model that connects film, poetry, music, and images through emotional and formal resonance—not surface similarity.

Taste is not a list of liked items. It's a pattern of attention. Arta infers this from your cultural traces—what you've seen, what moved you, what you avoided—and uses it to recommend works that stretch your understanding rather than comfort your preferences. The key principles and the rules to measure us by are:

- **Resonance** — Underlying Themes (e.g. loss, identity, nostalgia) beat _this is like X_. Always ask: Does this feel tuned to the person?
- **Intersectionality** — a film relates to a poem, literary piece, music and so forth, when the emotional frequencies have a shared idea
- **Coree** — look for and value permanent artistic axioms that share a deeper relation instead of transient moods
- **Editorial** — Echoes (validation), Counterpoints (stretching attention) and Judgement, never echo chambers or vanilla metadata lists

## Architecture

```
User data → Arta AI (local) → [Option A] Other models OR [Option B] You
```

**Arta AI** uses a multi-agent system with a reasoning engine that's model-agnostic, the core agents are:

1. **Taste Expert** — compacts your viewing history into signal JSON (axioms, patterns, anti-patterns)
2. **Curation Expert** — selects artwork candidates based on user taste profile-patterns
    - **Cultural Sub-Expert** — finds artistic connections across art by aesthetic relation (themes, meaning, style, etc.)
    - **Multimodal Sub-Expert** — analyses images (poster, still, cover) against your taste profile
4. **Retrieval Expert** — fetches and compresses evidence and findings for sourcing, relevance, and context management
6. **Editorial Expert** — writes briefings, analyses, and research answers in a human voice

## Data Flow
1. **Feed ingestion** — Letterboxd, reading notes, watch history → compacted into `taste_signals` JSON
2. **Request routing** — On Demand briefing, work analysis, cross-modal bridge, academic retrieval
3. **Retrieval** — Tool Calling to fetch and compress evidence from local PDFs, EPUBs, or your own files
4. **Reasoning** — AI-Model synthesises signals + retrieved context into a response
5. **Reaction log** — user feedback updates the taste model

## Main Offering
- **On Demand briefing** — one film + one literary passage around a precise theme
- **Work analysis** — thesis-driven reading: what gives the work its force, what does it circle, how is the meaning shaped
- **Cross-modal bridge** — related works from other media chosen by emotional/philosophical logic
- **Academic retrieval** — fetch, extract, rank, compress evidence and output answers with citations

## Blueprint
1. Open Arta → Sync your Art Favourites → System loads your compact taste profile
2. On-demand briefing or suggestion (with explanation why) → User consumes suggestion or asks for analysis
3. Agent retrieves and reasons based on online sources and your profile → User consumes and rates output → Arta updates user taste profile

| Layer | Tool |
|-------|------|
| Model | OSS Local / Proprietary |
| Orchestration | Python/TypeScript |
| Data store | SQLite / JSON |
| Retrieval | PyMuPDF, EPUB parser, OCR |
| Embeddings | Small OSS model |
| MCP/tool layer | Direct backend |
| UI | Local Web UI |
