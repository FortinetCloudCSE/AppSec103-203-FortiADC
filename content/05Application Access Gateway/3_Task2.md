---
title: "Configuring an App Group"
linkTitle: "Configuring an App Group"
weight: 2
---
### **Configuring an App Group**

An App Group is a logical container that organizes application bookmarks—each representing a backend resource such as an RDP host, SSH server, or internal web application. App Groups are assigned to App Portals, which define the user-facing interface through which authenticated users access their authorized applications.

Each App Group can contain bookmarks of various types (Web, RDP, SSH, VNC, etc.), and users accessing a given App Portal will only see the applications associated with its linked App Groups.

![](aag3.png)

To create an App Group:

1. Navigate to Application Access Manager > Agentless Application Gateway.
The configuration page displays the App Portal tab.
2. Click the App Group tab.
3. Click Create New to display the configuration editor.
4. In the Name field, specify a unique name for the App Group configuration object. Valid characters are A-Z, a-z, 0-9, _, and -. No space is allowed.
5. Click Save.

Once the App Group is created, the App Bookmark section becomes configurable.
Each VDOM supports up to 1024 App Groups, but a single App Portal can be associated with a maximum of 32 App Groups.

### App Bookmark Configuration Overview

The App Bookmark configuration workflow is entirely dependent on the specific protocol. Each App Bookmark within an App Group is configured with application-specific parameters to ensure optimal access control and user experience. Once configured, an App Group can be added to an App Portal, making the applications available to authenticated users. The steps below outline the basic workflow to configure an App Bookmark.

1. Go to **Application Access Manager > Agentless Application Gateway**
The configuration page displays the App Portal tab.
Click the App Group tab.
2. Create a new App Group or edit an existing configuration.
3. Under the App Bookmark section, click **Create New** to display the configuration editor.
4. In the Name field, specify a unique name for the App Bookmark configuration object. Valid characters are A-Z, a-z, 0-9, _, and -. No space is allowed.
5. From the Type field, select an application from the drop-down menu. This selection determines the parameters to configure.
6. To view the configuration parameters for each application, see App Bookmark Types where you can navigate to the desired application type.
7. Click **Save** to save the configuration.
Repeat the steps to add up to 256 Bookmarks per App Group.

**App Bookmark Types**

Each App Bookmark Type requires specific parameters to be configured. The following table lists the supported Types and their usage. Use the links under the Application Type column to navigate to the configuration parameters applicable to each App Bookmark Type.

| Application Type | Usage                                                                  |
|------------------|------------------------------------------------------------------------|
|Web RDP|Provides web-based remote desktop access via an HTML5 client, eliminating the need for an RDP client on the user’s device.|
|Native RDP|Establishes a direct connection to an RDP server, requiring an installed RDP client on the user’s device.|
|Remote App|Enables access to specific Windows applications over RDP without exposing the full desktop session.|
|Web VNC|Grants browser-based access to remote desktops running Virtual Network Computing (VNC).|
|Web SSH|Allows command-line access to remote Linux or Unix servers via a secure, browser-based SSH session.|
|Web Telnet|Provides browser-based access to Telnet-enabled devices for legacy terminal access.|

**Web RDP**

Web RDP (Remote Desktop Protocol) provides web-based access to a remote Windows desktop session without requiring an RDP client. It allows users to connect to Windows systems securely through their browser, making it ideal for remote administration, virtual desktop access, and troubleshooting.

![](aag4.png)

|Parameter| Description                                                                                                              |
| --- |--------------------------------------------------------------------------------------------------------------------------|
| Host | The IP address or hostname of the target Windows machine.                                                                |
| Port | The port used for the RDP connection (default: 3389, range: 1-65535).                                                    |
| Description | Optional description for the Web RDP bookmark.                                                                           |
| Advanced Setting |
| Single Sign-On | Determines whether Single Sign-On is used.                                                                               |
| Username | The username for authentication when Single Sign-On is disabled.                                                         |
| Password | The password for authentication when Single Sign-On is disabled.                                                         |
|SSO Credential| Appears when Single Sign-On is set to App Portal Login. The SSO Credential is set to use the App Portal Login by default.|
|Color Depth|Sets the color depth for the remote session.|
|Screen Width|Specifies the width of the remote session display (default: 1024, range: 200-8192).|
|Screen Height|Specifies the height of the remote session display (default: 768, range: 200-8192).|
|Security|Defines the security protocol for the RDP session.|
|Clipboard|Enables or disables clipboard sharing between the remote session and the local machine.|

**RemoteApp**

RemoteApp provides access to specific applications hosted on a remote Windows server without opening a full remote desktop session. Unlike Web RDP, which grants access to the entire remote desktop environment, RemoteApp launches only the selected application in a separate window, making it appear as if it is running locally on the user's device. This approach enhances security by restricting access to only approved applications and improves the user experience by integrating remote applications seamlessly into the local desktop environment.

**When publishing RemoteApp bookmarks:**
- Privacy and security settings, such as camera redirection, must be properly configured on the RDP session host.
- Redirect-printer support requires that the appropriate printer driver is installed on the RDP server before use.

![](aag5.png)

