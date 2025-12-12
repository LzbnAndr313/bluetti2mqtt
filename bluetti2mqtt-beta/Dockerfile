ARG BUILD_FROM
FROM $BUILD_FROM

# Copy data for add-on
COPY rootfs /

# Install bluetti_mqtt
RUN apk add --update --no-cache \
	bluez \
	git \
	&& pip install git+https://github.com/LzbnAndr313/bluetti_mqtt.git@79102323e42fda5207362c2f704ad2c2b5c6a7f5 \
	&& apk del git \
	&& rm -rf /var/cache/apk/* /lib/apk/db/* \
	&& chmod a+x /run.sh

CMD [ "/run.sh" ]
