FROM python:3.11.6-slim



ENV PYTHONDONTWRITEBYTECODE 1
ENV PYTHONUNBUFFERED 1


RUN apt-get update && apt-get install -y python3-opencv
RUN apt-get install -y libvips


# Temporary install gcc, needed for some of the requirements
RUN apt-get install -y gcc g++

# Remove gcc
RUN apt-get purge -y --auto-remove gcc g++

RUN pip install --upgrade pip
RUN apt-get install -y git

RUN git clone https://github.com/CellProfiling/pipex.git
WORKDIR /pipex
RUN pip install -r requirements.txt

