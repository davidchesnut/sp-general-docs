---
title: Resources URI for Excel Services REST API
ms.prod: OFFICE365
ms.assetid: 79f95305-ec9e-4842-b937-85f66ced98e4
---


# Resources URI for Excel Services REST API

You can link to entities directly by using the REST API in Excel Services. 
  
    
    


> [!NOTE]  
> The Excel Services REST API applies to SharePoint 2013 and SharePoint 2016 on-premises. For Office 365 Education, Business, and Enterprise accounts, use the Excel REST APIs that are part of the  [Microsoft Graph](http://graph.microsoft.io/en-us/docs/api-reference/v1.0/resources/excel
) endpoint.
  
    
    


## Base REST URL

The following is an example of a REST URL to a specific element in a workbook. 
  
    
    

```

http://<ServerName>/_vti_bin/ExcelRest.aspx/<DocumentLibrary>/<FileName>/<ResourceLocation>
```

A relative REST URL is based off the base REST URL. The following is an example of a base REST URL to a specific workbook. 
  
    
    



```
http://<ServerName>/_vti_bin/ExcelRest.aspx/<DocumentLibrary>/<FileName>
```

For example, if you have a workbook named "sampleWorkbook.xlsx" in the following document library: 
  
    
    



```
http://<ServerName>/Docs/Documents/sampleWorkbook.xlsx
```

The base REST URL to the workbook is: 
  
    
    



```
http://<ServerName>/_vti_bin/ExcelRest.aspx/Docs/Documents/sampleWorkbook.xlsx
```


## Resources URI

Table 1 shows all the accessible resources in the Excel Services REST API. To access a particular resource, append the resource location to the base REST URL to a workbook. 
  
    
    

**Table 1. Accessible resources in the Excel Services REST API**


|** **Resource Location****|** **Format****|** **Example****|** **Notes****|
|:-----|:-----|:-----|:-----|
|/model |Atom (default) |/model |Returns an Atom feed with the resources supported by the Excel Services REST API. The supported resources are ranges, charts, tables, and PivotTables. |
|/model |workbook |/model?$format=workbook |This is the workbook. Supported workbook formats are xlsx, xlsb, and xlsm. |
|/model/Ranges |Atom (default) |/model/Ranges?$format=atom |An Atom feed that listis all the named ranges in the workbook. |
|/model/Ranges('[Name]') |HTML (default) |/model/Ranges('MyRange')?$format=html |An HTML fragment for the requested range. |
|/model/Ranges('[Name]') |Atom |/model/Ranges('MyRange')?$format=atom |An Atom entry that contains an XML representation of the data within the range. |
|/model/Charts |Atom (default) |/model/Charts?$format=atom |An Atom feed that lists all the charts in the workbook. |
|/model/Charts('[Name]') |Image (default) |/model/Charts('MyChart')?$format=image |An image of the chart. The image is in Portable Network Graphics (PNG) format. |
|/model/Tables |Atom (default) |/model/Tables?$format=atom |An Atom feed that lists all the available tables in the workbook. |
|/model/Tables('[Name]') |HTML (default) |/model/Tables('MyTable')?$format=html |An HTML fragment for the requested table. |
|/model/Tables('[Name]') |Atom |/model/Tables('MyTable')?$format=atom |An Atom entry that contains an XML representation of the data within the table. |
|/model/PivotTables |Atom (default) |/model/PivotTables?$format=atom |An Atom feed that lists all the available PivotTables in the workbook |
|/model/PivotTables('[Name]') |HTML (default) |/model/PivotTables('MyPivotTable)?$format=html |An HTML fragment for the requested PivotTable. |
|/model/PivotTables('[Name]') |Atom |/model/PivotTables('MyPivotTable')?$format=atom |An Atom entry that contains an XML representation of the data within the PivotTables. |
   

> [!NOTE]  
> Excel Services limits the number of ranges that you can include in a URL to 10. If you include more than 10 Ranges in a URL, you will get an error that indicates that the service is unavailable. 
  
    
    


## See also


#### Concepts


  
    
    
 [Basic URI Structure and Path](basic-uri-structure-and-path.md)
