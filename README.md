# faf-memory-proof

**Reproducible methodology + scripts for the `.fafm` binary tier — the receipt behind the 400+× type-filter speedup vs `grep` on AI memory corpora.**

Built 2026-05-13 — the same day `application/vnd.fafm+yaml` was IANA-registered. This is the first real-world implementation of the registered format applied to AI memory-corpus storage, measured at scale (492 `.md` files).

---

## Headline

Claude's persistent memory corpus, compiled end-to-end and benched against the status-quo `.md` + `grep` baseline:

| Tier | Size | Cold load (492 files) | Type-filter query (warm) |
|---|---:|---:|---:|
| `.md` (status quo — grep on prose) | 2,099 KB | 80.6 ms | 29.5 ms |
| `.fafmbin.gz` (compiled binary) | **996 KB** | **49.4 ms** | **0.072 ms** |
| **Ratio** | **2.11× smaller** | **1.63× faster** | **412× faster** |

Numbers are rounded down to **400+×** in headline copy ([strategic-undersell](https://en.wikipedia.org/wiki/Underpromise_and_overdeliver) — the receipt holds the actual 412×). Full methodology, hardware, sanitization notes, and per-stage results in [**RECEIPT.md**](./RECEIPT.md).

---

## Reproduce in 30 seconds

The repo ships with a **10-file sanitized pilot corpus** at every tier (`pilot/md/`, `pilot/fafm/`, `pilot/bin/`) so you can run the benchmarks without supplying your own data.

### Setup

```bash
git clone https://github.com/Wolfe-Jam/faf-memory-proof.git
cd faf-memory-proof
python3 -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
```

### Run

Each block is paste-and-go — no comments inside, so any shell works.

**1. Grep baseline on the pilot:**
```bash
python3 query_bench.py
```

**2. `.fafmbin` tier on the pilot (the 412× lane):**
```bash
python3 query_bench_binary.py
```

**3. Compile your own `.md` → `.fafm` → `.fafmbin`:**
```bash
python3 convert_md_to_fafm.py
python3 compile_to_binary.py
```

**4. Full pipeline + bench on your own memory dir:**
```bash
SRC_DIR=/path/to/your/memory python3 scale_up.py
```

All scripts honor environment variables for input/output paths — defaults point at the bundled pilot (`pilot/md`, `pilot/fafm`, `pilot/bin`). See each script's header.

### One-liner — fresh-clone smoke test

```bash
git clone https://github.com/Wolfe-Jam/faf-memory-proof.git && cd faf-memory-proof && python3 -m venv .venv && source .venv/bin/activate && pip install -r requirements.txt && python3 query_bench.py
```

### Notes

- **Pilot vs full corpus.** Pilot bench (10 files) shows ~200× type-filter speedup; the headline **412×** is the full 492-file run — the structured tier's advantage scales with corpus size.
- **macOS:** the system `python` alias may not exist — `python3` always works. Use the venv above to sidestep PEP 668 ("externally-managed-environment").
- **Type vs substring.** Type/date filters dominate; full-text substring search is `grep`'s natural strength — by design.

**Requirements:** Python 3.11+, PyYAML. Pinned in [`requirements.txt`](./requirements.txt).

---

## What's in here

| Path | What |
|---|---|
| `RECEIPT.md` | Full methodology, hardware, ratios, sanitization notes |
| `scale_up.py` | End-to-end pipeline + bench runner (the 492-file run) |
| `convert_md_to_fafm.py` | `.md` → `.fafm` (structured YAML) |
| `compile_to_binary.py` | `.fafm` → `.fafmbin` + `.fafmbin.gz` (binary tier) |
| `query_bench.py` | Grep baseline benchmark on `.md` |
| `query_bench_binary.py` | Type-filter benchmark on `.fafmbin` |
| `pilot/md/` | 10 sanitized `.md` memory files (the pilot corpus) |
| `pilot/fafm/` | The same 10, transformed to `.fafm` |
| `pilot/bin/` | The same 10, compiled to `.fafmbin` + `.fafmbin.gz` |

---

## Format

`.fafm` — **IANA-registered** as `application/vnd.fafm+yaml` on **2026-05-13**.

- Sibling of `.faf` (`application/vnd.faf+yaml`, IANA-registered 2025-10-30)
- Spec: [`Wolfe-Jam/faf` · MEMORY-FORMAT.md](https://github.com/Wolfe-Jam/faf/blob/main/MEMORY-FORMAT.md)
- Paper: [Zenodo DOI 10.5281/zenodo.20348942](https://doi.org/10.5281/zenodo.20348942)

---

## The FAF cluster (for context)

- [`faf-plugin`](https://github.com/Wolfe-Jam/faf-plugin) — Claude Code plugin for `.faf` context (FCL)
- `faf-memory` *(coming)* — Claude Code plugin for `.fafm` Permanent Memory Layer (PML)
- This repo — the falsifiable receipt the memory plugin's perf claims rest on

---

## License

MIT. See [LICENSE](./LICENSE).

Authored by [wolfejam](https://github.com/Wolfe-Jam) (James Wolfe), with Claude as session collaborator.
