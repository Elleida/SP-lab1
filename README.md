# Lab Work #1 — Speech Signal Analysis and Processing

**Erasmus Mundus Master in Linguistic Data Science**  
University of Zaragoza · Academic Year 2025–2026  
*Course Instructors: Prof. Eduardo Lleida · Prof. Antonio Miguel · Prof. Alfonso Ortega*

---

## Overview

This laboratory introduces the **Source-Filter Model** of speech production and its
practical applications in acoustic phonetics and speech technology. Students work with
real speech recordings using **Praat** and **Python (Google Colab)** to explore how the
glottal source, vocal-tract filter, and prosodic parameters interact to produce the
speech signal.

---

## Repository Contents

| File | Description |
|---|---|
| `SP-lab1.pdf` | Lab manual (compiled PDF, ready to read) |
| `task4_vowel_analysis.ipynb` | Python notebook for Task 4 (vowel analysis) |

> The LaTeX source (`SP-lab1.tex`) is not included in the public repository.

### Audio Data

The audio corpora (`femalefiles.zip` and `malefiles.zip`) are too large for the repository.
Download them from the **[Releases page](https://github.com/Elleida/SP-lab1/releases/latest)**:

| File | Contents | Size |
|---|---|---|
| `femalefiles.zip` | Vowel recordings — female speakers | ~25 MB |
| `malefiles.zip` | Vowel recordings — male speakers | ~25 MB |

---

## Tasks

### Task 1 — The Effect of Sampling Frequency
- Understand the Nyquist–Shannon sampling theorem in practice.
- Downsample a speech recording to telephone (8 kHz), wideband (16 kHz), and full-band (44.1 kHz) qualities using Praat.
- Compare spectrograms and listen to the perceptual effect of band-limitation and aliasing.

### Task 2 — Recording and Annotation in Praat
- Record the sentence *"She left the door open."* in three prosodic modes: **declarative**, **interrogative**, and **exclamative**.
- Annotate the recordings with TextGrids in Praat (word and phoneme tiers).
- Measure $F_0$ contours, intensity, and segment durations and relate them to prosodic contrasts.

### Task 3 — Prosody and Glottal Synthesis
- Extract the $F_0$ contour from the recordings using Praat's pitch analysis.
- Re-synthesise the voiced excitation from the detected pitch using three different source models and compare their perceptual qualities:
  - **Pulse train** (`To Sound (pulse train)`) — raw Dirac impulses, maximally robotic.
  - **Hum** (`To Sound (hum)`) — band-limited pulse train, smoother buzzing quality.
  - **Sinusoid** (`To Sound (sine)`) — pure $F_0$ tone, isolates the intonation contour.
- Modulate the amplitude of the synthesised signal using the original intensity envelope (`To Intensity` → `Down to IntensityTier` → `Multiply`) to obtain a more natural-sounding result.

### Task 4 — Vowel Analysis in Python (Google Colab)
- Analyse a corpus of sustained vowel recordings (/a/, /i/, /u/) from male and female speakers using **Parselmouth** (Python bindings for Praat).
- Extract $F_1$ and $F_2$ formants automatically after silence trimming.
- Plot vowel spaces and compare male vs. female formant distributions.
- Fit **Gaussian Mixture Models (GMM)** to the formant data and evaluate speaker-group separation using the **Bayesian Information Criterion (BIC)**.

---

## Tools and Requirements

| Tool | Purpose |
|---|---|
| [Praat](https://www.fon.hum.uva.nl/praat/) | Speech analysis, annotation, and synthesis (Tasks 1–3) |
| Python ≥ 3.9 | Scripting and statistical modelling (Task 4) |
| [praat-parselmouth](https://parselmouth.readthedocs.io/) | Praat engine as a Python library |
| numpy, pandas, matplotlib, scipy, scikit-learn | Data processing and visualisation |
| Google Colab (optional) | Cloud execution of the notebook |

---

## Background Reading

The lab manual includes self-contained theoretical sections covering:

- The **Source-Filter Model** ($S(f) = G(f) \cdot V(f) \cdot R(f)$) and its LPC formulation.
- **Formants** and the vowel quadrilateral ($F_1$ ↔ tongue height, $F_2$ ↔ tongue backness).
- The **Cepstrum** as a tool for source-filter separation.
- **Prosody**: intonation ($F_0$), prominence (intensity + duration), and rhythm.
- **GMM** clustering and model selection with BIC.

---

## License

Course material — University of Zaragoza. For educational use within the Erasmus Mundus Master in Linguistic Data Science programme.
