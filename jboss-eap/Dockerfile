FROM jboss/base-jdk:8
MAINTAINER "praveen" "<mathprav@gmail.com>"
USER root
#ADD build/jboss-eap-7.4.0.zip /tmp/
ADD https://github.com/mathprav/180-labs/raw/jboss/jboss-eap/build/jboss-eap-7.4.0.zip .
RUN unzip ./jboss-eap-7.4.0.zip
ENV JBOSS_HOME /opt/jboss/jboss-eap-7.4
RUN chown -R jboss:jboss /opt/jboss && \
chmod -R 755 /opt/jboss && \
$JBOSS_HOME/bin/add-user.sh admin Password1 --silent
EXPOSE 8080 9990
USER jboss
CMD ["/opt/jboss/jboss-eap-7.4/bin/standalone.sh","-b","0.0.0.0","-bmanagement", "0.0.0.0"]