# Prerequisites for participants

This tutorial includes an hands-on session where you'll have to program a very small assignment in Java. To include 
this in the continuous integration stack demonstrated in the tutorial, you will have to use the following tools on 
your computer.

In case of need, do not hesitate to contact us by email ([mosser@i3s.unice.fr](mosser@i3s.unice.fr)), or by filling 
up an issue on this website.

## Setting up your environment

This tutorial requires Git, Java (8+), Maven (3+) and Docker. See next section if you need more details for these tools. 
To prepare your computer for this session, please execute the following command on your computer, it will save time and 
bandwidth during the session. It basically: 

  1. retrieves the material from Github;
  2. downloads all the dependencies 
needed by Java;
  3. downloads all the docker images necessary for the continuous integration steps.

```
azrael:~ mosser$ git clone  https://github.com/mosser/agile-tutorial.git
azrael:~ mosser$ cd agile-tutorial
azrael:~/agile-tutorial mosser$ mvn clean package
azrael:~/agile-tutorial mosser$ cd ci
azrael:~/agile-tutorial/ci mosser$ docker network create re18-network
azrael:~/agile-tutorial/ci mosser$ docker-compose up -d
azrael:~/agile-tutorial/ci mosser$ docker-compose down
```

## Setting up your computer (if needed)

### Version control system

We will use the Git source code version control system.

* https://git-scm.com/book/en/v2/Getting-Started-Installing-Git

```
azrael:~ mosser$ git --version
git version 2.15.2 (Apple Git-101.1)
```

### Development Language

We will develop using the Java Language, using JDK 8+ features.

* https://www.java.com/en/download/help/download_options.xml

```
azrael:~ mosser$ java -version
java version "1.8.0_102"
Java(TM) SE Runtime Environment (build 1.8.0_102-b14)
Java HotSpot(TM) 64-Bit Server VM (build 25.102-b14, mixed mode)

azrael:~ mosser$ javac -version
javac 1.8.0_102
```

You can rely on any environment to edit Java code (_e.g._, IntelliJ, Eclipse, Sublime, Emacs, Vi).

### Build environment & Dependency management

We will use Maven to take care of Java dependencies (i.e., tests frameworks for unit testing and acceptance scenarios)

* https://maven.apache.org/install.html

```
azrael:~ mosser$ mvn -v
Apache Maven 3.5.3 (3383c37e1f9e9b3bc3df5050c29c8aff9f295297; 2018-02-24T20:49:05+01:00)
Maven home: /opt/local/share/java/maven3
Java version: 1.8.0_102, vendor: Oracle Corporation
Java home: /Library/Java/JavaVirtualMachines/jdk1.8.0_102.jdk/Contents/Home/jre
Default locale: en_US, platform encoding: UTF-8
OS name: "mac os x", version: "10.13.6", arch: "x86_64", family: "mac"
```


### Deployment engine

To avoid the installation of tons of different software stacks on your computer, we rely on the Docker engine to use a 
container-based deployment environment for the continuous integration stack.

* https://docs.docker.com/install/

```
azrael:~ mosser$ docker -v
Docker version 18.06.0-ce, build 0ffa825

azrael:~ mosser$ docker-compose -v
docker-compose version 1.22.0, build f46880f
```

