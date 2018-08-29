FROM tensorflow/tensorflow:nightly

# Install java
RUN add-apt-repository -y ppa:openjdk-r/ppa && \
    apt-get update && \
    apt-get install -y --no-install-recommends \
    openjdk-8-jdk openjdk-8-jre-headless && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/*

ENV PASSWORD abc
ENV JAVA_HOME /usr/lib/jvm/java-8-openjdk-amd64
ENV LD_LIBRARY_PATH $LD_LIBRARY_PATH:$JAVA_HOME/jre/lib/amd64/server

ADD events.out.tfevents.1535206827.NTB-GOFFTON /tf_logs/
RUN chmod 777 /tf_logs/*
ENTRYPOINT ["tensorboard"]