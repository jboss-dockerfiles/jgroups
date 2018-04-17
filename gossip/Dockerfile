FROM jboss/base-jdk:8

ENV JGROUPS_VERSION 4.0.8.Final

ENV LOG4J2_VERSION 2.7
ENV LOG4J2_FILE /opt/jboss/log4j2.xml

ENV LogLevel INFO

ENV JGROUPS_SHA1 a6fa159de0973e03c4db2eddcb5d7c5e8abe95cb

RUN curl -o jgroups.jar https://repo1.maven.org/maven2/org/jgroups/jgroups/$JGROUPS_VERSION/jgroups-$JGROUPS_VERSION.jar \ 
    && sha1sum jgroups.jar | grep $JGROUPS_SHA1

RUN curl -o log4j-core.jar http://repo1.maven.org/maven2/org/apache/logging/log4j/log4j-core/$LOG4J2_VERSION/log4j-core-$LOG4J2_VERSION.jar
RUN curl -o log4j-api.jar http://repo1.maven.org/maven2/org/apache/logging/log4j/log4j-api/$LOG4J2_VERSION/log4j-api-$LOG4J2_VERSION.jar

COPY log4j2.xml /opt/jboss

EXPOSE 12001

CMD java -classpath jgroups.jar:log4j-core.jar:log4j-api.jar -DLogLevel=$LogLevel -Dlog4j.configurationFile=${LOG4J2_FILE} org.jgroups.stack.GossipRouter
