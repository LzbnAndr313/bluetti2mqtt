ARG BUILD_FROM
FROM $BUILD_FROM

# Copy data for add-on
COPY rootfs /

# Install bluetti_mqtt
RUN apk add --update --no-cache \
	bluez \
	git \
	&& pip install git+https://github.com/LzbnAndr313/bluetti_mqtt.git@9f15ae231f6c499099aa0f94ce649baac95cefc4 \
	&& apk del git \
	&& rm -rf /var/cache/apk/* /lib/apk/db/* \
	&& chmod a+x /run.sh

CMD [ "/run.sh" ]
