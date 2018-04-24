---
layout: post
title:Design solutions using virtual machines -1
description: "Design solutions using virtual machines"
modified: 2017-08-31
tags: [Compute, 70-535]
categories: [Azure]
author: Ajeet
---

# Design Compute Infrastrcture

* Design solutions using virtual machines

    -   [Design VM deployments by leveraging availability sets, fault domains, and update domains in Azure](https://docs.microsoft.com/en-us/azure/virtual-machines/windows/manage-availability) - [My Notes]()
    -   [Use web app for containers](https://docs.microsoft.com/en-us/azure/app-service/containers/)
    -   [design VM Scale Sets](https://docs.microsoft.com/en-us/azure/virtual-machine-scale-sets/virtual-machine-scale-sets-design-overview)
    -   design for compute-intensive tasks using Azure Batch; define a migration strategy from cloud services; 
    -   recommend use of Azure Backup and Azure Site Recovery

*   Design solutions for serverless computing
    -   Use Azure Functions to implement event-driven actions; 
    -   Design for serverless computing using Azure Container Instances; 
    -   design application solutions by using Azure Logic Apps, Azure Functions, or both; 
    -   determine when to use API management service

*   Design microservices-based solutions  
    -   Determine when a container-based solution is appropriate; 
    -   determine when container-orchestration is appropriate; determine when Azure Service Fabric (ASF) is appropriate; determine when Azure Functions is appropriate; determine when to use API management service; determine when Web API is appropriate; determine which platform is appropriate for container orchestration; consider migrating existing assets versus cloud native deployment; design lifecycle management strategies
Design web applications
Design Azure App Service Web Apps; design custom web API; secure Web API; design Web Apps for scalability and performance; design for high availability using Azure Web Apps in multiple regions; determine which App service plan to use; design Web Apps for business continuity; determine when to use Azure App Service Environment (ASE); design for API apps; determine when to use API management service; determine when to use Web Apps on Linux; determine when to use a CDN; determine when to use a cache, including Azure Redis cache
Create compute-intensive application
Design high-performance computing (HPC) and other compute-intensive applications using Azure Services; determine when to use Azure Batch; design stateless components to accommodate scale; design lifecycle strategy for Azure Batch