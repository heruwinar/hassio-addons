ARG BUILD_FROM
FROM $BUILD_FROM
ENV LANG C.UTF-8

RUN apk update && apk upgrade

RUN apk add --no-cache git \
    iw \
    dnsmasq \
    hostapd \
    screen \
    curl \
    g++ \
    make \
    py3-pip \
    py3-setuptools \
    py3-wheel \
    python3-dev \
    mosquitto \
    haveged \
    net-tools\
    libressl-dev

RUN python3 -m pip install --upgrade paho-mqtt tornado git+https://github.com/drbild/sslpsk.git pycryptodomex

# Copy data for add-on
COPY start.sh /
RUN chmod a+x /start.sh
CMD [ "/start.sh" ]