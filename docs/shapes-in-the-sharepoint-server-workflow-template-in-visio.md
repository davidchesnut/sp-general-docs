---
title: Shapes in the SharePoint Server workflow template in Visio
ms.prod: SHAREPOINT
ms.assetid: f35bdf5d-c102-4e2d-8a23-1d2df17155b9
---



# Shapes in the SharePoint Server workflow template in Visio
Learn about the shapes in the SharePoint 2013 Workflow template in Visio 2013. 
 **Last modified:** September 17, 2015
  
    
    

 * **Applies to:** SharePoint Server 2013 | Visio 2013* 
## Introduction
<a name="VSSPD_Shapes_Intro"> </a>

This article lists the shapes contained in the SharePoint 2013 Workflow template in Visio 2013 and in the Visual Designer in SharePoint Designer 2013. When the template is opened, also opens the SharePoint 2013 Workflow Actions, SharePoint 2013 Workflow Conditions, and SharePoint 2013 Workflow Terminators stencils. Many of the shapes listed in the stencils correspond to specific actions, conditions, or other logical constructs in the Declarative Designer for building workflows in SharePoint Designer 2013. 
  
    
    

> [!Important]  
> The following is a reference for workflow actions that are supported in SharePoint Designer 2013. Most of these actions are available in SharePoint Designer 2010, although one of those (Wait for List Item Event) has been revised and enhanced in the present version. Twelve new actions are introduced in the present version, and 25 actions have been removed. (To see a list of actions, conditions, and blocks that have been removed, see  [Workflow actions available using the workflow interop bridge](workflow-actions-available-using-the-workflow-interop-bridge.md).) 
  
    
    


## Action shapes
<a name="VSSDP_Actions"> </a>

The following table shows a list of all the shapes that are contained in the SharePoint 2013 Actions stencil in the SharePoint 2013 Workflow template in Visio 2013. 
  
    
    

> [!Note]  
> Each shape listed in the following table will have the properties listed and a  **Properties** property.
  
    
    



|**Shape in Visio 2013 and SharePoint Designer 2013 Visual Designer **|**Action in the SharePoint Designer 2013 Declarative Designer **|**Properties in SharePoint Designer 2013 Visual Designer **|**Description **|
|:-----|:-----|:-----|:-----|
|Add a Comment |**Add a Comment**|**Comment**|Enables you to leave informative comments in the workflow designer for reference purposes. This is especially helpful when there are other users collaborating on the workflow. |
|Add Time to Date |**Add Time to Date**|**Months** **Days** **Hours** **Minutes** **Date** **Output**|Adds a specific time in minutes, hours, days, or months to a date, and stores the output value as a variable. The date can be a current data, specific date, or a lookup. The 'Current Date' value returns UTC midnight. |
|Assign a Task |**Assign a Task**|**Task Settings** **Task Outcome** **Task Item ID**|Assigns a workflow task to a user and establishes a due date for completion of the task. |
|Call HTTP web service |**Call HTTP Web Service**|**HTTP Request** **Parameters** **Response Content Variable** **Response Header Variable** **Response Code Variable**|Functions as a method call to a HTTP web service. > [!Note]  > The current build supports SharePoint calls only to  **anonymous** HTTP services and only using **string** parameters and return types. Also, we do not support composite XML elements. Note, too, that we currently support classic ASMX only and do not provide support for the WCG service.          |
|Check In Item |**Check In Item**|**Item** **Comment**|Checks in an item that is checked out. You can check in items only from a document library. > [!Caution]  > The workflow crashes if you try to check in an item that is not checked out.           |
|Check Out Item |**Check Out Item**|**Item**|Checks out an item. The workflow verifies whether the item is checked in before it checks out a document. You can check out items only from a library in your site. > [!Caution]  > The workflow crashes if you try to check out an item that is not checked in.           |
|Copy document |**Copy Document**|**Document** **Library**|Copies a document from the current list to a different Document Library list. |
|Count items in dictionary |**Count Items in a Dictionary**|**Dictionary** **Output Variable**|Counts the number of items in a dictionary variable. |
|Create a project from current item |**Create Project From Current Item**|**Enterprise Project Type**|Takes the current item and creates a new project in the SharePoint farm PWA site. |
|Create List Item |**Create List Item**|**Item** **Output Variable**|Creates a new list item in the list that you specify. You can supply the fields and values in the new item. You can use this action whenever you want a new item to be created with specific information. |
|Delete Item |**Delete Item**|**Item**|Deletes an item. > [!Note]  > This action is terminated on the computer running the Workflow Manager workflow engine and throws a  **System.InvalidOperationException** exception. There is no workaround.          |
|Discard Check Out |**Discard Check Out Item**|**Item**|Discards the changes and checks the item back in if an item is checked out and changes have been made to it. > [!Caution]  > The workflow crashes if you try to check in an item that is not checked out.           |
|Do Calculation |**Do Calculation**|**LeftOperand** **Operator** **RightOperand** **To**|Performs an arithmetic calculation and stores the output value in a variable. > [!Note]  > For SharePoint 2013, this action supports only the  **Double** numeric type. Integers are not supported. Use of the "+" operator (concatenation) for strings is not supported.          |
|Extract Substring from End of String |**Extract Substring from End of String**|**Number of Characters** **String** **Output**|Copies a specified number of characters starting from the end of a string and stores the output in a variable. |
|Extract Substring from Index of String |**Extract Substring from Index of String**|**String** **Index** **Output**|Copies a substring starting at a specified index in the string and places the value in a variable. > [!Note]  > Be aware that although the index value in the present Technical Preview build of SharePoint Designer is zero-based, values in SharePoint Designer 2010 were indexed starting at 1.           |
|Extract Substring from Start of String |**Extract Substring from Start of String**|**Number of Characters** **String** **Output**|Copies a specified number of characters beginning at the start of a string and stores the output in a variable. |
|Extract Substring of String from Index with Length |**Extract Substring of String from Index with Length**|**String** **Index** **Number of Characters** **Output**|Copies out a substring comprising a specified number of characters, starting at a specified index in the string, and places the value in a variable. > [!Note]  > Be aware that although the index value in the present Technical Preview build of SharePoint Designer is zero-based, values in SharePoint Designer 2010 were indexed starting at 1.           |
|Find Interval Between Dates |**Find Interval Between Dates**|**Units** **Start Date** **End Date** **Output**|Calculates the time interval in minutes, hours, or days between two dates and stores the output in a variable. |
|Find substring in string |**Find Substring in String**|**Substring** **String** **Output**|Finds a particular substring inside of a string and returns the index of the substrings's starting position. |
|Get item from dictionary |**Get Item From Dictionary**|**Item Name of Path** **Dictionary** **Output Variable**|Returns a particular item from a dictionary variable. |
|Log to History List |**Log to History List**|**Message**|Writes a message from a list of predefined message items to the workflow history list. |
|Pause for Duration |**Pause for Duration**|**Days** **Hours** **Minutes**|Causes a workflow to pause executing for a specified time interval, in days, hours, and minutes. |
|Pause until Date |**Pause Until Date**|**Date**|Causes a workflow to pause executing until a specified date and time. |
|Replace substring in String |**Replace Substring in String**|**Search String** **Replace String** **String** **Output**|Replaces a particular substring with another substring. |
|Send an Email |**Send an email**|**Email**|Automatically sends an email message that contains a predetermined message to a user or group when a specified workflow event occurs. > [!Important]  > If the site is not added to the Trusted Sites list then emails are routed to the Outlook Junk folder.           |
|Set field in Current Item |**Set Field in Current Item**|**Field** **Value**|Sets a field in the current item to a value. |
|Set Time Portion of Date/Time Field |**Set Time Portion of Date/Time Field**|**Hours** **Minutes** **Date** **Output**|Creates a timestamp, and stores the output value in a variable. You can set the time in hours and minutes and add a current date, specific date, or lookup. |
|Set workflow status |**Set Workflow Status**|**Status**|Sets the status of the workflow. |
|Set Workflow Variable |**Set Workflow Variable**|**Variable** **Value**|Sets a workflow variable to a value. You can also use this action when you want the workflow to assign data to a variable. |
|Start a list workflow |**Start a List Workflow**|**Association Name** **Inputs** **Item**|Starts a SharePoint 2010 List workflow. > [!Note]  >  The Start a list workflow has the following issues:>  The 'Assignments' type field cannot be used as a parameter when the 2010 workflow has a TaskProcess action in it.>  When multiple calls are made to the same 2010 workflow the result will be multiple data sources in the 2013 workflow lookup functionality. These data sources are all the same.>  Variable names in 2013 cannot contain special characters such as '?' and '#'. If a 2010 workflow contains special characters then they will be converted to hexadecimal code in the 2013 workflow.          |
|Start a site workflow |**Start a Site Workflow**|**Association name** **Parameters**|Starts a SharePoint 2010 Site Workflow. > [!Note]  >  The Start a list workflow has the following issues:>  The 'Assignments' type field cannot be used as a parameter when the 2010 workflow has a TaskProcess action in it.>  When multiple calls are made to the same 2010 workflow the result will be multiple data sources in the 2013 workflow lookup functionality. These data sources are all the same.>  Variable names in 2013 cannot contain special characters such as '?' and '#'. If a 2010 workflow contains special characters then they will be converted to hexadecimal code in the 2013 workflow.          |
|Start a task process |**Start a Task Process**|**Process Settings** Process Outcome|Creates tasks on multiple users and enables the tasks to be taken through a customized process. |
|Translate document |**Translate Document**|**Document** **Language** **Document Library**|Translates a document into a particular language > [!Note]  > Requires a preconfigured Machine Translation Service Application.           |
|Trim String |**Trim String**|**String** **Output**|Removes white spaces from the beginning and end of a string. |
|Update List Item |**Update List Item**|**Item**|Updates a list item. You can specify the fields and the new values in those fields. |
|Wait for Event in List Item |**Wait for Event in List Item**|**Event** **Related Item**|[Enhanced version of Office 2010 action.] Pauses the current instance of the workflow to await a specified list item event. This action listens for two events:  **ItemUpdated** and **ItemAdded**. |
|Wait for field change |**Wait for Field Change**|**Field** **Value**|Waits for a field on the current item to equal a particular value. |
|Set Project Field |**Set Project Field**|**Field** **Value**|Sets a value for a particular field on Project Server. > [!Note]  > This action requires the project to be checked in first. If the project is not checked in, the workflow will be terminated and users cannot open that project in Project Web App.           |
|Set Project Stage Status |**Set Project Stage Status**|**Stage Status** **Stage Information**|Sets the status of the Project Stage. > [!Note]  > An exception occurs when a current project is checked out.           |
|Set status field in idea list |**Set Status Field in Idea List**|**Status**|Updates the status on the original list item that is associated to the current project. |
|Wait for Project Event |**Wait for Project Event**|**Event Name**|Waits for a particular Project Event. |
   

## Condition shapes
<a name="VSSPD_Conditions"> </a>

The following table shows a list of all the shapes that are contained in the SharePoint 2013 Conditions stencil in the SharePoint 2013 Workflow template. 
  
    
    


|**Shape in Visio 2013 and SharePoint Designer 2013 Visual Designer **|**Action in the SharePoint Designer 2013 Declarative Designer **|**Properties in SharePoint Designer 2013 Visual Designer **|**Description **|
|:-----|:-----|:-----|:-----|
|If Any Value Equals Value |**If any value equals value**|**Value** **Operand** **Value**|Compares two values. You can specify whether the values should be equal or not equal. |
|Person is a Valid SharePoint User |**Person is a valid SharePoint user**|**User**|Checks to see whether a specific user is a registered user or a member of a group on the SharePoint site. |
|Skip Project Stage |**Skip Project Stage**|NA |This condition checks to see if the skip to stage feature has been activated on the server for the current workflow instance. |
   

## Terminator shapes
<a name="VSSPD_Terminators"> </a>

The following table shows a list of all the shapes that are contained in the SharePoint 2013 Terminators stencil in the SharePoint 2013 Workflow template. 
  
    
    


|**Shape in Visio 2013 and SharePoint Designer 2013 Visual Designer **|**Action in the SharePoint Designer 2013 Declarative Designer **|**Properties in SharePoint Designer 2013 Visual Designer **|**Description **|
|:-----|:-----|:-----|:-----|
|Start |NA |NA |Begins the workflow. Every SharePoint 2013 workflow diagram must have only one Start shape. |
|Stage |**Stage**|NA |Contains any number of shapes and may include branching. All actions in the workflow must be contained by a stage. Stage shapes are visualized by using container shapes. A Stage shape requires that an Enter and an Exit shape be added to the edges of the container to define the paths in and out of the stage. For more information, see the section titled "Stages, loops, and steps" in the article  [Workflow development in SharePoint Designer and Visio](workflow-development-in-sharepoint-designer-and-visio.md). |
|Step |**Step**|NA |Represents a grouped series of sequential actions. Steps must be contained by a stage. A step shape must also have an Enter and Exit shape, which are added when the shape is dropped onto the canvas. For more information, see the section titled "Stages, loops, and steps" in the article  [Workflow development in SharePoint Designer and Visio](workflow-development-in-sharepoint-designer-and-visio.md). |
|Simple Stage |**Stage**|NA |Adds new stages to the top level of the workflow when in Stage View in Visio 2013. |
|Loop n Times |**Loop n Times**|**Loop Count**|Defines a series of connected shapes that will execute as a loop, returning from the last shape in the series to the first, until the loop has executed a specified amount of times. Like stages, loops are represented by a container shape that includes an Enter and Exit shape. For more information, see the section titled "Stages, loops, and steps" in the article  [Workflow development in SharePoint Designer and Visio](workflow-development-in-sharepoint-designer-and-visio.md). |
|Loop with condition |**Loop with Condition**|**Loop Count**|Loops until a specific condition is met. |
|Start Parallel Action |**Parallel Block**|NA ||
|End Parallel Action |**Parallel Block**|NA ||
   

## Additional resources
<a name="VSSPD_Additional"> </a>


-  [Workflow development in SharePoint Designer and Visio](workflow-development-in-sharepoint-designer-and-visio.md)
    
  
-  [Workflow actions quick reference (SharePoint 2013 Workflow platform)](workflow-actions-quick-reference-sharepoint-2013-workflow-platform.md)
    
  
-  [SharePoint Workflow template shapes guide](http://office.microsoft.com/en-us/visio-help/sharepoint-workflow-template-shapes-guide-HA101903894.aspx)
    
  
-  [SharePoint Developer Center](http://msdn.microsoft.com/en-us/sharepoint/default.aspx)
    
  
-  [Visio Developer Center](http://msdn.microsoft.com/en-us/office/aa905478)
    
  
