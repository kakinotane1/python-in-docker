FROM ubuntu:22.04

LABEL maintainer="Kakinotane" \
    version="1.0" \
    description="Python_Docker"

# Define arguments
ARG USERNAME=vscode
ARG USER_UID=1000
ARG USER_GID=${USER_UID}
ARG WORKDIR=/home/${USERNAME}/work

# Create user and install packages
RUN groupadd --gid ${USER_GID} ${USERNAME} \
    && useradd -s /bin/bash --uid ${USER_UID} --gid ${USER_GID} -m ${USERNAME} \
    && apt-get update \
    && apt-get install -y \
    python3 \
    python3-pip \
    python3-venv \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/*

USER ${USERNAME}
WORKDIR ${WORKDIR}
