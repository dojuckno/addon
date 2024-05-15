FROM python:3

ENV LANG C.UTF-8

# Copy data for add-on
COPY run.sh /
COPY js /js

WORKDIR /share

# Install requirements for add-on
RUN apk update
RUN apk add --no-cache jq npm make gcc g++ python3 linux-headers udev
RUN python3 -m pip install pyserial
RUN python3 -m pip install paho-mqtt
RUN python3 -m pip install typing_extensions

WORKDIR /
COPY package.json /
RUN npm install

RUN chmod a+x /run.sh

CMD [ "/run.sh" ]
