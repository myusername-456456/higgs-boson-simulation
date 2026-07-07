# Higgs Boson Reconstruction ($H \rightarrow 4\ell$)

A vectorized, columnar analysis pipeline using **Coffea** and **Awkward Array** to reconstruct the Higgs Boson from its decay into four leptons ($4\ell$) using CMS open data. It covers three decay channels: $4e$, $4\mu$, and $2e2\mu$.

---

## Features

* **Physics Analysis:** Particle selection via isolation, impact parameters ($IP_{3D}$), and charge conservation.
* **Vectorized Processing:** Leverages `awkward` and `vector` libraries for efficient array-based computations without event loops.

---

## Decay Channels & Selection

The pipeline filters events across three targeted final states based on strict kinematic and quality cuts:

* **$4e$ Channel:** Filters for exactly 4 electrons ($p_T > 7\text{ GeV}$, $|\eta| < 2.5$).
* **$4\mu$ Channel:** Filters for exactly 4 muons ($p_T > 5\text{ GeV}$, $|\eta| < 2.4$).
* **$2e2\mu$ Channel:** Filters for exactly 2 electrons and 2 muons.

### Core Cuts Applied
* **Isolation:** `pfRelIso03_all < 0.40` for all leptons.
* **Impact Parameters:** $SIP_{3D} < 4$, $|d_{xy}| < 0.5\text{ cm}$, and $|d_z| < 1.0\text{ cm}$.
* **Charge Conservation:** Net charge of the final $4\ell$ state must equal $0$.

---

## Quick Start

### Installation
```bash
pip install coffea awkward vector numpy matplotlib
