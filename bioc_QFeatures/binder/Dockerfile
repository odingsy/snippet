FROM rocker/binder:3.6.3

USER root

# install dependencies
RUN install2.r statmod \
  && Rscript -e 'BiocManager::install("QFeatures", update=FALSE)' \
  && rm -rf /tmp/downloaded_files

# copy files
COPY --chown=rstudio:rstudio ./bioc_QFeatures/data ${HOME}/data/
COPY --chown=rstudio:rstudio ./bioc_QFeatures/index.Rmd ${HOME}

USER rstudio
