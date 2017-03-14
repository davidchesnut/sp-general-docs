---
title: Workflow activity classes in SharePoint 2013
ms.prod: SHAREPOINT
ms.assetid: 70d5ca8d-520d-40a9-b24e-52bb31bd6c22
---


# Workflow activity classes in SharePoint 2013
Provides a summary of the SharePoint workflow activity classes that are available in SharePoint 2013. 
The palette of activity classes has been revised for SharePoint 2013. Table 1 lists the current catalog of 49 available activities grouped by their respective activity categories. 
  
    
    


> [!NOTE]  
> In future releases, the activities listed in this table will provide links to the API reference documentation for their respective managed classes. 
  
    
    


## Workflow activity classes available in SharePoint 2013
<a name="bk_wfactivityclasses"> </a>


**Table 1. Workflow activity classes**

||||
|:-----|:-----|:-----|
|**Activity**|**Category**|**Description**|
|CreatedBy |Condition |Returns whether current item was created by specified user. |
|CreatedInRange |Condition |Returns whether current item was created in specified date range. |
|ModifiedBy |Condition |Returns whether current item was modified by specified user. |
|ModifiedInRange |Condition |Returns whether current item was modified in specified date range. |
|WordsInTitle |Condition |Returns whether specified keywords are present in the title of the current item. |
|WorkflowInterop |Coordination |Starts a SharePoint 2010 workflow (Windows Workflow Foundation 3.5). |
|WaitForCustomEvent |Event |Waits for a custom event to be sent in to the workflow. |
|WaitForFieldChange |Event |Waits for specified field to change to specified value on the specified list item. |
|WaitForItemEvent |Event |Waits for specified event to happen on specified list item. |
|CheckInItem |List |Checks in the specified list item. |
|CheckOutItem |List |Checks out the specified list item. |
|CopyItem |List |Copies the specified file item to the specified document library. Does not apply to non-file-list items. |
|CreateListItem |List |Creates a list item. |
|DeleteListItem |List |Deletes a list item. |
|LookupSPList |List |Returns information about the list that corresponds to the specified list ID. |
|LookupSPListItem |List |Returns properties of the specified list item. |
|LookupSPListItemBooleanProperty |List |Returns value of specified list item property as **Boolean**. |
|LookupSPListItemDateTimeProperty |List |Returns value of specified list item property as **DateTime**. |
|LookupSPListItemDoubleProperty |List |Returns value of specified list item property as **Double**. |
|LookupSPListItemDynamicValueProperty |List |Returns value of specified list item property as **DynamicValue**. |
|LookupSPListItemGuid |List |Returns GUID property of the first list item that matches specified filter criteria of property name and property value. |
|LookupSPListItemInt32Property |List |Returns value of specified list item property as **Int32**. |
|LookupSPListItemProperty |List |Returns value of specified list item property as **Object**. |
|LookupSPListItemStringProperty |List |Returns value of specified list item property as **String**. |
|LookupSPListProperty |List |Returns list properties as **DynamicValue**. |
|UndoCheckOutItem |List |Undoes checkout of the specified list item. |
|UpdateListItem |List |Updates a list item. |
|CompositeTask |Task |Runs a task process - assigns multiple tasks to multiple people in series or parallel, waits for tasks to complete, and calculates aggregate outcome. |
|SingleTask |Task |Runs a simple task process - assigns a single task to a single person or a group, waits for the task to complete. |
|ExpandGroupToUsers |User |Returns a collection of LoginNames of users who are members of a specified SharePoint group principal. |
|IsValidUser |User |Checks whether specified User Principal ID represents a valid SharePoint user. |
|LookupSPGroup |User |Returns information about an SP group that corresponds to the specified principal id. |
|LookupSPGroupMembers |User |Returns collection of information about each member of a group. |
|LookupSPPrincipal |User |Returns information about an SP Principal (Principal represents a user or a group in SharePoint that can be assigned permissions). |
|LookupSPPrincipalId |User |Returns Principal ID that corresponds to a specified user name. |
|LookupSPPrincipalProperty |User |Returns value of a specified property of a specified SP Principal. |
|LookupSPUser |User |Returns information about a user that corresponds to the specified principal ID. |
|LookupSPUserProperty |User |Returns value of a specified property of the user that corresponds to specified SP Principal. |
|Email |Utility |Sends an email message to SharePoint site users. |
|GetCurrentItemGuid |Utility |Returns GUID property of SharePoint List Item on which the workflow instance is running. |
|GetCurrentListId |Utility |Returns ID property of SharePoint list on which the workflow instance is running. |
|GetHistoryListId |Utility |Returns ID of the history list of a workflow instance, if a history list is specified for the workflow association. |
|GetTaskListId |Utility |Returns ID of the task list of a workflow instance, if a history list is specified for the workflow association. |
|LookupWorkflowContextProperty |Utility |Returns value of specified workflow context property. |
|SetField |Utility |Sets a field on current item. |
|SetWorkflowStatus |Utility |Sets specified text as status on specified field on current list item. Allows the workflow to set the value of any string field of a list item as "workflow status." |
|TranslateDocument |Utility |Creates a translated copy of specified document in a specified document library using SharePoint Translation Services. |
|WebUri |Utility |Returns absolute URI of the SP web that contains the workflow. |
|WriteToHistory |Utility |Writes specified comment to history list. |
   

## Additional resources
<a name="bkm_addlresource"> </a>


-  [Workflow actions and activities reference for SharePoint 2013](workflow-actions-and-activities-reference-for-sharepoint-2013.md)
    
  
-  [Develop SharePoint 2013 workflows using Visual Studio](develop-sharepoint-2013-workflows-using-visual-studio.md)
    
  
-  [Set up and configure SharePoint 2013 Workflow Manager](set-up-and-configure-sharepoint-2013-workflow-manager.md)
    
  

