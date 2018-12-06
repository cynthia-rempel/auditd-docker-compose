FROM registry.hub.docker.com/library/centos:centos7

ENV container docker

RUN rpm --import /etc/pki/rpm-gpg/RPM-GPG-KEY-CentOS-7 && \
    yum install audit epel-release -y && \
    rpm --import /etc/pki/rpm-gpg/RPM-GPG-KEY-EPEL-7 && \
    yum clean all

COPY auditd.conf audit.rules /

RUN mv /auditd.conf /etc/audit/ && \
    mv /audit.rules /etc/audit/rules.d/ && \
    /usr/sbin/augenrules
    
# ENTRYPOINT ["/sbin/auditd","-n"]
CMD ["/sbin/auditd","-n"]

