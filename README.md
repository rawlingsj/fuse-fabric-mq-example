fuse-fabric-mq-example
======================

Example of using JBoss Fuse ESB, JBoss Fuse MQ and Fabric to build highly scalable messaging solutions.

The example will show how to create multiple containers using Fabric to dynamically scale and discover services within the ESB.  Rather than using the default Fuse broker the example will show how to add new brokers with custom broker configuration.  The intention is that this example can be used as a quick way to start looking at how Fuse provides answers to the demands of resiliant high volume messaging requirements.

<h4>Getting started...</h4>

1. Clone this repo  
2. Build and install example into your local maven repo  
`$ mvn clean install`  
3. Copy the folder fuse-fabric-mq-example/fuse-example-broker-config to the root of your JBoss Fuse ESB install directory (this is added to the zookeeper registry when running the karaf install scripts)  
4. Launch JBoss Fuse ESB  
5. Create a Fabric and run Karaf installer  
`fabric:create --clean`  
`sleep 10000`  
`shell:source mvn:org.fusebyexample.mq/fuse-fabric-mq-example-features/0.0.1-SNAPSHOT/karaf/installer`  
6. Wait for containers to successfully provision  
7. Use hawtio to see what's going on!  

The fabric profile contains the ports that Hawtio runs on each container.  You can change this in the fuse-fabric-mq-example.karaf script.  Using the default ports in this script the following links will point you to each container..

Broker - http://localhost:8380/hawtio (ActiveMQ view)  
Producer - http://localhost:8381/hawtio (Camel view)  
Consumer 1 - http://localhost:8382/hawtio (Camel view)  
Consumer 2 - http://localhost:8383/hawtio (Camel view)  

<h4>What you should see</h4>

The producer is generating messages every second, two consumers are registered so the consumption of messsages is split between each container.

<h4>Want to see what else you can do?</h4>

Try some of the following...

1. Add to the producer and consumer camel routes and checkout how cool hawtio is!
2. Play around with the broker topologies using master / slave and a network of brokers [mq fabric](http://fuse.fusesource.org/mq/docs/mq-fabric.html)
3. See how dynamic and scalable Fuse is by running loads tests and adding child / remote containers to the fabric (this example broker uses the JMS port 61616 set using the fabric profile)

# Useful links

* [Jboss Fuse](https://access.redhat.com/site/documentation/JBoss_Fuse/)
* [hawtio](http://hawt.io/)
* [Fabric](http://fuse.fusesource.org/fabric/docs/index.html)
* [Competing Consumer EIP](http://www.enterpriseintegrationpatterns.com/CompetingConsumers.html)
