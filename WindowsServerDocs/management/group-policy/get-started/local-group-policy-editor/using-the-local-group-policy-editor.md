---
title: Working with Local Group Policy Objects for Windows settings using the Local Group Policy editor
description: Using the Local Group Policy editor
ms.prod: windows-server-threshold
ms.technology: manage-group-policy
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: d8a2e6f8-8693-4dc5-88b1-abe31dfc4555
author: coreyp-at-msft
ms.author: coreyp
manager: dongill
ms.date: 10/12/2016
---
# Working with local Group Policy Objects for Windows settings using  the Local Group Policy editor

>Applies To: Windows Server 2016, Windows Server 2012 R2, Windows Server 2012

This topic describes how to use the Local Group Policy editor (gpedit) to perform basic procedures on GPOs.

## Introduction
**Editing Windows settings**

Windows Settings are available under both User Configuration and Computer Configuration in the console tree of Group Policy Management editor and the Local Group Policy editor.

**Computer Configuration**\Windows Settings is for Windows settings that apply to all users who log on to the computer. It includes five subitems:

-   Name Resolution Policy

-   Scripts

-   Deployed printers

-   Security Settings

-   Policy-based QoS

**User Configuration**\Windows Settings is for Windows settings that apply to users regardless of which computer they log on to. It includes five subitems:

-   Scripts

-   Security Settings

-   Policy-based QoS

-   Deployed printers

-   Internet Explorer Maintenance

Modifying Windows Settings on the local computer, whether creating new settings or editing existing ones, can be performed using the Local Group Policy editor by selecting the subitem and then selecting the appropriate task from the **Action** menu. If the computer is joined to a domain, the changes to the setting might be overridden by the next refresh of a GPO. If changes to the setting are done on the server where your GPOs are maintained, using the Group Policy Management editor, the GPO that contains the setting must be updated as well.

**Editing software settings**

Group Policy Software Installation enables you to provide on-demand software installation and automatic repair of applications. Group Policy offers a convenient method for delivering software, especially if you are already using Group Policy for other purposes such as securing your client and server computers.

Group Policy Software Installation enables you to:

-   Set options for Group Policy Software Installation that includes default settings, automatic installation settings, and specifying categories to help you manage applications

-   Work with applications by assigning, publishing, upgrading or removing managed applications

-   Set application properties such as installation options, categories for add or remove Programs, automatic installation, and installation permissions

-   Add or remove modifications for an application package

## How to edit a single local GPO

#### To edit a local Group Policy Object

1.  Open the Local Group Policy editor.

2.  In the console tree, double-click the folders to view the policy settings in the details pane.

3.  In the results pane, double-click a policy setting to open the **Properties** dialog box, and then edit the policy setting.

### Additional considerations

-   To complete this procedure, you must have edit setting permission to edit a GPO. By default, members of the Domain Administrators security group, the Enterprise Administrators security group, or the Group Policy Creator Owners security group have edit setting permission to edit a GPO.

-   Local Group Policy editor and the Resultant Set of Policy snap-in are available in Windows Server 2008 R2 and Windows 7 Professional, Windows 7 Ultimate, and Windows 7 Enterprise. For more information, see [http://go.microsoft.com/fwlink/?LinkId=139815](http://go.microsoft.com/fwlink/?LinkId=139815).

## How to edit multiple local GPOs
Multiple Local Group Policy is a collection of Local Group Policy objects (LGPOs) designed to provide improved management for computers that are not part of a domain. This collection consists of the following LGPOs:

-   **Local computer Policy**. This LGPO applies policy settings to the computer and any users logging on to the computer. This is the same LGPO that was included in earlier versions of Microsoft Windows.

-   **Administrators Local Group Policy**. This LGPO applies user policy settings to members of the Administrators group.

-   **Non-Administrators Local Group Policy**. This LGPO applies user policy settings to users who are not included in the Administrators group.

-   **User-Specific Local Group Policy**. This LGPO applies user policy settings to a specific local user.

#### To edit Multiple Local Group Policy

1.  Open Microsoft Management Console.

2.  Click **File** and then click **add/remove Snap-in**.

3.  Click **Group Policy Object editor** in the **Available Snap-ins** list and click **Add**.

4.  Click the **Browse** button in the **Select Group Policy Object** dialog box.

5.  Click the **Users** tab in the **Browse for the Group Policy Object** dialog box.

6.  Click the user or group for which you want to create or edit local Group Policy. Click **OK**, click **Finish**, and then click **OK**.

7.  Configure policy settings.

### Additional considerations

-   Multiple Local Group Policy objects (MLGPOs) are not available on domain controllers.

-   Local Group Policy is processed in the following order, with the final LGPO taking precedence over all others:

    1.  Local Group Policy (also known as Local computer Policy).

    2.  Administrators or non-administrators Local Group Policy.

    3.  User-specific Local Group Policy.

-   Local Group Policy editor and the Resultant Set of Policy snap-in are available in Windows Server 2008 R2 and Windows 7 Professional, Windows 7 Ultimate, and Windows 7 Enterprise. For more information, see [http://go.microsoft.com/fwlink/?LinkId=139815](http://go.microsoft.com/fwlink/?LinkId=139815).

## How to disable user or computer policy settings in a Local Group Policy Object
Occasionally you may want to disable policy settings rather than delete the entire Local Group Policy.

#### To disable user or computer policy settings in a Local Group Policy Object

1.  Open Microsoft Management Console.

2.  Click **File** and then click **add/remove Snap-in**.

3.  In the **add/remove Snap-in** dialog box, in the **Available Snap-ins** list box, click **Group Policy Object editor**, and then click **add**.

4.  In the **select Group Policy Object** dialog box, click **Browse**.

5.  To specify Local computer Policy, click **OK** and then click **Finish**. Proceed to Step 7.

6.  To specify Local computer Policy for users or groups, click the **Users** tab, and select from the following Local Group Policy objects:

    -   **Administrators**: Predefined Local Group Policy that applies to users included in the Administrators group.

    -   **Non-Administrators**: Predefined Local Group Policy that applies to users not included in the Administrators group.

    -   **User-Specific**: Local Group Policy objects associated with a specific local user account.

7.  Right-click the name of the Local Group Policy object, and then click **Properties**.

8.  Click **Disable computer Configuration settings** or **Disable User Configuration settings**.

9. Click **OK**, and then close Microsoft Management Console.

### additional considerations

-   Local computer Policy allows you to disable both computer and user configurations. Administrators, Non-Administrators, and User-Specific Local Group Policies allow you to disable only the user configuration.

-   Local Group Policy editor and the Resultant Set of Policy snap-in are available in Windows Server 2008 R2 and Windows 7 Professional, Windows 7 Ultimate, and Windows 7 Enterprise. For more information, see [http://go.microsoft.com/fwlink/?LinkId=139815](http://go.microsoft.com/fwlink/?LinkId=139815).

## How to delete Multiple Local Group Policy Objects
You can delete Multiple Local Group Policy objects. Use this procedure to delete Administrators, Non-Administrators, or User-Specific Local Group Policy objects.

#### To delete Multiple Local Group Policy Objects

1.  Open Microsoft Management Console.

2.  Click **File**, and then click **Add/remove Snap-in**.

3.  Click **Group Policy Object editor** in the **Available Snap-ins** list and click **Add**.

4.  In the **select Group Policy Object** dialog box, click **Browse**. Click the **Users** tab.

5.  Right-click the **Administrators, Non-Administrators,** or **User-Specific** Local Group Policy object. Click **Remove Group Policy Object**.

6.  Click **Yes** to confirm the deletion of the Local Group Policy object.

7.  Close Microsoft Management Console.

> [!NOTE]
> The text located in the **Group Policy Object Exists** column next to the item selected in Step 4 will display **No**.

### additional considerations

-   Multiple Local Group Policy Objects are not available on domain controllers.

-   You cannot delete the Local Group Policy Object (also known as Local computer Policy).

-   Local Group Policy editor and the Resultant Set of Policy snap-in are available in Windows Server 2008 R2 and Windows 7 Professional, Windows 7 Ultimate, and Windows 7 Enterprise. For more information, see [http://go.microsoft.com/fwlink/?LinkId=139815](http://go.microsoft.com/fwlink/?LinkId=139815).