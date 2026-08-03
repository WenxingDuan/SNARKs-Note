# Mathematical Notes on SNARKs

This repository contains two LaTeX notebooks:

- `main.tex` — the main note on zero knowledge, polynomial commitments, polynomial IOPs, Plonk, Groth16, and FRI;
- `threshold_crypto.tex` — a companion note on Paillier, threshold decryption, and CRT.

The source of truth is modular: every chapter and appendix is a separate `.tex` file.

```text
SNARKs-Note/
|-- main.tex
|-- chapters/
|   |-- ch01_overview.tex
|   |-- ...
|   `-- ch11_synthesis.tex
|-- appendices/
|   |-- app_a_bulletproofs.tex
|   `-- app_d_fri.tex
|-- macro.tex
|-- references.bib
|-- zero_knowledge_references.bib
|-- threshold_crypto.tex
`-- output/pdf/
```

The main note is ordered as follows.

| Files | Contents |
| --- | --- |
| `chapters/ch01_*.tex`–`chapters/ch04_*.tex` | overview, zero knowledge, foundations, and algebra |
| `chapters/ch05_*.tex`–`chapters/ch08_*.tex` | polynomial commitments, polynomial IOPs, proof gadgets, and Plonk |
| `chapters/ch09_*.tex`–`chapters/ch11_*.tex` | Groth16, FRI, and synthesis |
| `appendices/app_*.tex` | complete worked examples for IPA, Plonk, R1CS/QAP, and FRI |
| `references.bib`, `zero_knowledge_references.bib` | bibliography for the main note |

## Build

From the repository root:

```powershell
latexmk -pdf -interaction=nonstopmode -halt-on-error -outdir=output/pdf -jobname=SNARKs-Note main.tex
latexmk -pdf -interaction=nonstopmode -halt-on-error -outdir=output/pdf -jobname=Threshold-Cryptography-Note threshold_crypto.tex
```

Release PDFs are placed in `output/pdf/`. Temporary render and inspection files belong in `tmp/` and are ignored by Git.

## Editing conventions

- Add new main chapters as `chapters/ch<number>_<topic>.tex` and include them from `main.tex`.
- Add worked examples as `appendices/app_<letter>_<topic>.tex`.
- Keep `% !TeX root = ../main.tex` at the top of chapter and appendix files so editors compile the correct root document.
- Keep theorem statements, protocol algorithms, and security assumptions explicit; use appendices for full arithmetic transcripts.
- Add citations to the relevant bibliography and run LaTeX enough times to resolve all references.

## Research roadmap

Natural extensions include recursive and folding systems (Nova, HyperNova, ProtoStar), transparent recursive arguments (Fractal), and further comparisons among Aurora, HyperPlonk, Sonic, and modern accumulation schemes.
