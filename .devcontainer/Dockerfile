
FROM mcr.microsoft.com/vscode/devcontainers/miniconda:3
RUN apt-get -y update && apt-get -y upgrade
RUN apt-get install -y --no-install-recommends build-essential gcc
# Copy environment.yml (if found) to a temp location so we update the environment. Also
COPY environment.yml /tmp/conda-tmp/environment.yml
RUN if [ -f "/tmp/conda-tmp/environment.yml" ]; then umask 0002 && conda env create -f /tmp/conda-tmp/environment.yml; fi \
    && rm -rf /tmp/conda-tmp
