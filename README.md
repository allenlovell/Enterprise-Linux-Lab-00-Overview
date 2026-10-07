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

***"<ins>Many</ins>,"*** being the operative word here, but we will get into that further into the lab.

At the same time, the project will analyze where Microsoft and Linux technologies differ, where they overlap, and where interoperability becomes important.

---

# The Two Enterprise Environments

## Environment 1: *Microsoft-Compatible Architecture*

The first environment wll use **Samba Active Directory** as its core system for identity and authentication.

```text
              CORP ENTERPRISE
                    |
              Samba AD DC
                    |
          +---------+---------+
          |                   |
      Users/Groups        DNS/Kerberos
          |
       Windows 11
        Clients
```

Samba is capable of giving us an Active Directory-compatible domain controller, and allows a linux server to provide many of the services normally associated with a Windows Server AD environment including:

- Centeralized user accounts
- Groups
- Organizational units
- Kerberos authentication
- LDAP directory services
- DNS integration
- Windows domain joining
- SMB file services
- and Group Policy functionality

Windows 11 clients will join this domain as if they were taking part in a classic Windows enterprise environment, and gives us the excuse to answer a fundamental question:

> *How far can Linux replace or reproduce the infrastructure normally provided by Microsoft Active Directory*

---

## Environment 2: *Linux-Native Architecture*

The second environment will take a wholly different approach: Instead of plagiarizing Microsoft's Active Directory architecture, it will use **FreeIPA** as the identity management platform.

```text
              LINUX ENTERPRISE
                    |
                 FreeIPA
                    |
          +---------+---------+
          |                   |
      Identity             Policies
          |
       Fedora KDE
        Client
```

FreeIPA provides an integrated identity management environment designed for Linux and other Unix-like systems, and combines technologies such as:

- Kerberos
- LDAP
- DNS
- Certiicate management
- User and group management
- Host management
- SSSD integration
- Host-based access control
- Sudo(*root or admin*) policies

The Fedora KDE workstation will join to the Linux-native environment and authenticate against the centralized identity infrastructure while affording us the opportunity to answer a different question:

>*What does an enterprise environment look like when it is designed around Linux rather than around compatibility with Windows?*

---

## Why Use Two Separate Environments?

The two environments will initially and **<ins>INTENTIONALLY</ins>** remain separate.  Attempting to make both environments work together immediately would make it difficult to determine what is responsible when something breaks.

Instead, we will establish two (*hopefully*) clean baselines:

```text
Microsoft-Compatible

Samba AD
    |
Windows 11
```

and:

```text
Linux-Native

FreeIPA
    |
Fedora KDE
```

Once both environments work independently, we can begin investigating where interoperability can(*or should...*) happen.

This creates a progression:

```text
1. Build
   |
2. Configure
   |
3. Authenticate
   |
4. Administer
   |
5. Secure
   |
6. Troubleshoot
   |
7. Compare
   |
8. Integrate
```

This approach also makes the project easier to document and troubleshoot because each stage has a clearly defined objective.

---

# What We(*or just I*) Will Learn

> *again, hopefully...*

Throughout the project we will work with many of the systems and concepts encountered in real enterprise IT environments.

### Identity and Authentication

We will learn how centralized identity systems work and how clients authenticate against them.

Topics will include:

- Active Directory concepts
- LDAP
- Kerberos
- Users
- Groups
- Organizational structure
- Authentication vs. authorization
- SSSD
- Identity mapping
- Enterprise accounts

---

### DNS and Networking

Enterprise authentication depends heavily on networking and DNS; therefore we will analyze:

- DNS records
- Forward and reverse DNS
- Hostnames
- IP addressing
- Network connectivity
- Kerberos dependencies
- Service discovery
- Troubleshooting network authentication

This reinforces an important help desk and systems administration lesson:

> *When authentication fails, the problem may not actually be the user's password.*

DNS, networking, time synchronization, certificates, directory services, and client configuration can all affect authentication.

---

### Windows and Linux Administration

The lab will provide experience managing both Windows and Linux endpoints in such ways:

```text
Windows Endpoint
      |
      v
Samba AD
      |
      +-- Users
      +-- Groups
      +-- DNS
      +-- Kerberos
      +-- Policies
```

***vs.***:

```text
Fedora Endpoint
      |
      v
FreeIPA
      |
      +-- Users
      +-- Groups
      +-- Kerberos
      +-- LDAP
      +-- SSSD
      +-- Access Policies
```

This gives us an opportunity to compare how similar enterprise problems are solved using different technologies.

---

### Security

Security will be incorporated into the environment rather than treated as a completely separate topic.  I do that because sometimes things like this are not just plug and play at anytime, and any good security measures are built-in and not an afterthought.  Eventually this lab will include centralized security monitoring and logging.

One of the planned components is **Wazuh**.  This provides capabilities such as:

- Log collection
- Security monitoring
- File integrity monitoring
- Vulnerability detection
- Configuration assessment
- Security alerts
- Endpoint monitoring

This allows the project to progress from:

> *"Can I make the computer work?"*

to:

> *"Can I determine what happened when something goes wrong?"*

That contrast is notably important when moving from general IT support toward cybersecurity(my ultimate goal).

---


