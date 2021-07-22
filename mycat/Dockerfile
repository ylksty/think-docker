FROM java:8-jre
MAINTAINER <ylkget@163.com>
LABEL Description="使用mycat做mysql数据库的读写分离"
ENV mycat-version Mycat-server-1.6.5-release-20180122220033-linux.tar.gz
USER root
COPY install/Mycat-server-1.6.5-release-20180122220033-linux.tar.gz /
RUN tar -zxf /Mycat-server-1.6.5-release-20180122220033-linux.tar.gz
COPY install/Mycat-web-1.0-SNAPSHOT-20170102153329-linux.tar.gz /
RUN tar -zxf /Mycat-web-1.0-SNAPSHOT-20170102153329-linux.tar.gz
ENV MYCAT_HOME=/mycat
ENV PATH=$PATH:$MYCAT_HOME/bin
WORKDIR $MYCAT_HOME/bin
RUN chmod u+x ./mycat

EXPOSE 8066 9066 8082
CMD ["sh","/mycat-web/start.sh"]
CMD ["./mycat","console"]