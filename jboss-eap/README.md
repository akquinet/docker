# JBoss EAP 7 Image
Bare distribution for JBoss EAP 7

Current version is 7.0.3.GA

# Build & Run
It has been build with this command:

	docker build -t jboss-eap .
	docker tag jboss-eap jboss-eap:7.0.3.GA

# Run & watch (Mapped to host ports 8888 and 9999, respectively)
	docker run -p 8888:8080 -p 9999:9990 --rm --name jboss-eap jboss-eap
	docker exec -it jboss-eap /bin/bash
	
# Commit and run from DockerHub repository
	docker commit -m symlink -a "M. Dahm" 5a3d71d59867 mdahm/jboss-eap
	docker tag af9eafefd2ad mdahm/jboss-eap:7.0.3.GA
	docker push mdahm/jboss-eap
	
	docker run mdahm/jboss-eap