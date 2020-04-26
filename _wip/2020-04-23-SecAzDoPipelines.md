---
layout: post
title: Secure your secretes in Azure DevOps Pipelines
description: "Securing Azure DevOps Pipelines using Key Vault"
modified: 2020-04-23
tags: [ Azure, YML Pipelines, KeyVault, AZ-400]
categories: [Azure, DevOps]
author: Ajeet
---

## Secure your secretes in Azure DevOps Pipelines using Azure Key Vault  

Security is an integral part of the Application Life Cycle Management and must be implemented right from the beginning. Its everyone's responsibility to ensure security compliance in every process and each phase.

In this post, I will talk on how to ensure security in terms of ***Key, Secrete, Certificate*** management as part of your Azure DevOps pipelines (YML based). 

![ ](https://media1.giphy.com/media/JpGRoqJXTqv4f1mrJb/100.webp?cid=ecf05e47d6cfd92788dfc2cd326e5a4af621da17e69257b7&rid=100.webp)

<!--more-->

## Problem Statement

CI CD pipeline pushes your app into different environments, but as a good DevSecOps architect, you wanted to ensure **separation of concern and responsibilities**. *If secrets are stored in code in an appsettings.json file, for example, then you're creating a security risk*.

## Follow Sepration of Concern principal

To ensure security compliance and less management overhead, you need to store sensitive information into a different component.  By design, this component is responsible for storing and securely retrieving information. 

### Store Senstive Information away from Pipeline

Azure Key Vault allows you to manage the separation of concern using industry-standard security practices. 

Some of the features are: 

- **Secrets Management** - Azure Key Vault can be used to Securely store and tightly control access to tokens, passwords, certificates, API keys, and other secrets.

- **Key Management** - Azure Key Vault can also be used as a Key Management solution. Azure Key Vault makes it easy to create and control the encryption keys used to encrypt your data.

- **Certificate Management** - Azure Key Vault is also a service that lets you easily provision, manage, and deploy public and private Transport Layer Security/Secure Sockets Layer (TLS/SSL) certificates for use with Azure and your internal connected resources.

- **Store secrets backed by Hardware Security Modules** - The secrets and keys can be protected either by software or FIPS 140-2 Level 2 validated HSMs.

> read more about [**Azure Key Vault**](https://docs.microsoft.com/en-in/azure/key-vault/general/overview).

### Let's Start

You can choose one of the following approach to integrate Azure Key Vault with pipelines.

- [**Variable groups**](#variables-groups)
- [**Azure Key Vault Task**](#azure-key-vault-task)

### Variable Groups

The variable groups store values that you want to control and make available across multiple pipelines. 

Variable groups are also used to store secrets and other values that might need to be passed into a YAML pipeline. Variable groups are defined and managed in the Library page under Pipelines.

1. Create a Key Vault and add Secrets

![Key vault and Secrets](/images/posts/azdo/keyvault.JPG)

2. Create a Variable Group
 
 2.1  Create variable group and enable  
  
  ![Link Variable Group](/images/posts/azdo/linkkv.JPG)

  2.2 Select Subscription and Key Vault: You need to authroize the subscription. 

 ![Link Variable Group](/images/posts/azdo/kvpipeline3.JPG)

Select and authorize the Key Vault, this action will create a service principal and it to Key Vault access policies with Get and List permission only.

  ![Link Variable Group](/images/posts/azdo/selectkv.JPG)

Now you can select the keys that you wanted to be avaiable for pipeline as variable.

![Link Variable Group](/images/posts/azdo/filter.JPG)

4. Add key-value

5. Integrate Key Vault

6. Add variable group in pipeline

7. Add a task to display variable

### Azure Key Vault Task

The above approach requires manual intervention to link Key vault with the pipeline.

Follow steps 1 to 4 mention in the previous approach.

1. Add variables in the pipeline YML file.

2. Add Azure Key Vault task

3. Add display task
