---
title: "WAF Profile"
linkTitle: "WAF Profile"
chapter: false
weight: 70
---

### Step 2 - Create WAF profile 

Now, we will create a WAF Profile and associate the Adaptive Learning profiles (JuiceShop & DVWA) we created earlier with the WAF Profile. 

* Login to the FortiADC (FAD-Primary) with the username ```xperts2025``` and password ```AppSec-Xp3rts2025!```
* Go to **Web Application FireWall** → **WAF Profile**
* Click on **+Create New** 

![WAF-Profile9](WAF-Profile9.png)

* Name: `JuiceShop`
* Adaptive Learning: Select **JuiceShop** from the dropdown
* Click **Save**

![WAF-Profile10](WAF-Profile10.png)


* For this exercise, we will focus solely on configuring the Adaptive Learning module and will not configure the other WAF modules. In a production environment, however, all relevant WAF modules would be configured as needed to ensure comprehensive protection.

* After that, we will create a second WAF Profile for the DVWA application

* Go to **Web Application FireWall** → **WAF Profile**
* Click on **+Create New** 

![WAF-Profile11](WAF-Profile11.png)

* Name: `DVWA`
* Adaptive Learning: Select **DVWA** from the dropdown
* Click **Save**

![WAF-Profile12](WAF-Profile12.png)

* After adding them, the WAF Profile page should look like this:

![WAF-Profile13](WAF-Profile13.png)

