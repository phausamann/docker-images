# Dockerfile for setting up Docker container with Miniconda and dependencies

FROM continuumio/miniconda3:latest

RUN conda update -y conda

# python packages from conda
RUN conda install -yq -c conda-forge numpy xarray pandas matplotlib six click

# R packages from conda
RUN conda install -yq -c conda-forge \
    rpy2 r-signal r-pracma r-cairo r-e1071 r-lubridate r-r.utils r-pixmap \
    r-jsonlite r-httr r-spatstat r-withr

# matplotlib config
RUN mkdir -p /root/.config/matplotlib
RUN echo "backend : Agg" > /root/.config/matplotlib/matplotlibrc

# fonts for cairo
RUN apt-get update && apt-get install -y \
    xfonts-base libfontconfig1 libxrender1 libsm6

# packages for testing
RUN conda install -y -q nose coverage

# packages for building docs
RUN conda install -yq -c conda-forge \
    make sphinx sphinx_rtd_theme sphinx-gallery numpydoc
