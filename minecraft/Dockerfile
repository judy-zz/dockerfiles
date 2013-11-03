# Minecraft server for 1.7.2
# Originally forked from crosbymichael at https://github.com/crosbymichael/Dockerfiles

MAINTAINER Clinton Judy, clinton@j-udy.com
FROM ubuntu

# Update and grab dependencies
RUN echo "deb http://archive.ubuntu.com/ubuntu precise main universe" > /etc/apt/sources.list
RUN apt-get update
RUN apt-get upgrade -y
RUN apt-get install -y openjdk-7-jre-headless openjdk-7-jre-lib wget git curl wget

# Install minecraft.jar to /minecraft
RUN mkdir /minecraft
RUN wget -O /minecraft/minecraft.jar https://s3.amazonaws.com/Minecraft.Download/versions/1.7.2/minecraft_server.1.7.2.jar
RUN chmod +x /minecraft/minecraft.jar

# Use default port of 25565, and require it externally.
EXPOSE 25565:25565

# Default command runs minecraft with recommended memory settings.
WORKDIR /minecraft
ENTRYPOINT ["/usr/bin/java", "-Xmx1024M", "-Xms1024M", "-jar", "/minecraft/minecraft.jar", "nogui"]
