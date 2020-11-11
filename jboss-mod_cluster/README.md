# JBoss mod_cluster Image
Run preconfigured Apache HTTPD with mod\_cluster in order to be used as a load balancer for a cluster of EAP servers.

Current version is 1.3.1.Final

# Build & Run
The image has been build with this command:

	docker build -t jboss-mod_cluster .
	docker tag jboss-mod_cluster jboss-mod_cluster:1.3.1.Final

# Run & watch
	docker run --rm --name jboss-mod_cluster jboss-mod_cluster
	docker exec -it jboss-mod_cluster /bin/bash
