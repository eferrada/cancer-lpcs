# Cancer RNA-seq notebook with separate TSV inputs

1. Unzip the entire archive.
2. Keep `Cancer_RNAseq_full_pipeline_S3_S4.ipynb` beside the `inputs/` folder.
3. Start Jupyter in this folder and run the notebook. The default `saved_results` mode regenerates the figures from the observed TSV results.
4. To rerun the complete analysis, set `MODE = 'raw_counts'`, configure the `.h5ad` paths and install the Python/R dependencies described in the notebook.

The analysis and plotting definitions are unchanged. The compressed table string has been removed. Each source TSV is byte-for-byte identical to its previously embedded version; the JSON manifest records its SHA-256 checksum.

The notebook includes executed saved-results outputs. Raw-count mode still requires the original AnnData files and analysis environment.

The six TSV files contain the composition/target summary, historical robustness classifications, integrated ComBat-seq results, LOSO summaries, within-study effects, and meta-analysis results. Missing values are retained.

## Code annotations

The revised notebook has 60 cells, including 25 code cells. Each operation has an explanation of its purpose, inputs, outputs and QC checkpoint. Function docstrings and inline calculation comments were added, dense Python statements were reformatted, and the R helpers are readable multiline programs. Executable behavior was verified unchanged after ignoring documentation.
