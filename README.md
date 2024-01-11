# qiime2_tutorial
Analysis of bacterial 16s amplicon Illumina data using [QIIME2](https://docs.qiime2.org/)
## Usage
### Data preparation
- Create a shortcut or copy the content of your Novogene result into `data/raw`
```bash
# create shortcut or symlink
NOVOGENE_PATH="/mnt/c/Users/matinnu/OneDrive - Danmarks Tekniske Universitet/16S amplicon sequencing data- PMA of env samples with live FISH/X204SC23114431-Z01-F001/X204SC23114431-Z01-F001"
mkdir -p data/raw
ln -s "$NOVOGENE_PATH" data/raw/
```
The data folder will look something like this:
```bash
data
└── raw
    └── X204SC23114431-Z01-F001
        ├── 01.RawData
        │   └── S1
        │       ├── MD5.txt
        │       ├── S1_FKDN230538023-1A_HNN3CDRX3_L2_1.fq.gz
        │       └── S1_FKDN230538023-1A_HNN3CDRX3_L2_2.fq.gz
        ├── 02.Report_X204SC23114431-Z01-F001
        ├── 02.Report_X204SC23114431-Z01-F001.zip
        ├── MD5.txt
        ├── MD5.zip
        ├── Readme.html
        ├── checkSize.xls
        └── metadataFISH.xlsx
```

### Installing QIIME2
- Install [qiime2 conda environment](https://docs.qiime2.org/2023.9/install/native/)
```bash
wget https://data.qiime2.org/distro/amplicon/qiime2-amplicon-2023.9-py38-linux-conda.yml -nc
mamba env create -n qiime2-amplicon-2023.9 --file qiime2-amplicon-2023.9-py38-linux-conda.yml
conda activate qiime2-amplicon-2023.9
mamba install jupyterlab -y
mamba env export > env.yaml
```

### Using Jupyter Notebooks
- Run the Notebooks
```bash
# initiate a jupyter lab server
jupyter lab
```

### Setting up Metadata and Manifest Files
- Prepare metadata and manifest files