---
title: Administer Microsoft Power Platform
description: The Power Platform admin center is a unified portal for administrators to manage environments and settings.
author: sericks007
ms.topic: overview
ms.date: 02/04/2025
ms.author: sericks
---
# Administer Microsoft Power Platform

The Power Platform admin center (<https://admin.powerplatform.microsoft.com>) provides a unified portal for administrators to manage environments and settings for Power Apps, Power Automate, Power Pages, and Microsoft Copilot Studio.

The Power Platform admin center is also used by administrators of some Dynamics 365 apps, such as Dynamics 365 Sales, Dynamics 365 Customer Service, and Dynamics 365 Marketing, to manage environments and settings.

> [!Note]
> Power BI administrators use the Power BI admin portal (<https://app.powerbi.com>) to manage a Power BI tenant including the configuration of governance policies, usage monitoring, and provisioning of licenses, capacities, and organizational resources. Learn more about Power BI admin portal at [What is Power BI administration?](/power-bi/service-admin-administering-power-bi-in-your-organization).

## Manage your environments and settings

The Power Platform admin center provides the following capabilities.

|Feature  |Description  | Learn more |
|---------|---------|----------------|
|Environments | View, create, and manage your environments. Select an environment to see details and manage its setting. |[Manage environment settings](./admin-settings.md)|
| Environment groups |  Similar to folders, _environment groups_ are designed to help administrators organize their flat list of environments into structured groups based on different criteria, such as business unit, project, and location | [Environment groups](environment-groups.md) |
| Advisor | Power Platform Advisor is your guide to personalized recommendations to optimize your Power Platform tenant. Advisor analyzes all Managed Environments and the apps in these environments within your Power Platform tenant. Advisor offers solutions to enhance security, reliability, and overall health. | [Use Power Platform Advisor](power-platform-advisor.md) |
|Security | Run your organizational workloads in the safest way possible with a wide set of security features available. | [Security overview](security/security-overview.md) |
|Analytics     | Get a detailed view of key metrics for Microsoft Power Platform apps. |[Microsoft Dataverse analytics](./analytics-common-data-service.md)    |
|Billing  |  View a summary of environments in your tenant requiring licensing attention and license consumption for your environments. |[Business subscription and billing documentation](/microsoft-365/commerce) and [View license consumption](view-license-consumption-issues.md) |
|Settings  |  Manage settings for all environments in your tenant.|[Tenant settings](tenant-settings.md) |
| Copilot | Access educational resources, track usage, and access governance controls about Copilot features. | [Manage Copilot](copilot/copilot-hub.md) |
|Resources  |  View and manage resources in your tenant and environments. |[View and manage resources](view-manage-resources.md)  |
|Help + support     | Get a list of self-help solutions or create a support ticket for technical support.<br/><br/>**Note**: Although, you administer Power BI using the Power BI admin portal, you request support for Power BI through Help + support in the Power Platform admin center.| [Get Help + Support](./get-help-support.md).  |
|Data integration| The Data Integrator (for Admins) is a point-to-point integration service used to integrate data into Dataverse. | [Integrate data into Dataverse](data-integrator.md)|
|Data| Manage your cloud and data gateway connections.| [Set up data transfer between on-premises data and cloud services](onpremises-data-gateway-management.md) |
|Policies     | View and manage various policies for your tenant and environments. | <br/>- [Manage data policies](prevent-data-loss.md)<br/>- [Tenant isolation policy](cross-tenant-restrictions.md)<br/>- [Customer Lockbox policy](about-lockbox.md)<br/>- [Enterprise policies](customer-managed-key.md)<br/>- [Billing policies](pay-as-you-go-overview.md)|

## Personalize your Home page

You can personalize your **Home** page by selecting a theme, setting your language, and timezone from the **Settings** gear.

To personalize your dashboard, select **+ Add cards** on top of the homepage and drag any card onto the dashboard to the location you want.

:::image type="content" source="media/home-page.png" alt-text="Power Platform admin center Home page":::

The following are the cards you can add to the dashboard.

### Monitor service health

This card shows whether your Microsoft services are healthy, or if they're experiencing an active advisory or incident. For more info about an advisory or incident, select it to open the **Service health** page of the Microsoft 365 admin center.

### Message center

This card helps you manage upcoming changes to our Microsoft services. Select a post to open it in the details panel. To view the full list of messages across all Microsoft services, select **Show all**. [More info about the message center](/office365/admin/manage/message-center).

### Resources for documentation and training

This card provides links to related documentation and information sources.

### Related content

[Working with various admin portals](wp-work-with-admin-portals.md) <br />
[Training: Microsoft Power Platform Fundamentals](/training/paths/power-plat-fundamentals)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
