# Use explicit base image – required since Supervisor 2026.04
FROM ghcr.io/home-assistant/base:2026.08

# Build arguments (optional, can be overridden by CI)
ARG BUILD_VERSION="dev"
ARG BUILD_ARCH="aarch64"

# Install runtime dependencies (adjust to what your add-on actually needs)
RUN apk add --no-cache \
    python3 \
    py3-pip \
    jq \
    bashio

# Copy add-on files into the image
COPY run.sh /run.sh
COPY config.yaml /data/options.json  # fallback, actual options come from Supervisor
COPY noah_mqtt/ /app/

RUN chmod a+x /run.sh

# Labels required for apps (adjust values to your add-on)
LABEL \
  io.hass.version="${BUILD_VERSION}" \
  io.hass.arch="${BUILD_ARCH}" \
  io.hass.type="app" \
  io.hass.name="Noah-MQTT" \
  io.hass.description="Integrating Growatt Noah 2000 home batteries with Home Assistant via MQTT" \
  io.hass.url="https://github.com/Hypopheralcus/hassio-addons"

WORKDIR /app

CMD ["/run.sh"]
