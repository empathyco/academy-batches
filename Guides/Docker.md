The _**Quick** and **Splendid**_ guide to **_Docker_**
Today, @mariol and I spent a couple hours fighting with docker. As we wish this fate to noone, we have teamed up to make this quick guide that will get your project going. Note that this is a very basic skeleton, so feel free to tinker with it! (please, please, please do not use this in serious production)

The first thing we are going to need is a Dockerfile. This is basically a bunch of boilerplate that will package our application into a docker container. To have it up and running, it is as simple as creating in the project root a file “Dockerfile” and then pasting the following inside:

```docker
#
# Build stage
#
FROM maven AS build
COPY src /home/app/src
COPY pom.xml /home/app/
RUN mvn -f /home/app clean package

#
# Package stage
#
FROM openjdk
COPY --from=build /home/app/target/demo_search-0.0.1-SNAPSHOT.jar /usr/local/lib/demo.jar
EXPOSE 8080
ENTRYPOINT ["java","-jar","/usr/local/lib/demo.jar"]
```

Easy as that!

What? You want a little explanation? Okay then. This happens in two stages. First is the build stage. We move our project to an easily findable location in the docker container (This is done by the two COPY commands). Then, we just have to ask maven to package up our project in the new location (This is the RUN, the -f flag lets us specify a project).

Then, we have our package built up. But docker needs to know what does it need to do to run our application. This is where the second phase comes. Here we tell docker where our package is. We follow the same approach as before, we copy the .jar executable to an easily findable location (the –from=build is so that docker knows wher to find the .jar, don’t worry about it for now). Then we need to say which port(s) our app will use, in our case, the 8080 port. Finally, we specify which command to run to stage up our app. In this case, we run the .jar with java.

At this point, we have our app ready for deployment, but we don't have the elasticsearch server with all the information indexed.
Indexing every time we create the container would be a waste of time, so we must create a docker image with all the documents
indexed previously. In order to achive this, we must follow this steps:
1. Create an elasticsearch container using the image provided by Elastic, as usually:
```
docker run -d --name elasticsearch -p 9200:9200 -p 9300:9300 -e "discovery.type=single-node" \ docker.elastic.co/elasticsearch elasticsearch:7.17.2
```
2. Now, using Insomnia or anyother API Client, index all the files as we were doing previously.
3. Once all the information is indexed, we should create an image of the current state of the container. It may tike a while.
```
docker commit <container_name>
```
  - The container name should be elasticsearch, you can check it running the following command and look for the names parameter:
```
docker ps
```
4. We can check the image was created and also the IMAGE ID that will be useful for the next steps.
```
docker images -a
```
5. Now, we have the image in our local machine, so we need to upload it to some online repository. I recommend you to use [Docker Hub](https://hub.docker.com/). You should create there an account and a public repository. For more information you can follow this link: [Manage Repositories](https://docs.docker.com/docker-hub/repos/#:~:text=To%20push%20an%20image%20to,docs%2Fbase%3Atesting%20)
6. Once, the repository is created. We should push the image to it, but first we have to give it a name.
```
docker tag <IMAGE_ID> <Hub Username>/<Hub Repo>:<tag> #By default, the tag is latest
```
7. Finally, push the image to the online repo.
```
docker push <Hub Username>/<Hub Repo>:<tag>
```

Now, we must create a docker-compose file. Don’t panic, it's easier to understand compared to Dockerfile.

The main objective of a docker-compose file is managing the initialization of the different docker containers that we are going to deploy. In our case we are going to have two, one for the elasticsearch server and another for our REST Api.

We have two different parts that we can name “jobs”, the first job builds the elasticsearch container and the other the search api. We are giving you some important tips to be a docker-compose lover :) The hostname parameter is very important, because it’s the name we are going to use to connect to it from the search api container. The depends_on parameter manages how the containers will start. In this case, as the search api depends on the elasticsearch health status, it will not start until the elasticsearch container is up and the health status of elastic is correct.

This file must be named docker-compose.yml with the following content:

```yaml
version: '2.1'
services:
  elasticsearch:
    image: "<Hub Username>/<Hub Repo>:<tag>"
    hostname: "elasticsearch"
    container_name: elasticsearch-docker
    environment:
      - "discovery.type=single-node"
    ports:
      - "9200:9200"
    healthcheck:
      test: [ "CMD", "curl", "-u", "elastic:searchPathRules", "-f", "localhost:9200" ]
      interval: 30s
      retries: 10

  searchapi:
    container_name: searchApi
    build:
      context: .
      dockerfile: Dockerfile
    ports:
      - "8080:8080"
    depends_on:
      elasticsearch:
        condition: service_healthy
```
You must change the link to the elasticsearch image previously upload to Docker Hub.

Finally, we need swing to know that there is now another possible endpoint for elastic, that of our docker container. To do this, it is only needed to add a new HttpHost to the client like so.

```java
RestClient restClient = RestClient.builder(new HttpHost("localhost", 9200),
        new HttpHost("elasticsearch", 9200)).build();
```

And there you have it! Two fresh docker containers that will carry our project wherever it need to go!

Of course, this all would be for naught if we didn’t know how to run it. Luckily we do! There are three important commands:

```bask
$ docker compose up –build -d
$ docker compose up -d
$ docker compose down
```

The first and second will get your project running. The main difference is that the first one rebuilds your project and the last one takes your project down. The first time do always the docker-compose up --build -d to ensure everything is build correctly. Note that you must close any other containers you may have running on ports 9200 and 8080, otherwise this won't work.

