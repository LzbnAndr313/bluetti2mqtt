ARG BUILD_FROM
FROM $BUILD_FROM

# Copy data for add-on
COPY rootfs /

# Install bluetti_mqtt
RUN apk add --update --no-cache \
	bluez \
	git \
	&& pip install git+https://github.com/LzbnAndr313/bluetti_mqtt.git@269749da5273ee894535fdca86add8bf595bf6b7 \
	&& apk del git \
	&& rm -rf /var/cache/apk/* /lib/apk/db/* \
	&& chmod a+x /run.sh

CMD [ "/run.sh" ]
