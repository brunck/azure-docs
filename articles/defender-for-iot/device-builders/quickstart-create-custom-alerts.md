---
title: Create custom alerts
description: Understand, create, and assign custom device alerts for the Microsoft Defender for IoT security service.
ms.topic: how-to
ms.date: 11/09/2021
---

# Create custom alerts

Using custom security groups and alerts, takes full advantage of the end-to-end security information and categorical device knowledge to ensure better security across your IoT solution.

> [!NOTE]
> The Microsoft Defender for IoT legacy experience under IoT Hub has been replaced by our new Defender for IoT standalone experience, in the Defender for IoT area of the Azure portal. The legacy experience under IoT Hub will not be supported after **March 31, 2023**.
## Why use custom alerts?

You know your IoT devices best.

For customers who fully understand their expected device behavior, Defender for IoT allows you to translate this understanding into a device behavior policy and alert on any deviation from expected, normal behavior.

## Security groups

Security groups enable you to define logical groups of devices, and manage their security state in a centralized way.

These groups can represent devices with specific hardware, devices deployed in a certain location, or any other group suitable to your specific needs.

Security groups are defined by a device twin tag property named **SecurityGroup**. By default, each IoT solution on IoT Hub has one security group named **default**. Change the value of the **SecurityGroup** property to change the security group of a device.

For example:

```
{
  "deviceId": "VM-Contoso12",
  "etag": "AAAAAAAAAAM=",
  "deviceEtag": "ODA1BzA5QjM2",
  "status": "enabled",
  "statusUpdateTime": "0001-01-01T00:00:00",
  "connectionState": "Disconnected",
  "lastActivityTime": "0001-01-01T00:00:00",
  "cloudToDeviceMessageCount": 0,
  "authenticationType": "sas",
  "x509Thumbprint": {
    "primaryThumbprint": null,
    "secondaryThumbprint": null
  },
  "version": 4,
  "tags": {
    "SecurityGroup": "default"
  },
```

Use security groups to group your devices into logical categories. After creating the groups, assign them to the custom alerts of your choice, for the most effective end-to-end IoT security solution.

## Customize an alert

1. Open your IoT Hub and select **Settings** from the **Security** menu.

1. Select on **Custom alerts**.

1. Choose a security group you wish to apply the customization to.

1. Select **Add a custom alert**.

1. Select a custom alert from the dropdown list.

1. Edit the required properties, select **OK**.

1. Make sure to select **SAVE**. Without saving the new alert, the alert is deleted the next time you close IoT Hub.

## Alerts available for customization

Defender for IoT offers a large number of alerts, which can be customized according to your specific needs. Review the [customizable alert table](concept-customizable-security-alerts.md) for alert severity, data source, description, and our suggested remediation steps if and when each alert is received.

## Next steps

Advance to the next article to learn how to deploy a security agent...

> [!div class="nextstepaction"]
> [Deploy a security agent](how-to-deploy-agent.md)
