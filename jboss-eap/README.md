# JBoss EAP 7 Image
Bare distribution for JBoss EAP 7

Current version is 7.0.7.GA

# Split distribution

split -b 50m jboss-eap-7.1.1.GA.zip 

# Build & Run
It has been build with these command:
	docker build -t mdahm/jboss-eap .
	docker tag mdahm/jboss-eap mdahm/jboss-eap:7.0.7.GA
	docker tag mdahm/jboss-eap mdahm/jboss-eap:latest

# Run & watch (Mapped to host ports 8888 and 9999, respectively)
	docker run -p 8888:8080 -p 9999:9990 --rm --name jboss-eap jmdahm/boss-eap
	docker exec -it jboss-eap /bin/bash
	
# Commit and run from DockerHub repository
	docker commit -m symlink -a "M. Dahm" 68c3ad257135 mdahm/jboss-eap
	docker tag jboss-eap:latest mdahm/jboss-eap
	docker tag jboss-eap:7.0.7.GA mdahm/jboss-eap:7.0.7.GA
	docker push mdahm/jboss-eap 
	docker push mdahm/jboss-eap:7.0.7.GA
	
# Run with parameters to standalone.sh
