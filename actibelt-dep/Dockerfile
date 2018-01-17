# Dockerfile for setting up Docker container with Miniconda and dependencies

FROM continuumio/miniconda3:latest

# python packages from conda
RUN conda install -y -q -c conda-forge \
    make gxx_linux-64 gfortran_linux-64 numpy xarray pandas matplotlib six

# R packages from conda
RUN conda install -y -q \
     rpy2=2.9 r-e1071 r-r.utils r-lubridate r-cairo

# matplotlib config
RUN mkdir -p /root/.config/matplotlib
RUN echo "backend : Agg" > /root/.config/matplotlib/matplotlibrc
