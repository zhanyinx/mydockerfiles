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


RUN apt-get update && apt-get install -y libgit2-dev

RUN Rscript -e "install.packages(c('BiocManager', 'workflowr', 'knitr'))"
RUN Rscript -e "BiocManager::install('casper')"

RUN Rscript -e "BiocManager::install(c('biomaRt', 'limma', 'GO.db', 'org.Hs.eg.db', 'GOstats',  'GenomicRanges'))"

RUN Rscript -e "install.packages(c('devtools'))"
RUN Rscript -e "devtools::install_github(c('akdess/CaSpER'))"
RUN Rscript -e "install.packages(c('DT'))"
