# Use any Linux distribution
FROM ubuntu

# Use which version?
ENV MOD_CLUSTER_VERSION 	1.3.1.Final
ENV LINUX_ARCH				linux-x86_64
ENV BASE_URL				http://downloads.jboss.org/mod_cluster/
ENV DIST_TAR				mod_cluster-${MOD_CLUSTER_VERSION}-linux2-x64.tar.gz
ENV	TEMP_FILE				/tmp/mod_cluster.tar.gz

ENV HTTPD_ROOT 				/opt/jboss/httpd
ENV MOD_CLUSTER_HOME 		${HTTPD_ROOT}/${MOD_CLUSTER_VERSION}

RUN apt-get -y update && apt-get -y install curl
RUN curl ${BASE_URL}/${MOD_CLUSTER_VERSION}/${LINUX_ARCH}/${DIST_TAR} -o ${TEMP_FILE} \
	&& tar xfz ${TEMP_FILE} && rm -f ${TEMP_FILE}

EXPOSE 80

# Default startup
#CMD ${JBOSS_EXEC} -b 0.0.0.0  -bmanagement 0.0.0.0
