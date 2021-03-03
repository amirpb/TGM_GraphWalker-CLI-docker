FROM debian:stretch

RUN apt-get update
RUN apt-get install -y \
    wget \
    openjdk-8-jdk

# Get the GraphWalker CLI jar
RUN wget https://github.com/GraphWalker/graphwalker-project/releases/download/4.2.0/graphwalker-cli-4.2.0.jar

# Create a script
RUN echo '#!/bin/bash\n/usr/lib/jvm/java-8-openjdk-amd64/jre/bin/java -jar /graphwalker-cli-4.2.0.jar "$@"' >> /graphwalker-cli
RUN chmod +x graphwalker-cli

# Create a symbolic link
RUN ln -s /graphwalker-cli /usr/bin/gw
