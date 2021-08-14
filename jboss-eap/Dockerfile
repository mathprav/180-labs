FROM jboss/base-jdk:8
MAINTAINER "praveen" "<mathprav@gmail.com>"
USER jboss
#ADD build/jboss-eap-7.4.0.zip /tmp/
ADD https://github.com/mathprav/180-labs/raw/jboss/jboss-eap/build/jboss-eap-7.4.0.zip .
RUN unzip /tmp/jboss-eap-7.4.0.zip
#RUN mkdir /opt/jboss/jboss-eap-7.4/standalone/log
ENV JBOSS_HOME /opt/jboss/jboss-eap-7.4
#RUN chown -R jboss:jboss $JBOSS_HOME && \
#	chmod -R 755 $JBOSS_HOME && \
RUN	$JBOSS_HOME/bin/add-user.sh admin Password1 --silent

EXPOSE 8080 9990
#USER jboss
CMD ["/opt/jboss/jboss-eap-7.4/bin/standalone.sh","-b","0.0.0.0","-bmanagement", "0.0.0.0"]