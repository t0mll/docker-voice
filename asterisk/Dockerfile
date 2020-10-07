FROM debian:buster-slim
LABEL maintainer="Thomas Carlier <carlier.thomas@gmail.com>"

RUN useradd --system asterisk

RUN apt-get update -qq && \
    DEBIAN_FRONTEND=noninteractive \
    apt-get install -y --no-install-recommends \
            autoconf \
            binutils-dev \
            build-essential \
            ca-certificates \
            curl \
            libcurl4-openssl-dev \
            libedit-dev \
            libgsm1-dev \
            libjansson-dev \
            libogg-dev \
            libpopt-dev \
            libresample1-dev \
            libspandsp-dev \
            libspeex-dev \
            libspeexdsp-dev \
            libsqlite3-dev \
            libsrtp2-dev \
            libssl-dev \
            libvorbis-dev \
            libxml2-dev \
            libxslt1-dev \
            portaudio19-dev \
            uuid \
            uuid-dev \
            vim \
            xmlstarlet \
            && \
    apt-get purge -y --auto-remove && rm -rf /var/lib/apt/lists/*

ENV ASTERISK_VERSION=17.4.0
ADD /build-asterisk.sh /src/
RUN echo $(ls -a1 /src)
RUN /src/build-asterisk.sh && rm -f /src/build-asterisk.sh
COPY conf/ /etc/asterisk/
CMD ["/usr/sbin/asterisk", "-f"]
