FROM 10.19.13.18:5000/jdk:7
MAINTAINER gucl<gucl@asiainfo.com>

#Install tomcat7
ADD ./apache-tomcat-7.0.72.tar.gz /opt/
RUN ls /opt/apache-tomcat-7.0.72 

RUN sed -i '/\# OS/i JAVA_OPTS="$JAVA_OPTS -server -Xms512M -Xmx512M -XX:PermSize=64M -XX:MaxPermSize=128M  -XX:+UseConcMarkSweepGC -XX:ParallelGCThreads=8 -XX:+PrintCommandLineFlags -XX:+PrintGCDetails -XX:+UseCompressedOops -XX:-UseLargePagesIndividualAllocation -XX:+HeapDumpOnOutOfMemoryError" \n if [[ "$JAVA_OPTS" != *-Djava.security.egd=* ]]; then \n   JAVA_OPTS="$JAVA_OPTS -Djava.security.egd=file:/dev/./urandom" \n  fi'  /opt/apache-tomcat-7.0.72/bin/catalina.sh

ENV CATALINA_HOME /opt/apache-tomcat-7.0.72  
ENV PATH $PATH:$CATALINA_HOME/bin  
ENV PATH $CATALINA_HOME/bin:$PATH

#Expose ports.  
EXPOSE 8080
