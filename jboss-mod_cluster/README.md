# JBoss mod_cluster Image
Run preconfigured Apache HTTPD with mod_cluster in order to be used as a load balancer for a cluster of EAP servers.

Current version is 1.3.1.Final

# Build & Run
It has been build with this command:

	docker build -t jboss-mod-cluster .
	docker tag jboss-mod-cluster jboss-mod-cluster:1.3.1.Final
