---
title: Get started with Business Connectivity Services in SharePoint 2013
ms.prod: SHAREPOINT
ms.assetid: c6bf3db0-db79-4b13-9834-891d24b2c9e5
---



# Get started with Business Connectivity Services in SharePoint 2013
Learn the basics of what Business Connectivity Services (BCS) provides to developers of SharePoint 2013 solutions, along with how to get started using BCS in various types of solutions. 
## What is Business Connectivity Services?


|||
|:-----|:-----|
|Business Connectivity Services (BCS) was introduced in SharePoint Server 2010 as an evolution of the Business Data Catalog released in Office SharePoint Server 2007. BCS enables SharePoint 2013 to work with data that is hosted externally. Possible sources can include databases, web services, Windows Communication Foundation (WCF) services, Open Data Protocol (OData) sources, and other proprietary data that is accessed by using custom .NET assemblies.  [![Get set up](images/mod_icon_getstartbox.gif)          ](get-started-with-business-connectivity-services-in-sharepoint-2013.md#SP15GettingStartedBCS_WhatDoYouNeed) [![Get to work](images/mod_icon_dobox.gif)          ](get-started-with-business-connectivity-services-in-sharepoint-2013.md#SP15GettingStartedBCS_WhatCanYouDo) [![Learn more](images/mod_icon_startbox.gif)          ](get-started-with-business-connectivity-services-in-sharepoint-2013.md#SP15GettingStartedBCS_LearnMore)|
**Watch the video: SharePoint 2013 business connectivity services and OData services overview**

  
    
    

  
    
    
![Videos](images/mod_icon_video.png)
  
    
    

  
    
    

  
    
    
|
   
In a dynamic workplace, information workers need access to data that resides in separate software worlds, for example: 
  
    
    

- Structured data that exists in the organization's enterprise applications, such as enterprise resource planning (ERP) and customer resource management (CRM) applications. 
    
  
- Unstructured data in business productivity applications, such as those in Microsoft Office, in team and collaboration applications such as SharePoint, and in Web 2.0 services such as Internet applications, wikis, blogs, and social networking sites. 
    
  
Although most information workers spend much of their work time within the productivity applications (for example, the Microsoft Office environment), they also need a way to integrate that environment with the enterprise applications and collaboration software and services they use. BCS provides that capability in SharePoint 2013. 
  
    
    

## Get started with Business Connectivity Services
<a name="SP15GettingStartedBCS_WhatDoYouNeed"> </a>

To get started developing with BCS, you will need the following: 
  
    
    

- SharePoint 2013 
    
  
- Visual Studio 
    
  
- Office Developer Tools for Visual Studio 2012 
    
    or 
    
  
- SharePoint Designer 
    
  
For information about how to set up your development environment, see  [Set up a general development environment for SharePoint 2013](set-up-a-general-development-environment-for-sharepoint-2013.md). 
  
    
    

### Business Connectivity Services essentials

The following table highlights the core concepts that you will need to be familiar with to start developing BCS solutions. 
  
    
    

**Table 1. Core concepts for understanding BCS**


|**Article**|**Description**|
|:-----|:-----|
| [Entity Data Model Key Concepts](http://msdn.microsoft.com/en-us/library/ee382840.aspx)|The Entity Data Model (EDM) uses three key concepts to describe the structure of data: entity type, association type, and property. These are the most important concepts in describing the structure of data in any implementation of the EDM. |
| [Basic Security Practices for Web Applications](http://msdn.microsoft.com/en-us/library/zdh19h94.aspx)|The topic of creating a secure web application is extensive. It requires study to understand security vulnerabilities. You also need to become familiar with the security facilities of the Windows operating system, the .NET Framework, and ASP.NET. Finally, it is essential to understand how to use these security features to counter threats. |
| [WCF Data Services](http://msdn.microsoft.com/en-us/data/odata.aspx)|WCF Data Services, formerly known as ADO.NET Data Services, enable the creation and consumption of OData services for the web. |
| [Open Data Protocol (OData)](http://www.odata.org)|OData is an industry standard protocol for accessing data through URLs. It basically sits on top of the HTTP protocol to provide read and write functions using existing HTTP verbs. |
| [Internet Information Services](http://www.iis.net/)|Internet Information Services (IIS) is the platform that SharePoint runs on. You should understand how to create websites, virtual directories, web services, URLs, web security, and other technologies related to IIS. |
| [External content types in SharePoint 2013](external-content-types-in-sharepoint-2013.md)|External content types are descriptions of the external systems that they represent. They are reusable when imported into SharePoint and can be used to create complex code-free solutions using SharePoint Designer 2013, Outlook 2013, Web Parts, external lists, and custom client applications. |
| [Get started using the client object model with external data in SharePoint 2013](get-started-using-the-client-object-model-with-external-data-in-sharepoint-2013.md)|SharePoint 2013 provides the ability to access all objects through a carefully constructed URL. BCS has been extended to provide this same functionality. |
   

## What can you do with Business Connectivity Services?
<a name="SP15GettingStartedBCS_WhatCanYouDo"> </a>

With BCS, you can bring information into SharePoint from many different sources. For example, you can bring data from an external SQL Server database, a traditional web service, a WCF service, proprietary systems, and OData services. 
  
    
    

**Table 2. Basic tasks for working with Business Connectivity Services**


|**Task**|**Description**|
|:-----|:-----|
| [External content types in SharePoint 2013](external-content-types-in-sharepoint-2013.md)|Learn about creating Business Connectivity Services (BCS) external content types. |
| [How to: Create an external content type from an OData source in SharePoint 2013](how-to-create-an-external-content-type-from-an-odata-source-in-sharepoint-2013.md)|Find information that is needed to get started creating external content types based on OData sources and using that data in SharePoint or Office components. |
| [How to: Create external event receivers](how-to-create-external-event-receivers.md)|Learn the concepts behind creating event receivers that can be attached to external lists and will execute when the external data that the list represents is updated. |
| [How to: Create an add-in-scoped external content type in SharePoint 2013](how-to-create-an-add-in-scoped-external-content-type-in-sharepoint-2013.md)|Learn how to create external content types that are installed or scoped at the app level, enabling developers to create data-rich apps using external data sources. |
| [How to: Use the client code library to access external data in SharePoint 2013](how-to-use-the-client-code-library-to-access-external-data-in-sharepoint-2013.md)|Learn how to use the SharePoint 2013 client object model to work with BCS in SharePoint 2013. |
   

## Beyond the basics: Learn more about Business Connectivity Services
<a name="SP15GettingStartedBCS_LearnMore"> </a>

When you master the basic concepts of BCS, you can use the more advanced features to build many powerful types of solutions. 
  
    
    

**Table 3. Advanced concepts in BCS**


|**Topic**|**Description**|
|:-----|:-----|
| [How to: Create an OData data service for use as a BCS external system](how-to-create-an-odata-data-service-for-use-as-a-bcs-external-system.md)|Learn how to create an Internet-addressable WCF service that uses OData to send notifications to SharePoint 2013 when the underlying data changes. These notifications are used to trigger events that are attached to external lists. |
| [BDC model schema reference for SharePoint 2013](bdc-model-schema-reference-for-sharepoint-2013.md)|Find reference documentation for the schema of the BDC model. |
| [BCS client object model reference for SharePoint 2013](bcs-client-object-model-reference-for-sharepoint-2013.md)|Get a summary of the objects that are available for creating client-side scripts using the SharePoint 2013 client object model to access external data exposed by Business Connectivity Services (BCS). |
| [BCS REST API reference for SharePoint 2013](bcs-rest-api-reference-for-sharepoint-2013.md)|Find reference information for constructing Representational State Transfer (REST) URIs used for accessing and manipulating OData sources. |
   

## Additional resources
<a name="SP15GettingStartedBCS_LearnMore"> </a>


-  [Business Connectivity Services in SharePoint 2013](business-connectivity-services-in-sharepoint-2013.md)
    
  
-  [Open Data Protocol website](http://www.odata.org/)
    
  
-  [External content types in SharePoint 2013](external-content-types-in-sharepoint-2013.md)
    
  
-  [Using OData sources with Business Connectivity Services in SharePoint 2013](using-odata-sources-with-business-connectivity-services-in-sharepoint-2013.md)
    
  
-  [External events and alerts in SharePoint 2013](external-events-and-alerts-in-sharepoint-2013.md)
    
  
-  [Add-in-scoped external content types in SharePoint 2013](add-in-scoped-external-content-types-in-sharepoint-2013.md)
    
  
-  [Get started using the client object model with external data in SharePoint 2013](get-started-using-the-client-object-model-with-external-data-in-sharepoint-2013.md)
    
  
