# Arta - Your Private Art Curator

Arta (Romanian word for "the art") is your personal, private, and local hosted art curator. Architectured on top of my own artistic experience, it's structured around the idea of a taste model that connects across art forms, substance, impact, and patterns.

Taste is seen not as a list of likes but a pattern of unyielding attention with its own cultural traces, history, memory, and behaviour. Not a recommendation engine. But a private curator that guides you even when it means steering away from your places of comfort.

This is meant to be a multi-agentic system with a local reasoning layer for: _Taste_ (for Retrieval Augmented Generation), _Resonance_ (axioms and themes that resonate with you), _Intersectionality_ (a film relates to a poem or song or painting or performance, …) and _Curator-Guide_ (selection and analysis of artworks). But this shouldn't come at the cost of your own privacy. So everything is done privately, locally, or in a Docker-ephemeral environment by default.

## Pre-Release Version 0.0.1

The Minimal Viable Product now focuses on just being a place for literary discovery and curation, with unconsumed poetry masterworks defined by necessity, illusions, the existential, loss, transcendence, and being human.

Sources of the Pre-Release Version curation span years, but the core sources for this version were [Poetry Foundation](https://www.poetryfoundation.org), [Having a Poem with You](https://havingapoemwithyou.tumblr.com), and [Rádio e Televisão de Portugal](https://www.rtp.pt/play). With credits also to [impeccable](https://github.com/pbakaus/impeccable).

* **Multimodal**: Spoken-word performance inline video alongside the text.
* **Pre-Built Page**: Visit the page or download locally (Zero dependencies, runtime, or other steps).
* **Self-Hosted**: Create your own custom curated version inside Docker/self-hosted.
    1. Pull & Sync - Use [`pull-art.gs`](pull-art.gs) (Google Apps Script) to pull YouTube playlist metadata into Google Sheets and export `poetry_archive.csv`.
    2. Ingest - Run [`scripts/sync_art.py`](scripts/sync_art.py) to convert the CSV into `data/art_dataset.json`.
    3. Launch with Docker: `cd docker` then `docker-compose up -d` and finally open `http://localhost:8080`.
