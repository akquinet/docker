# Use latest openjdk 1.8
FROM openjdk:8

# Use which version?
ENV EAP_VERSION 	7.0.3.GA

ENV JBOSS_LATEST 	jboss-eap
ENV JBOSS_VERSION 	jboss-eap-${EAP_VERSION}
ENV JBOSS_ROOT 		/opt/jboss

ENV JBOSS_HOME 		${JBOSS_ROOT}/${JBOSS_LATEST}
ENV JBOSS_ZIP 		${JBOSS_VERSION}.zip
ENV JBOSS_EXEC		${JBOSS_HOME}/bin/standalone.sh

RUN mkdir -p ${JBOSS_ROOT}

# Github has a restriction of 100MB maximum file size
# Thus we had to split the original file
COPY xa? ${JBOSS_ROOT}/

RUN cd ${JBOSS_ROOT} && cat xa? > ${JBOSS_ZIP} && unzip ${JBOSS_ZIP} \
	&& ln -s ${JBOSS_VERSION} ${JBOSS_LATEST} \
	&& chmod 755 ${JBOSS_HOME}/bin/*.sh \
	&& rm -f ${JBOSS_ZIP} xa?

EXPOSE 8080
EXPOSE 9990

# Default startup
CMD ${JBOSS_EXEC} -b 0.0.0.0 -bmanagement 0.0.0.0
