FROM erlang:18

RUN apt-get update && \
    apt-get install -y vim python perl libtemplate-perl gnuplot && \
    curl http://tsung.erlang-projects.org/dist/tsung-1.7.0.tar.gz --output /tmp/tsung-1.7.0.tar.gz \
    && cd /tmp/ \
    && tar xzf ./tsung-1.7.0.tar.gz \
    && cd tsung-1.7.0 \
    && ./configure \
    && make \
    && make install \
    && mkdir -p /usr/share/tsung \
    && cp tsung-1.0.dtd /usr/share/tsung/ \
    && rm -rf /tmp/tsung* \
    && apt-get clean

EXPOSE 8091

ENTRYPOINT ["tsung"]



