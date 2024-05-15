FROM alpine:latest

ENV LANG C.UTF-8

# Copy data for add-on
COPY run.sh /
COPY js /js

WORKDIR /share

# Install requirements for add-on
RUN apk update
RUN apk add --no-cache jq npm make gcc g++ python3 linux-headers udev
RUN apt-get update && apt-get -y install jq
RUN python3 -m pip install pyserial && \
        python3 -m pip install paho-mqtt

WORKDIR /
COPY package.json /
RUN npm install

RUN chmod a+x /run.sh

CMD [ "/run.sh" ]
