# LiFang_scRNAseq
single cell RNA seq scripts for Li Fang Jack's fluidigm data

To initially process the expression data (which was mapped via bowtie2), we use the following Rmd script. 

To set up the environment:

```
conda env create -f environment_scRNAseqbest.yml
conda activate scRNAseq_best
```

Change the paths to the data, and then run the Rmd file:

```
fluidigm_sc_analysis.rmd
```

This gets you a seurat object. The seurat object is then used to make an h5ad file to read into python.

Conversion to h5ad:

```
Rscript convert_seurat2anndata.R
```

Now you can run pseudo time and real time analysis with the h5ad ann data object.

To run pseudotime, first install the pseudotime environment:

```
source install_pseudotime_env.sh
```
Then activate:

```
source pst_env/bin/activate
```

Change paths to your h5ad file and run jupyter notebook:

```
pseudotime_LiFang.ipynb
```

For real time, first install the realtime environment and activate it:

```
conda env create -f realtime.yml
conda activate realtime
```

Change paths to your h5ad file and run jupyter notebook:

```
realtime_Lifang.ipynb
```
