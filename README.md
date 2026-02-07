
# SC-Quantathon-v1-2024: Quantum Random Number Generation & Analysis

**Thanks to DoraHacks for sponsoring us to continue work on QRNG!**

This repository contains all code, data, and analysis for our quantum random number generation (QRNG) research, spanning the original Quantathon and the subsequent MiniGrant continuation.

---

## Repository Structure

```
SC-Quantathon-v1-2024/
│
├── MiniGrant/
│   ├── Data/                # Raw and processed QRNG datasets (simulator & real QPU)
│   ├── DataGeneration/      # Scripts for generating QRNG data using various methods
│   └── PostProcessing/      # Entropy extraction, analysis, and postprocessing scripts/notebooks
│
├── SC-Quantathon-2024/
│   ├── Stage1/              # QRNG implementation on IBM QPUs (algorithms)
│   ├── Stage2/              # Machine learning classifiers for QRNG verification
│   ├── Stage3/              # Noise/fidelity analysis and modeling
│   ├── Stage4/              # Entropy extraction, real-world application (HPCG)
│   ├── Stage5/              # Final high-accuracy classification & verification
│   ├── common/              # Shared code (e.g., Toeplitz hashing)
│   └── renamed-datasets/    # Datasets for experiments and benchmarks
│
├── README.md                # (You are here)
└── ...
```

---

## Project Overview

This project explores quantum random number generation using IBM QPUs and simulators, with a focus on:

- Designing and benchmarking multiple QRNG algorithms
- Characterizing noise and fidelity in quantum hardware
- Extracting high-entropy randomness via postprocessing
- Verifying QRNG quality with machine learning classifiers
- Applying QRNG output to real-world benchmarks (HPCG)

---

## Major Components

### 1. QRNG Algorithms (Stage 1, MiniGrant/DataGeneration)
- **Concatenation**: Joins bitstrings from multiple qubits.
- **Iteration with Chunking**: Iteratively generates and chunks bitstrings.
- **Reduce XOR (Mod2)**: Applies XOR reduction for randomness extraction.
- **Combined Methods**: Integrates all above for robust QRNG.

See: `SC-Quantathon-2024/Stage1/`, `MiniGrant/DataGeneration/`

### 2. Machine Learning Verification (Stage 2, 5)
- **Classifiers**: SVM, XGBoost, Gradient Boosting, Random Forest
- **Goal**: Distinguish QRNG from pseudo-random/classical sources

See: `SC-Quantathon-2024/Stage2/`, `SC-Quantathon-2024/Stage5/`

### 3. Noise & Fidelity Analysis (Stage 3)
- **Hardware noise modeling**: T1/T2 decoherence, gate/readout errors
- **Simulator comparison**: Noiseless, noisy, and pseudo-random

See: `SC-Quantathon-2024/Stage3/`

### 4. Entropy Extraction & Real-World Application (Stage 4, MiniGrant/PostProcessing)
- **Toeplitz Hashing**: High-entropy extraction via matrix hashing
- **Von Neumann Extraction**: Removes bias from bitstreams
- **HPCG Benchmark**: Applies QRNG to high-performance computing

See: `SC-Quantathon-2024/Stage4/`, `MiniGrant/PostProcessing/`

---

## Notable Scripts & Notebooks

- `DataGeneration.py` / `methods.py`: Generate QRNG data using all methods
- `postprocessing.py`: Entropy extraction, entropy/waste/throughput analysis
- `parity-extractor.py`: Shannon entropy via parity chunking
- `ottoeplitz.py`: Toeplitz matrix hashing implementation (shared)
- Jupyter Notebooks: Analysis, benchmarking, and visualization for each stage

---

## How to Use

1. **Data Generation**: Use scripts in `MiniGrant/DataGeneration/` to generate new QRNG datasets (requires Qiskit, IBM QPU access for real data).
2. **Postprocessing**: Run scripts/notebooks in `MiniGrant/PostProcessing/` or `SC-Quantathon-2024/Stage4/` for entropy extraction and analysis.
3. **Classification**: Use notebooks in `SC-Quantathon-2024/Stage2/` and `Stage5/` to train/test classifiers on QRNG vs. classical data.
4. **Noise Analysis**: Explore `SC-Quantathon-2024/Stage3/` for noise/fidelity modeling and simulation.