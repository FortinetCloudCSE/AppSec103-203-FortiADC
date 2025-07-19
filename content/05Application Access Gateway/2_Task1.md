---
title: "Authentication for AAG"
linkTitle: "Authentication for AAG"
weight: 1
---
### **Selecting Optimal Authentication for AAG**

Choosing the appropriate authentication method for FortiADC's Agentless Application Gateway (AAG) is critical for securing access to applications while ensuring compatibility with existing identity management frameworks. This section provides a structured approach to determining the most suitable authentication mechanism based on user types, security policies, and infrastructure requirements.

**Authentication Methods and Deployment Considerations**

FortiADC supports multiple authentication mechanisms for AAG access, all enforced through Access Policies. Each authentication method is suited to specific deployment scenarios. The table below outlines the key characteristics of each method:

|Authentication Method|Best Suited For|Key Advantages|
|---------------------|---------------|--------------|
|Local User Authentication|Small-scale or standalone deployments without external authentication infrastructure|Self-contained user management with minimal configuration, allowing direct user administration within FortiADC|
|Remote User Authentication (LDAP, RADIUS)|Enterprises with centralized identity systems|Integration with Active Directory or RADIUS servers|
|SAML Authentication|Federated authentication across domains/clouds|Seamless login experience via trusted Identity Providers (IdPs), including FortiAuthenticator and Microsoft Entra ID|

**Multi-factor authentication (MFA) is not currently supported in the initial AAG release. Although FortiADC supports MFA in general access policies, these features are not enforced at the AAG App Portal level.**

**Authentication Deployment Considerations**

Local User Authentication

- Local user accounts are defined and stored directly on FortiADC. This method is suitable for small deployments or administrative access when external identity systems are unavailable. Local users can be assigned to User Groups and linked to App Portals via Access Policies.
- **Pros:** Simple configuration, independent of external systems
- **Cons:** Manual account provisioning, limited scalability

For details, see [Local User](https://docs.fortinet.com/document/fortiadc/8.0.0/administration-guide/037414/local-user).

**LDAP/RADIUS Authentication**

AAG integrates with LDAP directories (e.g., Microsoft Active Directory) and RADIUS servers to authenticate users based on corporate credentials. This allows centralized user account management and simplifies integration into existing identity infrastructures.
- Supports: Secure credential validation, dynamic group mapping
- Does not support: MFA enforcement for AAG App Portal access

For details, see [Using an LDAP authentication server](https://docs.fortinet.com/document/fortiadc/8.0.0/administration-guide/628325/using-an-ldap-authentication-server) and [Using a RADIUS authentication server](https://docs.fortinet.com/document/fortiadc/8.0.0/administration-guide/110302/using-a-radius-authentication-server).

**SAML-Based Authentication**

SAML is the preferred method for organizations using federated identity platforms such as FortiAuthenticator or Microsoft Entra ID (formerly Azure AD). FortiADC acts as a SAML 2.0 Service Provider (SP), redirecting authentication requests to the Identity Provider (IdP).

**Benefits:**
- Centralized authentication and single sign-on (SSO)
- Passwordless experience through external IdP
- Support for cross-domain identity federation

**Aligning Authentication with Security Policies**

Authentication settings should be configured in conjunction with FortiADC’s access control policies, session management rules, and logging mechanisms to ensure a secure and compliant deployment.

By selecting an appropriate authentication method—such as Local User, LDAP, RADIUS, or SAML—and integrating with centralized identity services where applicable, organizations can strengthen authentication workflows and improve user experience in their AAG deployments.