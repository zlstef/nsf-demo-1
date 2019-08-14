FROM tomcat:7.0.77-jre8


ADD target/nsf*.war /usr/local/tomcat/webapps/
RUN cd /usr/local/tomcat/webapps && \
    mv nsf*.war ROOT.war && \
    rm -rf ROOT 
    
RUN mkdir -p /opt/nsf && cd /opt/nsf && \
    wget "http://qingzhou.shdq.com/download/nsf-agent-v2.4-190613.jar"
ADD nsf.yml /opt/nsf/nsf.yml

RUN mkdir -p /opt/apm && cd /opt/apm && \
    wget "http://qingzhou.shdq.com/download/napm-java-agent-v2.2.0-190129-6cc820e7.tar.gz" && \
    tar zxvf napm-java-agent.tar.gz && \
    cd ./napm-java-agent/conf && \
    echo "endpoint=http://apm-collector.qingzhou.shdq.com\ncustomHeader=stockCode" >> napm-agent.properties 

CMD ["catalina.sh", "run"]

