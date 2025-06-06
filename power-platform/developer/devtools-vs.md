---
title: "What is Power Platform Tools for Visual Studio | Microsoft Docs"
description: "Learn about the Power Platform Tools extension for Visual Studio and how to install and uninstall it."
ms.custom: ""
ms.date: 02/04/2025
ms.reviewer: "pehecke"
ms.topic: concept-article
author: "phecke" # GitHub ID
ms.subservice: developer
ms.author: "pehecke" # MSFT alias of Microsoft employees only
---

# What is Power Platform Tools for Visual Studio

Power Platform Tools for Visual Studio supports the rapid creation, debugging, and deployment of plug-ins. Other capabilities include development of custom workflow activities, web resources, integration technologies like Azure Service endpoints and webhooks, and more.

This topic describes how to install and uninstall the Power Platform Tools extension in Visual Studio.

:::image type="content" source="media/tools/devtools-main-views.png" alt-text="Power Platform Tools." lightbox="media/tools/devtools-main-views.png":::

> [!IMPORTANT]
> While Power Platform Tools for Visual Studio is similar in appearance and function to the Developer Toolkit for Microsoft Dynamics CRM 2013, Power Platform Tools is a new product and completely independent of the Developer Toolkit. Power Platform Tools is not directly compatible with any templates or projects from the Developer Toolkit and vice versa.

## Prerequisites

Before installing Power Platform Tools into Visual Studio you must have the following applications and frameworks installed on your development computer:

- Microsoft Visual Studio 2019 or 2022.

- .NET Framework 4.6.2 (required only for plug-in and workflow activity development), or later

- C# programming language

In addition, you must also have access to a Microsoft Dataverse environment. A [trial environment](https://powerplatform.microsoft.com/dataverse/) will be sufficient.

## Install Power Platform Tools extension for Visual Studio

To install Power Platform Tools, follow these steps:

1. Start Visual Studio, and select **Continue without code** in the dialog. Optionally, you can open an existing project or create a new one.

1. Select **Extensions** > **Manage extensions**.

1. Expand the left navigation panel node **Online** > **Visual Studio Marketplace**. Search for "Power Platform Tools", then download and install the extension.

> [!IMPORTANT]
> There are two different tool extensions currently available for download from the [Marketplace](https://marketplace.visualstudio.com/). The extension named "Power Platform Tools" is for Visual Studio 2019. The extension named "Power Platform Tools for VS 2022" is for Visual Studio 2022.
>
> After installing Power Platform Tools, you will not find any Power Platform Tools related menu items or views in the Visual Studio user interface until you create or load a Visual Studio solution that contains at least one project created from a Power Platform Tools template.

### Uninstall Power Platform Tools extension

To uninstall Power Platform Tools, follow these steps:

1. Launch Visual Studio, and select **Continue without code** in the dialog. Optionally, you can open an existing project or create a new one.

1. Select **Extensions** > **Manage extensions**.

1. Expand the left navigation panel node **Installed**. Search for or scroll to the "Power Platform Tools" extension, select it, and then choose **Uninstall**.

## Install the Plug-in Profiler

If you are planning on developing plug-ins and would like to use the Plug-in Profiler to aid with plug-in debugging, the tool's Dataverse solution must be installed into your development environment. You can install or uninstall the tool's solution easily using Power Platform Tools for Visual Studio.

1. In Visual Studio, if you are not already connected to a Dataverse environment then do so now by choosing **Tools** > **Connect to Dataverse**.

1. Choose **View** > **Power Platform Explorer** to display its view.

1. Expand the target environment's node.

1. Right-click the **Plug-in Assemblies** node. You will see **Install Profiler** or **Uninstall Profiler** in the menu. If you see the **Uninstall Profiler** menu option, then the tool is already installed in your environment. Otherwise, choose **Install Profiler** to install the tool.

## Power Platform Tools options

You can find a few Power Platform Tools options in Visual Studio by choosing **Tools** > **Options** and searching for "Power Platform" in the **Options** dialog search field.

:::image type="content" source="media/tools/devtools-options.png" alt-text="Tool options":::

### Next steps

[Quickstart: Create a Power Platform Tools project](devtools-vs-create-project.md)<br/>
[Quickstart: Create a plug-in using Power Platform Tools](/power-apps/developer/data-platform/tools/devtools-create-plugin)<br/>

### See also
[Power Platform Tools extension for Visual Studio 2019](https://marketplace.visualstudio.com/items?itemName=microsoft-IsvExpTools.PowerPlatformTools)  
[Power Platform Tools extension for Visual Studio 2022](https://marketplace.visualstudio.com/items?itemName=microsoft-IsvExpTools.PowerPlatformToolsVS2022)
