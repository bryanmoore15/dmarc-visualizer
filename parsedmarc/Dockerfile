FROM python:3.9-alpine3.16

# Environment variables for the wait-for-it script and Elasticsearch service
ENV WAIT_FOR_IT_SCRIPT="wait-for-it.sh"
ENV ELASTICSEARCH_HOST="elasticsearch"
ENV ELASTICSEARCH_PORT="9200"

# The directory for running scripts
WORKDIR /scripts

# Installing required packages and libraries for your project and the script
RUN apk add --update --no-cache libxml2-dev libxslt-dev bash \
    && apk add --update --no-cache --virtual .build_deps build-base libffi-dev \
    && pip install parsedmarc 'msgraph-core<1.0.0' \
    && apk del .build_deps

# Add wait-for-it.sh script to the container
COPY parsedmarc.ini /
COPY wait-for-it.sh /scripts/
COPY parsedmarc.ini /scripts/

# Mark the script as executable
RUN chmod +x /scripts/wait-for-it.sh

# Setting the entrypoint to the wait-for-it script, followed by the parsedmarc job
ENTRYPOINT ["/scripts/wait-for-it.sh", "elasticsearch:9200", "--"]
CMD ["parsedmarc", "-c", "/scripts/parsedmarc.ini", "/input/*", "--debug"]
