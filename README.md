# BMAC060 metatranscriptomics probe design

## 1. Genome annotation

### 1.1 Clone repository

```{sh}
git clone https://github.com/3d-omics/BMAC060_metatranscriptomics_probe_design.git
cd BMAC060_metatranscriptomics_probe_design
```

### 1.2 Untar and prepare genomes

```{sh}
for f in resources/*.tar.gz; do
  tar -xzf "$f" -C resources
done
```

Remove shit created by MacOS when preparing the genomes

```{sh}
find resources -name ".DS_Store" -delete
find resources -name "._*" -delete
```

### 1.3 Run annotation

We will run a fast annotation in a screen session using [drakkar](https://github.com/alberdilab/drakkar), as we only need the predicted genes.

```{sh}
screen -S BMAC060
conda activate drakkar
drakkar annotating -b resources --annotation-type kegg
```

## 2. Probe design

Coming next...