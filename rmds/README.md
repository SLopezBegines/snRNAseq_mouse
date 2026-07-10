# RMarkdown Notebooks — Usage Guide

This directory contains all analysis notebooks. They share the modular scripts in `../code/` and `../code_claude/`.

---

## Which notebook to use

| Notebook | Type | When to use |
|---|---|---|
| `snRNAseq_pipeline.qmd` | ⭐ **Template** | Full snRNA-seq pipeline. **Start here for any new multi-sample experiment.** Covers QC → normalisation → integration → UMAP → clustering → DE. |

---

## Recommended workflow for a new dataset

```
1. Copy the SCT template:
   cp "snRNAseq_pipeline.qmd \
      "MyExperiment_SCT.qmd"

2. Edit the setup chunk (~lines 20–40):
   - Set output_path to your output directory
   - Point data loading to your CellRanger filtered_feature_bc_matrix/ folders
   - Adjust QC thresholds in ../code/global_variables.R

3. Run Clustering Association_FindAllMarkers.Rmd after clustering is complete.
```

---

## Notes

- All notebooks expect `../code/global_variables.R` to be sourced first.
- Outputs are written to `../output/<experiment_name>/` (gitignored).
- Raw 10X data (`rawdata/`) is gitignored — see the main README for download instructions.
