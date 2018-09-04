FROM centos:7

COPY platform-setup-x64-linux-4.5.0.12904.sh /tmp
COPY response.varfile /tmp

RUN yum install -y which libaio numactl \
    && /tmp/platform-setup-x64-linux-4.5.0.12904.sh -q -varfile /tmp/response.varfile \
    && ls -l /opt/appdynamics/enterpriseconsole/installer 
#    && /opt/appdynamics/platform-admin/bin/platform-admin.sh create-platform --name test_jboss --installation-dir /opt/appdynamics/test_jboss