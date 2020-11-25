FROM debian

MAINTAINER mlmpofu

ENV TS3SERVER_LICENSE=accept

WORKDIR /home/teamspeak

EXPOSE 9987:9987/udp 10011:10011 30033:30033

RUN apt-get update && apt-get upgrade && apt-get install wget && \
    wget https://files.teamspeak-services.com/releases/server/3.6.1/teamspeak3-server_linux_amd64-3.6.1.tar.bz2 && \
    tar -xf teamspeak3-server_linux_amd64-3.6.1.tar.bz2 \
    mkdir teamspeak && \
    mv teamspeak3-server_linux_amd64/* /teamspeak && \
    cd teamspeak

WORKDIR teanspeak/teamspeak3-server_linux_amd64

ENTRYPOINT sh ts3server_startscript.sh