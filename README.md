fuse-fabric-mq-example
======================

Example of using JBoss Fuse ESB, JBoss Fuse MQ and Fabric to build a highly scalable messaging solution.

Getting started...

1. Clone this repo
2. Build and install example into your local maven repo
  
  $ mvn clean install

3. Copy the folder fuse-fabric-mq-example/fuse-example-broker-config to the root of your JBoss Fuse ESB install directory (this is added to the zookeeper registry when running the example install scripts)
4. Launch Fuse
5. Create a Fabric and run Karaf installer

  fabric:create --clean
  sleep 10000
  shell:source mvn:com.truphone.esb/features/1.0.0-SNAPSHOT/karaf/installer

6. Wait for containers to successfully provision
7. Use hawtio to see what's going on!

The fabric profile contains the ports that Hawtio runs on each container.  You can change this in the fuse-fabric-mq-example.karaf script.  Using the default ports in this script the following links will point you to each container..

Broker - http://localhost:8380/hawtio
Producer - http://localhost:8381/hawtio
Consumer 1 - http://localhost:8382/hawtio
Consumer 2 - http://localhost:8383/hawtio

Want to see what else you can do?  Try some of the followng...

1. Add to the producer and consumer camel routes and checkout how cool hawtio is!
2. Play around with the broker topologies using master / slave and a network of brokers (http://fuse.fusesource.org/mq/docs/mq-fabric.html)
3. See how dynamic and scalable Fuse is by running loads tests and adding child / remote containers to the fabric (this example broker uses the JMS port 61616 set using the fabric profile)

Useful links

hawtio - http://hawt.io/
Jboss Fuse - https://access.redhat.com/site/documentation/JBoss_Fuse/
Fabric - http://fuse.fusesource.org/fabric/docs/index.html
Competing Consumer EIP - http://www.enterpriseintegrationpatterns.com/CompetingConsumers.html
