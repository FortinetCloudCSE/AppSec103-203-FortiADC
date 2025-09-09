---
title: "Testing WAF"
linkTitle: "Testing WAF"
chapter: false
weight: 90
---

### Testing WAF

For this section, we will simulate attacks using the **ZAP tool** installed on the Client machine.

* From the Client with the username ```xperts2025``` and password ```AppSec-Xp3rts2025!```
* Click on **Activities** in the top left corner and open the **ZAP** tool.

{{< figure src="zap-tool-1.png" >}}

* It will take few seconds for it to load on the Client machine. 

{{< figure src="zap-tool-2.png" >}}

* The **ZAP** tool will show a pop-up showing different options. Select the default one as shown below and click **Start**

{{< figure src="zap-tool-3.png" >}}

* Go to the Dashboard and click **Tools** then **Options**

{{< figure src="zap-dash.png" >}}

* Once the Options page opens select **Display** and **Enable app integration in containers**

{{< figure src="zap1.png" >}}

* Scroll down in the list and select **Selenium**
* Update the paths to the **geckodriver** and the **Firefox Binary**

{{< figure src="zap2.png" >}}

* **geckodriver:** ```/home/xperts2025/.ZAP/webdriver/linux/64/geckodriver```
* **Binary:** ```/snap/firefox/current/usr/lib/firefox/firefox```
* Click **Bundled**
* Click **OK**
* Click the **Automated Scan** option shown as below. 

{{< figure src="zap-tool-4.png" >}}

* Enter ```https://10.1.1.101/dvwa/``` under the **URL to attack:** textbox and keep everything else default, click **Attack**. 

{{< figure src="zap-tool-5.png" >}}

* The **ZAP** tool will show the progress of the attack under the **Active Scan** tab as shown below. It shows all the requests **ZAP** is making to the various URL's in DVWA, as shown below. Let it run until it's finished (a few minutes).

{{< figure src="zap-tool-7.png" >}}

* Login to the FortiADC (FAD-Primary) with the username ```xperts2025``` and password ```AppSec-Xp3rts2025!```
* Go to **Log & Report** → **Security Log**. It will show all the **Attacks** coming in from the **ZAP** tool hitting the **DVWA** application behind the **FortiADC**. 

{{< figure src="zap-tool-8.png" >}}
