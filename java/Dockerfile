FROM openjdk:18-jdk-bullseye
SHELL ["bash", "-c"]
ENV JAVA_VERSION=${JAVA_VERSION:-17}
ENV MINECRAFT_VERSION=${MINECRAFT_VERSION:-1.17.1}

# Volumes for minecraft server
RUN mkdir -vp "/srv/minecraft"
VOLUME ["/srv/minecraft"]
WORKDIR /srv

RUN apt-get update

# Download minecraft server JAR
RUN wget https://launcher.mojang.com/v1/objects/a16d67e5807f57fc4e550299cf20226194497dc2/server.jar; \
mv -v server.jar "minecraft-server-${MINECRAFT_VERSION}.jar"

# CMD ["java", "-Xms1024", "-Xmx4096", "-jar", "minecraft-server-${MINECRAFT_VERSION}.jar", "nogui"]