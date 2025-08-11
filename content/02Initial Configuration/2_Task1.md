---
title: "Health Checks"
linkTitle: "Health Checks"
weight: 1
---
### **Health Checks**

In server load balancing deployments, the system uses health checks to poll the members of the real server pool to determine if an application is available. You can also configure additional health checks to poll related servers, and include results for both in the health check rule. For example, you can configure an HTTP health check test and a database server health check test. In a web application that requires access to a database to function, the web server is deemed available only if both the web server and the related database server pass the health check.

**Configure a Health Check**
- Login to the FortiADC with username ```admin``` and password ```fortinet```
- Go to **Shared Resources -> Health Check**
- Click on **+Create New**

![](fad-shared-resources.png)

- Name: **Web_Application**
- Type: **HTTP**
- Port: **0**
- **Save**

Notice that when you change the Type to HTTP, additional options related to HTTP become available, such as method, version, response code, and authentication requirements. For this exercise, we will accept the default values for all other entries except those defined above.

![](web-app-healthck.png)