FROM python:3.9-alpine3.16

RUN apk add --update --no-cache libxml2-dev libxslt-dev
RUN apk add --update --no-cache --virtual .build_deps build-base libffi-dev \
    && pip install parsedmarc 'msgraph-core<1.0.0' \
    && apk del .build_deps

COPY parsedmarc.ini /
#COPY GeoLite2-Country.mmdb /usr/share/GeoIP/GeoLite2-Country.mmdb

# Command to run the parsedmarc tool
CMD ["parsedmarc"]