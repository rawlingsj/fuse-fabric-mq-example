fuse-fabric-mq-example
======================

Example of using JBoss Fuse ESB, JBoss Fuse MQ and Fabric to build highly scalable messaging solutions.

The example will show how to create multiple containers using Fabric to dynamically scale and discover services within the ESB.  Rather than using the default Fuse broker the example will show how to add new brokers with custom broker configuration.  The intention is that this example can be used as a quick way to start looking at how Fuse provides answers to the demands of resiliant high volume messaging requirements.

<h4>Getting started...</h4>

1. Clone this repo  
2. Build and install example into your local maven repo  
`$ mvn clean install`  
4. Launch JBoss Fuse ESB  
5. Run Karaf installer  
`shell:source mvn:org.fusebyexample.mq/fuse-fabric-mq-example-features/0.0.1-SNAPSHOT/karaf/installer`  
6. Wait for containers to successfully provision  
7. Use hawtio to see what's going on!  

Hawtio - http://localhost:8181/hawtio  

<h4>What you should see</h4>

The producer is generating messages every second, two consumers are registered so the consumption of messsages is split between each container.

<h4>Want to see what else you can do?</h4>

Try some of the following...

1. Add to the producer and consumer camel routes and checkout how cool hawtio is!

# Useful links

* [Jboss Fuse](https://access.redhat.com/site/documentation/JBoss_Fuse/)
* [hawtio](http://hawt.io/)
* [Fabric](http://fabric8.io)
* [Competing Consumer EIP](http://www.enterpriseintegrationpatterns.com/CompetingConsumers.html)
