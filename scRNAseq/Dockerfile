FROM rocker/rstudio

RUN apt-get update && \
    apt-get upgrade -y && \
    apt-get install -y \
        libhdf5-dev \
        libcurl4-gnutls-dev \
        libssl-dev \
        libxml2-dev \
        libpng-dev \
        libxt-dev \
        zlib1g-dev \
        libbz2-dev \
        liblzma-dev \
        libglpk40 \
        #libgit2-28 \
        ffmpeg \
        libcairo2-dev \
#        libcurl4-openssl-dev \
        libglu1-mesa-dev \
        libgsl-dev \
        libmagick++-dev \
        libmariadb-dev \
        libssh2-1-dev \
        libudunits2-dev \
        software-properties-common && \
    apt-get clean all && \
    apt-get purge && \
    rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*

# install JAVA jdk
RUN echo "deb http://ppa.launchpad.net/linuxuprising/java/ubuntu bionic main" | tee /etc/apt/sources.list.d/linuxuprising-java.list && \
apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv-keys 73C3DB2A && \
apt-get update
# && \
# echo oracle-java11-installer shared/accepted-oracle-license-v1-2 select true | sudo /usr/bin/debconf-set-selections && \
# apt-get install -y oracle-java11-installer-local


# install MAGIC and PHATE
# RUN pip3 install --user magic-impute phate


RUN Rscript -e "install.packages(c('BiocManager', 'devtools', 'git2r', 'XML', 'RCurl', 'stringr', 'knitr', 'bookdown', 'pheatmap', 'statmod', 'mvoutlier', 'mclust', 'dplyr', 'penalized', 'cluster', 'Seurat', 'KernSmooth', 'mgcv', 'ROCR', 'googleVis', 'tidyverse', 'ggplot2', 'ggthemes', 'ggbeeswarm', 'corrplot', 'matrixStats', 'lle', 'Rtsne', 'cowplot', 'crayon', 'ggforce', 'ggraph', 'clustree', 'RColorBrewer', 'circlize', 'Rmagic', 'phateR', 'png', 'RMySQL', 'energy', 'doParallel', 'Formula', 'rARPACK', 'seqinr', 'scales', 'data.table', 'ggrepel', 'caret', 'psych', 'colorRamps', 'DT', 'RColorBrewer', 'patchwork', 'reshape2'))"

RUN Rscript -e "BiocManager::install(c('pcaMethods', 'limma', 'SingleCellExperiment', 'Rhdf5lib', 'beachmat', 'scater', 'scran', 'RUVSeq', 'sva', 'SC3', 'TSCAN', 'monocle', 'destiny', 'DESeq2', 'edgeR', 'MAST', 'scfind', 'scmap', 'MultiAssayExperiment', 'SummarizedExperiment', 'annotate', 'biomaRt', 'genefilter', 'geneplotter', 'rtracklayer', 'GenomicFeatures', 'EDASeq', 'ComplexHeatmap', 'scde', 'GSVA', 'AUCell', 'clusterProfiler', 'DOSE', 'GSEABase', 'PGSEA', 'pathview', 'org.Hs.eg.db', 'BiocParallel', 'fgsea', 'clusterExperiment', 'Biobase', 'iCOBRA', 'slingshot', 'CEMiTool', 'BSgenome.Dmelanogaster.UCSC.dm6'))"

RUN Rscript -e "BiocManager::install(c('celldex', 'scran', 'zellkonverter', 'AnnotationDbi', 'DropletUtils', 'EnsDb.Mmusculus.v79', 'SingleR', 'SoupX', 'anndata', 'cerebroApp', 'org.Mm.eg.db', 'patchwork', 'scDblFinder'))"

RUN Rscript -e "install.packages('pathfindR')"

RUN Rscript -e "devtools::install_github(c('hemberg-lab/scRNA.seq.funcs', 'Vivianstats/scImpute', 'theislab/kBET', 'JustinaZ/pcaReduce', 'tallulandrews/M3Drop', 'jw156605/SLICER', 'kieranrcampbell/ouija', 'sinhrks/ggfortify', 'nghiavtr/BPSC', 'statOmics/zingeR', 'dviraran/xCell', 'drisso/zinbwave', 'vqv/ggbiplot', 'thomasp85/gganimate@v0.1.1'))"


RUN sudo apt-get install -y libproj-dev
RUN sudo apt remove -y libmariadb-dev 
RUN sudo apt-get install -y libgdal-dev

RUN Rscript -e "devtools::install_github('aet21/SCENT')"
RUN Rscript -e "install.packages('Signac')"

