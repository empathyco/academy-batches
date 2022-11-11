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





Now, we must create a docker-compose file. Don’t panic, it's easier to understand compared to Dockerfile.

The main objective of a docker-compose file is managing the initialization of the different docker containers that we are going to deploy. In our case we are going to have two different containers, one for the elasticsearch server and another for our REST Api.

```yaml
version: '2.1'
services:
  elasticsearch:
    image: "docker.elastic.co/elasticsearch/elasticsearch:7.17.2"
    hostname: "elasticsearch"
    container_name: elasticsearch-docker
    environment:
      - "discovery.type=single-node"
    ports:
      - "9200:9200"

  searchapi:
    container_name: searchApi
    build:
      context: .
      dockerfile: Dockerfile
    ports:
      - "8080:8080"
    depends_on:
      - elasticsearch
```

We have two different parts that we can name “jobs”, the first job builds the elasticsearch container. The hostname parameter is very important, because it’s the name we are going to use to connect to it from the search api container. To make this work correctly you have to add a new HttpHost in the place where you are creating the ElasticsearchClient.


Finally, we need swing to know that there is now another possible endpoint for elastic, that of our docker container. To do this, it is only needed to add a new HttpHost to the client like so.


And there you have it! A fresh, docker container that will carry your code wherever it need to go!

Of course, this all would be for naught if we didn’t know how to run it. Luckily we do! There are three important commands:

```bask
$ docker compose up –build -d
$ docker compose up -d
$ docker compose down
```

The first and second will get your project running. The main difference is that the first one rebuilds your project (meaning that, if you had anything indexed in elastic, it WILL be gone). The last one takes your project down.

