FROM r-base

# Install base utilities
RUN apt-get update && \
    apt-get install -y build-essential  && \
    apt-get install -y wget && \
    apt-get install -y tabix && \
    apt-get install -y libreadline-dev && \
    apt-get clean && \
    apt-get install -y procps g++ && \
    rm -rf /var/lib/apt/lists/* 


# Install miniconda
ENV CONDA_DIR /opt/conda
RUN wget --quiet https://repo.anaconda.com/miniconda/Miniconda2-4.6.14-Linux-x86_64.sh -O ~/miniconda.sh && \
    /bin/bash ~/miniconda.sh -b -p /opt/conda

# Put conda in path so we can use conda activate
ENV PATH=$CONDA_DIR/bin:$PATH

RUN conda config --add channels http://conda.anaconda.org/dranew
RUN conda install citup -y
RUN conda install decorator=4.4.1 -y
