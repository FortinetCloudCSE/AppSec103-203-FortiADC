---
title: "Configuration steps"
linkTitle: "Virtual Server"
chapter: false
weight: 90
---

### Step 3 - Associate the WAF profile with the Virtual Server created in Step 1

Now, we will associate the WAF profiles with a Virtual Server. Refer to the diagram in the traffic flow section to understand how traffic is processed through FortiADC for better context.

* Access Primary FortiADC's GUI from the console using the link provided
* Login to the FortiADC with the username ```admin``` and password ```fortinet```
* Go to **ServerLoad Balance** → **Virtual Server**
* Double click **JuiceShop** or click on edit (pencil icon) on the right side of **JuiceShop** 

![](.png)

* Click on **Security** tab 
* Select **JuiceShop** from the WAF Profile dropdown menu
* Click **Save**

![](.png)

We will follow the same steps for configuring the **DVWA** application. 

* Go to **ServerLoad Balance** → **Virtual Server**
* Double click **DVWA** or click on edit (pencil icon) on the right side of **DVWA** 

![](.png)

* Click on **Security** tab 
* Select **DVWA** from the WAF Profile dropdown menu
* Click **Save**

![](.png)

