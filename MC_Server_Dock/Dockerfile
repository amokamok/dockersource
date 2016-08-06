FROM java

RUN groupadd -g 1234 minecraft && useradd -u 1234 -g minecraft minecraft

USER minecraft

WORKDIR /opt/minecraft
RUN mkdir server
WORKDIR server
RUN cp /opt/minecraft/etc/default/*.* .
RUN echo eula=true > eula.txt
RUN wget http://s3.amazonaws.com/Minecraft.Download/versions/1.10.2/minecraft_server.1.10.2.jar -O minecraft_server.jar

RUN java -Xmx1024M -Xms1024M -jar minecraft_server.jar nogui
