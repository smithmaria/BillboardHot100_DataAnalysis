# Billboard Chart Performance Analysis

**How music trends have evolved on the Billboard Hot 100 (1958–2021)**

An exploratory data analysis of over 327,000 Billboard Hot 100 chart entries spanning six decades, examining how songs perform on the charts, how those patterns have shifted in the streaming era, and which artists have dominated across generations.

## Overview

Billboard has ranked the most popular songs in the U.S. every week since the "Hot 100" launched in August 1958. 
Since then, many technological advancements have changed the way we listen to and discover new music. Vinyl, CDs, and social media all affected music in aspects like average song length, time spent on charts, initial chart position, or amount climbing charts before peak or the lack thereof. 

This project uses the full chart history, joined with Spotify audio features, to ask this question:

> **How have songs performed on the charts over time, and what factors influence these trends?**

## Key Findings

- **Chart success is highly unequal.** Chart longevity follows a long-tail distribution- most songs last a median of ~10 weeks, while a small number of mega-hits stay on for 80+ weeks.
- **The streaming era changed chart cycles (~2010).** "Climber" songs (those entering low and working their way up) fell from ~75% of the charts to under 20%. Songs now debut with immediate impact rather than building gradually.
- **Songs got shorter.** Average runtime rose from ~2.5 minutes to a 1990s peak of ~4.5 minutes, then fell ~32% to ~3.2 minutes by 2021. The ebb and flow of song length was affected by physical media constraints (Vinyl -> CDs) then became optimized for streaming economics and the push for virality in the digital era.
- **There's no audio "formula" for a hit.** Across six Spotify audio features (energy, danceability, valence, tempo, loudness, acousticness), *none* meaningfully predicts chart position (all |r| < 0.06), in either the pre-2010 or post-2010 era.
- **Peak position drives longevity.** The strongest relationship found: songs that peak higher stay on the charts significantly longer — success reinforces success.
- **Chart dominance is era-specific.** Top-5 performers in each decade consistently captured 4–8% of all chart weeks, but raw hit counts and total-weeks-charted tell very different stories (e.g. Glee Cast leads in hit count, Taylor Swift in cumulative weeks).

## Dataset

**Top 100 Billboard** — 327,895 chart entries (Aug 1958 – May 2021), with 29,383 unique songs joined to Spotify audio features (99.8% match rate).

- **Source:** [Kaggle — Top 100 Billboard](https://www.kaggle.com/datasets/sujaykapadnis/top-100-billboard) (Sujay Kapadnis, 2023), compiled from Billboard.com chart data and the Spotify Web API.
- Both data files (`data/billboard.csv`, `data/audio_features.csv`) are included in this repository, so no separate download is required.

A full data card — field definitions, limitations, licensing, and attribution — is documented at the top of the notebook.

## Tech Stack

Python · pandas · NumPy · SciPy · Matplotlib · Seaborn · Plotly · Jupyter

## Getting Started

This project uses a conda environment defined in `environment.yml`.

```bash
# 1. Create the environment
conda env create -f environment.yml

# 2. Activate it
conda activate billboard-analysis

# 3. Launch Jupyter and open the notebook
jupyter lab final-project.ipynb
```

Run the notebook cells top to bottom to reproduce the full analysis and visualizations.

## Repository Structure

```
├── final-project.ipynb   # Main analysis notebook
├── data/
│   ├── billboard.csv          # Chart entries (1958–2021)
│   └── audio_features.csv     # Spotify audio features
├── environment.yml       # Conda environment definition
└── README.md
```

## Author

**Maria Smith** — [github.com/smithmaria](https://github.com/smithmaria)
