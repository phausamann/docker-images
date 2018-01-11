# Dockerfile for setting up Docker container with Miniconda and dependencies

FROM continuumio/miniconda3:latest

# Python packages from conda
RUN conda install -q -y -c conda-forge \
    make gxx_linux-64 gfortran_linux-64 numpy xarray pandas matplotlib six rpy2=2.9

# matplotlib config
RUN mkdir -p /root/.config/matplotlib
RUN echo "backend : Agg" > /root/.config/matplotlib/matplotlibrc
