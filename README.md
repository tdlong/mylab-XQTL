# mylab-XQTL

This is a project repo for running the [XQTL2 pipeline](https://github.com/tdlong/XQTL2).

## Setup

1. Clone this repo and rename it to your lab (e.g. `SmithLab-XQTL`):
   ```bash
   git clone https://github.com/tdlong/mylab-XQTL.git SmithLab-XQTL
   cd SmithLab-XQTL
   ```

2. Clone XQTL2 alongside it and create the pipeline symlink:
   ```bash
   cd ..
   git clone https://github.com/tdlong/XQTL2.git
   cd SmithLab-XQTL
   ln -s ../XQTL2 pipeline
   ```

3. Follow the [XQTL2 README](https://github.com/tdlong/XQTL2) to complete installation
   (download founder BAMs, download and index the reference genome).

4. Run the malathion training example to verify your installation works —
   see `scripts_oneoffs/malathion/malathion_pipeline.sh`.

## Structure

```
mylab-XQTL/
├── pipeline -> ../XQTL2        ← symlink (create after cloning)
├── helpfiles/
│   └── <project>/              ← barcodes, bam_list, hap_params, design
├── scripts_oneoffs/
│   └── <project>/              ← submission scripts
├── data/                       ← gitignored (raw reads, BAMs)
├── process/                    ← gitignored (pipeline output)
└── logs/                       ← gitignored (SLURM logs)
```

Each project lives in its own subdirectory under `helpfiles/` and `scripts_oneoffs/`.
See `helpfiles/malathion/` and `scripts_oneoffs/malathion/` for a worked example.
