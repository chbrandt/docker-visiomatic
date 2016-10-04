FROM bitnami/apache:latest

MAINTAINER "Carlos Brandt <carloshenriquebrandt.gmail>"

RUN DEBIAN_FRONTEND='noninteractive'        && \
    apt-get update                          && \
    apt-get install -y wget unzip vim git   && \
    apt-get clean

ENV APPDIR='/app'

WORKDIR $APPDIR

RUN git clone https://github.com/astromatic/visiomatic.git

RUN LIB="leaflet" LIBV="1.0.1" LIBF="$LIB".zip          && \
    URL="http://cdn.leafletjs.com/$LIB/v$LIBV/$LIBF"    && \
    wget -q $URL -O $LIBF                               && \
    unzip $LIBF -d $LIB

COPY app/index.html $APPDIR/
