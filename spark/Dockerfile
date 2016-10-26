
FROM openjdk:8u92-jdk-alpine
RUN apk update && \
    apk add bash python3 && \
    ln -s /usr/bin/python3 /usr/bin/python

RUN mkdir -p /spark/yarn-conf
ENV YARN_CONF_DIR "/data/yarn-conf"
ENV HADOOP_USER_NAME "hdfs"
ENV SPARK_HOME "/spark/spark-2.0.1-bin-hadoop2.7/"

# install spark
RUN cd /spark && \
    wget -qc "http://apache.fayea.com/spark/spark-2.0.1/spark-2.0.1-bin-hadoop2.7.tgz" && \
    tar -xf spark-2.0.1-bin-hadoop2.7.tgz && \
    rm -rf spark-2.0.1-bin-hadoop2.7.tgz && \
    ln -s "/spark/spark-2.0.1-bin-hadoop2.7/bin/"* "/usr/bin/"
CMD ["spark-shell"]
