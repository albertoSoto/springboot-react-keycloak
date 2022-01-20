#It just compiles parent version for M1
ARG KEYCLOAK_VERSION
FROM jboss/keycloak:${KEYCLOAK_VERSION:-16.1.0}
ENV KEYCLOAK_DEPLOYMENT_FOLDER=/opt/jboss/keycloak/standalone/deployments/
ENV JVM_XMS=1g
ENV JVM_XMX=2g
ENV KEYCLOAK_THEME_FOLDER=/opt/jboss/keycloak/themes/
# Profile behavior introduces importing data per environment & infinispan settings
# dev | test | staging | production
ENV PROFILE_BEHAVIOR=staging
#Migration strategy can be OVERWRITE_EXISTING | IGNORE_EXISTING | none
ENV MIGRATION_STRATEGY=OVERWRITE_EXISTING
ENV PROXY_ADDRESS_FORWARDING='true'
USER root
#Important note: procps-ng = sysctl. Apply changes from /etc/sysctl.conf: sysctl -p
RUN microdnf upgrade && microdnf install sudo procps-ng glibc-langpack-en gzip hostname findutils openssl tar which sed less nano unzip \
    && microdnf clean all \