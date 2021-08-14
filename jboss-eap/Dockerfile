FROM jboss/base-jdk:8
MAINTAINER "praveen" "<mathprav@gmail.com>"
USER root
#ADD build/jboss-eap-7.4.0.zip /tmp/
ADD https://download.jboss.org/jbossas/7.1/jboss-as-7.1.1.Final/jboss-as-7.1.1.Final.zip /tmp/
RUN unzip /tmp/jboss-as-7.1.1.Final.zip
ENV JBOSS_HOME /opt/jboss/jboss-as-7.1.1.Final
RUN $JBOSS_HOME/bin/add-user.sh admin Password1 --silent && \
	chown -R jboss:jboss $JBOSS_HOME && \
	chmod -R 755 $JBOSS_HOME
EXPOSE 8080 9990
USER jboss
CMD ["/opt/jboss/jboss-as-7.1.1.Final/bin/standalone.sh","-b","0.0.0.0","-bmanagement", "0.0.0.0"]




