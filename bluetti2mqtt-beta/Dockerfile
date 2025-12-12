ARG BUILD_FROM
FROM $BUILD_FROM

# Copy data for add-on
COPY rootfs /

# Install bluetti_mqtt
RUN apk add --update --no-cache \
	bluez \
	git \
	&& pip install git+https://github.com/LzbnAndr313/bluetti_mqtt.git@e0f7db93c868ee4a89f9417abdfe7601eb2b3b02 \
	&& apk del git \
	&& rm -rf /var/cache/apk/* /lib/apk/db/* \
	&& chmod a+x /run.sh

CMD [ "/run.sh" ]
