---
title: "Adaptive Learning Configuration"
linkTitle: "Adaptive Learning Configuration"
chapter: false
weight: 60
---

### Adaptive Learning - Configuration 

The configuration steps will be as follows:

1. Create an Adaptive Learning Profile 
2. Create a WAF Profile and add the Adaptive Learning Profile created in step 1
3. Associate the WAF Profile with the Virtual Server created in the "Initial Configuration" section of the lab. 



### Step 1 - Create an Adaptive Learning Profile
* Login to the FortiADC (FAD-Primary) with the username ```xperts2025``` and password ```AppSec-Xp3rts2025!```
* Go to **Web Application FireWall** → **Adaptive Learning**
* Click on **+Create New** 

![Adaptive-Learning](Adaptive-Learning1.png)

* Name: ```JuiceShop```
* Status: **Enable** the toggle
* Sampling Rate: ```100```
* False Positive Threshold: ```100000```
* Learning Time: ```1```
* Click **Save**

![JuiceShop-Adaptive-Learning2](JuiceShop-Adaptive-Learning2.png)  
 
* After that, click on the **+Create New** button to create a **URL List** 

![JuiceShop-Adaptive-Learning3](JuiceShop-Adaptive-Learning3.png)

* On the URL List page, type **/*** under URL textbox
* Click **Save**
* Click **Save** again

![JuiceShop-Adaptive-Learning4](JuiceShop-Adaptive-Learning4.png)

![JuiceShop-Adaptive-Learning6](JuiceShop-Adaptive-Learning6.png)


**We will repeat the same steps for the second application**

* Name: ```DVWA```
* Status: **Enable** the toggle
* Sampling Rate: ```100```
* False Positive Threshold: ```100000```
* Learning Time: ```1```
* Click **Save**

![DVWA-Adaptive-Learning5](DVWA-Adaptive-Learning5.png)

* After that, click on the **+Create New** button to create a **URL List** 

* On the URL List page, type **/*** under URL textbox
* Click **Save**
* Click **Save** again

![JuiceShop-Adaptive-Learning4](JuiceShop-Adaptive-Learning4.png)

![DVWA-Adaptive-Learning5](DVWA-Adaptive-Learning7.png)

* After adding them, the Adaptive Learning page should look like this:

![Adaptive-Learning](Adaptive-Learning8.png)