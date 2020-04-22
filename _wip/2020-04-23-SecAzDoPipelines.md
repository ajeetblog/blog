---
layout: post
title: Securing Azure DevOps Pipelines
description: "Securing Azure DevOps Pipelines using Key Vault"
modified: 2020-04-23
tags: [ Azure, YML Pipelines, KeyVault, AZ-400]
categories: [Azure, DevOps]
author: Ajeet
---

## Securing Azure DevOps Pipelines using Azure Key Vault  

Security is the integrated part of the Application Life Cycle Management. As a responsible member of the team delivering the security practices in every process and each phase is your responsibility.

In this post, I will talk on how to ensure security compliance in your Azure DevOps pipelines (YML based) when you are dealing with secrets and certificates.

<!--more-->

**Azure Key Vault** is a tool for securely storing and accessing secrets.  Some of the features are:

**Secrets Management** - Azure Key Vault can be used to Securely store and tightly control access to tokens, passwords, certificates, API keys, and other secrets.

**Key Management** - Azure Key Vault can also be used as a Key Management solution. Azure Key Vault makes it easy to create and control the encryption keys used to encrypt your data.

**Certificate Management** - Azure Key Vault is also a service that lets you easily provision, manage, and deploy public and private Transport Layer Security/Secure Sockets Layer (TLS/SSL) certificates for use with Azure and your internal connected resources.

**Store secrets backed by Hardware Security Modules** - The secrets and keys can be protected either by software or FIPS 140-2 Level 2 validated HSMs.

> read more about [**Azure Key Vault**](https://docs.microsoft.com/en-in/azure/key-vault/general/overview).

You can leverage one of the following approaches to integrate Azure Key Vault with pipelines.

-   **Variable group**
-   **Azure Key Vault task**