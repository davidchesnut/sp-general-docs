---
title: Work with user profiles in SharePoint 2013
ms.prod: SHAREPOINT
ms.assetid: 7437a7a8-85cb-4233-84af-1eec30dd54b2
---



# Work with user profiles in SharePoint 2013
Learn about common programming tasks for working with user profiles in SharePoint Server 2013. 
## APIs for working with user profiles in SharePoint 2013
<a name="bkmk_APIversions"> </a>

User profiles and user profile properties provide information about SharePoint users. SharePoint Server 2013 provides the following APIs that you can use to programmatically work with user profiles: 
  
    
    

- Client object models for managed code 
    
  - .NET client object model 
    
  
  - Silverlight client object model 
    
  
  - Mobile client object model 
    
  
- JavaScript object model 
    
  
- Representational State Transfer (REST) service 
    
  
- Server object model 
    
  
As a best practice in SharePoint 2013 development, use client APIs when you can. Client APIs include the .NET client object model, the JavaScript object model, and the REST service. For more information about the APIs in SharePoint 2013 and when to use them, see  [Choose the right API set in SharePoint 2013](choose-the-right-api-set-in-sharepoint-2013.md). 
  
    
    

> [!NOTE]  
> Not all functionality that you find in the **Microsoft.Office.Server.UserProfiles**assembly is available from client APIs. For example, you have to use the server object model to create or change user profiles because they're read-only from client APIs (except the user profile picture). Also, there's no client-side access to some namespaces, such as [Microsoft.Office.Server.Audience](https://msdn.microsoft.com/library/Microsoft.Office.Server.Audience.aspx) , [Microsoft.Office.Server.ReputationModel](https://msdn.microsoft.com/library/Microsoft.Office.Server.ReputationModel.aspx) , or [Microsoft.Office.Server.SocialData](https://msdn.microsoft.com/library/Microsoft.Office.Server.SocialData.aspx) . To see what's supported functionality for the client APIs, see [Microsoft.SharePoint.Client.Social](https://msdn.microsoft.com/library/Microsoft.SharePoint.Client.Social.aspx) and [Microsoft.SharePoint.Client.UserProfiles](https://msdn.microsoft.com/library/Microsoft.SharePoint.Client.UserProfiles.aspx) .
  
    
    

Each API includes a manager object that you use to perform core profile-related tasks. Table 1 shows the manager and other key objects (or REST resources) in the APIs and the class library (or access point) where you can find them. 
  
    
    

> [!NOTE]  
> The Silverlight and mobile client object models are not included in Table 1 or Table 2 because they provide the same core functionality as the .NET client object model and use the same signatures. The Silverlight client object model is defined in Microsoft.SharePoint.Client.UserProfiles.Silverlight.dll, and the mobile client object model is defined in Microsoft.SharePoint.Client.UserProfiles.Phone.dll. 
  
    
    


**Table 1. SharePoint 2013 APIs used for working with user profiles programmatically**

|||
|:-----|:-----|
|.NET client object model See:  [How to: Retrieve user profile properties by using the .NET client object model in SharePoint 2013](how-to-retrieve-user-profile-properties-by-using-the-net-client-object-model-in.md)|Manager object:            [PeopleManager](https://msdn.microsoft.com/library/Microsoft.SharePoint.Client.UserProfiles.PeopleManager.aspx)Primary namespace:            [Microsoft.SharePoint.Client.UserProfiles](https://msdn.microsoft.com/library/Microsoft.SharePoint.Client.UserProfiles.aspx)Other key objects:            [PersonProperties](https://msdn.microsoft.com/library/Microsoft.SharePoint.Client.UserProfiles.PersonProperties.aspx) , [ProfileLoader](https://msdn.microsoft.com/library/Microsoft.SharePoint.Client.UserProfiles.ProfileLoader.aspx) , [UserProfile](https://msdn.microsoft.com/library/Microsoft.SharePoint.Client.UserProfiles.UserProfile.aspx)Class library:           Microsoft.SharePoint.Client.UserProfiles.dll |
|JavaScript object model See:  [How to: Retrieve user profile properties by using the JavaScript object model in SharePoint 2013](how-to-retrieve-user-profile-properties-by-using-the-javascript-object-model-in.md)|Manager object:            [PeopleManager](http://msdn.microsoft.com/library/985fd2df-0e31-6ece-b846-ba2ccb156d00%28Office.15%29.aspx)Primary namespace:            [SP.UserProfiles](http://msdn.microsoft.com/library/8c1fcceb-cd9a-b25c-32f4-1cfb0578278c%28Office.15%29.aspx)Other key objects:            [PersonProperties](http://msdn.microsoft.com/library/0274d97f-b697-f436-2aaf-f5bcf9b70df8%28Office.15%29.aspx),  [ProfileLoader](http://msdn.microsoft.com/library/c8dd9919-66a9-fffc-1100-14472d2ec2cb%28Office.15%29.aspx),  [UserProfile](http://msdn.microsoft.com/library/f8c4a219-fbaa-2e50-1bd5-fdc80051b33d%28Office.15%29.aspx)Class library:           SP.UserProfiles.js |
|REST service See:  [User profiles REST API reference](http://msdn.microsoft.com/library/10757ed1-6e86-474f-89e0-6dec6aa66a2b%28Office.15%29.aspx)|Manager resource:            [PeopleManager](http://msdn.microsoft.com/library/10757ed1-6e86-474f-89e0-6dec6aa66a2b%28Office.15%29.aspx#bk_PeopleManager)Endpoint URI:            `http://<siteUri>/_api/SP.UserProfiles.PeopleManager`Primary namespace:           **SP.UserProfiles**Other key resources:            [PersonProperties](http://msdn.microsoft.com/library/10757ed1-6e86-474f-89e0-6dec6aa66a2b%28Office.15%29.aspx#bk_PersonProperties),  [ProfileLoader](http://msdn.microsoft.com/library/10757ed1-6e86-474f-89e0-6dec6aa66a2b%28Office.15%29.aspx#bk_ProfileLoader),  [UserProfile](http://msdn.microsoft.com/library/10757ed1-6e86-474f-89e0-6dec6aa66a2b%28Office.15%29.aspx#bk_UserProfile)|
|Server object model See:  [How to: Work with user profiles and organization profiles by using the server object model in SharePoint 2013](how-to-work-with-user-profiles-and-organization-profiles-by-using-the-server-obj.md)|Manager objects:            [UserProfileManager](https://msdn.microsoft.com/library/Microsoft.Office.Server.UserProfiles.UserProfileManager.aspx) , [PeopleManager](https://msdn.microsoft.com/library/Microsoft.Office.Server.UserProfiles.PeopleManager.aspx)Primary namespace:            [Microsoft.Office.Server.UserProfiles](https://msdn.microsoft.com/library/Microsoft.Office.Server.UserProfiles.aspx)Other key objects:            [UserProfile](https://msdn.microsoft.com/library/Microsoft.Office.Server.UserProfiles.UserProfile.aspx) , [CorePropertyManager](https://msdn.microsoft.com/library/Microsoft.Office.Server.UserProfiles.CorePropertyManager.aspx) , [ProfilePropertyManager](https://msdn.microsoft.com/library/Microsoft.Office.Server.UserProfiles.ProfilePropertyManager.aspx) , [ProfileSubtypeManager](https://msdn.microsoft.com/library/Microsoft.Office.Server.UserProfiles.ProfileSubtypeManager.aspx) , [ProfileSubtypePropertyManager](https://msdn.microsoft.com/library/Microsoft.Office.Server.UserProfiles.ProfileSubtypePropertyManager.aspx) , [ProfileTypePropertyManager](https://msdn.microsoft.com/library/Microsoft.Office.Server.UserProfiles.ProfileTypePropertyManager.aspx)Class library:           Microsoft.Office.Server.UserProfiles.dll |
   

## Common programming tasks for working with user profiles in SharePoint 2013
<a name="bkmk_CommonTasks"> </a>

Table 2 shows common programming tasks for working with user profiles and the members that you use to perform them. Members are from the .NET client object model (CSOM), JavaScript object model (JSOM), REST service, and server object model (SSOM). 
  
    
    

**Table 2. API for common programming tasks for working with user profiles**


|**Task**|**Members**|
|:-----|:-----|
|Create an instance of a manager object in the context of the current user |CSOM:  [PeopleManager](https://msdn.microsoft.com/library/Microsoft.SharePoint.Client.UserProfiles.PeopleManager.#ctor.aspx)JSOM:  [PeopleManager](http://msdn.microsoft.com/library/985fd2df-0e31-6ece-b846-ba2ccb156d00%28Office.15%29.aspx)REST:  [PeopleManager](http://msdn.microsoft.com/library/10757ed1-6e86-474f-89e0-6dec6aa66a2b%28Office.15%29.aspx#bk_PeopleManager)          **GET**`http://<siteUri>/_api/SP.UserProfiles.PeopleManager`SSOM:  [UserProfileManager](https://msdn.microsoft.com/library/Microsoft.Office.Server.UserProfiles.UserProfileManager.#ctor.aspx) (overloaded) or [PeopleManager](https://msdn.microsoft.com/library/Microsoft.Office.Server.UserProfiles.PeopleManager.#ctor.aspx)|
|Change the current user's profile picture |CSOM:  [SetMyProfilePicture](https://msdn.microsoft.com/library/Microsoft.SharePoint.Client.UserProfiles.PeopleManager.SetMyProfilePicture.aspx)JSOM:  [setMyProfilePicture](http://msdn.microsoft.com/library/a4f8d745-f211-e750-4fd0-047091804683%28Office.15%29.aspx)REST:  [SetMyProfilePicture](http://msdn.microsoft.com/library/10757ed1-6e86-474f-89e0-6dec6aa66a2b%28Office.15%29.aspx#bk_PeopleManagerSetMyProfilePicture)          **POST**`http://<siteUri>/_api/SP.UserProfiles.PeopleManager/SetMyProfilePicture` and pass the _picture_ parameter in the request bodySSOM:  [UserProfile](https://msdn.microsoft.com/library/Microsoft.Office.Server.UserProfiles.UserProfile.aspx) [PropertyConstants.PictureUrl].Value or [SetMyProfilePicture](https://msdn.microsoft.com/library/Microsoft.Office.Server.UserProfiles.PeopleManager.SetMyProfilePicture.aspx)|
|Get the current user's properties |CSOM:  [GetMyProperties](https://msdn.microsoft.com/library/Microsoft.SharePoint.Client.UserProfiles.PeopleManager.GetMyProperties.aspx)JSOM:  [getMyProperties](http://msdn.microsoft.com/library/be001abc-a431-8d48-8e6f-161251aa19ac%28Office.15%29.aspx)REST:  [GetMyProperties](http://msdn.microsoft.com/library/10757ed1-6e86-474f-89e0-6dec6aa66a2b%28Office.15%29.aspx#bk_PeopleManagerGetMyProperties)          **GET**`http://<siteUri>/_api/SP.UserProfiles.PeopleManager/GetMyProperties`          (or get some basic user properties from  `/_api/social.feed/my` or `/_api/social.following/my`) SSOM:  [GetUserProfile](https://msdn.microsoft.com/library/Microsoft.Office.Server.UserProfiles.UserProfileManager.GetUserProfile.aspx)|
|Get a particular user's properties |CSOM:  [GetPropertiesFor](https://msdn.microsoft.com/library/Microsoft.SharePoint.Client.UserProfiles.PeopleManager.GetPropertiesFor.aspx)JSOM:  [getPropertiesFor](http://msdn.microsoft.com/library/097464db-2630-4c7a-fd0c-0f333680b5a4%28Office.15%29.aspx)REST:  [GetPropertiesFor](http://msdn.microsoft.com/library/10757ed1-6e86-474f-89e0-6dec6aa66a2b%28Office.15%29.aspx#bk_PeopleManagerGetPropertiesFor)          **GET**`http://<siteUri>/_api/SP.UserProfiles.PeopleManager/GetPropertiesFor(accountName=@v)?@v='domain\\\\user'`SSOM:  [GetUserProfile](https://msdn.microsoft.com/library/Microsoft.Office.Server.UserProfiles.UserProfileManager.GetUserProfile.aspx) (overloaded) or [GetPropertiesFor](https://msdn.microsoft.com/library/Microsoft.Office.Server.UserProfiles.PeopleManager.GetPropertiesFor.aspx)|
|Get the user profile properties for a particular user |CSOM:  [GetUserProfilePropertiesFor](https://msdn.microsoft.com/library/Microsoft.SharePoint.Client.UserProfiles.PeopleManager.GetUserProfilePropertiesFor.aspx)JSOM:  [getUserProfilePropertiesFor](http://msdn.microsoft.com/library/8674e96f-d320-4a50-1580-9a4568842ee5%28Office.15%29.aspx)REST: not implemented           Call [GetPropertiesFor](http://msdn.microsoft.com/library/10757ed1-6e86-474f-89e0-6dec6aa66a2b%28Office.15%29.aspx#bk_PeopleManagerGetPropertiesFor) and then get the user profile properties from the**UserProfileProperties**property of the returned**PersonProperties**object.SSOM:  [GetEnumerator](https://msdn.microsoft.com/library/Microsoft.Office.Server.UserProfiles.UserProfile.GetEnumerator.aspx)|
|Get a specific user profile property for a user |CSOM:  [GetUserProfilePropertyFor](https://msdn.microsoft.com/library/Microsoft.SharePoint.Client.UserProfiles.PeopleManager.GetUserProfilePropertyFor.aspx)JSOM:  [getUserProfilePropertyFor](http://msdn.microsoft.com/library/da048bfa-54c6-8216-e8ef-09bd84f68d8d%28Office.15%29.aspx)REST:  [GetUserProfilePropertyFor](http://msdn.microsoft.com/library/10757ed1-6e86-474f-89e0-6dec6aa66a2b%28Office.15%29.aspx#bk_PeopleManagerGetUserProfilePropertyFor)          **GET**`http://<siteUri>/_api/SP.UserProfiles.PeopleManager/GetUserProfilePropertyFor(accountName=@v,propertyName='PreferredName')?@v='domain\\\\user'`SSOM:  [UserProfile](https://msdn.microsoft.com/library/Microsoft.Office.Server.UserProfiles.UserProfile.aspx) (overloaded) and specify the property name in the indexer|
|Get a user profile |CSOM:  [GetUserProfile](https://msdn.microsoft.com/library/Microsoft.SharePoint.Client.UserProfiles.ProfileLoader.GetUserProfile.aspx) (returns the [client-side user profile](work-with-user-profiles-in-sharepoint-2013.md#bkmk_NewUserObjects) for the current user only)JSOM:  [getUserProfile](http://msdn.microsoft.com/library/8e30e811-5da1-b6d0-a8b5-befea9b22496%28Office.15%29.aspx) (returns the [client-side user profile](work-with-user-profiles-in-sharepoint-2013.md#bkmk_NewUserObjects) for the current user only)REST:  [GetProfileLoader](http://msdn.microsoft.com/library/10757ed1-6e86-474f-89e0-6dec6aa66a2b%28Office.15%29.aspx#bk_ProfileLoaderGetProfileLoader)          **POST**`http://<siteUri>/_api/SP.UserProfiles.ProfileLoader.GetProfileLoader/GetUserProfile` (returns the [client-side user profile](work-with-user-profiles-in-sharepoint-2013.md#bkmk_NewUserObjects) for the current user only)SSOM:  [GetUserProfile](https://msdn.microsoft.com/library/Microsoft.Office.Server.UserProfiles.UserProfileManager.GetUserProfile.aspx) (overloaded)|
|Find out whether a user account exists |CSOM: not implemented JSOM: not implemented REST: not implemented SSOM:  [UserExists](https://msdn.microsoft.com/library/Microsoft.Office.Server.UserProfiles.UserProfileManager.UserExists.aspx)|
|Create or change user profiles and user profile properties and attributes (Client APIs can change the profile picture. See the "Change the user's profile picture" task in this table.) |CSOM: not implemented JSOM: not implemented REST: not implemented SSOM: multiple—see  [How to: Work with user profiles and organization profiles by using the server object model in SharePoint 2013](how-to-work-with-user-profiles-and-organization-profiles-by-using-the-server-obj.md)|
|Delete a user profile |CSOM: not implemented JSOM: not implemented REST: not implemented SSOM:  [RemoveProfile](https://msdn.microsoft.com/library/Microsoft.Office.Server.UserProfiles.UserProfileManager.RemoveProfile.aspx) or [RemoveUserProfile](https://msdn.microsoft.com/library/Microsoft.Office.Server.UserProfiles.UserProfileManager.RemoveUserProfile.aspx) (overloaded)|
|Provision a user's personal site |CSOM:  [CreatePersonalSiteEnque](https://msdn.microsoft.com/library/Microsoft.SharePoint.Client.UserProfiles.UserProfile.CreatePersonalSiteEnque.aspx) (overloaded)JSOM:  [createPersonalSiteEnque](http://msdn.microsoft.com/library/f4bcb82d-4048-0b29-9bc6-ce70ead49988%28Office.15%29.aspx) (overloaded)REST:  [CreatePersonalSiteEnque](http://msdn.microsoft.com/library/10757ed1-6e86-474f-89e0-6dec6aa66a2b%28Office.15%29.aspx#bk_UserProfileCreatePersonalSiteEnque)          **POST**`http://<siteUri>/_api/SP.UserProfiles.ProfileLoader.GetProfileLoader/GetUserProfile/CreatePersonalSiteEnqueue`SSOM:  [CreatePersonalSite()](https://msdn.microsoft.com/library/Microsoft.Office.Server.UserProfiles.UserProfile.CreatePersonalSite.aspx) (overloaded)|
|Provision one or more users' personal sites Available for My Site Host administrators on SharePoint Online only |CSOM:  [CreatePersonalSiteEnqueueBulk](what-s-new-for-developers-in-social-and-collaboration-features-in-sharepoint-201.md#bk_CreatePersonalSiteEnqueueBulk)JSOM: **createPersonalSiteEnqueueBulk**REST:  [CreatePersonalSiteEnqueueBulk](http://msdn.microsoft.com/library/10757ed1-6e86-474f-89e0-6dec6aa66a2b%28Office.15%29.aspx#bk_ProfileLoaderCreatePersonalSiteEnqueueBulk)          **POST**`https://<domain>-admin.sharepoint.com/_api/SP.UserProfiles.ProfileLoader.GetProfileLoader/CreatePersonalSiteEnqueueBulk` and pass a string array of email addresses for the _emailIDs_ parameter (200 characters maximum) in the request body (example: `{'emailIDs':['usera@contoso.onmicrosoft.com','userb@contoso.onmicrosoft.com']}`). SSOM: **CreatePersonalSiteEnqueueBulk**|
   

## New objects for users and user properties in SharePoint 2013
<a name="bkmk_NewUserObjects"> </a>

SharePoint Server 2013 includes the following new objects that represent users and user properties: 
  
    
    

- The  [SocialActor](https://msdn.microsoft.com/library/Microsoft.SharePoint.Client.Social.SocialActor.aspx) object and the [SocialActorInfo](https://msdn.microsoft.com/library/Microsoft.SharePoint.Client.Social.SocialActorInfo.aspx) object represent users (and documents, sites, and tasks) for feed and following activities.
    
  
- A new client-side  [UserProfile](https://msdn.microsoft.com/library/Microsoft.SharePoint.Client.UserProfiles.UserProfile.aspx) object that provides methods you can use to create a personal site for the current user. However, it does not contain all the user properties that the server-side [UserProfile](https://msdn.microsoft.com/library/Microsoft.Office.Server.UserProfiles.UserProfile.aspx) object contains.
    
  
- The  [PersonProperties](https://msdn.microsoft.com/library/Microsoft.SharePoint.Client.UserProfiles.PersonProperties.aspx) object contains general user properties and its [UserProfileProperties](https://msdn.microsoft.com/library/Microsoft.SharePoint.Client.UserProfiles.PersonProperties.UserProfileProperties.aspx) property contains user profile properties. [PersonProperties](https://msdn.microsoft.com/library/Microsoft.SharePoint.Client.UserProfiles.PersonProperties.aspx) is the primary API for accessing user properties from client-side code.
    
  

> [!NOTE]  
> Server object model versions are the  [SPSocialActor](https://msdn.microsoft.com/library/Microsoft.Office.Server.Social.SPSocialActor.aspx) object and the [PersonProperties](https://msdn.microsoft.com/library/Microsoft.Office.Server.UserProfiles.PersonProperties.aspx) object.
  
    
    


## Additional resources
<a name="bkmk_AdditionalResources"> </a>


-  [Social and collaboration features in SharePoint 2013](social-and-collaboration-features-in-sharepoint-2013.md)
    
  
-  [Get started developing with social features in SharePoint 2013](get-started-developing-with-social-features-in-sharepoint-2013.md)
    
  
-  [How to: Retrieve user profile properties by using the .NET client object model in SharePoint 2013](how-to-retrieve-user-profile-properties-by-using-the-net-client-object-model-in.md)
    
  
-  [How to: Retrieve user profile properties by using the JavaScript object model in SharePoint 2013](how-to-retrieve-user-profile-properties-by-using-the-javascript-object-model-in.md)
    
  
-  [User profiles REST API reference](http://msdn.microsoft.com/library/10757ed1-6e86-474f-89e0-6dec6aa66a2b%28Office.15%29.aspx)
    
  
-  [How to: Work with user profiles and organization profiles by using the server object model in SharePoint 2013](how-to-work-with-user-profiles-and-organization-profiles-by-using-the-server-obj.md)
    
  
-  [Follow people in SharePoint 2013](follow-people-in-sharepoint-2013.md)
    
  
