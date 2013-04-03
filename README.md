CQ Blueprint Sample
================

Sample application demonstrating use of [OSGi Blueprint](http://www.ibm.com/developerworks/opensource/library/os-osgiblueprint/) mechanism for consuming and
registering service with CQ. It consist of following modules

1. service - A hello world service using Blueprint
2. package-aries - Creates a CQ Content Package containing [Apache Aries] (http://aries.apache.org/modules/blueprint.html) related jars and the sample app
3. package-gemini - Creates a CQ Content Package containing [Eclipse Gemini] (http://www.eclipse.org/gemini/blueprint/) related jars and the sample app

To see the application in action you need to build it

```
$ git clone https://github.com/chetanmeh/cq-blueprint-sample.git
$ cd cq-blueprint-sample
$ mvn clean install
$ cd package-gemini
$ mvn clean install content-package:install -Dcrx.host=<CQ Server> -Dcrx.port=4502
$ curl -u admin:admin http://localhost:4502/content/cqgemini.html
    Service invocation result [Hello via Blueprint Service]
```

If the command line way of installing the package does not work then deploy the created package from target folder using the CQ Package Manager and then access the url http://localhost:4502/content/cqgemini.html. If all goes well it should say Hello!!



