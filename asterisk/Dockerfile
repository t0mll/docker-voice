FROM debian:buster-slim

LABEL maintainer="Thomas Carlier <carlier.thomas@gmail.com>"

ENV ASTERISK_VERSION asterisk-17-current

COPY build-asterisk.sh /
RUN  chmod 755 /build-asterisk.sh
RUN /build-asterisk.sh

EXPOSE 5060/udp 5060/tcp
VOLUME /var/lib/asterisk/sounds /var/lib/asterisk/keys /var/lib/asterisk/phoneprov /var/spool/asterisk /var/log/asterisk

COPY docker-entrypoint.sh /
RUN  chmod 755 /docker-entrypoint.sh
#ENTRYPOINT ["/docker-entrypoint.sh"]
CMD ["/usr/sbin/asterisk", "-vvvdddf", "-T", "-W", "-U", "asterisk", "-p"]