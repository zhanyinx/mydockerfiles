FROM python:3.12.0-bookworm
RUN git clone https://github.com/Genotek/ClassifyCNV.git
WORKDIR ClassifyCNV
RUN wget https://github.com/arq5x/bedtools2/releases/download/v2.28.0/bedtools
RUN chmod a+x bedtools
RUN mv bedtools /usr/local/bin
RUN sh update_clingen.sh
