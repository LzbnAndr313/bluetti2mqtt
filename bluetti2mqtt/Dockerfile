ARG BUILD_FROM
ARG BLUETTI_MQTT_VERSION
FROM $BUILD_FROM

# Re-declare ARG after FROM to use in RUN commands
ARG BLUETTI_MQTT_VERSION

# Copy data for add-on
COPY rootfs /

# Set as environment variable for runtime access
ENV BLUETTI_MQTT_VERSION=${BLUETTI_MQTT_VERSION}

# Install bluetti_mqtt
RUN apk add --update --no-cache \
	bluez \
	git \
	&& pip install git+https://github.com/LzbnAndr313/bluetti_mqtt.git@${BLUETTI_MQTT_VERSION} \
	# && pip install git+https://github.com/LzbnAndr313/bluetti_mqtt.git \
	&& apk del git \
	&& rm -rf /var/cache/apk/* /lib/apk/db/* \
	&& chmod a+x /run.sh

CMD [ "/run.sh" ]
