**Embedding comparison (3 models, chunking `B_rec_384_64`, dense top-3, 8 dev questions).**

- `bge-base` (open-source): Hit@3 1.00, MRR 0.938, Prec@3 0.54, index time 1s
- `mxbai-large` (open-source): Hit@3 1.00, MRR 0.875, Prec@3 0.50, index time 2s
- `bge-m3` (open-source): Hit@3 0.88, MRR 0.812, Prec@3 0.62, index time 7s

**Best overall by MRR:** `bge-base`. **Selected for the final system:** `bge-base` (best open-source: MRR 0.938, Hit@3 1.00).
Commercial comparison: skipped: no MISTRAL_API_KEY.
Cost/speed: `bge-base` indexes in 1s vs `bge-m3` in 7s. With only 8 dev questions, differences of a few points in MRR are within noise: read them as a tie-break between similar models, not as a ranking.
Caveat: synthetic questions are generated from the same text they are tested on, which can flatter models with high lexical overlap; hand-written questions in `eval_manual.csv` reduce this bias.