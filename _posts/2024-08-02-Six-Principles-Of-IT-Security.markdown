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

### Principal 4: Ensuring you always build resiliency into your systems and applications

### Principal 5: Recognize that you are a highly prized target in your industry

### Principal 6: 

## Conclusion

