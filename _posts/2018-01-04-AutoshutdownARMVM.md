---
layout: post
title: Auto-shutdown RM VM
description: "Auto-shutdown RM VM"
modified: 2018-01-04
tags: [Azure, IaC]
categories: [Cloud, DevOps]
author: Ajeet
---
We all know that we can either use run books or use the option of Auto shutdown inside the VM blade. but all this require a manual action to configure. We can use **Microsoft.DevTestLab/schedules** resource to automate this during the provision of VM it self.

```JSON
{
    "name": "[concat('shutdown-computevm-', parameters('virtualMachineName'))]",
    "type": "Microsoft.DevTestLab/schedules",
    "apiVersion": "2017-04-26-preview",
    "location": "[parameters('location')]",
    "properties": {
        "status": "[parameters('autoShutdownStatus')]",
        "taskType": "ComputeVmShutdownTask",
        "dailyRecurrence": {
            "time": "[parameters('autoShutdownTime')]"
        },
        "timeZoneId": "[parameters('autoShutdownTimeZone')]",
        "targetResourceId": "[resourceId('Microsoft.Compute/virtualMachines', parameters('virtualMachineName'))]",
        "notificationSettings": {
        "status": "[parameters('autoShutdownNotificationStatus')]",
        "emailRecipient": "[parameters('autoShutdownNotificationEmail')]",
        "notificationLocale": "[parameters('autoShutdownNotificationLocale')]",
        "timeInMinutes": "30"
        }
    },
    "dependsOn": [
       "[concat('Microsoft.Compute/virtualMachines/', parameters('virtualMachineName'))]"
        ]
    },
```
