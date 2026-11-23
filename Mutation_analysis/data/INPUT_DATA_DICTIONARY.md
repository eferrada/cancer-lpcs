# Input data and provenance

| File/folder | Role | Status |
|---|---|---|
| ESMs/*.esm | seq_id,mut_name,esm_score CSV; one per gene | User supplied at run time; not attached here |
| esm_inputs.tsv | Gene-to-score/CDS/protein filenames and selected transcript/sequence ID | Editable; canonical transcript candidates |
| sequences/*.cds.fasta | Single-record in-frame CDS; terminal stop allowed | Supply matching CDS or opt into retrieval |
| gene_manifest.tsv | Frozen GRCh38 full genomic span and canonical protein length in aa | Recovered previous analysis |
| figure5_digitized.tsv | Approximate bars, pixel positions and category | Digitized from attached Figure5.png |
| figure5_reference_lines_digitized.tsv | Approximate control-line positions | Raw control values unavailable |
| historical_correlation_x.tsv | Approximate All SNV fractions used in original S5/S7, preserving ties | Recovered previous analysis |
| cosmic_annotated_mutations.tsv | Joined COSMIC v104 target mutations, sample/classification fields | Archived 22,276 annotation rows before analysis filters |
| cosmic_expected_matrix.tsv | Independent 30 × 12 comparison matrix | Exact count verification |
| cosmic_join_audit.json | Original sample/phenotype join audit | Recovered previous analysis |
| api/*.json | gnomAD response, original query, dataset and retrieval date | Archived 11 Nov 2026 |
| all_target_variants.tsv.gz | Flattened archived gnomAD variants | External audit table; plots rebuilt from API cache |
| gnomAD_30genes_summary.tsv | Original count and quality-flag summaries | Independent count verification and frozen inclusion decisions |
| target_constraint_canonical.tsv | Target-only released constraint records | Archived release 4.1.2 slice |
| gnomAD_30genes_paired_values.tsv | Original integrated table, including expression approximations | Provenance; not required for primary figure calculations |
| provenance.json | Original gnomAD source URLs/checksums | References full source constraint resource, not bundled |
| reference_images/*.png | Four user-supplied figures | Visual comparison only |

Optional controls: create control_fractions.tsv (control_id, category, fraction). Category is All SNV or ROS, with one row per control/category. Use matching ESM and counting settings. No fabricated control data are included.

The ESM model checkpoint and complete human-genome reference datasets are not bundled. No HUMAN.map is required. All numerical inputs are external to the notebook.
