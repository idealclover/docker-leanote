FROM centos:latest

RUN  yum -y  install vim  ifconfig  curl wget  net-tools netstat git

ENV LEANOTE_VERSION 2.6.1
ENV MONGO_VERSION 3.0.1
ENV APP_SECRET=V85ZzBeTnzpsHyjQX4zuKbQ8qqtJu9y2aDM55VWxAH1Q0p19poekx3LkcDIvrD2y

WORKDIR /usr/local/bin/

COPY start.sh  .

RUN wget http://sourceforge.net/projects/leanote-bin/files/${LEANOTE_VERSION}/leanote-linux-amd64-v${LEANOTE_VERSION}.bin.tar.gz/download -O leanote-linux-amd64-v${LEANOTE_VERSION}.bin.tar.gz && \
    wget https://fastdl.mongodb.org/linux/mongodb-linux-x86_64-${MONGO_VERSION}.tgz && \
	tar xf leanote-linux-amd64-v${LEANOTE_VERSION}.bin.tar.gz && \
	tar xf mongodb-linux-x86_64-${MONGO_VERSION}.tgz && \
	echo "export PATH=$PATH:/usr/local/bin/mongodb-linux-x86_64-${MONGO_VERSION}/bin" >> /etc/profile && \
	sed -i "s#app.secret.*#app.secret=${APP_SECRET}#g" /usr/local/bin/leanote/conf/app.conf

EXPOSE 9000

CMD bash start.sh
