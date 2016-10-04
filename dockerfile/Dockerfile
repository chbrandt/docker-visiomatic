FROM bitnami/apache:latest

MAINTAINER "Carlos Brandt <carloshenriquebrandt.gmail>"

RUN DEBIAN_FRONTEND='noninteractive'        && \
    apt-get update                          && \
    apt-get install -y wget unzip vim git   && \
    apt-get clean

# Bitname/apache image provides '/app' for placing the app/www contents
ENV     APPDIR='/app'

# We will provide '/data' for placing the data to be shown by our app
VOLUME  /data

# We will put our html inside $APPDIR and a link to our data volume
WORKDIR $APPDIR
COPY    app/index.html $APPDIR/
RUN     ln -s /data data

# Now, let's just install the apps...
#
RUN git clone https://github.com/astromatic/visiomatic.git
#
RUN LIB="leaflet" LIBV="1.0.1" LIBF="$LIB".zip              && \
    URL="http://cdn.leafletjs.com/$LIB/v$LIBV/$LIBF"        && \
    wget -q $URL -O $LIBF                                   && \
    unzip $LIBF -d $LIB                                     && \
    rm $LIBF
