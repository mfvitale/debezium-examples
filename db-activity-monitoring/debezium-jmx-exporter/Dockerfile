ARG DEBEZIUM_VERSION
#FROM quay.io/debezium/connect:${DEBEZIUM_VERSION}
FROM myconnect:latest

ARG JMX_AGENT_VERSION
RUN mkdir /kafka/etc && cd /kafka/etc &&\
        curl -so jmx_prometheus_javaagent.jar \
        https://repo1.maven.org/maven2/io/prometheus/jmx/jmx_prometheus_javaagent/$JMX_AGENT_VERSION/jmx_prometheus_javaagent-$JMX_AGENT_VERSION.jar

RUN cd $KAFKA_HOME/libs &&\
     curl -so opentelemetry-api-1.39.0.jar \
            https://repo1.maven.org/maven2/io/opentelemetry/opentelemetry-api/1.39.0/opentelemetry-api-1.39.0.jar &&\
     curl -so opentelemetry-context-1.39.0.jar \
                https://repo1.maven.org/maven2/io/opentelemetry/opentelemetry-context/1.39.0/opentelemetry-context-1.39.0.jar &&\
    curl -so opentelemetry-sdk-trace-1.39.0.jar \
                    https://repo1.maven.org/maven2/io/opentelemetry/opentelemetry-sdk-trace/1.39.0/opentelemetry-sdk-trace-1.39.0.jar &&\
    curl -so opentelemetry-sdk-common-1.39.0.jar \
                        https://repo1.maven.org/maven2/io/opentelemetry/opentelemetry-sdk-common/1.39.0/opentelemetry-sdk-common-1.39.0.jar &&\
    curl -so opentelemetry-sdk-metrics-1.39.0.jar \
                            https://repo1.maven.org/maven2/io/opentelemetry/opentelemetry-sdk-metrics/1.39.0/opentelemetry-sdk-metrics-1.39.0.jar &&\
    curl -so opentelemetry-sdk-logs-1.39.0.jar.jar \
                                https://repo1.maven.org/maven2/io/opentelemetry/opentelemetry-sdk-logs/1.39.0/opentelemetry-sdk-logs-1.39.0.jar &&\
     curl -so opentelemetry-sdk-1.39.0.jar \
                https://repo1.maven.org/maven2/io/opentelemetry/opentelemetry-sdk/1.39.0/opentelemetry-sdk-1.39.0.jar

COPY config.yml /kafka/etc/config.yml
