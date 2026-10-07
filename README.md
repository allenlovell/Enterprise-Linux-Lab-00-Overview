# Enterprise Linux Lab
*A hands-on comparison of Samba/Windows interoperability and Linux-native identity, endpoint management, security, and infrastructure*

## Microsoft-Compatible vs. Linux-Native Enterprise Architecture

### Project Overview

This lab is a hands-on expedition into how a modern **enterprise** IT environment can be build and handled using Linux-based infrastructure.

The goal isn't to simply install a Linux server or configure a domain controller; rather this project will build two separate enterprise environments, each using a different approach to identity, authentication, endpoint management, and infrastructure.

```text
                         ENTERPRISE LAB
                               |
                 +-------------+-------------+
                 |                           |
          MICROSOFT-COMPATIBLE          LINUX-NATIVE
              ENVIRONMENT                ENVIRONMENT
                 |                           |
             Samba AD                    FreeIPA
                 |                           |
          Windows 11                    Fedora KDE
```
The **first** environment will establish how Linux can provide necessary infrastructure commonly associated with Microsoft Windows Server and Active Directory using OpenSource handlers, and the **second** environment will demonstrate a Linux-native enterprise architecture using tools designed specifically for Linux identity and system management.

*After* establishing both environments independently, the project will investigate how the two infrastructures can interact together and how enterprise identities, authentication, authorization, and resources can potentially operate across both environments.
