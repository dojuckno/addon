ARG BUILD_FROM
FROM $BUILD_FROM

ENV LANG C.UTF-8
# Copy data for add-on
COPY run.sh /
COPY js /js
WORKDIR /share

# Install requirements for add-on
RUN apk add --no-cache jq npm make gcc g++ python3 linux-headers udev \
&& npm init -f

RUN chmod a+x /run.sh

# CMD [ "/run.sh" ]
ENTRYPOINT [ "/run.sh" ]
