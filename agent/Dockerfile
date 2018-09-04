FROM jboss/wildfly

COPY AppServerAgent-4.5.1.23676.zip /tmp

RUN mkdir /opt/jboss/javaagent \
    && unzip -q -d /opt/jboss/javaagent /tmp/AppServerAgent-4.5.1.23676.zip \
    && echo "JAVA_OPTS=\"\$JAVA_OPTS -javaagent:/opt/jboss/javaagent/ver4.5.1.23676/javaagent.jar\"" >> /opt/jboss/wildfly/bin/standalone.conf

CMD ["/opt/jboss/wildfly/bin/standalone.sh", "-b", "0.0.0.0", "-bmanagement", "0.0.0.0"]