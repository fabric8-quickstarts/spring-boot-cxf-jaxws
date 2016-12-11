# Spring-Boot CXF JAXWS QuickStart

This example demonstrates how you can use Apache CXF with Spring Boot.

The quickstart uses Spring Boot to configure a little application that includes a CXF JAXWS endpoint.


### Building

The example can be built with

    mvn clean install


### Running the example locally

The example can be run locally using the following Maven goal:

    mvn spring-boot:run


### Running the example in OpenShift

It is assumed a running OpenShift platform is already running.

Assuming your current shell is connected to OpenShift so that you can type a command like

```
oc get pods
```

Then the following command will package your app and run it on OpenShift:

```
mvn fabric8:run
```

The output log will give the URL to access the endpoint, something like
```
[INFO] F8:[SVC] spring-boot-cxf-jaxws: http://192.168.64.7:32224
```

You need to append the context-path `service/hello` to access the service so the URL is something like

    http://192.168.64.7:32224/service/hello

To list all the running pods:

    oc get pods

Then find the name of the pod that runs this quickstart, and output the logs from the running pods with:

    oc logs <name of pod>

To access the endpoint, use the host and port from the output log when run mvn fabric8:run

    http://192.168.64.7:32224/service/hello?wsdl
    
... will now display the generated WSDL.

