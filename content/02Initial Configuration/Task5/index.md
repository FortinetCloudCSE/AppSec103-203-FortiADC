---
title: "Test Your Configuration"
linkTitle: "Test Your Configuration"
chapter: false
weight: 16
---
### **Test Your Configuration**

**To test for the first time:**

- From the Client:
  - username: ```xperts2025``` password: ```AppSec-Xp3rts2025!```
- Open Firefox and go to the JuiceShop application: **https://10.1.1.100**
  - Loading the splash page is good enough.  No need to log in or create an account.  We just want to know we can reach the application.  
- Open Firefox and go to the DVWA application: **https://10.1.1.101/dvwa**
  - Log in to DVWA with admin / ```password```. The username and password are saved in the browser.  We do want to make sure we can log in to DVWA as we will use this for other tests.

### **Lab Network Diagram**

{{< figure src="fad-logical-w-ips.png" >}}

> [!Info]
> There is a FortiGate in front of the FortiADC's.  The IP's we are testing are VIP's on the FortiGate and will not match the IP's we configured on the FortiADC.

**JuiceShop**

{{< figure src="juiceshop-test.png" >}}

**Damn Vulnerable Web Application \(DVWA\)**

{{< figure src="dvwa-test.png" >}}

This will complete the Initial Configuration Section