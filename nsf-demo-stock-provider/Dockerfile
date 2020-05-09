FROM tomcat:7.0.77-jre8

#add application jar
ADD ./nsf-demo-stock-provider/target/*.jar /opt/nsf/

#add run command
ADD ./nsf-demo-stock-provider/run.sh  /opt/nsf/
RUN chmod a+x /opt/nsf/run.sh

CMD ["/opt/nsf/run.sh"]