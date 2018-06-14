# Dockerfile for setting up Docker container with Miniconda and dependencies

FROM continuumio/miniconda3:latest

RUN conda update -y conda

# conda dependencies
RUN conda install -yq -c conda-forge numpy xarray pandas matplotlib six click \
    rpy2 r-signal r-pracma r-cairo r-e1071 r-lubridate r-r.utils r-pixmap \
    r-jsonlite r-httr r-spatstat r-withr r-spam r-locfit r-dotcall64 r-maps \
    r-fields nose coverage make sphinx sphinx_rtd_theme sphinx-gallery numpydoc

# system dependencies
RUN apt-get update && apt-get install -y \
    gcc gfortran xfonts-base libfontconfig1 libxrender1 libsm6

# matplotlib config
RUN mkdir -p /root/.config/matplotlib
RUN echo "backend : Agg" > /root/.config/matplotlib/matplotlibrc
