---
title: "Initial Configuration"
chapter: false
linkTitle: "Initial Configuration"
weight: 20
---

### **Initial Configuration**
In this section, we will review the steps needed to configure web application load balancing. The goal of deploying load balancers is to increase the availability of application servers, scale them to meet demand, and in some cases, modify content before sending the request to the origin server.

![](network-topo.png)

For this lab, we have set up an environment featuring two identical application servers positioned behind a pair of FortiADCs configured in High Availability (HA) mode. Additionally, we have included a FortiGate and a client workstation to simulate a typical client environment and facilitate testing.

The initial configuration steps, including network interface setup, admin settings, and HA configuration etc. , have already been completed. 

**HTTP load balancing**

In this section, we will review the steps needed to configure web application load balancing. The goal of deploying load balancers is to increase the availability of application servers, scale them to meet demand, and, in some cases, modify content before sending the request to the origin server.
