# NCH-Sleep-Data-Preprocessing
Preprocessing pipeline for the NCH Sleep DataBank, including patient selection, oxygen desaturation screening, and EEG epoch extraction.
# NCH Sleep Data Preprocessing

## Overview

This repository contains a preprocessing pipeline for the Nationwide Children's Hospital (NCH) Sleep DataBank.

The pipeline performs:
- Subject selection based on apnea and oxygen desaturation criteria
- Selection of desaturated and undesaturated groups
- EEG epoch extraction from EDF recordings
- Sleep stage filtering (N1, N2, N3, REM)
- Patient-level metadata generation

The extracted EEG epochs can be used for downstream feature extraction and machine learning analyses.

---

## Dataset

This project uses the Nationwide Children's Hospital (NCH) Sleep DataBank.

The dataset includes:
- Polysomnography (PSG) recordings
- EEG signals
- Pulse oximetry (SpO₂)
- Sleep stage annotations
- Apnea annotations
- Oxygen desaturation annotations

---

## Subject Selection

### Desaturated group
Subjects are selected if they:
- have at least one apnea event,
- have oxygen desaturation during the target sleep stage,
- show SpO₂ below 90% during the desaturation event.

### Undesaturated group
Subjects are selected if they:
- have no apnea events,
- never experience oxygen desaturation below 95% during the PSG study.

These criteria follow the methodology described in the reference paper.

---

## Output

The preprocessing pipeline generates:
- EEG epochs (.npy)
- Patient metadata (.csv)
- Subject summary tables

---

## Requirements

- Python 3.x
- MNE
- NumPy
- Pandas
- SciPy

---

## Citation

If you use this repository, please cite the original NCH Sleep DataBank and the corresponding research paper.
