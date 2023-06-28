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

# Install miniconda
ENV CONDA_DIR /opt/conda
RUN wget --quiet https://repo.anaconda.com/miniconda/Miniconda3-py39_22.11.1-1-Linux-x86_64.sh -O ~/miniconda.sh && \
    /bin/bash ~/miniconda.sh -b -p /opt/conda

# Put conda in path so we can use conda activate
ENV PATH=$CONDA_DIR/bin:$PATH

RUN pip install pandas

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
    libfreetype6-dev \
    libharfbuzz-dev \
    libfribidi-dev libfreetype6-dev libpng-dev libtiff5-dev libjpeg-dev

# samtools
RUN wget https://github.com/samtools/samtools/releases/download/1.17/samtools-1.17.tar.bz2
RUN tar -xf samtools-1.17.tar.bz2
WORKDIR samtools-1.17
RUN ./configure --prefix=/
RUN make
RUN make install

WORKDIR /

RUN Rscript -e "install.packages(c('BiocManager', 'devtools', 'tidyverse', 'reshape2'))"

RUN conda install pytables -y
RUN Rscript -e "BiocManager::install(c('rhdf5','timescape'))"
RUN Rscript -e "install.packages(c('getopt'))"


#pyclone

RUN pip install click h5py numba numpy==1.22.4 scipy
RUN pip install git+https://github.com/Roth-Lab/pyclone-vi.git


# pyranges
RUN pip install pyranges

# pandoc
RUN apt-get install pandoc -y
