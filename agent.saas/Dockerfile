FROM jboss/wildfly

COPY AppServerAgent-4.4.3.23530.zip /tmp

RUN mkdir /opt/jboss/javaagent \
    && unzip -q -d /opt/jboss/javaagent /tmp/AppServerAgent-4.4.3.23530.zip \
    && echo "JAVA_OPTS=\"\$JAVA_OPTS -javaagent:/opt/jboss/javaagent/ver4.4.3.23530/javaagent.jar -Dappdynamics.agent.applicationName=TestApp -Dappdynamics.agent.tierName=testTier -Dappdynamics.agent.nodeName=docker_jboss_wildfly\"" >> /opt/jboss/wildfly/bin/standalone.conf

CMD ["/opt/jboss/wildfly/bin/standalone.sh", "-b", "0.0.0.0", "-bmanagement", "0.0.0.0"]