FROM debian

ENV TS=/opt/TS3 TS3SERVER_LICENSE=accept

RUN apt update && apt upgrade -y && apt install bzip2 wget apt-utils ca-certificates -y && rm -rf /var/lib/apt/lists/* \
&& wget https://files.teamspeak-services.com/releases/server/3.12.1/teamspeak3-server_linux_amd64-3.12.1.tar.bz2 -O /tmp/chat_server.tar.bz2 \
&& tar jvxf /tmp/chat_server.tar.bz2 -C /opt \
&& mv /opt/teamspeak3-server_* ${TS} \
&& groupadd -g 503 teamspeakadmin \
&& useradd -u 503 -g 503 -d ${TS} teamspeakadmin \
&& mkdir /data \
&& chown -R teamspeakadmin:teamspeakadmin ${TS} /data


USER teamspeakadmin

EXPOSE 9987/UDP 30033 10011

WORKDIR ${TS}

ENTRYPOINT [ "sh", "ts3server_minimal_runscript.sh" ]