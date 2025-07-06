---
title: "Virtual Servers"
linkTitle: "Virtual Servers"
chapter: false
weight: 4
---
### **Define Virtual Server**

The next step is to configure a virtual server, which defines the type of traffic FortiADC will manage and how it will be processed. For this exercise, we will create two virtual servers, one for each of our web applications, while using the default settings wherever possible.

- Go to **Server Load Balance/Virtual Server**
- Click on **+Create New** then **Advanced Mode**

![](fad-vs.png)

### **NAT Source Pools**

Add how to for NAT Source Pools

![](image-placeholder) "screenshot here"

- On the Basic TAB 
- **Name:** juiceshop
- **Type:** Layer7
- **Nat Source pool List:** Juiceshop
- Click **Save**

![](image-placeholder) "screenshot here"

- Go to the **General** TAB 
- **Address:** 10.1.2.100
- **Port:** 443
- **Interface:** Port2 ( from the dropdown Menu) 
- **Profile:** LB_PROF_HTTPS
- **Client SSL Profile:** LB_CLIENT_SSL_PROF_DEFAULT
- **Persistence:** LB_Persis_SSL_SESS_ID
- **Method:** LB_METHOD_ROUNDROBIN
- **Real Server Pool:** WEB-APPLICATION
- Click **Save**

![](image-placeholder) "screenshot here"

- Go to the **MONITORING** TAB
- **TRAFFIC LOG:** Enable the Toggle
- **FortiView:** Enable the Toggle
- Click **Save**

![](fad-vs.png)

- Go to **Server Load Balance/Virtual Server**
- Click on **+Create New** then **Advanced Mode**

![](image-placeholder) "screenshot here"

- **Name:** DVWA
- **Type:** Layer7
- **Nat Source pool List:** DVWA-NAT
Click **Save**

![](image-placeholder) "screenshot here"