FROM ubuntu:jammy

ENV DEBIAN_FRONTEND=noninteractive

WORKDIR /minecraft

RUN apt-get update && apt-get install -y \
    openjdk-21-jdk \
    wget \
    && rm -rf /var/lib/apt/lists/*

RUN wget -O paper.jar https://api.papermc.io/v2/projects/paper/versions/1.21.1/builds/128/downloads/paper-1.21.1-128.jar

RUN echo "eula=true" > eula.txt

EXPOSE 25565

ENTRYPOINT [ "java" ]

CMD [ "-Xmx1024M", "-Xms1024M", "-jar", "paper.jar", "nogui" ]