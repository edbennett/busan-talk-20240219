# Work to date

-

## Timeline

- 2021: Decision to share data and reproducible workflow for all journal publications
- 2022:
  - 3 journal articles
  - 2 data releases
  - 2 workflow releases
- 2023:
  - 2 journal articles
  - 2 data releases
  - 2 workflow releases
  - 3 preprints under review

-

## General workflow

- Person leading analysis works in way more familiar to them
- If two people are sharing this work, they occasionally exchange data
- Draft is ready, and either
  - Submission to arXiv is delayed for a few weeks while
    - Analysis is automated
    - Code and data packaged for release
  - Submitted to arXiv with data and code "in preparation:"
    - Automation & packaging while paper under review
    - Plots, tables replaced with automatically generated versions later
    - Analysis mistakes are identified and corrected at this point

-

## General structure

<div style="width: 30%; float: left; vertical-align: middle;">
<pre>
.
├── code
│   ├── CITATION.cff
│   ├── LICENSE
│   ├── README.md
│   └── src
├── data
│   ├── input_data
│   ├── metadata
│   └── raw_data
└── paper
    ├── paper.tex
    └── references.bib
</pre>

</div>

<div style="width: 30%; float: left; vertical-align: middle;" class="fragment">

Run workflow

$\rightarrow$

</div>

<pre style="width: 30%; float: left; vertical-align: middle;" class="fragment">
.
├── code
│   ├── CITATION.cff
│   ├── LICENSE
│   ├── README.md
│   ├── environment.yml
│   └── src
├── data
│   ├── input_data
│   ├── metadata
│   ├── metafits.csv
│   ├── raw_data
│   └── spectrum.csv
└── paper
    ├── paper.tex
    ├── plots
    ├── references.bib
    └── tables
</pre>

-

## `paper.tex` example snippets

<div style="float: left; width: 40%; margin: 5%;">

If the captions are simple:
<pre>
\begin{figure}
  \includegraphics{plots/spectrum.pdf}
  \caption{\label{fig:spectrum}A spectrum.}
\end{figure}
</pre>

<pre>
\begin{table}
  \caption{\label{tab:spectrum}A spectrum.}
  \input{tables/spectrum.tex}
\end{table}
</pre>

</div>

<div style="float: left; width: 40%; margin: 5%;" class="fragment"">

If the captions contain data:
<pre>
\input{plots/spectrum.tex}
</pre>

<pre>
\input{tables/spectrum.tex}
</pre>

<div class="fragment">

Then `plots/spectrum.tex`:

<pre>
\begin{figure}
  \includegraphics{spectrum.pdf}
  \caption{\label{fig:spectrum}
    Spectrum of the ensembles A1, C2, D9.
    We observe $m = 1.234 \pm 0.056$.
  }
\end{figure}
</pre>
</div>
</div>

-

[![Screenshot of the header of the paper "Lattice studies of the Sp(4) gauge theory with two fundamental and three antisymmetric Dirac fermions"](./papers/2022-multirep.png)](https://doi.org/10.1103/PhysRevD.106.014501)

([Data release](https://zenodo.org/records/6637515) • [Code release](https://zenodo.org/records/6637743))

-

- Prepared by EB, from original analysis by JWL
- Mathematica $\rightarrow$ WolframScript
  - Plus a little Python, Bash
- Consolidated one notebook per ensemble $\rightarrow$ one script for all
- Workflow automated using GNU Make
<!-- ~4 weeks of development -->
- One command to install requirements:<br>`conda env create -f environment.yml`
- One command to run full analysis:<br>`make`

-

[![Code sample of a WolframScript file](./images/code-multirep.png) <!-- .element width="600px" -->](https://github.com/edbennett/sp2n-multirep-202203/blob/main/code/bulk_phase_transition.wls)
[![Code sample of a Makefile](./images/makefile-multirep.png) <!-- .element width="600px" -->](https://github.com/edbennett/sp2n-multirep-202203/blob/main/Makefile)

-

[![Screenshot of the header of the paper "Sp(2$N$) Yang-Mills theories on the lattice: Scale setting and topology"](./papers/2022-topology-prd.png)](https://doi.org/10.1103/PhysRevD.106.094503)

[![Screenshot of the header of the paper "Color dependence of the topological susceptibility in Yang-Mills theories"](./papers/2022-susceptibility-plb.png)](https://doi.org/10.1016/j.physletb.2022.137504)

([Data release](https://zenodo.org/records/6678411) • [Analysis release](https://zenodo.org/records/7260975))

-

- Prepared by EB, DV
- Python, plus some Bash
- Workflow automated using GNU Make
<!-- ~4 weeks of development -->
- One command to install requirements: <br>`conda env create -f environment.yml`
- One command to run full analysis: <br>`make`

-

[![Code sample of a Python file](./images/code-topology.png) <!-- .element width="600px" -->](https://github.com/edbennett/sp2n-topology-202205/blob/main/Makefile)
[![Code sample of a Makefile](./images/makefile-multirep.png) <!-- .element width="600px" -->](https://github.com/edbennett/sp2n-multirep-202203/blob/main/Makefile)

-

-

[![Screenshot of the header of the paper "Sp(2N) Lattice Gauge Theories and Extensions of the Standard Model of Particle Physics"](./papers/2023-review.png)](https://doi.org/10.3390/universe9050236)

- No new data or analysis presented $\Rightarrow$ no new data release
- Slightly restricted what could be presented

-

[![Screenshot of the header of the paper "Symplectic lattice gauge theories in the grid framework: Approaching the conformal window"](./papers/2023-grid.png)](https://doi.org/10.1103/PhysRevD.108.094508)

([Data release](https://zenodo.org/records/8136452) • [Analysis release](https://zenodo.org/records/8136514))

-

- Prepared by NF
- Python, with some Mathematica
- Separates out plot style into separate style sheet
<!-- Took some amount of time -->
- Generation and job submission scripts are included
- One command to install requirements:<br>`conda env create -f environment.yml`
- Multiple commands needed to run full analysis

-

[![Screenshot of the header of the paper "Singlets in gauge theories with fundamental matter"](./papers/2023-singlets.png)](https://arxiv.org/pdf/2304.07191)

([Data release](https://zenodo.org/records/10352099)  • [Analysis release](https://zenodo.org/records/10352176))

-

- Prepared by FZ
- Julia, plus Python
<!-- Not developed in a contiguous block -->
- Workflow managed from within Julia
- One command to install requirements:<br>`pipenv install -r requirements.txt`
- One command to run full analysis:<br>`julia main.jl`
