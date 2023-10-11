FROM r-base

# Install base utilities
RUN apt-get update && \
    apt-get install -y build-essential  && \
    apt-get install -y wget && \
    apt-get install -y tabix && \
    apt-get install -y libreadline-dev && \
    apt-get install -y libcairo2-dev && \
    apt-get install -y git && \
    apt-get clean && \
    apt-get install -y procps g++ && \
    rm -rf /var/lib/apt/lists/* 

RUN apt-get update && apt install -y procps g++ && apt-get clean && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*


# RNA seq annotation
RUN apt-get update -qq && apt-get -y --no-install-recommends install \
    curl \
    libxml2-dev \
    libssl-dev \
    libcurl4-openssl-dev \
    libssh2-1-dev \
    zlib1g-dev \
    openssl \
    gdebi-core \
    libgsl* \
    libudunits2-dev \
    libgs-dev \
    imagemagick \
    ghostscript \
    qpdf \
    libfontconfig1-dev \
    libharfbuzz-dev \
    libfribidi-dev  libpng-dev libtiff5-dev libjpeg-dev

WORKDIR /

RUN Rscript -e "install.packages(c('BiocManager', 'devtools', 'tidyverse', 'reshape2'))"

RUN Rscript -e "BiocManager::install(c('rhdf5','timescape','DESeq2'))"
RUN Rscript -e "install.packages(c('getopt','stringi'))"


