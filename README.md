# Three Decades of Pediatric NHANES Research: Bibliometric Analysis

A bibliometric analysis of pediatric NHANES (National Health and Nutrition Examination Survey) research from 1996–2025, examining methodological trends, thematic evolution, and biomarker utilization.

**Author:** January G. Msemakweli

---

## Overview

This project performs a comprehensive bibliometric analysis of scientific publications on pediatric NHANES research. It covers:

- **Descriptive performance analysis** — Annual publication trends, top authors, journals, institutions, and countries
- **Collaboration networks** — Country and institutional collaboration (chord diagrams, network graphs)
- **Keyword co-occurrence** — Thematic maps and keyword networks
- **Biomarker utilization** — Ranking, trends over time, and evolution across three decades
- **CiteSpace export** — WoS plain-text export for dual-map overlay visualization

---

## Requirements

- **R** (≥ 4.0 recommended)
- **RStudio** (optional, for interactive use)

### R Packages

The script installs missing packages automatically. Required packages:

| Package                        | Purpose               |
| ------------------------------ | --------------------- |
| bibliometrix                   | Bibliometric analysis |
| ggplot2                        | Plotting              |
| dplyr, tidyr                   | Data manipulation     |
| stringr                        | String handling       |
| viridis                        | Color scales          |
| circlize                       | Chord diagrams        |
| plotly                         | Interactive plots     |
| ggalluvial                     | Alluvial diagrams     |
| patchwork                      | Multi-panel figures   |
| sf, rnaturalearth, countrycode | Maps and geography    |

---

## Data

### Input

Place your **Web of Science** plain-text export files in the `data_wos/` folder:

1. Search Web of Science for pediatric NHANES publications
2. Export results in **Plain Text** format (not BibTeX or RIS)
3. Save each export as a `.txt` file in `data_wos/`

The script reads all `.txt` files in `data_wos/` and merges them, removing duplicates by DOI and title.

### Project Structure

```
├── README.md
├── analysis_script.Rmd      # Main analysis script
├── data_wos/                # Web of Science export files (.txt)
├── figures/                 # Generated figures (created on first run)
└── export_citespace/        # WoS export for CiteSpace (created on run)
```

---

## How to Run

### Option 1: RStudio

1. Open `analysis_script.Rmd` in RStudio
2. Click **Knit** (or press `Ctrl+Shift+K` / `Cmd+Shift+K`)
3. Choose output format: HTML, PDF, or Word

### Option 2: R Console

```r
# Install rmarkdown if needed
if (!requireNamespace("rmarkdown", quietly = TRUE)) install.packages("rmarkdown")

# Render to HTML (default)
rmarkdown::render("analysis_script.Rmd")

# Or to PDF
rmarkdown::render("analysis_script.Rmd", output_format = "pdf_document")

# Or to Word
rmarkdown::render("analysis_script.Rmd", output_format = "word_document")
```

### Option 3: Command Line

```bash
Rscript -e "rmarkdown::render('analysis_script.Rmd')"
```

---

## Output

- **HTML / PDF / Word report** — Full analysis with tables and figures
- **`figures/`** — PNG figures (annual trends, journals, maps, networks, thematic maps, biomarker plots)
- **`export_citespace/download_pediatric_nhanes.txt`** — WoS-format file for CiteSpace dual-map overlay

---

## CiteSpace Dual-Map Overlay

To create a dual-map overlay in CiteSpace:

1. Open CiteSpace
2. Go to **Data > Import/Export > WOS**
3. Select `export_citespace/download_pediatric_nhanes.txt`
4. Go to **Visualization > Dual Map Overlay**

---

## License

This project is shared for research and educational use. Please cite appropriately if you use or adapt the analysis.
