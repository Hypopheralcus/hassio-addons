# Use explicit base image – required since Supervisor 2026.04
# aarch64 + Python 3.13 on Alpine 3.21 (current latest)
FROM ghcr.io/home-assistant/aarch64-base-python:3.13-alpine3.21

# Build arguments (optional, can be overridden by CI)
ARG BUILD_VERSION="dev"
ARG BUILD_ARCH="aarch64"

# Install runtime dependencies (anpassen an deine Bedürfnisse)
RUN apk add --no-cache \
    python3 \
    py3-pip \
    jq \
    bashio

# Copy add-on files into the image
COPY run.sh /run.sh
COPY noah_mqtt/ /app/

RUN chmod a+x /run.sh

# Labels required for apps
LABEL \
  io.hass.version="${BUILD_VERSION}" \
  io.hass.arch="${BUILD_ARCH}" \
  io.hass.type="app" \
  io.hass.name="Noah-MQTT" \
  io.hass.description="Integrating Growatt Noah 2000 home batteries with Home Assistant via MQTT, enabling real-time monitoring and control of your energy storage system." \
  io.hass.url="https://github.com/Hypopheralcus/hassio-addons"

WORKDIR /app

CMD ["/run.sh"]
