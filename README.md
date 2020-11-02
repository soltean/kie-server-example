# README #

### What is this repository for? ###

This represents the Kie Server. It's basically the rules engine, though it can have more capabilities than rules.
Once we start this we can run the rules we create in the drools-workbench. We can start it embedded also in our application
but we lose the ability to develop rules faster. Once we create a rule in workbench we can deploy it on the KIE server and our
application will interact with it.

For a quick startup this is a pre-setup image with roles and users. This should be temporary and we need to revisit it.

### How do I get set up? ###

Just build the docker image. Again the Dockerfile is simple but we intend to put more there.
This is in case you are wondering why not using directly the official image.
```
docker build -t my-kie .
```

Start by running 
```
docker run -p 8180:8080 -d --name kie-server --link drools-wb:kie-wb my-kie:latest

```
drools-wb is the drools workbench container name. By linking them workbench can see all kie instances.

Go to 
```
http://localhost:8180/kie-server
```
and login using one of the users available. 


### Who do I talk to? ###

For more information contact Sergiu Oltean or go to https://registry.hub.docker.com/r/jboss/kie-server-showcase.