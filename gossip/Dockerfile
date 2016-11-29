FROM jboss/base-jdk:8

ENV JGROUPS_VERSION 3.6.11.Final 

ENV JGROUPS_SHA1 a8d8bcc854763aca0711452525639c9f9fa5d487

RUN curl -o jgroups.jar https://repo1.maven.org/maven2/org/jgroups/jgroups/$JGROUPS_VERSION/jgroups-$JGROUPS_VERSION.jar \ 
    && sha1sum jgroups.jar | grep $JGROUPS_SHA1

EXPOSE 12001

CMD ["java","-classpath","jgroups.jar","org.jgroups.stack.GossipRouter"]

