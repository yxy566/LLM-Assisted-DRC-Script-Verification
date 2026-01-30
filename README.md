#  LLM-Assisted-DRC-Script-Verification

This repository hosts the datasets and experimental outputs used in the accompanying paper. The source code that performs the model training and inference is owned by a corporate partner and cannot be published here, so only the data artifacts are shared for transparency and reuse.

## Data Contents
- `datasets/freepdk-45nm/`: curated ROIs, layout annotations, and metadata for the FreePDK 45nm process, structured for downstream language-model-based rule extraction.
- `datasets/freePDK15/`: the equivalent dataset formatted for the FreePDK15 process node, keeping the same conventions as the 45nm folder for consistency.
- `datasets/asap7/`: used with permission; the actual ASAP7 data is copyright-protected and must be downloaded separately via the link provided in that directory's `readme.md`.

## Experimental Outputs
- `outputs/freepdk-45nm/` and `outputs/freePDK15/`: each process directory contains rule examples (`.rul`), pointers to the matched GDS files, GPT-generated textual renditions (`*_gpt_output_shape_rules.json`), and derived spatial constraint summaries.
- Nested `rule_examples/` subdirectories group rules by ID for easier manual verification, and the `.rul` files reference the stripped GDS paths within this repository setup.
- The `.json` summaries detail the structure of generated rules and evaluation signals, so comparing them across runs reveals how the pipeline evolves.

## How to Use This Repository
1. Inspect the `readme.md` inside each dataset directory to understand what every field represents and how the layouts are arranged.
2. Study the `.rul` files to see how GPT outputs are rendered alongside their referenced GDS assets in `outputs/*/rule_examples/`.
3. Reconstruct or extend your own inference pipeline by feeding it the datasets here and comparing its outputs with the recorded `.json` and `.rul` artefacts.

## Access Restrictions
The codebase that powers the experiments is not included because it belongs to a partner organization. This repository is intended strictly for sharing data and results; reuse must respect any licensing constraints noted elsewhere.
