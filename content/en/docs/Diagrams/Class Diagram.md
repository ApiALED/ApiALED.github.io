---
categories: ["Examples"]
tags: ["test", "sample", "docs"]
title: "Flow Diagram"
linkTitle: "Flow Diagram"
date: 2017-01-05
description: Flow.
---

## **Flow Diagram**
{{% pageinfo %}}
![Full Image](http://image.noelshack.com/fichiers/2022/08/1/1645438287-diagramme-classe.png)
{{% /pageinfo %}}

### - - -

{{% pageinfo %}}
![Full Image](http://image.noelshack.com/fichiers/2022/08/1/1645438921-first.png)
{{% /pageinfo %}}

First we pass by the __**Core**__. the goal of this class is to make the link between everything else (chapeauter in French). The class will store all the information needed for the **ZIA**. 

The first thing we do is call the Config Loader, it will look for the config.json file (it can be anywhere) if the file is not found it will load a default configuration. The config file should look like this : 

{{% pageinfo %}}
![Full Image](http://image.noelshack.com/fichiers/2022/08/1/1645439643-config.png)
{{% /pageinfo %}}

It MUST have a **“Modules”** flag which MUST have a **“Path”** and **“List”** flag, the list represents the order the module needs to be loaded and used, and the path is where they are stored. 

It MUST have a **“Hosts”** flag which will indicate the address will listen on, this flag could change in the future. 

It MUST have a **“SSL”** flag which has a **“Certificate”** and **“Key”** path, they will represent the path to find what is needed for the SSL. 
 
Then we call the Logger to inform the server of the configuration it need. 

{{% pageinfo %}}
![Full Image](http://image.noelshack.com/fichiers/2022/08/1/1645440181-second.png)
{{% /pageinfo %}}

Now that we have the path and name of the modules we can start to load them using the **“Module Loader”**. 

Once loaded we can start the **“network”** part, create the listener and socket thanks to the config. 

Once it is done, we start getting HTTP requests by client, we need to store everything inside a request list ! Then the multi-threading starts every worker will start to take a job, don’t forget to mutex the request they take ! 

Every worker will go through the list of modules given in the config file, to create a response and send it to the client. 
 
To be clear, an HTTP request is a processing list. Every module will get as parameters the object, request, response, and PL. 

* The request is a representation of the received request; it will get full after the parsing of the client request. 
* The response is the object created in function of the received request 
* PL is the processing list attached to the request. 


If you have any **fatal error** you should throw a “**fatalException”**, set an error message and catch it in the main function. Then you can use the **“Logger”** to print the error message and also the function where the error occured. 