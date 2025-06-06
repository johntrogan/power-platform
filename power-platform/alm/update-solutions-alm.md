---
title: "Create and update custom solutions for ALM in Power Platform"
description: "Learn how to create and update custom solutions in Power Apps, including solution patches and clones."
keywords: 
author: Mattp123
ms.subservice: alm
ms.author: matp
ms.custom: ""
ms.date: 02/04/2025
ms.reviewer: ""
ms.topic: how-to
search.audienceType: 
  - maker
---
# Create and update solutions

To locate and work with just the components you’ve customized, create a solution and do all your customization there. Then, always remember to work in the context of the custom solution as you add, edit, and create components. This makes it easy to export your solution for import to another environment or as a backup. More information [Create a solution](/powerapps/maker/common-data-service/create-solution)

## Update a solution

Make changes to your unmanaged solution, such as adding or removing components.
Then, when you import a managed solution that was previously imported, the
import logic detects the solution as an update and displays the following screen of options.

> [!div class="mx-imgBorder"] 
> ![Solution update detected upon import.](media/solution-update-alm.png "Solution update detected upon import")

More information: [Apply an update or upgrade for a solution](/powerapps/maker/common-data-service/update-solutions) 

## Create solution patches

You can create a patch for a parent solution and export it as a minor update to the base solution. When you clone a solution, the system rolls up all related patches into the base solution and creates a new version.

> [!WARNING]
> Using clone a patch and clone solution to update a solution isn't recommended because it limits team development and increases complexity when storing your solution in a source control system. For information about how to update a solution, go to [Update a solution](#update-a-solution).

### Creating updates using clone solution and clone to patch

When you’re working with patches and cloned solutions, keep the following information in mind:  
  
- A patch represents an incremental minor update to the parent solution. A patch can add or update components and assets in the parent solution when installed on the target system, but it can’t delete any components or assets from the parent solution.  
- A patch can have only one parent solution, but a parent solution can have one or more patches.  
- A patch is created from an unmanaged solution. You can’t create a patch from a managed solution.  
- When you import a patch into a target system, you should export it as a managed patch. Don’t use unmanaged patches in production environments.  
- The parent solution must be present in the target system to install a patch.  
- You can delete or update a patch.  
- If you delete a parent solution, all child patches are also deleted. The system gives you a warning message that you can’t undo the delete operation. The deletion is performed in a single transaction. If one of the patches or the parent solution fails to delete, the entire transaction is rolled back.  
- After you have created the first patch for a parent solution, the solution becomes locked, and you can’t make any changes in this solution or export it. However, if you delete all of its child patches, the parent solution becomes unlocked.  
- When you clone a base solution, all child patches are rolled up into the base solution and it becomes a new version. You can add, edit, or delete components and assets in the cloned solution.  
- A cloned solution represents a replacement of the base solution when it’s installed on the target system as a managed solution. Typically, you use a cloned solution to ship a major update to the preceding solution.  

When you clone a solution, the version number you specify includes the major and minor positions. 

> [!div class="mx-imgBorder"]
> <img src="media/clone-solution.png" alt="Clone a patch major and minor version" height="560" width="307"> 

When you clone a patch, the version number you specify includes the build and revision positions. 

> [!div class="mx-imgBorder"] 
> <img src="media/clone-a-patch2.png" alt="Clone a patch build and revision version" height="560" width="307">

For more information about version numbers, go to [Clone solution and clone patch version numbers](#clone-solution-and-clone-patch-version-numbers) in this article.
  
## Create a solution patch

 A patch contains changes to the parent solution, such as adding or editing components and assets. You don’t have to include the parent’s components unless you plan to edit them.  
  
### Create a patch for an unmanaged solution  
  
1. Go to the Power Apps (make.powerapps.com), and then select **Solutions**.
1. In the solutions list, select an unmanaged solution where you want to create a patch. On the command bar, select **...** > **Clone** > **Clone a Patch**. The right pane that opens contains the base solution’s name and the patch version number. Select **Save**.  
   > [!div class="mx-imgBorder"] 
   > <img src="media/clone-a-patch.png" alt="Clone a patch" height="735" width="408">

1. In the solutions list, find and open the newly created patch. Notice that the unique name of the solution has been appended with _Patch_*hexnumber*. Just like with the base solution, add the components and assets you want.  
  
#### Create a patch using solution explorer

The following illustrations provide an example of creating a patch for an existing solution by using the legacy solution explorer. Start by selecting **Clone a Patch** (in the compressed view, the **Clone a Patch** icon is depicted as two small squares, as shown here).  
  
> [!div class="mx-imgBorder"] 
> ![Clone a patch icon.](media/solution-segmentation-click-patch-icon-admin.png "Clone a patch icon.")  
  
In the **Clone To Patch** dialog box you see that the version number for the patch is based on the parent solution version number, but the build number is incremented by one. Each subsequent patch has a higher build or revision number than the preceding patch.  
  
 ![Use Clone To Patch dialog.](media/solution-segmentation-clone-patch-dialog-admin.png "Use Clone To Patch dialog.")  
  
The following screenshot shows the base solution **SegmentedSolutionExample**, version **1.0.1.0**, and the patch **SegmentedSolutionExample_Patch**, version **1.0.2.0**.  
  
> [!div class="mx-imgBorder"] 
> ![A grid with solutions and patches.](media/solution-segmentation-solution-patch-grid-admin.png "A grid with solutions and patches.")  
  
In the patch, we added a new custom table called `Book`, and included all assets of the `Book` table in the patch.  
  
![Add custom table in the patch.](media/solution-segmentation-add-book-patch-admin.png "Add custom table in the patch.")  
  
### Clone a solution

When you clone an unmanaged solution, the original solution and all patches related to the solution are rolled up into a newly created version of the original solution. After cloning, the new solution version contains the original tables plus any components or tables that are added in a patch.

![Clone a solution.](media/cloned-solution.png)

> [!IMPORTANT]
> Cloning a solution merges the original solution and associated patches into a new base solution and removes the original solution and patches.
  
1. Go to the Power Apps (make.powerapps.com), and then select **Solutions**.
1. In the solutions list, select an unmanaged solution to create a clone. On the command bar, select **...** > **Clone** > **Clone solution**. The right pane displays the base solution’s name and the new version number. Select **Save**.  

### Clone solution and clone patch version numbers

A patch must have a higher build or revision number than the parent solution. It can’t have a higher major or minor version. For example, for a base solution with version 3.1.5.7, a patch could be a version 3.1.5.8 or version 3.1.7.0, but not version 3.2.0.0. A cloned solution must have the version number greater than or equal to the version number of the base solution. For example, for a base solution version 3.1.5.7, a cloned solution could be a version 3.2.0.0, or version 3.1.5.7. When you clone a solution or patch, you set the major and minor version values for a cloned solution, and the build or revision values for a patch.  
  
### See also

[Overview of tools and apps used with ALM](tools-apps-used-alm.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
