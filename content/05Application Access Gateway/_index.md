---
title: "Application Access Gateway"
chapter: false
linkTitle: "Application Access Gateway"
weight: 50
---

### Application Access Gateway (AAG)

The Agentless Application Gateway (AAG) in FortiADC provides secure, seamless remote access to enterprise applications and critical resources without requiring agent installation on endpoints or backend servers. Acting as a reverse proxy, AAG publishes a web-based authentication portal that enables clientless access to Remote Desktop Protocol (RDP), Virtual Network Computing (VNC), Secure Shell (SSH), Telnet, and web applications.

Authentication to the AAG App Portal is enforced via Access Policies. These policies define the accepted authentication methods—including Local User, LDAP, RADIUS, or SAML—and determine session behavior such as idle timeout and reauthentication. Application visibility is controlled by App Portals and App Groups.

![](aag.png)

**Key Features and Benefits**
- AAG in FortiADC delivers secure and scalable remote access with the following capabilities:
- Agentless Access – Eliminates the need for client-side agents, reducing endpoint dependency and administrative burden.
- Federated Authentication Support – Supports SAML 2.0-based authentication using providers like Microsoft Entra ID and FortiAuthenticator.
- Simplified Deployment – Requires no software installation, enabling rapid implementation in secure environments.
- Real-Time Monitoring – Tracks user sessions and access logs for compliance and auditing.
- Application-Layer Security Controls – Enforces IP reputation filtering and geolocation restrictions through the Application Profile attached to the AAG Virtual Server.

### Technical Overview
**Traditional vs. Agentless Application Access**

Traditional remote access solutions often require software agents installed on client devices or backend systems to enforce authentication and security policies. This introduces compatibility constraints, maintenance overhead, and security risks associated with unmanaged endpoints.

FortiADC’s Agentless Application Gateway (AAG) eliminates these dependencies by acting as a reverse proxy, terminating client sessions at the gateway and forwarding traffic to backend resources based on authentication and policy enforcement mechanisms.

### Authentication Flow and Identity Integration

**AAG supports the following authentication workflow:**

1. The user accesses the AAG App Portal via browser.
2. FortiADC evaluates the Access Policy and enforces the configured authentication method by:
3. Validating credentials against Local User, LDAP, or RADIUS servers. 
4. Redirecting to a SAML 2.0 Identity Provider (e.g., FortiAuthenticator, Microsoft Entra ID) for federated login. 
5. Upon successful authentication, FortiADC grants access to the App Portal associated with the user's session.

The user can view and launch their assigned application bookmarks for services such as RDP, SSH, VNC, Telnet, and web apps.

![](aag1.png)

**Supported Application Types in FortiADC AAG:**
- Web RDP – Provides full desktop access via Remote Desktop Protocol (RDP) through an HTML5 browser session. No RDP client is required on the endpoint.
- Native RDP – Enables traditional RDP access using the native RDP client installed on the user's device. Requires endpoint support for Microsoft RDP.
- RemoteApp – Launches individual Windows applications published via Remote Desktop Services, rather than a full desktop session.
- Web VNC – Offers browser-based access to VNC-enabled systems for remote control of graphical desktops.
- Web SSH – Delivers secure command-line access to Linux and Unix systems through a browser-based SSH terminal.
- Web Telnet – Enables text-based terminal sessions to legacy devices or servers using the Telnet protocol, directly within the browser.




