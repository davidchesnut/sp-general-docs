---
title: BCS client object model reference for SharePoint 2013
ms.prod: SHAREPOINT
ms.assetid: fe7d12a3-6ea9-47f9-b69e-f66da9e661dc
---



# BCS client object model reference for SharePoint 2013

  
    
    
![Class libraries and references](images/mod_icon_badge_reference.png)
  
    
    

  
    
    

  
    
    
Learn about the objects that are available for creating client-side scripts using the SharePoint 2013 client object model to access external data exposed by Business Connectivity Services (BCS). 
The following objects are available for creating client-side scripts using the SharePoint 2013 client object model to access external data that is exposed by Business Connectivity Services (BCS). The BCS object model components that are exposed to the client object model are located in Microsoft.SharePoint.Client.dll. 
  
    
    


## Entity object
<a name="bkmk_Entity"> </a>

The **Entity** object essentially represents a table in a database. The methods and properties presented here show the objects that can be manipulated through the use of the client code library. Each of these calls maps directly to a server object model call. However, they are callable by a detached client, such as in a web browser using JavaScript.
  
    
    

**Methods**


|**Methods**|**Method signature**|**Description**|
|:-----|:-----|:-----|
|**Create**| `Identity Create(FieldValueDictionary fieldValues, LobSystemInstance lobSystemInstanceName)`||
|**FindSpecificDefault**| `EntityInstance FindSpecificDefault(Identity identity, LobSystemInstance lobSystemInstanceName)`||
|**FindspecificByBdcIDDefault**| `EntityInstance FindSpecific(Identity identity, string specificFinderName, LobSystemInstance lobSystemInstanceName)`||
|**FindSpecificByBdcID**| `EntityInstance FindSpecificByBdcIDDefault(string BdcIdentity, LobSystemInstance lobSystemInstanceName)`||
|**GetCreatorView**| `EntityInstance FindSpecificByBdcID(string BdcIdentity, string specificFinderName,LobSystemInstance LobSystemInstanceName)`||
|**GetDefaultSpecificFinderView**| `View GetCreatorView(string methodInstanceName)`||
|**GetSpecificFinderView_Client**| `View GetDefaultSpecificFinderView()`||
|**GetUpdaterView_Client**| `View GetSpecificFinderView_Client( string specificFinderName)`||
|**GetIdentifiers**| `View GetUpdaterView_Client(string updaterName)`||
|**GetIdentifiers()**|||
   

**Properties**


|**Property**|**Description**|
|:-----|:-----|
| `long EstimatedInstanceCount { get; }`|Gets the number of expected external items of this external content type. |
| `string Name { get; }`|Gets the name of the metadata object. |
| `string Namespace { get; }`|Gets the namespace of the given data class. |
| `int GetIdentifierCount()`||
   

## EntityInstance method
<a name="bkmk_EntityInstance"> </a>


**Namespaces**


|**Managed**|**JavaScript**|
|:-----|:-----|
|**Microsoft.BusinessData.Runtime**|**SP.BusinessData.Runtime**|
   

**Methods**


|**Method**|**Return type**|**Description**|
|:-----|:-----|:-----|
|**Delete**|void |Deletes the External Item. |
|**FromXml**|void |Sets the values in this dictionary from specified XML. **Method signature**          `FromXml(string xml)`|
|**GetIdentity**|Identity |Gets the identity of this External Item. |
|**Delete**|void |Deletes the External Item. |
|**ToXml**|string |Retrieves the values in XML format. |
|**Update**|void |Submits the changes made to the External Item. |
   

  
    
    

**Properties**


|**Property**|**Return type**|**Description**|
|:-----|:-----|:-----|
| `this[string fieldDotNotation] { get; set; }`|Object |Gets or sets the value of the field referred to by the dot notation. |
| `RelatedSpecificFinderName { get; }`|string ||
   

## EntityView method
<a name="bkmk_entityview"> </a>

Specifies a customized view of the **Entity** data
  
    
    

**Namespaces**


|**Managed**|**JavaScript**|
|:-----|:-----|
|**Microsoft.BusinessData.MetadataModel**|**SP.BusinessData**|
   

**Methods**


|**Method**|**Return type**|**Description**|
|:-----|:-----|:-----|
|**GetDefaultValues_Client()**|**FieldValueDictionary**|Gets a field value dictionary that contains the default values for this view. |
|**GetXmlSchema()**|**string**|Gets the XML Schema of the view. |
|**GetType(string fieldDotNotation)**|**string**|Gets the type of the specified field. |
|**GetType(string fieldDotNotation)**|**TypeDescriptor**|Gets the **TypeDescriptor** object that corresponds to the given dot notation.|
   

**Properties**


|**Property**||**Description**|
|:-----|:-----|:-----|
| `Fields { get; }`|**FieldCollection**|Gets the collection of fields in the view. |
| `Name { get; }`|**string**|Gets the name of this **View** object|
| `RelatedSpecificFinderName { get; }`|**string**|Retrieves the name of the specific finder **MethodInstance** that this view is tied to.|
   

## LobSystem method
<a name="bkmk_LobSystem"> </a>


  
    
    

**Namespaces**


|**Managed**|**JavaScript**|
|:-----|:-----|
|**Microsoft.BusinessData.MetadataModel**|**SP.BusinessData**|
   

**Methods**


|**Method**|**Return type**|**Description**|
|:-----|:-----|:-----|
|**GetLobSystemInstances()**|**void**|Gives the list of LOB system instances. |
|**Name**|**void**|Gets the name of the **LobSystem**. |
   

**Properties**


|**Property**|**Description**|
|:-----|:-----|
|None. ||
   

## LobSystemInstance method
<a name="bkmk_LobSystemInstance"> </a>


  
    
    

**Namespaces**


|**Managed**|**JavaScript**|
|:-----|:-----|
|**Microsoft.BusinessData.MetadataModel**|**SP.BusinessData**|
   

**Methods**


|**Method**|**Return type**|**Description**|
|:-----|:-----|:-----|
|None. |**void**||
   

**Properties**


|**Property**|**Description**|
|:-----|:-----|
|None. ||
   

## Identifier method
<a name="bkmk_Identifier"> </a>


  
    
    

**Namespaces**


|**Managed**|**JavaScript**|
|:-----|:-----|
|**Microsoft.BusinessData.MetadataModel**|**SP.BusinessData**|
   

**Methods**


|**Method**|**Return type**|**Description**|
|:-----|:-----|:-----|
|**ContainsLocalizedDisplayName**|**bool**|Determines whether the metadata object contains localized display name. |
|**GetDefaultDisplayName**|**string**|Returns the default display name. |
|**GetLocalizedDisplayName**|**string**|Returns the localized display name. |
   

**Properties**


|**Property**|**Return type**|**Description**|
|:-----|:-----|:-----|
| `IdentifierType {get;}`|**string**|Returns the type of identifier. |
| `Name {get;}`|**string**|Gets the name of the identifier. |
   

## IdentifierCollection method
<a name="bkmk_IdentifierCollection"> </a>


  
    
    

**Namespaces**


|**Managed**|**JavaScript**|
|:-----|:-----|
|**Microsoft.BusinessData.MetadataModel.Collections**|**SP.BusinessData.Collections**|
   

**Methods**


|**Method**|**Return type**|**Description**|
|:-----|:-----|:-----|
|None. |**void**||
   

**Properties**


|**Property**|**Description**|
|:-----|:-----|
|None. ||
   

## Identity method
<a name="bkmk_Identity"> </a>


  
    
    

**Namespaces**


|**Managed**|**JavaScript**|
|:-----|:-----|
|**Microsoft.BusinessData.Runtime**|**SP.BusinessData.Runtime**|
   

**Constructor**


|**Constructor**|**Description**|
|:-----|:-----|
| `public Identity (Object[] identifierValues)`|Constructs a new instance of the class by using an array of identifier values. |
   

**Methods**


|**Method**|**Return type**|**Description**|
|:-----|:-----|:-----|
|**Serialize**|**string**|Gets a string representation of the identity. |
   

**Properties**


|**Property**|**Return type**|**Description**|
|:-----|:-----|:-----|
| `IdentifierCount { get; }`|**int**|Returns the number of identifiers. |
| `IsTemporary { get; }`|**bool**|Checks whether the identity is temporary. |
| `this[int identifierIndex] { get; }`|**Object**|Retrieves the element at the given index. CSOM does not support int-based indexing. String-based accessor implemented for the same. |
| `TemporaryId { get; }`|**Guid**|Returns the temporary part of the identity. |
   

## FieldValueDictionary method
<a name="bkmk_FieldValueDictionary"> </a>


  
    
    

**Namespaces**


|**Managed**|**JavaScript**|
|:-----|:-----|
|**Microsoft.BusinessData.Runtime**|**SP.BusinessData.Runtime**|
   

**Methods**


|**Method**|**Return type**|**Description**|
|:-----|:-----|:-----|
|**FromXml**|**void**|Sets the values in this dictionary from specified XML. |
|**GetCollectionSize**|int |Returns the size of the collection that the dot notation refers to. |
|**ToXml**|string |Retrieves the values in XML format. |
   

**Properties**


|**Property**|**Description**|
|:-----|:-----|
| `Object this[string fieldDotNotation] { get; set; }`|Gets or sets the value of the field referred to by the dot notation. |
   

## EntityFieldCollection method
<a name="bkmk_EntityFieldCollection"> </a>


  
    
    

**Namespaces**


|**Managed**|**JavaScript**|
|:-----|:-----|
|**Microsoft.BusinessData.Runtime**|**SP.BusinessData.Runtime**|
   

**Methods**


|**Method**|**Return type**|**Description**|
|:-----|:-----|:-----|
|None. |**void**||
   

**Properties**


|**Property**|**Description**|
|:-----|:-----|
|None. ||
   

## EntityField method
<a name="bkmk_Entityfield"> </a>


  
    
    

**Namespaces**


|**Managed**|**JavaScript**|
|:-----|:-----|
|**Microsoft.BusinessData.Runtime**|**SP.BusinessData.Runtime**|
   

**Methods**


|**Method**|**Return type**|**Description**|
|:-----|:-----|:-----|
|None. |void ||
   

**Properties**


|**Property**|**Return type**|**Read Only**|**Description**|
|:-----|:-----|:-----|:-----|
|**ContainsLocalizedDisplayName**|**Boolean**|Yes |Determines whether the field contains a localized display name. |
|**DefaultDisplayName**|**string**|Yes |Retrieves the default display name of the Field. |
|**GetLocalizedDisplayName**|**string**||Retrieves the localized display name of the Field. |
|**Name**|**string**|Yes |Retrieves the name of the Field. |
   

## TypeDescriptor class
<a name="bkmk_TypeDescriptor"> </a>


  
    
    

**Namespaces**


|**Managed**|**JavaScript**|
|:-----|:-----|
|**Microsoft.BusinessData.MetadataModel**|**SP.BusinessData**|
   

**Methods**


|**Method**|**Return type**|**Read Only**|**Description**|
|:-----|:-----|:-----|:-----|
|**ContainsLocalizedDisplayName()**|**Boolean**|Yes |Determines whether the type descriptor contains a localized display name. |
|**GetLocalizedDisplayName()**|**string**|Yes |Returns the localized display name. |
|**GetDefaultDisplayName()**|**string**||Returns the default display name. |
   

**Properties**


|**Property**|**Return type**|**Description**|
|:-----|:-----|:-----|
|**Name**|string |Retrieves the name of the Field. |
|**TypeName**|string |Retrieves the name of the data type represented by this type descriptor. |
|**IsReadOnly**|Boolean |Determines whether this type descriptor represents a read-only data structure. |
|**ContainsReadOnly**|Boolean |Determines whether this type descriptor or one of its children represent a read-only data structure. |
|**IsCollection**|Boolean |Determines whether the described type represents a collection data structure. |
   

## Interfaces
<a name="bkmk_Interfaces"> </a>

The namespace is **Microsoft.BusinessData.MetadataModel**. 
  
    
    


|**Interface**|**Description**|
|:-----|:-----|
|**IMetadataCatalog**|The entry point into the BDC object model. Use the **DatabaseBasedMetadataCatalog** on the server.|
|**ILobSystem**|Contains the details about an external system. |
|**IEntity**|An external content type in the BDC Metadata Store. |
|**IMethod**|An operation that can be performed on the external content type. |
|**IEntityInstance**|An entity instance (also known as external item) is a single item returned from an external system in BDC. The **IEntityInstance** interface abstracts the underlying data sources and insulates the clients from having to learn application-specific coding paradigms; it enables them to access all business data in a single, simplified way. By using the **IEntityInstance** interface, you can work with a row of data from a database in just the same way as working with a complex .NET Framework structure returned by a web service.An entity instance in BDC has special semantics attached to it. For example, it has the ability to know which field or fields in the row represent the identifier for the entity instance, and it enables you to call methods, such as **GetAssociated**, **GetIdentifierValues**, and **Execute**, on that entity instance. |
|**IEntityInstanceEnumerator**|Enumerators can be used to read the data in the external items collection, but they cannot be used to modify the underlying collection. **IEntityInstanceEnumerator** supports streaming and is therefore very useful when the back-end application returns large amounts of data.|
   

## Client Object model FAQ
<a name="bkmk_ClientObjectModelFAQ"> </a>


- **Does the <Method> tag need to be included in a CAML query when querying an external list**
    
    No. 
    
  
- **Do all fields in the external list need to be specified in the CAML query?**
    
    Using the ViewXML tag in the BDC model, the developer can specify only those fields that are required and the CSOM APIs for Lists will return only those fields. 
    
  

## Additional resources
<a name="bkmk_Addres"> </a>


-  [Business Connectivity Services programmers reference for SharePoint 2013](business-connectivity-services-programmers-reference-for-sharepoint-2013.md)
    
  
-  [.NET client API reference for SharePoint Online](http://msdn.microsoft.com/library/88e5e1b9-eab2-4f3b-a3f2-75c96b86f1f4%28Office.15%29.aspx)
    
  
-  [Get started using the client object model with external data in SharePoint 2013](get-started-using-the-client-object-model-with-external-data-in-sharepoint-2013.md)
    
  
-  [How to: Use the client code library to access external data in SharePoint 2013](how-to-use-the-client-code-library-to-access-external-data-in-sharepoint-2013.md)
    
  
-  [What's new in Business Connectivity Services in SharePoint 2013](what-s-new-in-business-connectivity-services-in-sharepoint-2013.md)
    
  
-  [Get started with Business Connectivity Services in SharePoint 2013](get-started-with-business-connectivity-services-in-sharepoint-2013.md)
    
  
