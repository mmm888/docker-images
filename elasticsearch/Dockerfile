FROM elasticsearch:5.6-alpine

ENV ES_JAVA_OPTS "-Xms256m -Xmx256m"

RUN ./bin/elasticsearch-plugin list | grep -q analysis-kuromoji || ./bin/elasticsearch-plugin install analysis-kuromoji && \
    ./bin/elasticsearch-plugin list | grep -q analysis-icu || ./bin/elasticsearch-plugin install analysis-icu

ENTRYPOINT ["/docker-entrypoint.sh", "elasticsearch"]
