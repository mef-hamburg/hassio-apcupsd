ARG BUILD_FROM
FROM $BUILD_FROM

ENV LANG C.UTF-8

COPY run.sh /
RUN chmod a+x /run.sh

RUN rm /sbin/poweroff
COPY hassio_poweroff /sbin/poweroff
RUN chmod a+x /sbin/poweroff

RUN rm /sbin/reboot
COPY hassio_reboot /sbin/reboot
RUN chmod a+x /sbin/reboot

RUN apk add --no-cache apcupsd jq curl openssh msmtp mailx libgcc libusb-compat musl util-linux libmodbus-dev libusb-dev

RUN ln -sf /usr/bin/msmtp /usr/sbin/sendmail

WORKDIR /data

CMD [ "/run.sh" ]
