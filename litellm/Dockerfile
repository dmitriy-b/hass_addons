ARG LITELLM_REPOSITORY LITELLM_VERSION
FROM $LITELLM_REPOSITORY:$LITELLM_VERSION as builder
# COPY --from=builder /app/ /app

# https://developers.home-assistant.io/docs/add-ons/configuration#add-on-dockerfile
# ARG BUILD_FROM
# FROM $BUILD_FROM

# Execute during the build of the image
#ARG TEMPIO_VERSION BUILD_ARCH
#RUN \
#    curl -sSLf -o /usr/bin/tempio \
#    "https://github.com/home-assistant/tempio/releases/download/${TEMPIO_VERSION}/tempio_${BUILD_ARCH}"

# Copy root filesystem
COPY rootfs /

# COPY docker-entrypoint.sh /tmp/docker-entrypoint.sh
ENTRYPOINT [ "--config", "/share/litellm/config.yaml", "--port", "4000", "--num_workers", "8" ]
EXPOSE 4000/tcp