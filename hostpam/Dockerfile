# Version: 0.0.1
# edt M06 2018-2019
# hostpam
#-------------------------------------------------
FROM fedora:27
LABEL author="@edt ASIX M06 2018-2019"
LABEL description="hos PAM 2018-2019"
RUN dnf -y install procps vim passwd openldap-clients nss-pam-ldapd
RUN mkdir /opt/docker
COPY * /opt/docker/
RUN chmod +x /opt/docker/*.sh
RUN  cp /opt/docker/ldap.conf /etc/openldap/ldap.conf
RUN  cp /opt/docker/nsswitch.conf /etc/nsswitch.conf
RUN  cp /opt/docker/nslcd.conf /etc/nslcd.conf
RUN  cp /etc/pam.d/system-auth /etc/pam.d/system-auth.bk
RUN  cp /opt/docker/system-auth /etc/pam.d/system-auth
WORKDIR /opt/docker
CMD ["/opt/docker/startup.sh"]
