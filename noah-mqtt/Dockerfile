# Use explicit base image – required since Supervisor 2026.04
FROM ghcr.io/home-assistant/aarch64-base-python:3.13-alpine3.21

ARG BUILD_VERSION="dev"
ARG BUILD_ARCH="aarch64"

# Version des noah-mqtt-Releases (anpassen!)
ENV NOAH_MQTT_VERSION="0.0.29"

# Architektur-Mapping für die noah-mqtt-Releases
# aarch64 → arm64, amd64 → amd64, etc.
RUN if [ "${BUILD_ARCH}" = "aarch64" ]; then \
      ARCH="arm64"; \
    elif [ "${BUILD_ARCH}" = "amd64" ]; then \
      ARCH="amd64"; \
    else \
      echo "Unsupported arch: ${BUILD_ARCH}"; exit 1; \
    fi && \
    echo "ARCH=${ARCH}" > /arch.txt

RUN apk add --no-cache \
    python3 \
    py3-pip \
    jq \
    bashio \
    curl \
    tar

# Download und Installation von noah-mqtt
RUN ARCH=$(cat /arch.txt | cut -d= -f2) && \
    curl -L -o /noah-mqtt.tar.gz \
      "https://github.com/mtrossbach/noah-mqtt/releases/download/v${NOAH_MQTT_VERSION}/noah-mqtt_${NOAH_MQTT_VERSION}_linux_${ARCH}.tar.gz" && \
    tar -xf /noah-mqtt.tar.gz -C / && \
    rm /noah-mqtt.tar.gz

# Copy run.sh (muss im Add-on-Ordner liegen)
COPY run.sh /run.sh
RUN chmod a+x /run.sh

LABEL \
  io.hass.version="${BUILD_VERSION}" \
  io.hass.arch="${BUILD_ARCH}" \
  io.hass.type="app" \
  io.hass.name="Noah-MQTT" \
  io.hass.description="Integrating Growatt Noah 2000 home batteries with Home Assistant via MQTT, enabling real-time monitoring and control of your energy storage system." \
  io.hass.url="https://github.com/Hypopheralcus/hassio-addons"

WORKDIR /

CMD ["/run.sh"]
