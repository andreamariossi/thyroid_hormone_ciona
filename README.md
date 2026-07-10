# Thyroid Hormone Signaling in Ciona

Analysis code and data for thyroid hormone receptor dynamics during *Ciona* development.

## Repository Structure

```
thyroid_hormone_ciona/
├── code/
│   └── Files.qmd          # Main analysis script
├── data/
│   ├── kallisto.merged.gene_counts_length_scaled.rds
│   └── Files.xlsx
├── output/                  # Created automatically, contains generated plots
└── README.md
```

### Folders
- `code/` — Markdown scripts used to process data and generate plots
- `figure/` — exported figure panels (main and supplementary)
- `data/` — source/quantification files used in the analyses

### Rendered analysis reports (HTML)
These HTML files are self-contained figure reports and can be opened in any browser:
- `Fig-00-fiji color scheme.html`
- `Fig-1A_thyroid-receptor.html`
- `Fig-1I_nkx2.1-mut_thr-reporter.html`
- `Fig-2BC_tailRegression-T4&T3.html`
- `Fig-2DE_T4-window_attachment.html`
- `Fig-2DF_T4-window_tailRegression.html`
- `Fig-4C_OEexp_photoreceptor.html`
- `Fig-4D_rescueExp_photoreceptor.html`
- `Fig-S5H_thr_RT-qPCR_nkx2.1-KD.html`
- `Fig-S6_S7_endodermal_strand.html`
- `Fig-S9_T4 & T3 RTqPCR.html`
- `Fig-S10A_goidrogendExp.html`
- `Fig-S10B_goidrogendExpRescue.html`


> If GitHub does not render an HTML file correctly, download it and open it locally (Chrome/Safari/Firefox).

## Requirements

### R Version
- R ≥ 4.0.0

### Required R Packages

Install all required packages with:

```r
install.packages(c(
  "tidyverse", "readxl", "here", "janitor", "paletteer", 
  "rstatix", "ggpubr", "knitr", "Cairo", "patchwork", 
  "lme4", "lmerTest", "emmeans", "kableExtra", "performance", 
  "DHARMa", "broom.mixed", "binom", "ggbeeswarm", "ggdist", 
  "gghalves", "Rmisc", "ggforce", "cowplot", "scales", 
  "car", "ggrepel", "gganimate", "gifski", "transformr"
))

# Bioconductor packages
if (!require("BiocManager", quietly = TRUE))
    install.packages("BiocManager")

BiocManager::install("SummarizedExperiment")
```

```
# # ---- packages ----
# suppressPackageStartupMessages({
#   # Project Management & Paths
#   library(here)         # Essential for relative paths
#   
#   # Data Wrangling
#   library(tidyverse)    # dplyr, ggplot2, forcats, etc.
#   library(readxl)       # Excel import
#   library(janitor)      # Cleaning headers
#   library(scales)       # Formatting axes
#   
#   # Statistics & Modeling
#   library(lme4)         # Mixed models
#   library(lmerTest)     # P-values for lmer
#   library(emmeans)      # Post-hoc comparisons
#   library(rstatix)      # Pipe-friendly stats
#   library(performance)  # Model diagnostics
#   library(DHARMa)       # Residual diagnostics
#   library(broom.mixed)  # Tidy model results
#   library(car)          # Anova tables
#   library(binom)        # Confidence intervals
#   library(Rmisc)
#   
#   # Visualization & Tables
#   library(ggpubr)       # Publication themes
#   library(patchwork)    # Combining plots
#   library(paletteer)    # Color scales
#   library(ggdist)       # Raincloud plots (stat_halfeye)
#   library(ggbeeswarm)   # Jittered points
#   library(gghalves)     # Half-half geoms
#   library(ggforce)      # Extra geoms
#   library(ggrepel)      # Non-overlapping text
#   library(cowplot)      # Publication themes/alignment
#   library(knitr)        # Tables
#   library(kableExtra)   # Table styling
#   library(Cairo)        # High-quality rendering
#   
#   # Animations (if needed)
#   library(gganimate)
#   library(gifski)
#   
#   # Specialized Data Types
#   library(SummarizedExperiment)
# })
```

## Running the Analysis

1. **Clone or download this repository**
   ```bash
   git clone https://github.com/andreamariossi/thyroid_hormone_ciona.git
   cd thyroid_hormone_ciona
   ```

2. **Open R/RStudio**
   - Set your working directory to the repository folder, OR
   - Open the `.Rproj` file

3. **Run the analysis**
   ```r
   # Option 1: Render the Quarto document
   quarto::quarto_render("code/Fig-1..._.qmd")
   
   # Option 2: Run chunks interactively in RStudio
   # Open code/Fig-1a.qmd and run chunks
   ```

4. **Find outputs**
   - Plots will be saved in the `output/` folder
   - HTML report will be generated in the `code/` folder

## Data Sources

- **RNA-seq data**: Hu et al. 2017 developmental time series (https://www.nature.com/articles/s41559-017-0318-0)
- **Proteomics data**: Frese & Mariossi et al. 2024 TMTproC quantification (https://www.cell.com/iscience/fulltext/S2589-0042(24)00576-5)

## Notes
- All paths are handled automatically using the `here` package
- Outputs are saved to `output/` folder when running from GitHub

## Citation

If you use this code or data, please cite:

Mariossi, A., & Levine, M. S. (2026). A thyroid hormone-mediated opsin switch initiates metamorphosis in a proto-vertebrate. *Science Advances*, 12(20), eaeb8106. [https://doi.org/10.1126/sciadv.aeb8106](https://doi.org/10.1126/sciadv.aeb8106)

## Contact

Andrea Mariossi
andrea.mariossi@gmail.com

