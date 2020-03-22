# Installing R version 3.6.1 from rocker
FROM rocker/rstudio

LABEL maintainer="Rami Krispin <rami.krispin@gmail.com>"

# Installing R external dependencies
RUN apt-get update && apt-get install -y --no-install-recommends \
        libgit2-dev \
        libxml2-dev \
        libudunits2-dev \
        libgdal-dev \
        libcairo2-dev \
        libxt-dev \
        libv8-dev \
        libssl-dev \
        r-cran-rcpp \
        r-cran-inline \
        libpoppler-cpp-dev \
        libtesseract-dev \
        libleptonica-dev \
        tesseract-ocr-eng \
        libmagick++-dev \
        libavfilter-dev \
        libzmq3-dev \
        cargo

# Installing required packages
RUN install2.r -r https://cran.microsoft.com/snapshot/2020-03-01 \
        --error \
#        --deps TRUE \
        dplyr \
        devtools \
        magrittr \
        rnaturalearth \
        sf


RUN R -e 'devtools::install_github("RamiKrispin/coronavirus")'

