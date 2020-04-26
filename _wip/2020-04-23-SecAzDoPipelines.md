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

![Create KV Secrets](/images/posts/azdo/keyvault.JPG)

2. Create a Variable Group
 
 2.1  Create variable group and enable  
  
![Create Variable Group](/images/posts/azdo/linkkv.JPG)

  2.2 Select Subscription and Key Vault: You need to authroize the subscription. 

![Link kv](/images/posts/azdo/kvpipeline3.JPG)


Select and authorize the Key Vault, this action will create a service principal and it to Key Vault access policies with Get and List permission only.

![authorize](/images/posts/azdo/selectkv.JPG)

Now you can select the keys that you wanted to be avaiable for pipeline as variable.

![filter](/images/posts/azdo/filter.JPG)

3. Create Pipeline\
*for this demo, I have choosen the default starter pipeline.*

```YML
# Starter pipeline
# Start with a minimal pipeline that you can customize to build and deploy your code.
# Add steps that build, run tests, deploy, and more:
# https://aka.ms/yaml

trigger:
- master

pool:
  vmImage: 'ubuntu-latest'

steps:
- script: echo Hello, world!
  displayName: 'Run a one-line script'

- script: |
    echo Add other tasks to build, test, and deploy your project.
    echo See https://aka.ms/yaml
  displayName: 'Run a multi-line script'
```
To integrate the pipeline with Variable group, you need to add variables in the pipeline

Under variables section, added group and local variables. 
> Learn more [variables in YML pipelines](https://docs.microsoft.com/en-us/azure/devops/pipelines/process/variables?view=azure-devops&tabs=yaml%2Cbatch)

```YML
# Starter pipeline
# Start with a minimal pipeline that you can customize to build and deploy your code.
# Add steps that build, run tests, deploy, and more:
# https://aka.ms/yaml

trigger:
- master

pool:
  vmImage: 'ubuntu-latest'
# variables to support local and Variable group
variables:
  - group: kv-pipelines
  - name: local
    value: 'Hello World'
    
steps:
- script: |
    echo Local variable
    echo $(local)
  displayName: 'Local Variables'

- script: |
    echo Secure value from KV
    echo Key 1 $(key1)
    echo Key 2 $(key2)
  displayName: 'Secure Variables'
```

While defining the variables name, you need to ensure that they are not repeated. In case of duplicate Keys, last one will have precednet over other. 

Once you define the keys, Azure DevOps will take care of getting them from respective soruces. Any vaules coming from Key Vault will not be displayed as simple text at any point of time and can only be updatd by the users who have RBAC permission inside Key vault access policies.
