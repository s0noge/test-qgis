FROM debian:buster-slim

ARG DEBIAN_FRONTEND=noninteractive

RUN apt-get update \
    && apt -y install wget \
    && apt -y install gnupg software-properties-common \
    && wget -qO - https://qgis.org/downloads/qgis-2021.gpg.key | gpg --no-default-keyring --keyring gnupg-ring:/etc/apt/trusted.gpg.d/qgis-archive.gpg --import \
    && chmod a+r /etc/apt/trusted.gpg.d/qgis-archive.gpg \
    && add-apt-repository "deb https://qgis.org/debian `lsb_release -c -s` main" \
    && apt-get update \
    && apt search qgis \
    && apt -y install qgis python-qgis qgis-plugin-grass saga
