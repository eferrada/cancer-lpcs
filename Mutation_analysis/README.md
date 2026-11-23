# Unified LPC ESM/COSMIC/gnomAD notebook

Unzip this whole folder. Open LPC_ESM_COSMIC_gnomAD_unified.ipynb from this folder and run all cells.

    conda env create -f environment.yml
    conda activate lpc_esm
    jupyter lab LPC_ESM_COSMIC_gnomAD_unified.ipynb

Default snapshot mode regenerates four figures and numerical outputs using the archived data. Figure 5 bars/reference lines are approximate digitizations, not raw ESM estimates. S5 and S7 use the historical approximate x values, retaining ties and the original Spearman tests. S6 is rebuilt from exact archived sample–variant observations.

## Recompute ESM fractions

Copy one CSV-format .esm file per gene to data/ESMs. Default names are CALHM1.esm, etc. Edit data/esm_inputs.tsv for other filenames and sequence IDs. Each CSV has seq_id, mut_name (M1A format), esm_score. No HUMAN.map is needed. Copy matched CDS FASTA into data/sequences, or explicitly enable Ensembl retrieval. The transcript IDs supplied are canonical Ensembl candidates, not guaranteed matches to the original OMA main isoforms. All translated CDS residues must match the ESM reference; the notebook stops on a mismatch. Set MODE="recompute" and run all cells.

ESM scores contain amino-acid changes, not codons: CDS is necessary to identify SNV-accessible and ROS outcomes. Scores alone cannot recover the ROS subset. Optional inference invokes an independently installed ntranoslab/esm-variants checkout using checked subprocess calls. No inference weights are bundled.

The latest snvs_ros_suppMat.ipynb defines the legacy analysis, including different denominators for All SNV and ROS and a hard-coded control SE denominator. See notebook for exact rules and an explicit comparable-missense sensitivity option. Controls require data/control_fractions.tsv with control_id,category,fraction. The original control data were not attached; snapshot line positions are digitized, not statistically verified.

## Folder contents
- data/: archived joined COSMIC annotations, gnomAD API caches and variants, gene/ESM manifests, digitized fractions and reference images.
- outputs/: executed figures PNG/PDF, tables, statistics, captions, checksums and run manifest.
- provenance/: original supplied notebooks.
- environment.yml: lightweight analysis environment.

The archived inputs are frozen; online sequence retrieval is opt-in. Mutation records may be subject to their source database access terms. These descriptive analyses do not establish causal ROS susceptibility or clinical pathogenicity.
