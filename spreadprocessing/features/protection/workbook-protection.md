---
title: Workbook Protection
page_title: Workbook Protection | UI for WinForms Documentation
description: Workbook Protection
slug: winforms/spreadprocessing/features/protection/workbook-protection
tags: workbook,protection
published: True
position: 0
previous_url: spreadprocessing-features-protection-workbook
---

# Workbook Protection



In certain cases when you present a workbook to the users, you may want to prevent them from adding, removing, renaming or reordering sheets. This is where workbook protection comes at hand. The feature allows you to lock the structure of your workbook with or without a password. You can always unprotect the workbook as needed, however, you can also let the user remove the protection by entering the correct password. Once protection is removed, the user can add, remove, rename and reorder sheets.
      

Note that workbook protection in the context of the document model is an entirely user-oriented feature. When a workbook is protected, the UI will not allow the user to add, delete, reorder or rename sheets. That said, you as a developer have full access to the sheets collection of the workbook and can perform any modifications using code behind.
      

## How to Protect a Workbook

To protect a workbook, use the __Protect(string)__ method of the __Workbook__ class. The method takes one string parameter that specifies the password used for enforcing protection.
        

__Example 1__ illustrates how to create a workbook from scratch and protect it using a password:
       
#### Example 1: Password-protect a Workbook


{{source=..\SamplesCS\RadSpreadProcessing\Features\Protection\RadSpreadProcessingWorkbookProtection.cs region=radspreadprocessing-features-protection-workbook_0}} 
{{source=..\SamplesVB\RadSpreadProcessing\Features\Protection\RadSpreadProcessingWorkbookProtection.vb region=radspreadprocessing-features-protection-workbook_0}} 

````C#
Workbook workbook = new Workbook();
workbook.Worksheets.Add();
workbook.Protect("telerik");

````
````VB.NET
Dim workbook As New Workbook()
workbook.Worksheets.Add()
workbook.Protect("telerik")

````

{{endregion}} 

## How to Unprotect a Workbook

Use the __Unprotect(string)__ method of the __Workbook__ class to remove the workbook protection. The method returns a Boolean value that indicates whether the workbook is successfully unprotected.
        

__Example 2__ demonstrates how to unprotect a workbook:
      
#### Example 2: Unprotect a Workbook

{{source=..\SamplesCS\RadSpreadProcessing\Features\Protection\RadSpreadProcessingWorkbookProtection.cs region=radspreadprocessing-features-protection-workbook_1}} 
{{source=..\SamplesVB\RadSpreadProcessing\Features\Protection\RadSpreadProcessingWorkbookProtection.vb region=radspreadprocessing-features-protection-workbook_1}} 

````C#
Workbook workbook = new Workbook();
workbook.Worksheets.Add();
workbook.Protect("telerik");
workbook.Unprotect("telerik");

````
````VB.NET
Dim workbook As New Workbook()
workbook.Worksheets.Add()
workbook.Protect("telerik")
workbook.Unprotect("telerik")

````

{{endregion}} 

# See Also

 * [Whats is a Workbook?]({%slug winforms/spreadprocessing/working-with-workbooks/whats-is-a-workbook?%})

 * [Worksheet Protection]({%slug winforms/spreadprocessing/features/protection/worksheet-protection%})
