---
title: BDC model schema reference for SharePoint 2013
ms.prod: SHAREPOINT
ms.assetid: 979a5ffc-f033-4e72-b2d1-11d8cb1b294a
---



# BDC model schema reference for SharePoint 2013
Contains reference documentation for the BDC model schema (BDCMetadata.xsd), which you can use to create external content types in SharePoint 2013. 
 **Last modified:** December 07, 2015
  
    
    

 * **Applies to:** SharePoint Foundation 2013 | SharePoint Server 2013* 
 [BDCMetadata.xsd](http://schemas.microsoft.com/windows/2007/BusinessDataCatalog)
  
    
    


## AccessControlEntry element
<a name="bkmk_AccessControlEntry"> </a>

Contains an access control entry (ACE) that specifies access rights for the parent element. 
  
    
    
See  [Business Connectivity Services security overview](http://technet.microsoft.com/en-us/library/ee661734%28office.14%29.aspx) to learn more about the Business Connectivity Services and security.
  
    
    
 **Namespace:** `http://schemas.microsoft.com/windows/2007/BusinessDataCatalog`
  
    
    
 **Schema:** BDCMetadata
  
    
    



```XML

<AccessControlEntry Principal = "String"> </AccessControlEntry>
```

The following sections describe attributes, child elements, and parent elements. 
  
    
    
 **Attributes**
  
    
    


|**Attribute **|**Description **|
|:-----|:-----|
|Principal |Required. The name of the security principal that has this ACE. Attribute type:  **String**|
   
 **Child elements**
  
    
    


|**Element **|**Description **|
|:-----|:-----|
| [Right Element in AccessControlEntry (BDCMetadata Schema)](http://msdn.microsoft.com/library/a2e4bd6c-2306-b657-7290-cc9c9b262911%28Office.15%29.aspx)|A  **Right** element that specifies the permissions available to the security principal.|
   
 **Parent element**
  
    
    


|**Element **|**Description **|
|:-----|:-----|
| [AccessControlList Element (BDCMetadata Schema)](http://msdn.microsoft.com/library/b7f97740-5d2c-f91a-1028-10e2890d4a99%28Office.15%29.aspx)|The access control list (ACL) that contains this ACE. |
   

## AccessControlList element
<a name="bkmk_AccessControlList"> </a>

Specifies an access control list (ACL) for the parent element. 
  
    
    
 **Namespace:** `http://schemas.microsoft.com/windows/2007/BusinessDataCatalog`
  
    
    
 **Schema:** BDCMetadata
  
    
    



```XML
<AccessControlList></AccessControlList>
```

The following sections describe attributes, child elements, and parent elements. 
  
    
    
 **Attributes**
  
    
    
None 
  
    
    
 **Child elements**
  
    
    


|**Element **|**Description **|
|:-----|:-----|
| [AccessControlEntry Element in AccessControlList (BDCMetadata Schema)](http://msdn.microsoft.com/library/85e24489-0a6b-dfda-fb03-474fe7b0d947%28Office.15%29.aspx)|An access control entry (ACE). |
   
 **Parent element**
  
    
    


|**Element **|**Description **|
|:-----|:-----|
| [Model Element (BDCMetadata Schema)](http://msdn.microsoft.com/library/d7823090-b20d-2c96-c359-081c055d0e65%28Office.15%29.aspx)|A model that contains external content types in a business application. |
| [LobSystem Element in LobSystems (BDCMetadata Schema)](http://msdn.microsoft.com/library/d4e58d7d-a628-8093-97fe-7c3136e8f6f2%28Office.15%29.aspx)|The LobSystems contained inside the model. |
| [Entity Element in Entities (BDCMetadata Schema)](http://msdn.microsoft.com/library/a8455bc4-12d8-85e0-146e-5d1d8579e1f5%28Office.15%29.aspx)|An external content type. |
| [Method Element in Methods (BDCMetadata Schema)](http://msdn.microsoft.com/library/70e87a9e-4959-0a7b-3f37-ddec36473ff4%28Office.15%29.aspx)|A method of an external content type. |
| [Association Element in MethodInstances (BDCMetadata Schema)](http://msdn.microsoft.com/library/9659a1f5-1b12-03ef-f9e3-5c9904cc5dd0%28Office.15%29.aspx)|An association. |
| [MethodInstance Element in MethodInstances (BDCMetadata Schema)](http://msdn.microsoft.com/library/577ff9d0-706b-be7d-af5b-883e137cada8%28Office.15%29.aspx)|A method instance of an external content type. |
   

## Action element
<a name="bkmk_Action"> </a>

Specifies an action supported by an external content type. 
  
    
    
 **Namespace:** `http://schemas.microsoft.com/windows/2007/BusinessDataCatalog`
  
    
    
 **Schema:** BDCMetadata
  
    
    
Actions bridge the gap between SharePoint 2013 and Office 2013 and an external system's user interface by providing a link back to the external system. 
  
    
    
By default, the Business Data Connectivity (BDC) service provides actions such as  **View Item**,  **Edit Item**, and  **Delete Item** after you model these operations in the BDC model. In addition to these default actions, you can create actions for other functionality you want to attach to your external content type. For example, you can use actions to perform simple actions, such as sending email messages to a customer from the Customer external content type or opening a customer's home page in a browser.
  
    
    
Actions travel with an external content type. That is, after you define an action for an external content type, the action appears everywhere you display that external content type—whether in an external list or Business Data Web Part or in an External Data column. 
  
    
    



```XML
<Action Position = "Integer" IsOpenedInNewWindow = "Boolean" Url = "String" ImageUrl = "String" Name = "String" DefaultDisplayName = "String" IsCached = "Boolean"> </Action>
```

The following sections describe attributes, child elements, and parent elements. 
  
    
    
 **Attributes**
  
    
    


|**Attribute **|**Description **|
|:-----|:-----|
|**Position**|Required. The suggested position of this action among the other actions of this external content type. Attribute type:  **Integer**|
|**IsOpenedInNewWindow**|Optional. Specifies whether the results of executing an action are presented in a new user interface window. Default value:  **false**Attribute type:  **Boolean**|
|**Url**|Required. The URL to go to when the action is invoked. The URL string is a .NET Framework format string. Each format specifier (for example, {0}) corresponds to an  **Action** parameter.Attribute type:  **String**|
|**ImageUrl**|Optional. The absolute or relative path to the icon image for the action. The icon image should be 16 x 16 pixels. Attribute type:  **String**|
|**Name**|Required. The name of this action. Attribute type:  **String**|
|**DefaultDisplayName**|Optional. The default display name for this action. Attribute type:  **String**|
|**IsCached**|Optional. Specifies whether this action is used frequently. This is used by the BDC client runtime to cache this action. Default value:  **true**Attribute type:  **Boolean**|
   
 **Child elements**
  
    
    


|**Element **|**Description **|
|:-----|:-----|
| [LocalizedDisplayNames Element in MetadataObject (BDCMetadata Schema)](http://msdn.microsoft.com/library/3202aecf-f98f-20cb-1fdd-f3a054cb24aa%28Office.15%29.aspx)|The localized names of the action. |
| [Properties Element in MetadataObject (BDCMetadata Schema)](http://msdn.microsoft.com/library/9901904f-96ee-0cbb-64a9-c2aad9d72128%28Office.15%29.aspx)|The properties of the action. |
| [ActionParameters Element in Action (BDCMetadata Schema)](http://msdn.microsoft.com/library/e14df901-621c-1851-db78-e99fd3cf31ae%28Office.15%29.aspx)|The parameters of the action. |
   
 **Parent element**
  
    
    


|**Element **|**Description **|
|:-----|:-----|
| [Actions Element in Entity (BDCMetadata Schema)](http://msdn.microsoft.com/library/c5a6c08d-a3df-61db-3ce3-1e6837bbf221%28Office.15%29.aspx)|The list of actions of an external content type. |
   

## ActionParameter element
<a name="bkmk_ActionParameter"> </a>

Specifies the parameters of a URL-based action. It defines how to parameterize the URL of an action with  **EntityInstance**-specific data. 
  
    
    
 **Namespace:** `http://schemas.microsoft.com/windows/2007/BusinessDataCatalog`
  
    
    
 **Schema:** BDCMetadata
  
    
    
The URL attribute of a URL-based action can receive parameters by using the  **ActionParameter** element.
  
    
    

> [!Important]  
>  **ActionParameters** can either represent identifier values, or values that correspond to **TypeDescriptors** in a **SpecificFinder** of the **Entity**. The  **ActionParameter** represents an identifier value when the **IdOrdinal** property is present. The value of the property specifies the index of the identifier whose value this **ActionParameter** represents. If the **IdOrdinal** property is not specified, the **ActionParameter** represents a **TypeDescriptor**, and the  **Name** attribute specifies which type descriptor is being represented. The **Name** attribute is specified as a **Dotted Path**. 
  
    
    

The  **ActionParameter** element accepts the following property.
  
    
    

> [!Important]  
> Properties are case-sensitive. 
  
    
    


**Properties**


|**Property **|**Type **|**Description **|**Required. **|**Default Value **|**Limits/Accepted Values **|
|:-----|:-----|:-----|:-----|:-----|:-----|
|**IdOrdinal**|**System.Int32**|Specifies if the  **ActionParameter** represents an identifier instead of a field.|Optional |||
   



```XML
<ActionParameter Index = "Integer" Name = "String" DefaultDisplayName = "String" IsCached = "Boolean"> </ActionParameter>
```

The following sections describe attributes, child elements, and parent elements. 
  
    
    
 **Attributes**
  
    
    


|**Attribute **|**Description **|
|:-----|:-----|
|**Index**|Required. An ordinal attribute that specifies the position of this  **ActionParameter** among other **ActionParameters** in the URL.Attribute type:  **Integer**|
|**Name**|Required. The name of the  **ActionParameter**. Attribute type:  **String**|
|**DefaultDisplayName**|Optional. The default display name for the  **ActionParameter**. Attribute type:  **String**|
|**IsCached**|Optional. Specifies whether this  **ActionParameter** is used frequently. This attribute is used by the BDC client runtime to cache this **Action**. Default value:  **true**Attribute type:  **Boolean**|
   
 **Child elements**
  
    
    


|**Element **|**Description **|
|:-----|:-----|
| [LocalizedDisplayNames Element in MetadataObject (BDCMetadata Schema)](http://msdn.microsoft.com/library/3202aecf-f98f-20cb-1fdd-f3a054cb24aa%28Office.15%29.aspx)|The localized display names for the  **ActionParameter**. |
| [Properties Element in MetadataObject (BDCMetadata Schema)](http://msdn.microsoft.com/library/9901904f-96ee-0cbb-64a9-c2aad9d72128%28Office.15%29.aspx)|The properties of the  **ActionParameter**. |
   
 **Parent element**
  
    
    


|** **Element****|**Description **|
|:-----|:-----|
| [ActionParameters Element in Action (BDCMetadata Schema)](http://msdn.microsoft.com/library/e14df901-621c-1851-db78-e99fd3cf31ae%28Office.15%29.aspx)|The  **ActionParameters** element that contains this **ActionParameter**. |
   

## ActionParameters element
<a name="bkmk_ActionParameters"> </a>

Specifies a list of  **ActionParameters** for an action.
  
    
    

  
    
    
 **Namespace:** `http://schemas.microsoft.com/windows/2007/BusinessDataCatalog`
  
    
    
 **Schema:** BDCMetadata
  
    
    



```XML
<ActionParameters></ActionParameters>
```

The following sections describe attributes, child elements, and parent elements. 
  
    
    
 **Attributes**
  
    
    
None. 
  
    
    
 **Child elements**
  
    
    


|**Element **|**Description **|
|:-----|:-----|
| [ActionParameter Element in ActionParameters (BDCMetadata Schema)](http://msdn.microsoft.com/library/1f5fa96a-1bff-f007-984d-a644cbbb2648%28Office.15%29.aspx)|An  **ActionParameter**. |
   
 **Parent element**
  
    
    


|**Element **|**Description **|
|:-----|:-----|
| [Action Element in Actions (BDCMetadata Schema)](http://msdn.microsoft.com/library/f58b96c0-77a8-69d3-8710-fff03d4970b9%28Office.15%29.aspx)|The  **Action** that these **ActionParameters** belong to.|
   

## Actions element
<a name="bkmk_Actions"> </a>

Specifies a list of actions of an external content type. 
  
    
    

  
    
    
 **Namespace:** `http://schemas.microsoft.com/windows/2007/BusinessDataCatalog`
  
    
    
 **Schema:** BDCMetadata
  
    
    



```XML
<Actions></Actions>
```

The following sections describe attributes, child elements, and parent elements. 
  
    
    
 **Attributes**
  
    
    
None 
  
    
    
 **Child elements**
  
    
    


|**Element **|**Description **|
|:-----|:-----|
| [Action Element in Actions (BDCMetadata Schema)](http://msdn.microsoft.com/library/f58b96c0-77a8-69d3-8710-fff03d4970b9%28Office.15%29.aspx)|An action of an external content type. |
   
 **Parent element**
  
    
    


|**Element **|**Description **|
|:-----|:-----|
| [Entity Element in Entities (BDCMetadata Schema)](http://msdn.microsoft.com/library/a8455bc4-12d8-85e0-146e-5d1d8579e1f5%28Office.15%29.aspx)|The external content type that these actions belong to. |
   

## Association element
<a name="bkmk_Association"> </a>

The Association element links related external content types within a system. For example, a customer is associated with a sales order in the AdventureWorks system: a customer makes sales orders. An Association holds pointers to the source and destination external content types and a pointer to the business logic (a  **MethodInstance** object) that allows a client to get the destination external content type from the source external content type. The traversal of an **Association** is a method call on the external system.
  
    
    

  
    
    
 **Namespace:** http://schemas.microsoft.com/windows/2007/BusinessDataCatalog
  
    
    
 **Schema:** BDCMetadata
  
    
    

> [!Important]  
> Properties are case-sensitive. 
  
    
    


**Properties**


|**Property **|**Type **|**Description **|**Required **|**Default Value **|**Limits/Accepted Values **|
|:-----|:-----|:-----|:-----|:-----|:-----|
|**HideOnProfilePage**|**System.Boolean**|Specifies whether the related external content type should be added to the profile page of the master external content type. |Optional |||
   



```XML
<Association Type = "String" Default = "Boolean" ReturnParameterName = "String" ReturnTypeDescriptorName = "String" ReturnTypeDescriptorLevel = "Integer" Name = "String" DefaultDisplayName = "String" IsCached = "Boolean"> </Association>
```

The following sections describe attributes, child elements, and parent elements. 
  
    
    
 **Attributes**
  
    
    


|**Attribute **|**Description **|
|:-----|:-----|
|**Type**|Required. The  **MethodInstanceType** that specifies the type of the Association.The following table lists the possible values for this attribute. |**Value **|**Description **|
|:-----|:-----|
|AssociationNavigator |The  **MethodInstance** is an **AssociationNavigator**. |
|Associator |The  **MethodInstance** is an **Associator**. |
|Disassociator |The  **MethodInstance** is a **Disassociator**. |
|**BulkAssociatedIdEnumerator**|The  **MethodInstance** is a **BulkAssociatedIdEnumerator**. |
|**BulkAssociationNavigator**|The  **MethodInstance** is a **BulkAssociationNavigator**. |
   
|
|Default |Optional. Specifies whether the Association is the default among all Associations sharing its type within the containing external content type. If set to  **true**, the Association is the default among all Associations sharing its type within the containing external content type. If set to  **false**, the Association is not the default among all Associations sharing its type within the containing external content type. Default value:  **false**Attribute type:  **Boolean**|
|ReturnParameterName |Optional. The name of the parameter that contains the  **ReturnTypeDescriptor** of the Association. The **Direction** attribute of the parameter must contain a value of either "Out", "InOut", or "Return".Attribute type:  **String**|
|ReturnTypeDescriptorName |Optional. This has been deprecated. Use the  **ReturnTypeDescriptorPath** instead.Attribute type:  **String**|
|ReturnTypeDescriptorLevel |Optional. This has been deprecated. Use the  **ReturnTypeDescriptorPath** instead.Attribute type:  **Integer**|
|ReturnTypeDescriptorPath |Optional. The dotted path of the  **TypeDescriptor** of the Association.Attribute type:  **String**|
|Name |Required. The name of the Association. Attribute type:  **String**|
|DefaultDisplayName |Optional. The default display name for the Association. Attribute type:  **String**|
|IsCached |Optional. Specifies whether this Association is frequently used. Default value:  **true**Attribute type:  **Boolean**|
   
 **Child elements**
  
    
    


|**Element **|**Description **|
|:-----|:-----|
| [LocalizedDisplayNames Element in MetadataObject (BDCMetadata Schema)](http://msdn.microsoft.com/library/3202aecf-f98f-20cb-1fdd-f3a054cb24aa%28Office.15%29.aspx)|The  **LocalizedDisplayNames** element specifies a list of localized names for the Association.|
| [Properties Element in MetadataObject (BDCMetadata Schema)](http://msdn.microsoft.com/library/9901904f-96ee-0cbb-64a9-c2aad9d72128%28Office.15%29.aspx)|The Properties element specifies the properties of the Association. |
| [AccessControlList Element (BDCMetadata Schema)](http://msdn.microsoft.com/library/b7f97740-5d2c-f91a-1028-10e2890d4a99%28Office.15%29.aspx)|The  **AccessControlList** element specifies a set of access rights for the Association.|
| [SourceEntity Element in Association (BDCMetadata Schema)](http://msdn.microsoft.com/library/19fb5f38-4e85-7fb0-2562-281b9a9ffbef%28Office.15%29.aspx)|The  **SourceEntity** element specifies the source external content type in the association.|
| [DestinationEntity Element in Association (BDCMetadata Schema)](http://msdn.microsoft.com/library/15c53c3b-888d-67c7-af7d-ef36922eeebc%28Office.15%29.aspx)|The  **DestinationEntity** element specifies the destination external content type in the Association.|
   
 **Parent element**
  
    
    


|**Element **|**Description **|
|:-----|:-----|
| [MethodInstances Element in Method (BDCMetadata Schema)](http://msdn.microsoft.com/library/dae3aeae-e72a-0b52-1348-f5e5cd31109f%28Office.15%29.aspx)|The  **MethodInstances** element that contains the Association.|
   

## AssociationGroup element
<a name="bkmk_AssociationGroup"> </a>

Specifies an  **AssociationGroup**.  **AssociationGroup** is a construct that ties the related **AssociationMethods** together. For example, **GetOrdersForCustomer**,  **GetCustomerForOrder**, and  **AssociateCustomerToOrder** are all association methods that work on the same relationship between Customer and Order.
  
    
    

  
    
    
 **Namespace:** `http://schemas.microsoft.com/windows/2007/BusinessDataCatalog`
  
    
    
 **Schema:** BDCMetadata
  
    
    
 **AssociationGroup** must be defined on the Entity element that is the Destination of the **AssociationReferences** that are not marked as **Reverse**, or the Source of the  **AssociationReferences** that are marked as Reverse.
  
    
    



```XML
<AssociationGroup Name = "String" DefaultDisplayName = "String" IsCached = "Boolean"> </AssociationGroup>
```

The following sections describe attributes, child elements, and parent elements. 
  
    
    
 **Attributes**
  
    
    


|**Attribute **|**Description **|
|:-----|:-----|
|**Name**|Required. The name of the  **AssociationGroup**. Attribute type:  **String**|
|**DefaultDisplayName**|Optional. The default display name of the  **AssociationGroup**. Attribute type:  **String**|
|**IsCached**|Optional. Specifies whether the  **AssociationGroup** is used frequently.Default value:  **true**Attribute type:  **Boolean**|
   
 **Child elements**
  
    
    


|**Element **|**Description **|
|:-----|:-----|
| [LocalizedDisplayNames Element in MetadataObject (BDCMetadata Schema)](http://msdn.microsoft.com/library/3202aecf-f98f-20cb-1fdd-f3a054cb24aa%28Office.15%29.aspx)|The localized names of the  **AssociationGroup**. |
| [Properties Element in MetadataObject (BDCMetadata Schema)](http://msdn.microsoft.com/library/9901904f-96ee-0cbb-64a9-c2aad9d72128%28Office.15%29.aspx)|The properties of the  **AssociationGroup**. |
| [AssociationReference Element in AssociationGroup (BDCMetadata Schema)](http://msdn.microsoft.com/library/e32c5267-53b0-9ff0-6e9a-1cb00d9f1d57%28Office.15%29.aspx)|An  **AssociationReference** of an **AssociationGroup**. |
   
 **Parent element**
  
    
    


|**Element **|**Description **|
|:-----|:-----|
| [AssociationGroups Element in Entity (BDCMetadata Schema)](http://msdn.microsoft.com/library/b50c2648-daea-d8c0-039a-b95590b9924c%28Office.15%29.aspx)|The  **AssociationGroups** element that contains this **AssociationGroup**. |
   

## AssociationGroups element
<a name="bkmk_AssociationGroups"> </a>

Specifies a list of  **AssociationGroup** elements.
  
    
    

  
    
    
 **Namespace:** `http://schemas.microsoft.com/windows/2007/BusinessDataCatalog`
  
    
    
 **Schema:** BDCMetadata
  
    
    



```XML
<AssociationGroups></AssociationGroups>
```

The following sections describe attributes, child elements, and parent elements. 
  
    
    
 **Attributes**
  
    
    
None 
  
    
    
 **Child elements**
  
    
    


|**Element **|**Description **|
|:-----|:-----|
| [AssociationGroup Element in AssociationGroups (BDCMetadata Schema)](http://msdn.microsoft.com/library/db30622e-3c2b-2735-9360-a702196cbcff%28Office.15%29.aspx)|An  **AssociationGroup**. |
   
 **Parent element**
  
    
    


|**Element **|**Description **|
|:-----|:-----|
| [Entity Element in Entities (BDCMetadata Schema)](http://msdn.microsoft.com/library/a8455bc4-12d8-85e0-146e-5d1d8579e1f5%28Office.15%29.aspx)|The external content type that this  **AssociationGroups** element is associated with.|
   

## AssociationReference element
<a name="bkmk_AssociationReference"> </a>

Specifies an  **AssociationReference** in an **AssociationGroup**. 
  
    
    

  
    
    
 **Namespace:** `http://schemas.microsoft.com/windows/2007/BusinessDataCatalog`
  
    
    
 **Schema:** BDCMetadata
  
    
    



```XML
<AssociationReference EntityNamespace = "String" EntityName = "String" AssociationName = "String" Reverse = "Boolean"> </AssociationReference>
```

The following sections describe attributes, child elements, and parent elements. 
  
    
    
 **Attributes**
  
    
    


|**Attribute **|**Description **|
|:-----|:-----|
|EntityNamespace |Optional. The namespace of the external content type where the  **Association** is defined. If **EntityName** is specified, **EntityNamespace** is required.Attribute type:  **String**|
|EntityName |Optional. The name of the external content type where the  **Association** is defined. If **EntityNamespace** is specified, **EntityName** is required.Attribute type:  **String**|
|AssociationName |Required. The name of the  **Association**. Attribute type:  **String**|
|Reverse |Optional. Specifies that the referenced  **Association** has its source and destination reversed. This would indicate the **Association** is working in the opposite direction compared to other associations in the same **AssociationGroup**. For example, if the  **AssociationGroup** references an **Association** "GetOrdersForCustomer", returning Order items for the given Customer item, then the **AssociationGroup** is in the direction of Customer to Order. The other **AssociationReference**, referencing another association "GetCustomerForOrder", must be marked as reverse, because this association is in the direction of Order to Customer. Default value:  **false**Attribute type:  **Boolean**|
   
 **Child elements**
  
    
    
None 
  
    
    
 **Parent element**
  
    
    


|**Element **|**Description **|
|:-----|:-----|
| [AssociationGroup Element in AssociationGroups (BDCMetadata Schema)](http://msdn.microsoft.com/library/db30622e-3c2b-2735-9360-a702196cbcff%28Office.15%29.aspx)|The  **AssociationGroup** that this **AssociationReference** belongs to.|
   

## ConvertType element
<a name="bkmk_ConvertType"> </a>

Specifies the rule to convert the data type of a data value into another data type. 
  
    
    
 **Namespace:** `http://schemas.microsoft.com/windows/2007/BusinessDataCatalog`
  
    
    
 **Schema:** BDCMetadata
  
    
    
The Convert element specifies the rule to convert the data type of a data value into another data type. When the rules are applied in order, this rule specifies the data type of the data value to be converted to the data type specified by the BDCType attribute. When the rules are applied in reverse order, this rule specifies the data type of the data value to be converted to the data type specified by the  **LOBType** attribute. For example, this rule can specify converting a date value obtained from an external system, into a culture and locale sensitive string which will eventually be displayed to the user, and converting the updated value for that string back into the date that is compatible with the external system.
  
    
    

> [!Caution]  
>  **ConvertType** does not support non-Gregorian calendars for conversions between **System.String** and **System.DateTime**. 
  
    
    




```XML
<ConvertType LOBType = "String" BDCType = "String"> </ConvertType>
```

The following sections describe attributes, child elements, and parent elements. 
  
    
    
 **Attributes**
  
    
    


|**Attribute **|**Description **|
|:-----|:-----|
|LOBType |Required. The data type to convert the data value into when the rules are applied in reverse order. Attribute type:  **String**|
|BDCType |Required. The data type to convert the data value into when the rules are applied in order. Attribute type:  **String**|
|LOBLocale |Optional. The locale of the data that is received from the external system. |
   
 **Child elements**
  
    
    
None 
  
    
    
 **Parent element**
  
    
    


|**Element **|**Description **|
|:-----|:-----|
| [Interpretation Element in TypeDescriptor (BDCMetadata Schema)](http://msdn.microsoft.com/library/730f9590-ab40-85b8-eb97-8fd9d8e33c8a%28Office.15%29.aspx)|The rules to apply to the data stored in the data structures that are represented by a  **TypeDescriptor**. |
   

## DefaultValue element
<a name="bkmk_DefaultValue"> </a>

Represents a default value. 
  
    
    
 **Namespace:** `http://schemas.microsoft.com/windows/2007/BusinessDataCatalog`
  
    
    
 **Schema:** BDCMetadata
  
    
    



```XML
<DefaultValue MethodInstanceName = "String" Type = "String"> </DefaultValue>
```

The following sections describe attributes, child elements, and parent elements. 
  
    
    
 **Attributes**
  
    
    


|**Attribute **|**Description **|
|:-----|:-----|
|**MethodInstanceName**|Required. The name of the  **MethodInstance** to which this DefaultValue applies.Attribute type:  **String**|
|**Type**| Required. The data type of the default value. The following are the acceptable values for this attribute. **System.Int16** **System.Int32** **System.Int64** **System.Single** **System.Double** **System.Decimal** **System.Boolean** **System.Byte** **System.UInt16** **System.UInt32** **System.UInt64** **System.Guid** **System.String** **System.DateTime** Any other serializable type (such as where `Type.IsSerializable == true`)  Attribute type: **String**|
   
 **Child elements**
  
    
    
None 
  
    
    
 **Parent element**
  
    
    


|**Element **|**Description **|
|:-----|:-----|
| [DefaultValues Element in TypeDescriptor (BDCMetadata Schema)](http://msdn.microsoft.com/library/635295d1-0f85-6308-976b-d0cb483dece6%28Office.15%29.aspx)||
   

## DefaultValues element
<a name="bkmk_DefaultValues"> </a>

Specifies a list of  **DefaultValues** of a **TypeDescriptor**. 
  
    
    
 **Namespace:** `http://schemas.microsoft.com/windows/2007/BusinessDataCatalog`
  
    
    
 **Schema:** BDCMetadata
  
    
    



```XML
<DefaultValues></DefaultValues>
```

The following sections describe attributes, child elements, and parent elements. 
  
    
    
 **Attributes**
  
    
    
None 
  
    
    
 **Child elements**
  
    
    


|**Element **|**Description **|
|:-----|:-----|
| [DefaultValue Element in DefaultValues (BDCMetadata Schema)](http://msdn.microsoft.com/library/ddb67f64-6361-7b59-6724-4680484d585d%28Office.15%29.aspx)|The default value of a  **TypeDescriptor** for a **MethodInstance**. |
   
 **Parent element**
  
    
    


|**Element **|**Description **|
|:-----|:-----|
| [TypeDescriptor Element (BDCMetadata Schema)](http://msdn.microsoft.com/library/ae423de8-c13b-aea5-d47b-17ef786fb5a7%28Office.15%29.aspx)|The  **TypeDescriptor** that these **DefaultValues** belong to.|
   

## DestinationEntity element
<a name="bkmk_DestinationEntity"> </a>

Specifies the destination external content type in the  **Association**. 
  
    
    
 **Namespace:** `http://schemas.microsoft.com/windows/2007/BusinessDataCatalog`
  
    
    
 **Schema:** BDCMetadata
  
    
    



```XML
<DestinationEntity Namespace = "String" Name = "String"> </DestinationEntity>
```

The following sections describe attributes, child elements, and parent elements. 
  
    
    
 **Attributes**
  
    
    


|**Attribute **|**Description **|
|:-----|:-----|
|**Namespace**|Required. The name of the entity namespace. Attribute type:  **String**|
|**Name**|Required. The name of the destination entity. Attribute type:  **String**|
   
 **Child elements**
  
    
    
None 
  
    
    
 **Parent element**
  
    
    


|**Element **|**Description **|
|:-----|:-----|
| [Association Element in MethodInstances (BDCMetadata Schema)](http://msdn.microsoft.com/library/9659a1f5-1b12-03ef-f9e3-5c9904cc5dd0%28Office.15%29.aspx)||
   

## Entities element
<a name="bkmk_Entities"> </a>

Specifies a list of external content types in an external system. 
  
    
    

  
    
    
 **Namespace:** `http://schemas.microsoft.com/windows/2007/BusinessDataCatalog`
  
    
    
 **Schema:** BDCMetadata
  
    
    



```XML
<Entities></Entities>
```

The following sections describe attributes, child elements, and parent elements. 
  
    
    
 **Attributes**
  
    
    
None 
  
    
    
 **Child elements**
  
    
    


|**Element **|**Description **|
|:-----|:-----|
| [Entity Element in Entities (BDCMetadata Schema)](http://msdn.microsoft.com/library/a8455bc4-12d8-85e0-146e-5d1d8579e1f5%28Office.15%29.aspx)|An external content type in an external system. |
   
 **Parent element**
  
    
    


|**Element **|**Description **|
|:-----|:-----|
| [LobSystem Element in LobSystems (BDCMetadata Schema)](http://msdn.microsoft.com/library/d4e58d7d-a628-8093-97fe-7c3136e8f6f2%28Office.15%29.aspx)|An external system. |
   

## Entity element
<a name="bkmk_Entity"> </a>

Specifies an external content type. 
  
    
    

  
    
    
 **Namespace:** `http://schemas.microsoft.com/windows/2007/BusinessDataCatalog`
  
    
    
 **Schema:** BDCMetadata
  
    
    



```XML
<Entity Namespace = "String" Version = "String" EstimatedInstanceCount = "Integer" DefaultOperationMode = "String" Name = "String" DefaultDisplayName = "String" IsCached = "Boolean"> </Entity>
```

The following sections describe attributes, child elements, and parent elements. 
  
    
    
 **Attributes**
  
    
    


|**Attribute **|**Description **|
|:-----|:-----|
|**Namespace**|Required. The namespace that this external content type belongs to. Attribute type:  **String**> [!Note]  > The namespace should not contain the asterisk special character " *****".           |
|**Version**|Required. The version number of this external content type. Attribute type:  **String**> [!Caution]  > When the BDC model changes, you must increase the version number of the external content type. If the structure of an external content type changes, you should increase the major number. Examples of structural changes include adding a field to a  **SpecificFinder** or changing an identifier field. If the change does not affect the structure of the external content type, for example, when adding a creator method, changing connection information, or when changing names of **LobSystems** and type descriptors, you should change the build number and revision number.          |
|**EstimatedInstanceCount**|Optional. The estimated number of external items contained by the external system. Default value: 10000 Attribute type:  **Integer**|
|**DefaultOperationMode**|Optional. Specifies the default behavior when interacting with the external system while creating, deleting, updating, or reading external items. Default value: Default The following table lists the possible values for this attribute. |**Value **|**Description **|
|:-----|:-----|
|Online |Bypass the cached external items for all operations and interact with the external system directly. |
|Cached |Perform  **Create**, **Read**, **Update**, and **Delete** operations directly against the cached external items. For **Read** operations, if the requested external items are available in the cache, use the external items in the cache. Otherwise, bypass the cache to obtain the external items from the external system, and put it in the cache for later use.|
|Offline |Perform  **Create**, **Read**, **Update**, and **Delete** operations against only the cached external items.|
|Default |Use the System default behavior. This uses Cached mode if the environment supports caching external items. |
   
|
|Name |Required. The name of the external content type. Attribute type:  **String**> [!Note]  > The name of an external content type should not contain the asterisk special character " *****".           |
|DefaultDisplayName |Optional. The default display name of the external content type. Attribute type:  **String**|
|IsCached |Optional. Specifies whether this external content type will be frequently used. If set to true, Business Data Connectivity (BDC) service will cache this external content type in memory. Default value:  **true**Attribute type:  **Boolean**|
   
 **Child elements**
  
    
    


|**Element **|**Description **|
|:-----|:-----|
| [LocalizedDisplayNames Element in MetadataObject (BDCMetadata Schema)](http://msdn.microsoft.com/library/3202aecf-f98f-20cb-1fdd-f3a054cb24aa%28Office.15%29.aspx)|The localized display names of this external content type. |
| [Properties Element in MetadataObject (BDCMetadata Schema)](http://msdn.microsoft.com/library/9901904f-96ee-0cbb-64a9-c2aad9d72128%28Office.15%29.aspx)|The properties of this external content type. |
| [AccessControlList Element (BDCMetadata Schema)](http://msdn.microsoft.com/library/b7f97740-5d2c-f91a-1028-10e2890d4a99%28Office.15%29.aspx)|The access control list (ACL) of this external content type. |
| [Identifiers Element in Entity (BDCMetadata Schema)](http://msdn.microsoft.com/library/6566cb43-4f9e-9a2e-7ec0-89057d7daacc%28Office.15%29.aspx)|The identifiers of the external content type. |
| [Methods Element in Entity (BDCMetadata Schema)](http://msdn.microsoft.com/library/42a24b32-bd97-4067-2e25-681d876d29fd%28Office.15%29.aspx)|The methods of the external content type. |
| [AssociationGroups Element in Entity (BDCMetadata Schema)](http://msdn.microsoft.com/library/b50c2648-daea-d8c0-039a-b95590b9924c%28Office.15%29.aspx)|The association groups of the external content type. |
| [Actions Element in Entity (BDCMetadata Schema)](http://msdn.microsoft.com/library/c5a6c08d-a3df-61db-3ce3-1e6837bbf221%28Office.15%29.aspx)|The actions of the external content type. |
   
 **Parent element**
  
    
    


|**Element **|**Description **|
|:-----|:-----|
| [Entities Element in LobSystem (BDCMetadata Schema)](http://msdn.microsoft.com/library/fa121ed1-160a-03c9-df42-851ddc2528d5%28Office.15%29.aspx)|The list of external content types in this external system. |
   

## FilterDescriptor element
<a name="bkmk_FilterDescriptor"> </a>

Specifies a filter descriptor of a method. 
  
    
    

  
    
    
 **Namespace:** `http://schemas.microsoft.com/windows/2007/BusinessDataCatalog`
  
    
    
 **Schema:** BDCMetadata
  
    
    



```XML
<FilterDescriptor Type = "String" FilterField = "String" Name = "String" DefaultDisplayName = "String" IsCached = "Boolean"> </FilterDescriptor>
```

The following sections describe attributes, child elements, and parent elements. 
  
    
    
 **Attributes**
  
    
    


|**Attribute **|**Description **|
|:-----|:-----|
|Type |Required. The type of the filter descriptor. The following table lists the possible values for this attribute. |**Value **|**Description **|
|:-----|:-----|
|Limit |Used while querying an external system and the value of which can be interpreted as a limit on the number of external items ( **EntityInstances**) that are returned when the method that it belongs to is called. |
|PageNumber ||
|Wildcard |Used while querying an external system. Its value represents a pattern of regular and wildcard characters that is matched against the value of a particular field of the set of  **EntityInstances**. The external system returns only those  **EntityInstances** whose field values match the specified pattern.|
|UserContext |Used while querying an external system. Its value can be set automatically by any client application to the identity of the user who is calling the external system. This value can then be used by the external system to authorize and then filter the results returned. |
|UserCulture ||
|Username ||
|Password ||
|LastId ||
|SsoTicket ||
|UserProfile |Used while querying an external system. Its value can be obtained by examining the current user's profile. The external system can use its value to filter the results returned. |
|Comparison |Used while querying an external system. An external system can compare a  **ComparisonFilter** value with the value of a particular field of a set of **EntityInstances** and only those **EntityInstances** where the field values pass the comparison test can be returned.|
|Timestamp ||
|Input |Used while calling an operation in an external system. An external system can use the value of an  **InputFilter** as additional arguments for the operation.|
|Output |Used while calling an operation in an external system. Additional results of an operation that cannot be captured by  **ReturnTypeDescriptor** can be retrieved as a value of the **InputOutputFilter**. |
|InputOutput |Used while calling an operation in an external system. An external system can use the value of an  **InputOutputFilter** as additional arguments for the operation, and additional results of an operation that cannot be captured by **ReturnTypeDescriptor** can be retrieved as a value of the **InputOutputFilter**. |
|Batching ||
|BatchingTermination ||
|ActivityId |**ActivityId** is used when calling an operation on the external system. Its value is set to a GUID that represents the current operation context. If no such value is available, this filter generates a random GUID. On SharePoint Foundation 2010, this filter uses the **CorrelationID**. |
   
|
|FilterField |Optional. Attribute type:  **String**|
|Name |Required. The name of the filter descriptor. Attribute type:  **String**|
|DefaultDisplayName |Optional. The default display name of the filter descriptor. Attribute type:  **String**|
|IsCached |Optional. Specifies whether this filter descriptor is used frequently. If set to  **true**, Business Data Connectivity (BDC) service caches this filter descriptor in memory. Default value:  **true**Attribute type:  **Boolean**|
   
 **Child elements**
  
    
    


|**Element **|**Description **|
|:-----|:-----|
| [LocalizedDisplayNames Element in MetadataObject (BDCMetadata Schema)](http://msdn.microsoft.com/library/3202aecf-f98f-20cb-1fdd-f3a054cb24aa%28Office.15%29.aspx)|The localized display names of this filter descriptor. |
| [Properties Element in MetadataObject (BDCMetadata Schema)](http://msdn.microsoft.com/library/9901904f-96ee-0cbb-64a9-c2aad9d72128%28Office.15%29.aspx)|The properties of this filter descriptor. |
   
 **Parent element**
  
    
    


|**Element **|**Description **|
|:-----|:-----|
| [FilterDescriptors Element in Method (BDCMetadata Schema)](http://msdn.microsoft.com/library/33d8e418-ddbb-e1ac-b145-836ed9f36e5c%28Office.15%29.aspx)|A list of filter descriptors of a method. |
   

## FilterDescriptors element
<a name="bkmk_FilterDescriptors"> </a>

Specifies a list of filter descriptors of a method. 
  
    
    
 **Namespace:** `http://schemas.microsoft.com/windows/2007/BusinessDataCatalog`
  
    
    
 **Schema:** BDCMetadata
  
    
    



```XML
<FilterDescriptors></FilterDescriptors>
```

The following sections describe attributes, child elements, and parent elements. 
  
    
    
 **Attributes**
  
    
    
None 
  
    
    
 **Child elements**
  
    
    


|**Element **|**Description **|
|:-----|:-----|
| [FilterDescriptor Element in FilterDescriptors (BDCMetadata Schema)](http://msdn.microsoft.com/library/8ce0a852-38f9-75d2-8258-27c57418f53c%28Office.15%29.aspx)|A filter descriptor. |
   
 **Parent element**
  
    
    


|**Element **|**Description **|
|:-----|:-----|
| [Method Element in Methods (BDCMetadata Schema)](http://msdn.microsoft.com/library/70e87a9e-4959-0a7b-3f37-ddec36473ff4%28Office.15%29.aspx)|The method this list of filter descriptors belongs to. |
   

## Identifier element
<a name="bkmk_Identifier"> </a>

Specifies an identifier of an external content type. 
  
    
    

  
    
    
 **Namespace:** `http://schemas.microsoft.com/windows/2007/BusinessDataCatalog`
  
    
    
 **Schema:** BDCMetadata
  
    
    

> [!Note]  
> Business Data Connectivity (BDC) service enables the mapping of identifiers to fields with nullable data types. However, for primary identifiers, BDC will cause an error when the value of these identifiers are  **null**. 
  
    
    




```XML
<Identifier TypeName = "String" Name = "String" DefaultDisplayName = "String" IsCached = "Boolean"> </Identifier>
```

The following sections describe attributes, child elements, and parent elements. 
  
    
    
 **Attributes**
  
    
    


|**Attribute **|**Description **|
|:-----|:-----|
|TypeName |Required. The data type of the value that corresponds to the identifier. The following table lists the possible values for this attribute. |**Value **|**Description **|
|:-----|:-----|
|System.Boolean |A bit. |
|System.Byte |A number ranging from 0 to 255 inclusive. |
|System.Char |A Unicode character. |
|System.DateTime |A date and time ranging from 12:00:00 midnight, January 1, 1 Anno Domini (Common Era) to 11:59:59 P.M. December 31, 9999 Anno Domini (Common Era) inclusive, in resolution of 100 nanoseconds. |
|System.Decimal |A number ranging from negative 79,228,162,514,264,337,593,543,950,335 to positive 79,228,162,514,264,337,593,543,950,335 inclusive. |
|System.Double |A double precision number ranging from negative 1.79769313486232e308 to positive 1.79769313486232e308 inclusive, and positive zero, negative zero, positive infinity, negative infinity, and not-a-number (NaN). |
|System.Guid |A GUID. |
|System.Int16 |A number ranging from negative 32768 to positive 32767 inclusive. |
|System.Int32 |A number ranging from 0 to 4,294,967,295 inclusive. |
|System.Int64 |A number ranging from 0 to 18,446,744,073,709,551,615 inclusive. |
|System.SByte |A number ranging from negative 128 to positive 127 inclusive. |
|System.Single |A single precision number ranging from negative 3.402823e38 to positive 3.402823e38 inclusive. |
|System.String |A string of Unicode text. |
|System.TimeSpan |A duration ranging from negative 10675199 days 2 hours 48 minutes 5 seconds 477 milliseconds 580 microseconds 800 nanoseconds to positive 10675199 days 2 hours 48 minutes 5 seconds 477 milliseconds 580 microseconds 800 nanoseconds inclusive, in resolution of 100 nanoseconds. |
|System.UInt16 |A number ranging from 0 to 65535 inclusive. |
|System.UInt32 |A number ranging from 0 to 4,294,967,295 inclusive. |
|System.UInt64 |A number ranging from 0 to 18,446,744,709,551,615 inclusive. |
   
|
|Name |Required. The name of the identifier. Attribute type:  **String**|
|DefaultDisplayName |Optional. The default display name of the identifier. Attribute type:  **String**|
|IsCached |Optional. Specifies whether this identifier is used frequently. If set to  **true**, Business Data Connectivity (BDC) service caches the identifier in memory. Default value:  **true**Attribute type:  **Boolean**|
   
 **Child elements**
  
    
    


|**Element **|**Description **|
|:-----|:-----|
| [LocalizedDisplayNames Element in MetadataObject (BDCMetadata Schema)](http://msdn.microsoft.com/library/3202aecf-f98f-20cb-1fdd-f3a054cb24aa%28Office.15%29.aspx)|The localized display names of the identifier. |
| [Properties Element in MetadataObject (BDCMetadata Schema)](http://msdn.microsoft.com/library/9901904f-96ee-0cbb-64a9-c2aad9d72128%28Office.15%29.aspx)|The properties of the identifier. |
   
 **Parent element**
  
    
    


|**Element **|**Description **|
|:-----|:-----|
| [Identifiers Element in Entity (BDCMetadata Schema)](http://msdn.microsoft.com/library/6566cb43-4f9e-9a2e-7ec0-89057d7daacc%28Office.15%29.aspx)|A list of identifiers of an external content type. |
   

## Identifiers element
<a name="bkmk_Identifiers"> </a>

Specifies a list of identifiers of an external content type. 
  
    
    
 **Namespace:** `http://schemas.microsoft.com/windows/2007/BusinessDataCatalog`
  
    
    
 **Schema:** BDCMetadata
  
    
    



```XML
<Identifiers></Identifiers>
```

The following sections describe attributes, child elements, and parent elements. 
  
    
    
 **Attributes**
  
    
    
None 
  
    
    
 **Child elements**
  
    
    


|**Element **|**Description **|
|:-----|:-----|
| [Identifier Element in Identifiers (BDCMetadata Schema)](http://msdn.microsoft.com/library/c4abf09b-10b6-0007-9214-35d5fe675be7%28Office.15%29.aspx)|Specifies an identifier. |
   
 **Parent element**
  
    
    


|**Element **|**Description **|
|:-----|:-----|
| [Entity Element in Entities (BDCMetadata Schema)](http://msdn.microsoft.com/library/a8455bc4-12d8-85e0-146e-5d1d8579e1f5%28Office.15%29.aspx)|The external content type that contains this list of identifiers. |
   

## Interpretation element
<a name="bkmk_Interpretation"> </a>

Specifies the rules to apply to the data stored in the data structures represented by a  **TypeDescriptor**. These rules are typically specified to change the data values returned by an external system to make it easier to represent them in the user interface. When the data value is obtained from the external system, the specified rules must be applied in the order they are specified in the **Interpretation** element. The first rule must be applied to the data value received from the external system; the consecutive rules apply to the data value that result from the application of the previous rule. When the data value is sent to external system, the specified rules must be applied in the reverse order they are specified in the **Interpretation** element. The first rule must be applied to the data value received from the user; the consecutive rules apply to the data value that result from the application of the previous rule.
  
    
    
 **Namespace:** `http://schemas.microsoft.com/windows/2007/BusinessDataCatalog`
  
    
    
 **Schema:** BDCMetadata
  
    
    



```XML
<Interpretation></Interpretation>
```

The following sections describe attributes, child elements, and parent elements. 
  
    
    
 **Attributes**
  
    
    
None 
  
    
    
 **Child elements**
  
    
    


|**Element **|**Description **|
|:-----|:-----|
| [ConvertType Element in Interpretation (BDCMetadata Schema)](http://msdn.microsoft.com/library/c474cf2c-b631-f3c9-daf1-f05d3e0d385f%28Office.15%29.aspx)|A  **ConvertType** element that specifies the conversion of a data type to another data type.|
| [NormalizeDateTime Element in Interpretation (BDCMetadata Schema)](http://msdn.microsoft.com/library/bbae3bfa-0754-d576-2bee-1ac0e8508a57%28Office.15%29.aspx)|A  **NormalizeDateTime** element that specifies the conversion of the date and time representation of a value obtained from an external system into another representation.|
|NormalizeString |A  **NormalizeString** element that specifies the conversion of the string representation of a value obtained from an external system into another representation.|
   
 **Parent element**
  
    
    


|**Element **|**Description **|
|:-----|:-----|
| [TypeDescriptor Element (BDCMetadata Schema)](http://msdn.microsoft.com/library/ae423de8-c13b-aea5-d47b-17ef786fb5a7%28Office.15%29.aspx)|The  **TypeDescriptor** element.|
   

## LobSystem element
<a name="bkmk_LobSystem"> </a>

Represents an external data source. 
  
    
    

  
    
    
 **Namespace:** `http://schemas.microsoft.com/windows/2007/BusinessDataCatalog`
  
    
    
 **Schema:** BDCMetadata
  
    
    



```XML
<LobSystem Type = "String" Name = "String" DefaultDisplayName = "String" IsCached = "Boolean"> </LobSystem>
```

The following sections describe attributes, child elements, and parent elements. 
  
    
    
 **Attributes**
  
    
    


|**Attribute **|**Description **|
|:-----|:-----|
|Type |The type of the  **LobSystem**. Required. The following table lists the possible values for this attribute. |**Value **|**Description **|
|:-----|:-----|
|Database |The represented external data source is a database. |
|DotNetAssembly |The represented external data source is a set of .NET Framework classes. |
|Wcf |The represented external data source is a WCF Service endpoint. |
|WebService |The represented external data source is a Web service. This has been deprecated, use WCF instead. |
|Custom |The represented external data source has a custom connector implemented to manage the connection and data transfer. |
   
|
|Name |The name of the  **LobSystem**. Required. Attribute type:  **String**|
|DefaultDisplayName |The default display name of the  **LobSystem**. Optional. Attribute type:  **String**|
|IsCached |Specifies whether the  **LobSystem** is frequently used. If frequently used, Business Data Connectivity (BDC) service caches the **LobSystem**. Optional. Default value:  **true**Attribute type:  **Boolean**|
   
 **Child elements**
  
    
    


|**Element **|**Description **|
|:-----|:-----|
| [LocalizedDisplayNames Element in MetadataObject (BDCMetadata Schema)](http://msdn.microsoft.com/library/3202aecf-f98f-20cb-1fdd-f3a054cb24aa%28Office.15%29.aspx)|The localized names of the  **LobSystem**. |
| [Properties Element in MetadataObject (BDCMetadata Schema)](http://msdn.microsoft.com/library/9901904f-96ee-0cbb-64a9-c2aad9d72128%28Office.15%29.aspx)|Specifies the properties of an  **LobSystem**. |
| [AccessControlList Element (BDCMetadata Schema)](http://msdn.microsoft.com/library/b7f97740-5d2c-f91a-1028-10e2890d4a99%28Office.15%29.aspx)|Specifies the access control list (ACL) of an  **LobSystem**. |
| [Proxy Element in LobSystem (BDCMetadata Schema)](http://msdn.microsoft.com/library/8ec2e7b0-156f-ff4a-a87b-fe5764e4875b%28Office.15%29.aspx)|Specifies a user-provided proxy that is identical to the one that would be generated if this element was not present. |
| [LobSystemInstances Element in LobSystem (BDCMetadata Schema)](http://msdn.microsoft.com/library/122e419a-0497-afdf-1117-a82ab429f3eb%28Office.15%29.aspx)|Specifies the external system instances for this external system. |
| [Entities Element in LobSystem (BDCMetadata Schema)](http://msdn.microsoft.com/library/fa121ed1-160a-03c9-df42-851ddc2528d5%28Office.15%29.aspx)|Specifies the external content types in this external system. |
   
 **Parent element**
  
    
    


|**Element **|**Description **|
|:-----|:-----|
| [LobSystems Element in Model (BDCMetadata Schema)](http://msdn.microsoft.com/library/d9bf0ca9-fb79-e3a5-cc84-9510d93798cb%28Office.15%29.aspx)|Specifies a list of external systems in this model. |
   

## LobSystemInstance element
<a name="bkmk_LobSystemInstance"> </a>

Specifies an external system instance. 
  
    
    
 **Namespace:** `http://schemas.microsoft.com/windows/2007/BusinessDataCatalog`
  
    
    
 **Schema:** BDCMetadata
  
    
    



```XML
<LobSystemInstance Name = "String" DefaultDisplayName = "String" IsCached = "Boolean"> </LobSystemInstance>
```

The following sections describe attributes, child elements, and parent elements. 
  
    
    
 **Attributes**
  
    
    


|**Attribute **|**Description **|
|:-----|:-----|
|Name |Required. The name of the external system instance. Attribute type:  **String**|
|DefaultDisplayName |Optional. The default display name of the external system instance. Attribute type:  **String**|
|IsCached |Optional. Specifies whether this external system instance is used frequently. If set to  **true**, Business Data Connectivity (BDC) service caches the external system instance. Default value:  **true**Attribute type:  **Boolean**|
   
 **Child elements**
  
    
    


|**Element **|**Description **|
|:-----|:-----|
| [LocalizedDisplayNames Element in MetadataObject (BDCMetadata Schema)](http://msdn.microsoft.com/library/3202aecf-f98f-20cb-1fdd-f3a054cb24aa%28Office.15%29.aspx)|The localized names of this external system instance. |
| [Properties Element in MetadataObject (BDCMetadata Schema)](http://msdn.microsoft.com/library/9901904f-96ee-0cbb-64a9-c2aad9d72128%28Office.15%29.aspx)|The properties of this external system instance. |
   
 **Parent element**
  
    
    


|**Element **|**Description **|
|:-----|:-----|
| [LobSystemInstances Element in LobSystem (BDCMetadata Schema)](http://msdn.microsoft.com/library/122e419a-0497-afdf-1117-a82ab429f3eb%28Office.15%29.aspx)|A list of external system instances. |
   

## LobSystemInstances element
<a name="bkmk_LobSystemInstances"> </a>

Specifies a list of external system instances. 
  
    
    
 **Namespace:** `http://schemas.microsoft.com/windows/2007/BusinessDataCatalog`
  
    
    
 **Schema:** BDCMetadata
  
    
    



```XML
<LobSystemInstances></LobSystemInstances>
```

The following sections describe attributes, child elements, and parent elements. 
  
    
    
 **Attributes**
  
    
    
None 
  
    
    
 **Child elements**
  
    
    


|**Element **|**Description **|
|:-----|:-----|
| [LobSystemInstance Element in LobSystemInstances (BDCMetadata Schema)](http://msdn.microsoft.com/library/a0c37891-ef4f-58af-445c-5ff4d5ad6cef%28Office.15%29.aspx)|An external system instance. |
   
 **Parent element**
  
    
    


|**Element **|**Description **|
|:-----|:-----|
| [LobSystem Element in LobSystems (BDCMetadata Schema)](http://msdn.microsoft.com/library/d4e58d7d-a628-8093-97fe-7c3136e8f6f2%28Office.15%29.aspx)|An external system. |
   

## LobSystems element
<a name="bkmk_LobSystems"> </a>

Specifies a list of  **LobSystem** elements of a model.
  
    
    
 **Namespace:** `http://schemas.microsoft.com/windows/2007/BusinessDataCatalog`
  
    
    
 **Schema:** BDCMetadata
  
    
    



```XML
<LobSystems></LobSystems>
```

The following sections describe attributes, child elements, and parent elements. 
  
    
    
 **Attributes**
  
    
    
None 
  
    
    
 **Child elements**
  
    
    


|**Element **|**Description **|
|:-----|:-----|
| [LobSystem Element in LobSystems (BDCMetadata Schema)](http://msdn.microsoft.com/library/d4e58d7d-a628-8093-97fe-7c3136e8f6f2%28Office.15%29.aspx)|A  **LobSystem** element that specifies a external system.|
   
 **Parent element**
  
    
    


|**Element **|**Description **|
|:-----|:-----|
| [Model Element (BDCMetadata Schema)](http://msdn.microsoft.com/library/d7823090-b20d-2c96-c359-081c055d0e65%28Office.15%29.aspx)|An application definition (BDC model). |
   

## LocalizedDisplayName element
<a name="bkmk_LocalizedDisplayName"> </a>

Specifies a localized name. 
  
    
    
 **Namespace:** `http://schemas.microsoft.com/windows/2007/BusinessDataCatalog`
  
    
    
 **Schema:** BDCMetadata
  
    
    



```XML
<LocalizedDisplayName LCID = "Integer"> </LocalizedDisplayName>
```

The following sections describe attributes, child elements, and parent elements. 
  
    
    
 **Attributes**
  
    
    


|**Attribute **|**Description **|
|:-----|:-----|
|LCID |Required. The language code identifier (LCID). Attribute type:  **Integer**|
   
 **Child elements**
  
    
    
None 
  
    
    
 **Parent element**
  
    
    


|**Element **|**Description **|
|:-----|:-----|
| [LocalizedDisplayNames Element in MetadataObject (BDCMetadata Schema)](http://msdn.microsoft.com/library/3202aecf-f98f-20cb-1fdd-f3a054cb24aa%28Office.15%29.aspx)|The  **LocalizedDisplayNames** element that contains this **LocalizedDisplayName**. |
   

## LocalizedDisplayNames element
<a name="bkmk_LocalizedDisplayNames"> </a>

Specifies a list of localized names of a  **MetadataObject**. 
  
    
    

  
    
    
 **Namespace:** `http://schemas.microsoft.com/windows/2007/BusinessDataCatalog`
  
    
    
 **Schema:** BDCMetadata
  
    
    



```XML
<LocalizedDisplayNames></LocalizedDisplayNames>
```

The following sections describe attributes, child elements, and parent elements. 
  
    
    
 **Attributes**
  
    
    
None 
  
    
    
 **Child elements**
  
    
    


|**Element **|**Description **|
|:-----|:-----|
| [LocalizedDisplayName Element in LocalizedDisplayNames (BDCMetadata Schema)](http://msdn.microsoft.com/library/93fb80ef-6347-b463-da90-4980d872678e%28Office.15%29.aspx)|A localized name. |
   
 **Parent element**
  
    
    


|**Element **|**Description **|
|:-----|:-----|
| [Model Element (BDCMetadata Schema)](http://msdn.microsoft.com/library/d7823090-b20d-2c96-c359-081c055d0e65%28Office.15%29.aspx)||
| [LobSystem Element in LobSystems (BDCMetadata Schema)](http://msdn.microsoft.com/library/d4e58d7d-a628-8093-97fe-7c3136e8f6f2%28Office.15%29.aspx)||
| [LobSystemInstance Element in LobSystemInstances (BDCMetadata Schema)](http://msdn.microsoft.com/library/a0c37891-ef4f-58af-445c-5ff4d5ad6cef%28Office.15%29.aspx)||
| [Entity Element in Entities (BDCMetadata Schema)](http://msdn.microsoft.com/library/a8455bc4-12d8-85e0-146e-5d1d8579e1f5%28Office.15%29.aspx)||
| [Identifier Element in Identifiers (BDCMetadata Schema)](http://msdn.microsoft.com/library/c4abf09b-10b6-0007-9214-35d5fe675be7%28Office.15%29.aspx)||
| [Method Element in Methods (BDCMetadata Schema)](http://msdn.microsoft.com/library/70e87a9e-4959-0a7b-3f37-ddec36473ff4%28Office.15%29.aspx)||
| [FilterDescriptor Element in FilterDescriptors (BDCMetadata Schema)](http://msdn.microsoft.com/library/8ce0a852-38f9-75d2-8258-27c57418f53c%28Office.15%29.aspx)||
| [Parameter Element in Parameters (BDCMetadata Schema)](http://msdn.microsoft.com/library/811cad0b-ba71-8be0-0765-3e0dec18a0d3%28Office.15%29.aspx)||
| [TypeDescriptor Element (BDCMetadata Schema)](http://msdn.microsoft.com/library/ae423de8-c13b-aea5-d47b-17ef786fb5a7%28Office.15%29.aspx)||
| [Association Element in MethodInstances (BDCMetadata Schema)](http://msdn.microsoft.com/library/9659a1f5-1b12-03ef-f9e3-5c9904cc5dd0%28Office.15%29.aspx)||
| [MethodInstance Element in MethodInstances (BDCMetadata Schema)](http://msdn.microsoft.com/library/577ff9d0-706b-be7d-af5b-883e137cada8%28Office.15%29.aspx)||
| [AssociationGroup Element in AssociationGroups (BDCMetadata Schema)](http://msdn.microsoft.com/library/db30622e-3c2b-2735-9360-a702196cbcff%28Office.15%29.aspx)||
| [Action Element in Actions (BDCMetadata Schema)](http://msdn.microsoft.com/library/f58b96c0-77a8-69d3-8710-fff03d4970b9%28Office.15%29.aspx)||
| [ActionParameter Element in ActionParameters (BDCMetadata Schema)](http://msdn.microsoft.com/library/1f5fa96a-1bff-f007-984d-a644cbbb2648%28Office.15%29.aspx)||
   

## MetadataObject element
<a name="bkmk_MetadataObject"> </a>

 **Namespace:**
  
    
    
 **Schema:**
  
    
    



```XML

```

The following sections describe attributes, child elements, and parent elements. 
  
    
    
 **Attributes**
  
    
    
 **Child elements**
  
    
    
 **Parent element**
  
    
    

## Method element
<a name="bkmk_Method"> </a>

Specifies a method of an external content type. 
  
    
    

  
    
    
 **Namespace:** `http://schemas.microsoft.com/windows/2007/BusinessDataCatalog`
  
    
    
 **Schema:** BDCMetadata
  
    
    



```XML
<Method IsStatic = "Boolean" LobName = "String" Name = "String" DefaultDisplayName = "String" IsCached = "Boolean"> </Method>
```

The following sections describe attributes, child elements, and parent elements. 
  
    
    
 **Attributes**
  
    
    


|**Attribute **|**Description **|
|:-----|:-----|
|IsStatic |Optional. Specifies whether the execution of this method requires an external item ( **EntityInstance**) to serve as a context for execution. If set to  **true**, the method represents a static method and does not require a specific  **EntityInstance** to provide context for execution. If set to **false**, the method represents an instance method and requires an  **EntityInstance** to provide the context for execution.Default value:  **true**Attribute type:  **Boolean**|
|LobName |Optional. The name of the operation defined in the external system that is represented by this method. Attribute type:  **String**|
|Name |Required. The name of this method. Attribute type:  **String**|
|DefaultDisplayName |Optional. The default display name of the method. Attribute type:  **String**|
|IsCached |Optional. Specifies whether this method is used frequently. If set to  **true**, Business Data Connectivity (BDC) service caches this method in memory. Default value:  **true**Attribute type:  **Boolean**|
   
 **Child elements**
  
    
    


|**Element **|**Description **|
|:-----|:-----|
| [LocalizedDisplayNames Element in MetadataObject (BDCMetadata Schema)](http://msdn.microsoft.com/library/3202aecf-f98f-20cb-1fdd-f3a054cb24aa%28Office.15%29.aspx)|The localized display names of the method. |
| [Properties Element in MetadataObject (BDCMetadata Schema)](http://msdn.microsoft.com/library/9901904f-96ee-0cbb-64a9-c2aad9d72128%28Office.15%29.aspx)|The properties of the method. |
| [AccessControlList Element (BDCMetadata Schema)](http://msdn.microsoft.com/library/b7f97740-5d2c-f91a-1028-10e2890d4a99%28Office.15%29.aspx)|The access control list (ACL) of this method. |
| [FilterDescriptors Element in Method (BDCMetadata Schema)](http://msdn.microsoft.com/library/33d8e418-ddbb-e1ac-b145-836ed9f36e5c%28Office.15%29.aspx)|The filter descriptors of the method. |
| [Parameters Element in Method (BDCMetadata Schema)](http://msdn.microsoft.com/library/343f4c25-e122-1a4c-2b80-bb8f25e3cc82%28Office.15%29.aspx)|The parameters of the method. A method cannot have more than one return parameter. |
| [MethodInstances Element in Method (BDCMetadata Schema)](http://msdn.microsoft.com/library/dae3aeae-e72a-0b52-1348-f5e5cd31109f%28Office.15%29.aspx)|The method instances of the method. |
   
 **Parent element**
  
    
    


|**Element **|**Description **|
|:-----|:-----|
| [Methods Element in Entity (BDCMetadata Schema)](http://msdn.microsoft.com/library/42a24b32-bd97-4067-2e25-681d876d29fd%28Office.15%29.aspx)|A list of methods of an external content type. |
   

## MethodInstance element
<a name="bkmk_MethodInstance"> </a>

Specifies a  **MethodInstance**. 
  
    
    
 **Namespace:** `http://schemas.microsoft.com/windows/2007/BusinessDataCatalog`
  
    
    
 **Schema:** BDCMetadata
  
    
    
The following two cases in a BDC model result in an  [InvalidOperationException](https://msdn.microsoft.com/library/system.invalidoperationexception%28v=vs.110%29.aspx) at run time:
  
    
    

- Two  **SpecificFinder** method instances that return the same set of fields.
    
  
- Two  **SpecificFinder** method instances that have the same number of fields and that share the same number of fields with another method instance, such as a **Finder**. 
    
  



```XML
<MethodInstance Type = "Strig" Default = "Boolean" ReturnParameterName = "String" ReturnTypeDescriptorName = "String" ReturnTypeDescriptorLevel = "Integer" Name = "String" DefaultDisplayName = "String" IsCached = "Boolean"> </MethodInstance>
```

The following sections describe attributes, child elements, and parent elements. 
  
    
    
 **Attributes**
  
    
    


|**Attribute **|**Description **|
|:-----|:-----|
|**Type**|Required. Specifies the type of the  **MethodInstance**. The following table lists the possible values for this attribute. |**Value **|**Description **|
|:-----|:-----|
|Finder |A type of  **MethodInstance** that can be called to return a collection of zero or more **EntityInstances** of a particular **Entity**.  **Finder** input is defined by the **FilterDescriptors** that are contained in the **Method** that contains the **Finder**. |
|SpecificFinder |A type of  **MethodInstance** that can be called to return a specific **EntityInstance** of a specific **Entity** given its **EntityInstanceId**.  **SpecificFinder** input is defined and ordered by the **Identifiers** that are associated with the **Entity**. |
|GenericInvoker |A type of  **MethodInstance** that can be called to perform a specific task in an external system. **GenericInvoker** input and output is specific to the **Method**. |
|IdEnumerator |A type of  **MethodInstance** that can be called to return the **Field** values that represent the identity of **EntityInstances** of a specific **Entity**. The  **IdEnumerator** input is defined by the **FilterDescriptors** that are contained in the method that contains the **IdEnumerator** to get the list of IDs, which are the unique keys for each entity that should be searchable. This method instance enables external data search in SharePoint Server.|
|ChangedIdEnumerator |A type of  **MethodInstance** that can be called to retrieve **EntityInstanceIds** of **EntityInstances** that were modified in an external system after a specified time.|
|DeletedIdEnumerator |A type of  **MethodInstance** that can be called to retrieve **EntityInstanceIds** of **EntityInstances** that were deleted from an external system after the specified time.|
|Scalar |A  **MethodInstance** that returns a single value that you can invoke in the external system. For example, you can use a scalar method instance to get the total sales made to date from the external system. **Entities** have zero or more scalar method instances.|
|AccessChecker |A type of  **MethodInstance** that can be called to retrieve the permissions that the calling security principal has for each of a collection of **EntityInstances** that are identified by the specified **EntityInstanceIds**. |
|Creator |A type of  **MethodInstance** that can be called to create an **EntityInstance**. The set of fields that are required to create the  **EntityInstance** is referred to as the Creator View.|
|Deleter |A type of  **MethodInstance** that can be called to delete an **EntityInstance** with a specified **EntityInstanceId**. |
|Updater |A type of  **MethodInstance** that can be called to update an **EntityInstance** identified by a specified **EntityInstanceId**. The set of fields that is required to update the  **EntityInstance** is known as the Updater View. The set of fields whose values should be passed before they are changed is known as the PreUpdater View.|
|StreamAccessor |A type of  **MethodInstance** that can be called to retrieve a field of an **EntityInstance** in the form of a data stream of bytes.|
|BinarySecurityDescriptorAccessor |A type of  **MethodInstance** that can be called to retrieve a sequence of bytes from an external system. The system-specific byte sequence describes a set of security principals and the associated permissions that each security principal has for the **EntityInstance** identified by a specified **EntityInstanceId**. |
|BulkSpecificFinder |A type of  **MethodInstance** that can be called to return a set of specific **EntityInstances** of an **Entity**, given a set of corresponding  **EntityInstanceIds**. |
|BulkIdEnumerator |A type of  **MethodInstance** that can be called to retrieve minimal information about the external items corresponding to the given identities. This method instance can be used to optimize synchronization of cached data. This method should return only the identities and version information of the external items that correspond to given **Identities**, which the calling application can compare with the local version to identify if anything has changed, and if so, request the changed external items to update the cached data. |
   
|
|**Default**|Optional. Specifies whether the  **MethodInstance** is the default among all **MethodInstances** that share its type within the containing external content type ( **Entity**). Default value:  **false**Attribute type:  **Boolean**|
|**ReturnParameterName**|Optional. The name of the  **Parameter** that contains the **ReturnTypeDescriptor** of the **MethodInstance**. The  **Direction** attribute of the **Parameter** must be a **ParameterDirection** attribute with a value of **Out**,  **InOut**, or  **Return**. This attribute must be specified for all types of  **MethodInstances** except **GenericInvoker**,  **Creator**,  **Deleter**, and  **Updater**. Attribute type:  **String**|
|**ReturnTypeDescriptorLevel**|Optional. This has been deprecated. Use the  **ReturnTypeDescriptorPath** instead.Attribute type:  **Integer**|
|**ReturnTypeDescriptorPath**|Optional. The dotted path of the  **TypeDescriptor** of the Association.Attribute type:  **String**|
|**Name**|Required. Specifies the name of the  **MethodInstance**. Attribute type:  **String**|
|**DefaultDisplayName**|Optional. Specifies the default display name for the  **MethodInstance**. Attribute type:  **String**|
|**IsCached**|Optional. Specifies whether the  **MethodInstance** is used frequently.Default value:  **true**Attribute type:  **Boolean**|
   
 **Child elements**
  
    
    


|**Element **|**Description **|
|:-----|:-----|
| [LocalizedDisplayNames Element in MetadataObject (BDCMetadata Schema)](http://msdn.microsoft.com/library/3202aecf-f98f-20cb-1fdd-f3a054cb24aa%28Office.15%29.aspx)|The localized display names of the  **MethodInstance**. |
| [Properties Element in MetadataObject (BDCMetadata Schema)](http://msdn.microsoft.com/library/9901904f-96ee-0cbb-64a9-c2aad9d72128%28Office.15%29.aspx)|The properties of the  **MethodInstance**. |
| [AccessControlList Element (BDCMetadata Schema)](http://msdn.microsoft.com/library/b7f97740-5d2c-f91a-1028-10e2890d4a99%28Office.15%29.aspx)|The access control lists (ACLs) of the  **MethodInstance**. |
   
 **Parent element**
  
    
    


|**Element **|**Description **|
|:-----|:-----|
| [MethodInstances Element in Method (BDCMetadata Schema)](http://msdn.microsoft.com/library/dae3aeae-e72a-0b52-1348-f5e5cd31109f%28Office.15%29.aspx)|The  **MethodInstances** element that contains this **MethodInstance**. |
   

## MethodInstances element
<a name="bkmk_MethodInstances"> </a>

Specifies a list of associations and method instances of a method. 
  
    
    
 **Namespace:** `http://schemas.microsoft.com/windows/2007/BusinessDataCatalog`
  
    
    
 **Schema:** BDCMetadata
  
    
    



```XML
<MethodInstances></MethodInstances>
```

The following sections describe attributes, child elements, and parent elements. 
  
    
    
 **Attributes**
  
    
    
None 
  
    
    
 **Child elements**
  
    
    


|**Element **|**Description **|
|:-----|:-----|
| [Association Element in MethodInstances (BDCMetadata Schema)](http://msdn.microsoft.com/library/9659a1f5-1b12-03ef-f9e3-5c9904cc5dd0%28Office.15%29.aspx)|An association. |
| [MethodInstance Element in MethodInstances (BDCMetadata Schema)](http://msdn.microsoft.com/library/577ff9d0-706b-be7d-af5b-883e137cada8%28Office.15%29.aspx)|A method instance. |
   
 **Parent element**
  
    
    


|**Element **|**Description **|
|:-----|:-----|
| [Method Element in Methods (BDCMetadata Schema)](http://msdn.microsoft.com/library/70e87a9e-4959-0a7b-3f37-ddec36473ff4%28Office.15%29.aspx)|The method that this method instance belongs to. |
   

## Methods element
<a name="bkmk_Methods"> </a>

Specifies a list of methods of an external content type. 
  
    
    

  
    
    
 **Namespace:** `http://schemas.microsoft.com/windows/2007/BusinessDataCatalog`
  
    
    
 **Schema:** BDCMetadata
  
    
    



```XML
<Methods></Methods>
```

The following sections describe attributes, child elements, and parent elements. 
  
    
    
 **Attributes**
  
    
    
None 
  
    
    
 **Child elements**
  
    
    


|**Element **|**Description **|
|:-----|:-----|
| [Method Element in Methods (BDCMetadata Schema)](http://msdn.microsoft.com/library/70e87a9e-4959-0a7b-3f37-ddec36473ff4%28Office.15%29.aspx)|Specifies a method. |
   
 **Parent element**
  
    
    


|**Element **|**Description **|
|:-----|:-----|
| [Entity Element in Entities (BDCMetadata Schema)](http://msdn.microsoft.com/library/a8455bc4-12d8-85e0-146e-5d1d8579e1f5%28Office.15%29.aspx)|The external content type that this list of methods belongs to. |
   

## Model element
<a name="bkmk_Model"> </a>

Specifies the root element that represents an application definition. Models define external content types that are contained by external applications. 
  
    
    
 **Namespace:** `http://schemas.microsoft.com/windows/2007/BusinessDataCatalog`
  
    
    
 **Schema:** BDCMetadata
  
    
    



```XML
<Model Name = "String" DefaultDisplayName = "String" IsCached = "Boolean"> </Model>
```

The following sections describe attributes, child elements, and parent elements. 
  
    
    
 **Attributes**
  
    
    


|**Attribute **|**Description **|
|:-----|:-----|
|Name |The name of the  **Model**. Required. Attribute type:  **String**|
|DefaultDisplayName |The default display name of the  **Model**. Optional. Attribute type:  **String**|
|IsCached |Specifies whether the  **Model** is used frequently. If this is set to **true**, then the  **Model** is cached by the Business Data Connectivity (BDC) service.Optional. Default value:  **true**Attribute type:  **Boolean**|
   
 **Child elements**
  
    
    


|**Element **|**Description **|
|:-----|:-----|
| [LocalizedDisplayNames Element in MetadataObject (BDCMetadata Schema)](http://msdn.microsoft.com/library/3202aecf-f98f-20cb-1fdd-f3a054cb24aa%28Office.15%29.aspx)|The localized names of the  **Model**. |
| [Properties Element in MetadataObject (BDCMetadata Schema)](http://msdn.microsoft.com/library/9901904f-96ee-0cbb-64a9-c2aad9d72128%28Office.15%29.aspx)|The properties of the  **Model**. |
| [AccessControlList Element (BDCMetadata Schema)](http://msdn.microsoft.com/library/b7f97740-5d2c-f91a-1028-10e2890d4a99%28Office.15%29.aspx)|The access control list (ACL) of the  **Model**. |
| [LobSystems Element in Model (BDCMetadata Schema)](http://msdn.microsoft.com/library/d9bf0ca9-fb79-e3a5-cc84-9510d93798cb%28Office.15%29.aspx)|The  **LobSystems** contained inside this **Model**. |
   
 **Parent element**
  
    
    
None 
  
    
    

## NormalizeDateTime element
<a name="bkmk_NormalizeDateTime"> </a>

Specifies the rule used to convert the representation of a date and time value to another representation. For example, this rule can specify converting a value represented in Coordinated Universal Time (UTC) into a local time zone. 
  
    
    
 **Namespace:** `http://schemas.microsoft.com/windows/2007/BusinessDataCatalog`
  
    
    
 **Schema:** BDCMetadata
  
    
    



```XML
<NormalizeDateTime LobDateTimeMode = "String"> </NormalizeDateTime>
```

The following sections describe attributes, child elements, and parent elements. 
  
    
    
 **Attributes**
  
    
    


|**Attribute **|**Description **|
|:-----|:-----|
|**LobDateTimeMode**|Required. Specifies the conversion to apply. The following table lists the possible values for this attribute. |**Value **|**Description **|
|:-----|:-----|
|UTC |The value that is received from the external system is UTC (Coordinated Universal Time). If the value received is  **Local**, it is converted to UTC. BDC sends UTC to the external system. |
|Local |The value received from the external system is  **Local**. If the value received from the external system is  **Local**, then it will be converted to UTC. BDC sends  **Local** to the external system.|
|Unspecified |The value sent by the external system has Unspecified kind. BDC assumes the value is in UTC by overwriting the kind to be UTC. BDC sends UTC values as Unspecified kind to the external system. |
   
|
   
 **Child elements**
  
    
    
None 
  
    
    
 **Parent element**
  
    
    


|**Element **|**Description **|
|:-----|:-----|
| [Interpretation Element in TypeDescriptor (BDCMetadata Schema)](http://msdn.microsoft.com/library/730f9590-ab40-85b8-eb97-8fd9d8e33c8a%28Office.15%29.aspx)|An  **Interpretation** element that specifies the rules to apply to the data that is stored in the data structures represented by a **TypeDescriptor**. |
   

## NormalizeString element
<a name="bkmk_NormalizeString"> </a>

Specifies a parameter of a method. 
  
    
    
 **Namespace:** `http://schemas.microsoft.com/windows/2007/BusinessDataCatalog`
  
    
    
 **Schema:** BDCMetadata
  
    
    



```XML

```

The following sections describe attributes, child elements, and parent elements. 
  
    
    
 **Attributes**
  
    
    
 **Child elements**
  
    
    
 **Parent element**
  
    
    

## Parameter element
<a name="bkmk_Parameter"> </a>

Specifies a parameter of a method. 
  
    
    
 **Namespace:** `http://schemas.microsoft.com/windows/2007/BusinessDataCatalog`
  
    
    
 **Schema:** BDCMetadata
  
    
    



```XML
<Parameter Direction = "String" Name = "String" DefaultDisplayName = "String" IsCached = "Boolean"> </Parameter>
```

The following sections describe attributes, child elements, and parent elements. 
  
    
    
 **Attributes**
  
    
    


|**Attribute **|**Description **|
|:-----|:-----|
|Direction |Required. The direction of the parameter. The following table lists the possible values for this attribute. |**Value **|**Description **|
|:-----|:-----|
|In |The represented  **Parameter** is an input parameter.|
|Out |The represented parameter is an output parameter. |
|InOut |The represented parameter is an input and output parameter. In C#, these correspond to " **ref**". |
|Return |The represented parameter is a return parameter. |
   
|
|**Name**|Required. The name of the parameter. Attribute type:  **String**|
|**DefaultDisplayName**|Optional. The default display name of the parameter. Attribute type:  **String**|
|**IsCached**|Optional. Specifies whether the  **Parameter** is used frequently.Default value:  **true**Attribute type:  **Boolean**|
   
 **Child elements**
  
    
    


|**Element **|**Description **|
|:-----|:-----|
| [LocalizedDisplayNames Element in MetadataObject (BDCMetadata Schema)](http://msdn.microsoft.com/library/3202aecf-f98f-20cb-1fdd-f3a054cb24aa%28Office.15%29.aspx)|The localized names of the parameter. |
| [Properties Element in MetadataObject (BDCMetadata Schema)](http://msdn.microsoft.com/library/9901904f-96ee-0cbb-64a9-c2aad9d72128%28Office.15%29.aspx)|The properties of the parameter. |
| [TypeDescriptor](http://msdn.microsoft.com/library/30e38d7f-af18-20ec-45ab-0bece071ce67.aspx)|The root type descriptor of the parameter. |
   
 **Parent element**
  
    
    


|**Element **|**Description **|
|:-----|:-----|
| [Parameters Element in Method (BDCMetadata Schema)](http://msdn.microsoft.com/library/343f4c25-e122-1a4c-2b80-bb8f25e3cc82%28Office.15%29.aspx)|The  **Parameters** element that contains this parameter.|
   

## Parameters element
<a name="bkmk_Parameters"> </a>

Specifies a list of parameters of a method. 
  
    
    

  
    
    
 **Namespace:** `http://schemas.microsoft.com/windows/2007/BusinessDataCatalog`
  
    
    
 **Schema:** BDCMetadata
  
    
    



```XML
<Parameters></Parameters>
```

The following sections describe attributes, child elements, and parent elements. 
  
    
    
 **Attributes**
  
    
    
None 
  
    
    
 **Child elements**
  
    
    


|**Element **|**Description **|
|:-----|:-----|
| [Parameter Element in Parameters (BDCMetadata Schema)](http://msdn.microsoft.com/library/811cad0b-ba71-8be0-0765-3e0dec18a0d3%28Office.15%29.aspx)|A parameter. |
   
 **Parent element**
  
    
    


|**Element **|**Description **|
|:-----|:-----|
| [Method Element in Methods (BDCMetadata Schema)](http://msdn.microsoft.com/library/70e87a9e-4959-0a7b-3f37-ddec36473ff4%28Office.15%29.aspx)|The method these parameters belong to. |
   

## Properties element
<a name="bkmk_Properties"> </a>

Specifies a list of properties of a metadata object. 
  
    
    
 **Namespace:** `http://schemas.microsoft.com/windows/2007/BusinessDataCatalog`
  
    
    
 **Schema:** BDCMetadata
  
    
    



```XML
<Properties></Properties>
```

The following sections describe attributes, child elements, and parent elements. 
  
    
    
 **Attributes**
  
    
    
None 
  
    
    
 **Child elements**
  
    
    


|**Element **|**Description **|
|:-----|:-----|
| [Property Element in Properties (BDCMetadata Schema)](http://msdn.microsoft.com/library/2e6e8d5d-ef3b-c536-f3d1-ad2039b92c24%28Office.15%29.aspx)|Specifies a property. |
   
 **Parent element**
  
    
    


|**Element **|**Description **|
|:-----|:-----|
| [Model Element (BDCMetadata Schema)](http://msdn.microsoft.com/library/d7823090-b20d-2c96-c359-081c055d0e65%28Office.15%29.aspx)||
| [LobSystem Element in LobSystems (BDCMetadata Schema)](http://msdn.microsoft.com/library/d4e58d7d-a628-8093-97fe-7c3136e8f6f2%28Office.15%29.aspx)||
| [LobSystemInstance Element in LobSystemInstances (BDCMetadata Schema)](http://msdn.microsoft.com/library/a0c37891-ef4f-58af-445c-5ff4d5ad6cef%28Office.15%29.aspx)||
| [Entity Element in Entities (BDCMetadata Schema)](http://msdn.microsoft.com/library/a8455bc4-12d8-85e0-146e-5d1d8579e1f5%28Office.15%29.aspx)||
| [Identifier Element in Identifiers (BDCMetadata Schema)](http://msdn.microsoft.com/library/c4abf09b-10b6-0007-9214-35d5fe675be7%28Office.15%29.aspx)||
| [Method Element in Methods (BDCMetadata Schema)](http://msdn.microsoft.com/library/70e87a9e-4959-0a7b-3f37-ddec36473ff4%28Office.15%29.aspx)||
| [FilterDescriptor Element in FilterDescriptors (BDCMetadata Schema)](http://msdn.microsoft.com/library/8ce0a852-38f9-75d2-8258-27c57418f53c%28Office.15%29.aspx)||
| [Parameter Element in Parameters (BDCMetadata Schema)](http://msdn.microsoft.com/library/811cad0b-ba71-8be0-0765-3e0dec18a0d3%28Office.15%29.aspx)||
| [TypeDescriptor](http://msdn.microsoft.com/library/30e38d7f-af18-20ec-45ab-0bece071ce67.aspx)||
| [TypeDescriptor Element (BDCMetadata Schema)](http://msdn.microsoft.com/library/ae423de8-c13b-aea5-d47b-17ef786fb5a7%28Office.15%29.aspx)||
| [Association Element in MethodInstances (BDCMetadata Schema)](http://msdn.microsoft.com/library/9659a1f5-1b12-03ef-f9e3-5c9904cc5dd0%28Office.15%29.aspx)||
| [MethodInstance Element in MethodInstances (BDCMetadata Schema)](http://msdn.microsoft.com/library/577ff9d0-706b-be7d-af5b-883e137cada8%28Office.15%29.aspx)||
| [AssociationGroup Element in AssociationGroups (BDCMetadata Schema)](http://msdn.microsoft.com/library/db30622e-3c2b-2735-9360-a702196cbcff%28Office.15%29.aspx)||
| [Action Element in Actions (BDCMetadata Schema)](http://msdn.microsoft.com/library/f58b96c0-77a8-69d3-8710-fff03d4970b9%28Office.15%29.aspx)||
| [ActionParameter Element in ActionParameters (BDCMetadata Schema)](http://msdn.microsoft.com/library/1f5fa96a-1bff-f007-984d-a644cbbb2648%28Office.15%29.aspx)||
   

## Property element
<a name="bkmk_Property"> </a>

Specifies the name and type of a property of a metadata object. 
  
    
    
 **Namespace:** `http://schemas.microsoft.com/windows/2007/BusinessDataCatalog`
  
    
    
 **Schema:** BDCMetadata
  
    
    



```XML
<Property Name = "String" Type = "String"> </Property>
```

The following sections describe attributes, child elements, and parent elements. 
  
    
    
 **Attributes**
  
    
    


|**Attribute **|**Description **|
|:-----|:-----|
|**Name**|Required. Specifies the name of the property. Attribute type:  **String**|
|**Type**|Required. Specifies data type of the property. Attribute type:  **String**|
   
 **Child elements**
  
    
    
None 
  
    
    
 **Parent element**
  
    
    


|**Element **|**Description **|
|:-----|:-----|
| [Properties Element in MetadataObject (BDCMetadata Schema)](http://msdn.microsoft.com/library/9901904f-96ee-0cbb-64a9-c2aad9d72128%28Office.15%29.aspx)|The  **Properties** element that contains this property.|
   

## Proxy element
<a name="bkmk_Proxy"> </a>

Specifies a user-provided proxy that is identical to the one that would be generated if this element was not present. This is used to improve performance by removing the proxy generation overhead. To specify custom business logic that connects to an external system, .NET Connectivity Assembly type external systems must be used. 
  
    
    
 **Namespace:** `http://schemas.microsoft.com/windows/2007/BusinessDataCatalog`
  
    
    
 **Schema:** BDCMetadata
  
    
    



```XML
<Proxy></Proxy>
```

The following sections describe attributes, child elements, and parent elements. 
  
    
    
 **Attributes**
  
    
    
None 
  
    
    
 **Child elements**
  
    
    
None 
  
    
    
 **Parent element**
  
    
    


|**Element **|**Description **|
|:-----|:-----|
| [LobSystem Element in LobSystems (BDCMetadata Schema)](http://msdn.microsoft.com/library/d4e58d7d-a628-8093-97fe-7c3136e8f6f2%28Office.15%29.aspx)|The  **LobSystem** element that this proxy applies to.|
   

## Right element
<a name="bkmk_Right"> </a>

Specifies a single access permission for an access control entry (ACE). 
  
    
    
 **Namespace:** `http://schemas.microsoft.com/windows/2007/BusinessDataCatalog`
  
    
    
 **Schema:** BDCMetadata
  
    
    



```XML
<Right BdcRight = "String"> </Right>
```

The following sections describe attributes, child elements, and parent elements. 
  
    
    
 **Attributes**
  
    
    


|**Attribute **|**Description **|
|:-----|:-----|
|BdcRight |Required. The permission available to the security principal holding the right. The following table lists the possible values for this attribute. |**Value **|**Description **|
|:-----|:-----|
|None |No permissions. |
|Execute |The represented security principal has the permission to invoke a  **MethodInstance**. |
|Edit |The represented security principal has permission to change the attributes of a metadata object or its relationship to other metadata objects. |
|SetPermissions |The represented security principal has permission to change the set of permissions for a metadata object. |
|SelectableInClients |The represented security principal has permission to select the metadata object this right refers to. If a user does not have this permission, the metadata object should not be selectable. |
   
|
   
 **Child elements**
  
    
    
None 
  
    
    
 **Parent element**
  
    
    


|**Element **|**Description **|
|:-----|:-----|
| [AccessControlEntry Element in AccessControlList (BDCMetadata Schema)](http://msdn.microsoft.com/library/85e24489-0a6b-dfda-fb03-474fe7b0d947%28Office.15%29.aspx)|The  **AccessControlEntry** element that contains this right.|
   

## SourceEntity element
<a name="bkmk_SourceEntity"> </a>

Specifies a source external content type of an  **Association**. 
  
    
    
 **Namespace:** `http://schemas.microsoft.com/windows/2007/BusinessDataCatalog`
  
    
    
 **Schema:** BDCMetadata
  
    
    



```XML
<SourceEntity Namespace = "String" Name = "String"> </SourceEntity>
```

The following sections describe attributes, child elements, and parent elements. 
  
    
    
 **Attributes**
  
    
    


|**Attribute **|**Description **|
|:-----|:-----|
|Namespace |Required. The namespace of the external content type that is the source of the  **Association** that contains this element.Attribute type: String |
|Name |Required. The name of the external content type that is the source of the  **Association** that contains this element.Attribute type:  **String**|
   
 **Child elements**
  
    
    
None 
  
    
    
 **Parent element**
  
    
    


|**Element **|**Description **|
|:-----|:-----|
| [Association Element in MethodInstances (BDCMetadata Schema)](http://msdn.microsoft.com/library/9659a1f5-1b12-03ef-f9e3-5c9904cc5dd0%28Office.15%29.aspx)|The  **Association** that contains this element.|
   

## TypeDescriptor element
<a name="bkmk_TypeDescriptor"> </a>

Specifies a  **TypeDescriptor**. 
  
    
    
 **Namespace:** `http://schemas.microsoft.com/windows/2007/BusinessDataCatalog`
  
    
    
 **Schema:** BDCMetadata
  
    
    



```XML
<TypeDescriptor TypeName = "String" LobName = "String" IdentifierEntityNamespace = "String" IdentifierEntityName = "String" IdentifierName = "String" ForeignIdentifierAssociationName = "String" ForeignIdentifierAssociationEntityName = "String" ForeignIdentifierAssociationEntityNamespace = "String" AssociatedFilter = "String" IsCollection = "Boolean" ReadOnly = "Boolean" CreatorField = "Boolean" UpdaterField = "Boolean" PreUpdaterField = "Boolean" Significant = "Boolean" Name = "String" DefaultDisplayName = "String" IsCached = "Boolean"> </TypeDescriptor>
```

The following sections describe attributes, child elements, and parent elements. 
  
    
    
 **Attributes**
  
    
    


|**Attribute **|**Description **|
|:-----|:-----|
|**TypeName**|Required. The identifier of the data type of the data structure that is represented by the  **TypeDescriptor**. Attribute type:  **String**|
|**LobName**|Optional. The data structure that is represented by the  **TypeDescriptor**. The default value of this attribute is the name of the  **TypeDescriptor**. For example, a line-of-business (LOB) system data structure named "CN1A" can be represented by a  **TypeDescriptor** with **Name** attribute equal to "Customer Name", if the **LobName** attribute of this **TypeDescriptor** is equal to "CN1A".Attribute type:  **String**|
|**IdentifierEntityNamespace**|Optional. The namespace of the external content type that contains the identifier that the  **TypeDescriptor** references. If the **TypeDescriptor** does not reference an **Identifier**, this attribute must not be present. When this attribute is present, the  **IdentifierEntityName** and **IdentifierName** attributes must also be present. The default value of this attribute is the namespace of the external content type that contains the method containing the parameter that contains the **TypeDescriptor**. Attribute type:  **String**|
|**IdentifierEntityName**|Optional. The name of the  **Entity** that contains the **Identifier** that the c **TypeDescriptor** references. If the **TypeDescriptor** does not reference an **Identifier**, this attribute must not be present. When this attribute is present, the  **IdentifierEntityNamespace** and **IdentifierName** attributes must also be present. The default value of this attribute is the name of the **Entity** that contains the **Method** containing the **Parameter** that contains the **TypeDescriptor**. Attribute type:  **String**|
|**IdentifierName**|Optional. The name of the  **Identifier** referenced by the **TypeDescriptor**. If the  **TypeDescriptor** does not reference an **Identifier**, this attribute must not be present. Attribute type:  **String**|
|**ForeignIdentifierAssociationName**|Optional. The name of the  **Association** referenced by the **TypeDescriptor**. If the  **TypeDescriptor** does not reference an **Association**, this attribute must not be present. When this attribute is present, the  **IdentifierName** attribute must also be present. The **ForeignIdentifierAssociationName** attribute must be specified when the **Identifier** referenced by this **TypeDescriptor** is related to an **Association**, and the  **Identifier** is contained by a source **Entity** of the **Association**. Attribute type:  **String**|
|**ForeignIdentifierAssociationEntityName**|Optional. The name of the  **Entity** that contains the **Association** referenced by the **TypeDescriptor**. If the  **TypeDescriptor** does not reference an **Association**, this attribute must not be present. When this attribute is present, the  **ForeignIdentifierAssociationEntityNamespace** and **ForeignIdentifierAssociationName** attributes must also be present. The default value of this attribute is the name of the **Entity** that contains the **Method** containing the **Parameter** that contains the **TypeDescriptor**. Attribute type:  **String**|
|**ForeignIdentifierAssociationEntityNamespace**|Optional. The namespace of the  **Entity** that contains the **Association** referenced by the **TypeDescriptor**. If the  **TypeDescriptor** does not reference an **Association**, this attribute must not be present. When this attribute is present, the  **ForeignIdentifierAssociationEntityName** and **ForeignIdentifierAssociationName** attributes must also be present. The default value of this attribute is the namespace of the **Entity** that contains the **Method** containing the **Parameter** that contains the **TypeDescriptor**. Attribute type:  **String**|
|**AssociatedFilter**|Optional. The name of a  **FilterDescriptor** that is associated with the **TypeDescriptor**. If the  **TypeDescriptor** is not associated with a **FilterDescriptor** this attribute must not be present.Attribute type:  **String**|
|**IsCollection**|Optional. Specifies whether the  **TypeDescriptor** represents a single data structure or a collection of data structures.Default value:  **false**Attribute type:  **Boolean**|
|**ReadOnly**|Optional. Specifies whether the data stored by the data structure represented by the  **TypeDescriptor** can be modified. This attribute must not be specified if the value of the **Direction** attribute of the **Parameter** that contains the **TypeDescriptor** is "In".Default value:  **false**Attribute type:  **Boolean**|
|**CreatorField**|Optional. Specifies whether the  **TypeDescriptor** represents a field for **MethodInstances** of type **Creator** that are contained by the **Method** that contains the **Parameter** containing the **TypeDescriptor**. Default value:  **false**Attribute type:  **Boolean**|
|**UpdaterField**|Optional. Specifies whether the  **TypeDescriptor** represents a field for **MethodInstances** of type **Updater** that are contained by the **Method** that contains the **Parameter** containing the **TypeDescriptor**. When this attribute is specified, a  **PreUpdaterField** attribute must not be specified.Default value:  **false**Attribute type:  **Boolean**|
|**PreUpdaterField**|Optional. Specifies whether data structure represented by the  **TypeDescriptor** stores the latest data value received from the external system of a field for **MethodInstances** of type **Updater**. When this attribute is specified, a  **UpdaterField** attribute must not be specified.Default value:  **false**Attribute type:  **Boolean**|
|**Significant**|Optional. Specifies whether values stored by the data structure represented by this  **TypeDescriptor** are included in calculating a hash code or comparing values stored in the data structures. For example, a **TypeDescriptor** representing a customer's last name is taken into account when determining whether a record has been modified, and so it is significant, whereas the **TypeDescriptor** representing the date on which the customer record is last modified typically is not taken into account to determine whether a record has been modified, and so it is not significant.Default value:  **true**Attribute type:  **Boolean**|
|**Name**|Required. The name of the  **TypeDescriptor**. Attribute type:  **String**> [!Note]  > The name of a  **TypeDescriptor** should not contain the special characters for forward slash ("/"), period ("."), or opening bracket ("[").          |
|**DefaultDisplayName**|Optional. The display name of the  **TypeDescriptor**. Attribute type:  **String**|
|**IsCached**|Optional. Specifies whether the  **TypeDescriptor** is used frequently.Default value:  **true**Attribute type:  **Boolean**|
   
 **Child elements**
  
    
    


|**Element **|**Description **|
|:-----|:-----|
| [LocalizedDisplayNames Element in MetadataObject (BDCMetadata Schema)](http://msdn.microsoft.com/library/3202aecf-f98f-20cb-1fdd-f3a054cb24aa%28Office.15%29.aspx)|The localized names of the  **TypeDescriptor**. |
| [Properties Element in MetadataObject (BDCMetadata Schema)](http://msdn.microsoft.com/library/9901904f-96ee-0cbb-64a9-c2aad9d72128%28Office.15%29.aspx)|The properties of the  **TypeDescriptor**. When the  **TypeDescriptor** is of type **System.String**, the  **Properties** element can contain a **Property** of type **System.Int32** with the **Name** attribute set to **Size**. The value of the  **Property** specifies the expected maximum string length of the value of the data structure described by this **TypeDescriptor**. |
| [Interpretation Element in TypeDescriptor (BDCMetadata Schema)](http://msdn.microsoft.com/library/730f9590-ab40-85b8-eb97-8fd9d8e33c8a%28Office.15%29.aspx)|The rules for the data stored by the data structure represented by the  **TypeDescriptor**. |
| [DefaultValues Element in TypeDescriptor (BDCMetadata Schema)](http://msdn.microsoft.com/library/635295d1-0f85-6308-976b-d0cb483dece6%28Office.15%29.aspx)|The default values of the  **TypeDescriptor**. |
| [TypeDescriptors Element in TypeDescriptor (BDCMetadata Schema)](http://msdn.microsoft.com/library/322b2d3f-c92d-3c24-9f22-07b56396275b%28Office.15%29.aspx)|The child  **TypeDescriptors** of the **TypeDescriptor**. |
   
 **Parent element**
  
    
    


|**Element **|**Description **|
|:-----|:-----|
| [TypeDescriptors Element in TypeDescriptor (BDCMetadata Schema)](http://msdn.microsoft.com/library/322b2d3f-c92d-3c24-9f22-07b56396275b%28Office.15%29.aspx)||
   

## TypeDescriptors element
<a name="bkmk_TypeDescriptors"> </a>

Specifies a list of  **TypeDescriptors** of a parent TypeDescriptor.
  
    
    
 **Namespace:** `http://schemas.microsoft.com/windows/2007/BusinessDataCatalog`
  
    
    
 **Schema:** BDCMetadata
  
    
    



```XML
<TypeDescriptors></TypeDescriptors>
```

The following sections describe attributes, child elements, and parent elements. 
  
    
    
 **Attributes**
  
    
    
None 
  
    
    
 **Child elements**
  
    
    


|**Element **|**Description **|
|:-----|:-----|
| [TypeDescriptor Element (BDCMetadata Schema)](http://msdn.microsoft.com/library/ae423de8-c13b-aea5-d47b-17ef786fb5a7%28Office.15%29.aspx)|A  **TypeDescriptor**. |
   
 **Parent element**
  
    
    


|**Element **|**Description **|
|:-----|:-----|
| [TypeDescriptor Element (BDCMetadata Schema)](http://msdn.microsoft.com/library/ae423de8-c13b-aea5-d47b-17ef786fb5a7%28Office.15%29.aspx)||
| [TypeDescriptor](http://msdn.microsoft.com/library/30e38d7f-af18-20ec-45ab-0bece071ce67.aspx)||
   

## Additional resources
<a name="bkmk_Addres"> </a>


-  [Changes in the BDC model schema for SharePoint 2013](changes-in-the-bdc-model-schema-for-sharepoint-2013.md)
    
  
-  [External content types in SharePoint 2013](external-content-types-in-sharepoint-2013.md)
    
  
-  [Get started using the client object model with external data in SharePoint 2013](get-started-using-the-client-object-model-with-external-data-in-sharepoint-2013.md)
    
  
-  [Business Connectivity Services in SharePoint 2013](business-connectivity-services-in-sharepoint-2013.md)
    
  
-  [What's new in Business Connectivity Services in SharePoint 2013](what-s-new-in-business-connectivity-services-in-sharepoint-2013.md)
    
  
-  [Get started with Business Connectivity Services in SharePoint 2013](get-started-with-business-connectivity-services-in-sharepoint-2013.md)
    
  
-  [Business Connectivity Services programmers reference for SharePoint 2013](business-connectivity-services-programmers-reference-for-sharepoint-2013.md)
    
  
