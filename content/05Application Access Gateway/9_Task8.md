---
title: "AAG Quick Start Lab Guide"
linkTitle: "AAG Lab Guide - Start Here"
weight: 7 
---

### AAG Quick Start Lab Guide
A Quick Start Lab Guide on how to set up the Application Access Gateway using a local user account.

**Workflow:**

1. Configure a local user
2. Configure a user group
3. Configure the AAG Application Group
4. Configure the AAG Application Portal
5. Configure the AAG Application Access Policy
6. Configure a Virtual Server for the AAG
7. Test

{{% expand title="**Configure a Local User**" %}}

**Configure A local User**

- Login to the FortiADC (FAD-Primary) with the username ```xperts2025``` and password ```AppSec-Xp3rts2025!```
- Go to **Application Access Manager → Local User**
- Click **+Create New**

<img src=aag-qlg-local-user.png>

- Name: **user1**
- Password: **user1**
- **Save**

<img src=aag-qlg-user-form.png>

{{% /expand %}}

{{% expand title="**Configure a User Group**" %}}

**Configure a User Group**
- Go to **Application Access Manager → User Group**
- Click **+Create New**
- Group Name: **AAG-Users** 
- **Save**
- Click **+Create New**

<img src=aag-qlg-user-form1.png>

- Type: **Local**
- Local User: **user1**
- **Save**

<img src=aag-qlg-user-form2.png>

{{% /expand %}}

{{% expand title="**Configure the AAG Application Group**" %}}

**Configure the AAG Application Group**
- Go to **Application Access Manager → Agentless Application Gateway → App Group**
- Click **+Create New**

<img src=aag-qlg-aag.png>

- Name: **AAG-App-Group**
- **Save**
- Click **+Create New**

<img src=aag-qlg-app-access-adv.png>

- Name: **DVWA-SSH**
- Type: **Web-SSH**
- Host: **10.1.3.4**
- Port: **22**
- Set the **Advanced Setting** flag to **ON**
- **Username:** ```xperts2025```
- **Password:** ```AppSec-Xp3rts2025!```
- **Save**
- **Save**

{{% /expand %}}

{{% expand title="**Configure the AAG Application Portal**" %}}

**Configure the AAG Application Portal**
- Go to **Application Access Manager → Agentless Application Gateway → App Portal**
- Click **+Create New**

<img src=aag-qlg-app-portal.png>

- Name: **AAG-App-Portal**
- **Save**
- Click **+Create New**

<img src=aag-qlg-aag-app-portal1.png>

- Title: **AAG-App-Portal**
- App Group: **AAG-App-Group**
- **Save**
- **Save**

{{% /expand %}}

{{% expand title="**Configure the AAG Application Access Policy**" %}}

**Configure the AAG Application Access Policy**
- Go to **Application Access Manager → Agentless Application Gateway → Access Policy**
- Click **+Create New**

<img src=aag-qlg-access-policy.png>

- Name: **AAG-Access-Policy**
- Set the **App Portal Access** flag to **ON**
- **Save**

<img src=aag-qlg-access-policy1.png>

- Click **+Create New**

<img src=aag-qlg-portal-users.png>

- Name: **AAG-Portal-Users**
- User Group: **AAG-Users**
- App Portal: **AAG-App-Portal**
- **Save**
- **Save**

{{% /expand %}}

{{% expand title="**Configure a Virtual Server for the AAG**" %}}

**Configure a Virtual Server for the AAG**
- Go to **Server Load Balance → Virtual Server**
- Click **+Create New** then **Advanced Mode**

<img src=fad-vs.png>

- Name: **AAG**
- Type: **Layer 7**

<img src=aag-qlg-vs1.png>

> [!Info]
> There is no need to save yet.  We will go to the **General** Tab and the **Monitoring** Tab then save the whole thing.

- Click on the **General** Tab

<img src=aag-qlg-vs-gen.png>

- Address: **10.1.2.100**
- Port: **9443**
- Interface: **Port1**
- Profile: **LB_PROFILE_APP_ACCESS**
- Access Policy: **AAG-Access-Policy**

No need to save yet.

> [!Info]
> The Profile needs to be an AAG Profile.

- Click on the **Monitoring** Tab

<img src=aag-qlg-vs-monitoring.png>

- Toggle the **Traffic Log** flag to **ON**
- **Save**

> [!Info]
> Traffic logging should be used mainly for debugging; traffic logging will consume extensive memory and CPU resources. Please disable traffic logging after debugging is complete.

Go to **FortiView → Logical Topology**

You should see your Application Access Gateway.

<img src=aag-qlg-fortiview.png>

{{% /expand %}}

{{% expand title="**Test**" %}}

**Test AAG Access**
- From the Client with username ```xperts2025``` and password ```AppSec-Xp3rts2025!```
- Open Firefox
- Go to **https://10.1.1.100:9443**

<img src=aag-qlg-app-portal-access.png>

- Username: **user1**
- Password: **user1**

<img src=aag-qlg-user1.png>

You should see your **Application App Group**

Click the **DVWA-SSH** App Group

<img src=aag-qlg-dvwa-ssh.png>

You should have access to the DVWA server via SSH.

{{% /expand %}}


