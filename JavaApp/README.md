How to Create java app, build and deploy on docker container.

1. Create a helloworld application using mvn archetype.
	mvn archetype:generate -DgroupId=com.venky -DartifactId=HelloWorldWebApp -DarchetypeArtifactId=maven-archetype-webapp -DinteractiveMode=false
2. Create a Dockerfile which is used to create docker image for your service. Use Tomcat as the base Image.
3. Copy the war file to webapps folder inside docker container, start the tomcat service.
4. build the image - docker build . -t test/javatomcat
5. run the container - docker run -p 8080:8080 -ti test/javatomcat /bin/bash
6. Above command should start the docker container and map 8080 port of container to host.
7. open browser and http://localhost:8080/ should open the tomcat startup page.
8. 

Another Method
1. Do till step 3 in above.
2. create a docker-compose.yml file. 
3. run - docker-compose up. this should bring up the server with all port mapping.