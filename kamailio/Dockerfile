FROM debian:buster-slim

LABEL maintener="Thomas Carlier <carlier.thomas@gmail.com>"

# avoid httpredir errors
RUN sed -i 's/httpredir/deb/g' /etc/apt/sources.list

RUN rm -rf /var/lib/apt/lists/* && apt-get update &&   apt-get install --assume-yes gnupg wget
# kamailio repo
RUN echo "deb     http://deb.kamailio.org/kamailio54 buster main" >   /etc/apt/sources.list.d/kamailio.list
RUN echo "deb-src http://deb.kamailio.org/kamailio54 buster main" >   /etc/apt/sources.list.d/kamailio.list
RUN wget -O- http://deb.kamailio.org/kamailiodebkey.gpg | apt-key add -

RUN apt-get update && apt-get install --assume-yes kamailio kamailio-autheph-modules kamailio-berkeley-bin kamailio-berkeley-modules kamailio-cnxcc-modules kamailio-cpl-modules kamailio-erlang-modules kamailio-extra-modules kamailio-geoip-modules kamailio-geoip2-modules kamailio-ims-modules kamailio-json-modules kamailio-kazoo-modules kamailio-ldap-modules kamailio-lua-modules kamailio-memcached-modules kamailio-mongodb-modules kamailio-mono-modules kamailio-mysql-modules kamailio-outbound-modules kamailio-perl-modules kamailio-phonenum-modules kamailio-postgres-modules kamailio-presence-modules kamailio-python-modules kamailio-python3-modules kamailio-rabbitmq-modules kamailio-radius-modules kamailio-redis-modules kamailio-ruby-modules kamailio-sctp-modules kamailio-snmpstats-modules kamailio-sqlite-modules kamailio-systemd-modules kamailio-tls-modules kamailio-unixodbc-modules kamailio-utils-modules kamailio-websocket-modules kamailio-xml-modules kamailio-xmpp-modules

VOLUME /etc/kamailio

# clean
RUN apt-get clean && rm -rf /var/lib/apt/lists/*

ENTRYPOINT ["kamailio", "-DD", "-E"]