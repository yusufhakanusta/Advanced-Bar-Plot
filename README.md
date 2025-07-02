# GO Term NES Classification Plotter

## 📊 Overview

This R Markdown notebook generates a **grouped bar chart** of Gene Ontology (GO) terms based on **Normalized Enrichment Score (NES)** values across multiple experimental conditions. It supports grouped visualization and faceting by condition or GO categories.

The output is a high-resolution `.tiff` image suitable for publications or presentations.

---

## 🧰 Features

- Imports enrichment data from a `.csv` file.
- Plots GO terms using `ggplot2` with grouping and faceting by conditions.
- Supports custom color themes and font settings.
- Exports the plot in high-resolution `.tiff` format (700 dpi).

---

## 🗂️ Input

The input is a `.csv` file with at least the following columns:

| Column Name   | Description                                       |
|---------------|---------------------------------------------------|
| `NES`         | Normalized Enrichment Score (numeric)             |
| `Description` | GO term description (character)                   |
| `Condition`   | Condition or sample group label (factor/character)|
| `Contion1`    | Higher-level category for facetting (e.g., GO BP) |

> ⚠️ **Note**: The column name `Contion1` appears to be a typo. It should likely be `Condition1`. Update both the code and the CSV if necessary.

---

## 📦 Required Libraries

Make sure you have the following R packages installed:

```r
install.packages(c("ggplot2", "ggthemes", "ggpubr", "Cairo"))
▶️ How to Run

Open the .Rmd or .nb.html file in RStudio.
Click Run All or run each code chunk interactively.
Use file.choose() to select your .csv file when prompted.
The plot will display in RStudio.
A high-resolution Significant GO.tiff will be saved in the working directory.
🖼️ Output

Plot: A grouped and faceted bar chart of NES values by GO term and condition.
Exported File: Significant GO.tiff (500×250 mm, 700 dpi)
🎨 Customization

Colors: Defined manually using scale_fill_manual()
Fonts: Set to Times New Roman
Facets: Controlled via facet_grid() using Condition and Contion1
You can easily modify color schemes, font styles, or resolution in the script.

📝 Notes

This script is ideal for visualizing results from GSEA, ReactomePA, clusterProfiler, or similar enrichment tools.
The exported .tiff file is publication-ready and compatible with high-resolution figure requirements.
👤 Author

Yusuf Hakan Usta
University of Manchester, 2024
Division of Cell Matrix Biology

