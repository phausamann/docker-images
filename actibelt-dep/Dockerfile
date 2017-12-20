# Dockerfile for setting up Docker container with Miniconda and dependencies

FROM ubuntu:14.04

# System packages
RUN apt-get update && apt-get install -y curl
RUN sudo apt-get install -y libglu1

# Install miniconda to /miniconda
RUN curl -LO http://repo.continuum.io/miniconda/Miniconda3-latest-Linux-x86_64.sh
RUN bash Miniconda3-latest-Linux-x86_64.sh -p /miniconda -b
RUN rm Miniconda3-latest-Linux-x86_64.sh
ENV PATH=/miniconda/bin:${PATH}
RUN conda update -y conda

# Python packages from conda
RUN conda install -q -y -c conda-forge \
    make gxx_linux-64 r-e1071 numpy xarray pandas matplotlib tqdm six rpy2=2.9

# matplotlib config
RUN mkdir -p /root/.config/matplotlib
RUN echo "backend : Agg" > /root/.config/matplotlib/matplotlibrc
