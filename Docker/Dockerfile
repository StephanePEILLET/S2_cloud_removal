########################################################################
## Image environnement FLAIR
########################################################################

FROM condaforge/mambaforge

ARG http_proxy=""
ARG https_proxy=""
ARG no_proxy=""
ARG env_name=${env_name}
ENV http_proxy=${http_proxy}
ENV https_proxy=${https_proxy}
ENV no_proxy=${no_proxy}

# Nécessaire pour éviter les messages d'erreur issue de l'installation de libgl1
ARG DEBIAN_FRONTEND=noninteractive

# Mise à jour image
RUN apt-get update \
    && apt-get upgrade -y \
    && apt-get clean \
    && apt-get install -fy fish ranger zip libgl1 libglib2.0-0 \
    && rm -rf /var/lib/apt/lists/*

RUN mamba update -n base -c conda-forge conda

# Création de l'environnement
COPY env/flairhub.yml /home/${env_name}.yml
RUN mamba env create --file=/home/${env_name}.yml

# Definition du bash qui sera utilisé
SHELL ["mamba", "run", "-n", "${env_name}", "/bin/bash", "-c"]

# Nettoyage
RUN mamba clean --all --yes
RUN apt-get clean && \
    apt-get autoremove

WORKDIR /app

# Si utilisation du container en interactif avec fish
ENV MAMBA_ROOT_PREFIX='/opt/conda'
ENTRYPOINT ["mamba", "run", "-n", "${env_name}", "python", "/app/src/main.py"]

# RUN conda init fish
# CMD fish