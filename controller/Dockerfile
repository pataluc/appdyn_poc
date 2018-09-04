FROM centos:7

COPY platform-setup-x64-linux-4.5.0.12904.sh /tmp
COPY response.varfile /tmp

RUN yum install -y which libaio numactl \
    && echo "serverHostName=`hostname`" >> /tmp/response.varfile \
    && /tmp/platform-setup-x64-linux-4.5.0.12904.sh -q -varfile /tmp/response.varfile \
    && /opt/appdynamics/enterpriseconsole/platform-admin/bin/platform-admin.sh create-platform --name test_jboss --installation-dir /opt/appdynamics/controller \
    && /opt/appdynamics/enterpriseconsole/platform-admin/bin/platform-admin.sh add-hosts --hosts localhost \
    && /opt/appdynamics/enterpriseconsole/platform-admin/bin/platform-admin.sh submit-job --service controller --job install --args controllerPrimaryHost=localhost controllerAdminUsername=admin controllerAdminPassword=password controllerRootUserPassword=password mysqlRootPassword=password