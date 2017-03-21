---
title: Workflow actions quick reference (SharePoint 2013 Workflow platform)
ms.prod: SHAREPOINTDESIGNER
ms.assetid: eb3434e5-bc75-4474-8873-4980062fd29c
---



# Workflow actions quick reference (SharePoint 2013 Workflow platform)
This reference lists the workflow actions that are supported in the current build of SharePoint Designer 2013, in addition to those that are not available. 
## Workflow actions in SharePoint Designer 2013
<a name="bkm_WorkflowActions"> </a>

The following is a reference for workflow actions available for the SharePoint 2013 Workflow platform. In addition to the SharePoint 2013 Workflow platform, SharePoint Designer 2013 also supports the SharePoint 2010 Workflow platform. To view workflow actions for the 2010 platform, see  [Workflow actions quick reference (SharePoint 2010 Workflow platform)](workflow-actions-quick-reference-sharepoint-2010-workflow-platform.md)
  
    
    

### Core actions
<a name="bkm_CoreActions"> </a>

Core actions are those that are most commonly performed, and they are grouped together for easy access. 
  
    
    

**Table 1. Core actions reference**


|**Action**|**Description**|
|:-----|:-----|
|Add a Comment |Enables you to leave informative comments in the workflow designer for reference purposes. This is especially helpful when there are other users collaborating on the workflow. |
|Add Time to Date |Adds a specific time in minutes, hours, days, or months to a date (Year is not supported), and stores the output value as a variable. The date can be a current data, specific date, or a lookup. The 'Current Date' value returns UTC midnight. |
|Build Dictionary |Builds a Dictionary variable of key/value pairs. > [!NOTE]  > The Dictionary uses JSON notation to store data.           For more information on the Dictionary variable, see  [Understanding Dictionary actions in SharePoint Designer 2013](understanding-dictionary-actions-in-sharepoint-designer-2013.md)|
|Call HTTP Web Service |Functions as a method call to an HTTP web service and returns data using the JSON format. Basic authentication is supported through the RequestHeader. For more information on the Dictionary variable, see  [Understanding Dictionary actions in SharePoint Designer 2013](understanding-dictionary-actions-in-sharepoint-designer-2013.md)|
|Count Items in a Dictionary |Returns a count of the number of items in a specified dictionary. |
|Do Calculation |Performs an arithmetic calculation and stores the output value in a variable. > [!NOTE]  > For SharePoint 2013, this action supports only the **Double** numeric type. Integers are not supported. Use of the "+" operator (concatenation) for strings is not supported.          |
|Get an Item from a Dictionary |Returns a particular item from a dictionary variable. |
|Log to History List |Writes a message from a list of predefined message items to the workflow history list. |
|Pause for Duration |Causes a workflow to pause executing for a specified time interval, in days, hours, and minutes. |
|Pause Until Date |Causes a workflow to pause executing until a specified date and time. |
|Send an Email |Automatically sends an email message that contains a predetermined message to a user or group when a specified workflow event occurs. > [!IMPORTANT]  > If the site is not added to the Trusted Sites list then emails are routed to the Outlook Junk folder.           |
|Set Time Portion of Date/Time Field |Creates a timestamp, and stores the output value in a variable. You can set the time in hours and minutes and add a current date, specific date, or lookup. |
|Set Workflow Status |Sets the status of the workflow. |
|Set Workflow Variable |Sets a workflow variable to a value. You can also use this action when you want the workflow to assign data to a variable. |
|Go to Stage |Specifies the next stage to which flow control should be handed. |
   

### Coordination actions
<a name="bkm_CoreActions"> </a>

Coordination actions are used to invoke a workflow based on the SharePoint 2010 Workflow platform. For more information on Coordination actions, see  [Understanding Coordination actions in SharePoint Designer 2013](understanding-coordination-actions-in-sharepoint-designer-2013.md)
  
    
    

**Table2. Coordination actions reference**


|**Action**|**Description**|
|:-----|:-----|
|Start a List Workflow |Starts a List workflow based on the SharePoint 2010 Workflow platform. > [!NOTE]  >  The Start a list workflow has the following issues:>  The 'Assignments' type field cannot be used as a parameter when the 2010 workflow has a TaskProcess action in it.>  When multiple calls are made to the same 2010 workflow the result will be multiple data sources in the 2013 workflow lookup functionality. These data sources are all the same.>  Variable names in 2013 cannot contain special characters such as '?' and '#'. If a 2010 workflow contains special characters then they will be converted to hexadecimal code in the 2013 workflow.          |
|Start a Site Workflow |Starts a Site workflow based on the SharePoint 2010 Workflow platform.. > [!NOTE]  >  The Start a list workflow has the following issues:>  The 'Assignments' type field cannot be used as a parameter when the 2010 workflow has a TaskProcess action in it.>  When multiple calls are made to the same 2010 workflow the result will be multiple data sources in the 2013 workflow lookup functionality. These data sources are all the same.>  Variable names in 2013 cannot contain special characters such as '?' and '#'. If a 2010 workflow contains special characters then they will be converted to hexadecimal code in the 2013 workflow.          |
   

### List actions
<a name="bkm_ListActions"> </a>

List actions group together actions that are used to manipulate lists and list items. 
  
    
    

**Table3. List actions reference**


|**Action**|**Description**|
|:-----|:-----|
|Check In Item |Checks in an item that is checked out. You can check in items only from a document library. > [!CAUTION]  > The workflow crashes if you try to check in an item that is not checked out.           |
|Check Out Item |Checks out an item. The workflow verifies whether the item is checked in before it checks out a document. You can check out items only from a library in your site. > [!CAUTION]  > The workflow crashes if you try to check out an item that is not checked in.           |
|Copy Document |Copies a document from the current list to a different Document Library list. |
|Create List Item |Creates a new list item in the list that you specify. You can supply the fields and values in the new item. You can use this action whenever you want a new item to be created with specific information. |
|Delete Item |Deletes an item. > [!NOTE]  > This action is terminated on the computer running the Workflow Manager workflow engine and throws a **System.InvalidOperationException** exception. There is no workaround.          |
|Discard Check Out Item |Discards the changes and checks the item back in if an item is checked out and changes have been made to it. > [!CAUTION]  > The workflow crashes if you try to check in an item that is not checked out.           |
|Set Field in Current Item |Sets a specified field in the current item to a specified value. > [!NOTE]  > If you need the workflow to pause until the value of the field has changed, use the **Wait for Event in List Item** action instead of this action.          |
|Translate Document |Translates a document into a particular language > [!NOTE]  > Requires a preconfigured Machine Translation Service Application.           |
|Update List Item |Updates a list item. You can specify the fields and the new values in those fields. |
|Wait for Event in List Item |[Enhanced version of Office 2010 action.] Pauses the current instance of the workflow to await a specified list item event. This action listens for two events: **ItemUpdated** and **ItemAdded**. |
|Wait for Field Change in Current Item |Waits for a field on the current item to equal a particular value. |
   

### Project actions
<a name="bkm_ProjectActions"> </a>

Project actions support the integration of Microsoft Project. They are used to build Project-based workflows. All of the Project actions are new in SharePoint Designer 2013. 
  
    
    

**Table4. Project actions reference**


|**Action**|**Description**|
|:-----|:-----|
|Create Project from Current Item |Takes the current item and creates a new project in the SharePoint farm PWA site. Using App Steps with this action is not supported in Project Online. |
|Set Project Field |Sets a value for a particular field on Project Server. > [!NOTE]  > This action requires the project to be checked in first. If the project is not checked in, the workflow will be terminated and users cannot open that project in Project Web App.           |
|Set Project Stage Status |Sets the status of the Project Stage. > [!NOTE]  > An exception occurs when a current project is checked out.           |
|Set status field in idea list |Updates the status on the original list item that is associated to the current project. |
|Wait for Project Event |Waits for a particular Project Event. |
   

### Task actions
<a name="bkm_TaskActions"> </a>

Task actions provide the ability to invoke a workflow based on the SharePoint 2010 Workflow platform from within a workflow based on the SharePoint 2013 Workflow platform. 
  
    
    

**Table 5. Task actions reference**


|**Action**|**Description**|
|:-----|:-----|
|Assign a Task |Assigns a workflow task to a user and establishes a due date for completion of the task. |
|Start a Task Process |Creates tasks on multiple users and enables the tasks to be taken through a customized process. |
   

### Utility actions
<a name="bkm_UtilityActions"> </a>

Utility actions are actions that manipulate strings or find the interval between dates. 
  
    
    

**Table 6. Utility actions reference**


|**Action**|**Description**|
|:-----|:-----|
|Extract Substring from End of String |Copies a specified number of characters starting from the end of a string and stores the output in a variable. |
|Extract Substring from Index of String |Copies a substring starting at a specified index in the string and places the value in a variable. > [!NOTE]  > Be aware that although the index value in Microsoft SharePoint Designer 2013 is zero-based, values in SharePoint Designer 2010 were indexed starting at 1.           |
|Extract Substring from Start of String |Copies a specified number of characters beginning at the start of a string and stores the output in a variable. |
|Extract Substring of String from Index with Length |Copies out a substring comprising a specified number of characters, starting at a specified index in the string, and places the value in a variable. > [!NOTE]  > Be aware that although the index value in Microsoft SharePoint Designer 2013 is zero-based, values in SharePoint Designer 2010 were indexed starting at 1.           |
|Find Interval Between Dates |Calculates the time interval in minutes, hours, or days between two dates and stores the output in a variable. |
|Trim String |Removes white spaces from the beginning and end of a string. |
|Find Substring in String |Finds a particular substring inside of a string and returns the index of the substrings's starting position. |
|Replace Substring in String |Replaces a particular substring with another substring. |
|Trim String |Removes white spaces from the beginning and end of a string. |
   

## Workflow actions that are deprecated in SharePoint 2013
<a name="bkm_NotAvailable"> </a>

For a list of actions from SharePoint 2010 that are deprecated and will not appear in SharePoint 2013, see  [Workflow actions available using the workflow interop bridge](workflow-actions-available-using-the-workflow-interop-bridge.md). 
  
    
    

## Additional resources
<a name="bkm_addlresource"> </a>


-  [Workflow actions and activities reference for SharePoint 2013](workflow-actions-and-activities-reference-for-sharepoint-2013.md)
    
  
-  [SharePoint 2013 workflow fundamentals](sharepoint-2013-workflow-fundamentals.md)
    
  
-  [Get started with workflows in SharePoint 2013](get-started-with-workflows-in-sharepoint-2013.md)
    
  
-  [Workflow development in SharePoint Designer and Visio](workflow-development-in-sharepoint-designer-and-visio.md)
    
  
