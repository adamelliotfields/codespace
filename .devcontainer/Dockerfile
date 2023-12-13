# essentially recreate nikolaik/docker-python-nodejs as a dev environment
FROM mcr.microsoft.com/devcontainers/python:3-bookworm

# build args
ARG DEBIAN_FRONTEND=noninteractive
ARG NVM_DIR=/usr/local/share/nvm
ARG NVM_VERSION=lts/*

# some tools assume you want to use yarn if it's in your path
RUN apt-get remove -y yarn

# install poetry
RUN su vscode -c "/usr/local/py-utils/bin/pipx install poetry" 2>&1

# install node
RUN su vscode -c ". ${NVM_DIR}/nvm.sh --no-use && nvm install ${NVM_VERSION} && nvm alias default ${NVM_VERSION}" 2>&1
