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

## Why Build This Lab?

Enterprise environments are handled fairly well through Microsoft Server and AD(along with a plethora of repositories, documentation, and quality of life build-ins), so why try to improve on it?

> <ins>**BECAUSE**</ins> I don't enjoy *microsoft...*

I have been daily driving Linux in one form or another for 8 years now and I don't plan on stopping.  That, and enterprise environments are rarely made up of a single operating system or technology stack.

**A company may have:**
- Windows workstations
- Linux Servers
- Network infrastructure
- Centralized identity management
- File servers
- Security monitoring
- Helpdesk systems
- Internal applications
- Cloud infrastructure
- Different authentication mechanisms
- or Different admin tools

Understanding how all of these systems and components work and fit together is more valuable than simply knowing how to install a singular operating system.  This lab is designed to develop a broader understanding of all of these compenents.

**It will also demonstrate an important concept in modern IT:**

> *Linux isn't limited to being a server OS crammed between Windows infrastructure.  Linux can provide **many** of the core services that make an enterprise environment function.*

***"Many,"*** being the operative word here, but we will get into that further into the lab.

At the same time, the project will analyze where Microsoft and Linux technologies differ, where they overlap, and where interoperability becomes important.

---
