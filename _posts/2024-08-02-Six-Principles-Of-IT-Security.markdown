---
layout: posts
title: "Six Principles Of IT Security"
date: 2024-08-02 10:00:00 -0700
tagline: "Basics of IT Security"
tags: [IT, Security]
author_profile: true
author: Joel Holland
categories: [article]
header:
    overlay_image: 
    teaser: 
    caption: 
description: This is an article about basic principles of IT Security
highlight_home: true
---

# Six Principles of IT Security

As part of a new job, I was required to take an internal training on the 'Six Principles of IT Security'

The below article contains my notes.

## Overview

Principles:
- Protecting Software, Libraries & Applications
- Protecting Credentials & Data
- Managing Access
- Ensuring you always build resiliency into your systems and applications
- Recognize that you are a highly prized target in your industry

### Principal 1: Protecting Software, Libraries & Applications
From the training: "As a tech or product owner you may be directly responsible for implementing patching and updating code, other patching processes may include the assisting of patching or validation. In either case, you should know your role and take patching and updating serious as a first line of defense against adversaries." 

<u>Patching our systems and code includes:</u>
- Operating Systems
- Server and Desktop Applications
- Commercial and Open Source software
- Network Devices, Appliances, Firmware

While there are various parties responsible for each of the above, we all have individual responsibilities to enusre proper Policies & Procedures are followed within our realm of responsibility. Even if that is just restarting our computers each night.

<u>Code Toolsets that can assist in protecting software & code:</u>
- GitHub
- JFrog Artifactory
- CI/CD Enterprise Framework

#### GitHub
- [GH Advanced Security](https://docs.github.com/en/enterprise-cloud@latest/get-started/learning-about-github/about-github-advanced-security) - scan for secrets in code
    - code scanning - discovers security vulnerabilities and coding errors
    - dependency review - identifies insecure dependencies in the code
- [Pull Requests, PR](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/about-pull-requests) - process to ensure proper validations and approvals are in place. Ensure your code is reviewed by your peers, in order to meet branch policies for your project.
- Jira to GitHub integration - Ensures traceability of the code to requirements

#### JFrog Artifactory

Artifactory is integrated with JFrog XRay, which allows for analysis that helps scan artifacts, builds and release bundles for Open Source Software (OSS) components.  

It also detects security vulnerabilities and validates licenses in the software components.  

#### Enterprise standard CI/CD frameworks

Without going into too much detail, is effectively a standardized approach across multiple groups, project types, applications, data warehouses, etc. that can be used to plan, develop, troubleshoot, and deploy various technology/code based projects.

### Principal 2: Protecting Credentials

Credential attacks are prevalent in most network intrusions

#### Common exposed credentials include:
- Service Accounts
- Admin Passwords
- API Tokens & Keys
- SNMP Community Strings
- SSH Keys and Private Key Pairs for Certificates

#### Common exposed credential locations include:
- Committed Code
- Shell Scripts
- Scheduled Tasks
- Group Policy
- SNMP
- Config Files
- Word Docs
- Email
- Confluence
- ServiceNow

#### Code Repos:
- Treasure Trove for criminals
- GitHub remembers everything committed unless you explicitly delete it
- Enterprises will often have centralized code repos managed by specific teams who actively identify any security risks in commited code.
- Best practice is to not expose passwords directly in code, instead refer to config files, which in turn can execute commands while protecting credentials

#### Scheduled Tasks:
- Local system credential vaults are vulnerable to attack
- Running tasks as "system", or leveraging existing automation systems is a better alternative

#### Group Policy:
- Avoid using Group Policy to set systems passwords
- Instead using something like Windows LAPS and Privileged Access Management (PAM) allows for more secure credentials

#### SNMP Community Strings
- As a potential user of SNMP you need to:
    - Leverage a complex and non-default string name
    - Use the strongest transport security (SNMPv3)

#### In General
- Never use clear text or weak credential protection

### Principal 3: Managing Access
- An important piece of protecting cloud and mobile enabled environments is verifying:
    - Who is trying to gain access (Authentication) &
    - Validating what they are approved to access (Authorization)
- Multi-factor authentication (MFA) provides an extra layer of security and reduces the risk of a security breach allowing sensitive data to stay protected. 
- Integrating a time-based one-time password, via an authenticator application or device, goes a layer deeper because it helps achieve a zero-trust security remotely.
- Forced Single Sign-on (SSO) does not give users the option to use a password, but instead links their application access to an existing domain authentication.
    - This allows an end user to automatically log-in and access the app, i.e. MS Office or Workday.
    - Not only is forced SSO more secure, but:
        - Provides peace of mind to ensure enforcement of password policies
        - Enables business user access as they join a new team
        - Can be leveraged to enable multi-factor authentication
        - Enforce password re-entry when a certain amount of time passes
- Least privilege enforcement ensures the user or automated tool has the requisite access needed – and nothing more.

### Principal 4: Protect the Data
In addition to protecting credentials, we also need to protect data as it travels between systems, endpoints and to our partners and vendors. 

Some methods to accomplish this include: 
- Mobile Encryption
- Cloud Technologies
- Preventing Confidential Data Storage in Clear Text Logs
- Data Minimization

### Principal 5: Building Resiliency Into Systems And Apps (always plan for failure)
Some of the worst impacts form attackes result form the inability to access systems and data:
- Do your due diligence to ensure your systems, applications and data remain available or are recoverable in the event of catastrophic failure due to a cyber-attack.
- Understand the impact of a system or service failure.
- Identify the possible failure points in the system when designing systems. This includes internal and external dependencies such as identity providers and third party services.
- Identify each failure according to its overall risk. Consider these factors: 
    - What is the likelihood of the failure? Is it relatively common? Extremely rare? You don't need exact numbers; the purpose is to help rank the priority. 
    - What is the impact on the application in terms of availability, data loss, monetary cost, and business disruption?
- For each failure mode, determine how the application will respond and recover. Consider tradeoffs in cost and application complexity.
- Ensure backup of systems and data.  All archives should employ encryption. All backups of your systems and data require regular testing.  

### Principal 6: Realize you are targeted as a Privileged User
- Your goal is to prevent the criminals from gaining access to sessions and system memory or installing software on any of your systems including workstations, laptops and smartphones.

- Session Hijacking Defense: Session persistence allows attackers to reuse token and cookies as a method to gain access to a system while impersonating you. 
    - Ensure you log out of websites when done
    - Never click on website pop-ups
    - If your browser displays a warning about a website you are trying to access, pay attention and obtain the information from a more reliable source
    - Only go to sites using HTTPS
    - Only open email attachments if you trust the sender and are expecting the attachment
    - Be on the watch for phishing attempts
    - Ensure your systems receive regular updates and patches

- Multiple Account Management: When accessing systems or services with elevated permissions for technical tasks, you should always utilize your separate administrative account. This account is isolated and better protected from the typical attacks that we all experience while working at our desktops. 
    - The administrative account is:
        - Purpose designed, and non-administrative use exposes the credentials in locations that criminals access with various tools and techniques.
        - Administrative accounts should utilize MFA to prevent a direct capture and use of the credentials.

- Sharing Information: Many of us interact daily with technical peers or assist business peers with their technology issues.
    - You can help defend systems by doing the following:
        - Be on the lookout for unsolicited incoming calls asking you to take technical action or expose personal/technical information.
        - If you receive these types of communication, validate the person to ensure they are approved to receive the information.
        - Make sure you enforce the seemingly small items while managing systems. This adds up to a big defense when we all work to protect privileged access on the network.
