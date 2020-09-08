FROM node:14-alpine

RUN apk add python2 make g++ dpkg wget --no-cache && \
    wget --no-check-certificate --user-agent=Mozilla -O apache-pulsar-client-dev.deb "https://archive.apache.org/dist/pulsar/pulsar-2.4.2/DEB/apache-pulsar-client-dev.deb" && \
    wget --no-check-certificate --user-agent=Mozilla -O apache-pulsar-client.deb "https://archive.apache.org/dist/pulsar/pulsar-2.4.2/DEB/apache-pulsar-client.deb" && \
    dpkg --force-architecture -i apache-pulsar-client*.deb

COPY docker-entrypoint.sh /usr/local/bin/
RUN chmod 777 /usr/local/bin/docker-entrypoint.sh \
    && ln -s /usr/local/bin/docker-entrypoint.sh /

ENTRYPOINT ["docker-entrypoint.sh"]

CMD [ "node" ]

