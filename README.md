# Mathematical Notes on SNARKs

This repository contains two LaTeX notebooks:

- `snark_note.tex` — the main note on zero knowledge, polynomial commitments, polynomial IOPs, Plonk, Groth16, and FRI;
- `threshold_crypto.tex` — a companion note on Paillier, threshold decryption, and CRT.

The source of truth is modular: every chapter and appendix is a separate `.tex` file. The main note is ordered as follows.

| Files | Contents |
| --- | --- |
| `s1_overview.tex`–`s3_pcs.tex` | overview, foundations, algebra, and polynomial commitments |
| `s4_iop_paradigm.tex`–`s6_plonk.tex` | PCP/IOP paradigm, proof gadgets, and Plonk |
| `s7_groth16.tex`–`s9_synthesis.tex` | Groth16, FRI, and synthesis |
| `appendix_*.tex` | complete worked examples for IPA, Plonk, R1CS/QAP, and FRI |
| `references.bib`, `zero_knowledge_references.bib` | bibliography for the main note |

## Build

From the repository root:

```powershell
latexmk -pdf -interaction=nonstopmode -halt-on-error -outdir=output/pdf -jobname=SNARKs-Note snark_note.tex
latexmk -pdf -interaction=nonstopmode -halt-on-error -outdir=output/pdf -jobname=Threshold-Cryptography-Note threshold_crypto.tex
```

Release PDFs are placed in `output/pdf/`. Temporary render and inspection files belong in `tmp/` and are ignored by Git.

## Editing conventions

- Add new main chapters as `s<number>_<topic>.tex` and include them from `snark_note.tex`.
- Add worked examples as `appendix_<letter>_<topic>.tex`.
- Keep theorem statements, protocol algorithms, and security assumptions explicit; use appendices for full arithmetic transcripts.
- Add citations to the relevant bibliography and run LaTeX enough times to resolve all references.

## Research roadmap

Natural extensions include recursive and folding systems (Nova, HyperNova, ProtoStar), transparent recursive arguments (Fractal), and further comparisons among Aurora, HyperPlonk, Sonic, and modern accumulation schemes.
