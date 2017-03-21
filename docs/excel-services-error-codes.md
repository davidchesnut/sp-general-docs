---
title: Excel Services Error Codes
keywords: alerts
f1_keywords:
- alerts
ms.prod: OFFICE365
ms.assetid: ff128d67-f3ac-4a8f-ae8e-1e19e343014e
---


# Excel Services Error Codes

Excel Services generates errors and error messages in the SOAP exception based on errors that occur in Excel Services. The following table shows the errors that are accessible when calls to the Excel Web Services methods throw a SOAP exception. 
  
    
    

You use the  [SubCode](http://msdn.microsoft.com/library/frlrfSystemWebServicesProtocolsSoapExceptionClassSubCodeTopic.aspx) property of the **SoapException** class to capture the error codes. For more information about using the **SubCode** property to capture error codes, see [How to: Use the SubCode Property to Capture Error Codes](how-to-use-the-subcode-property-to-capture-error-codes.md)
For more information about Excel Services alerts, see  [Excel Services Alerts](excel-services-alerts.md). 
  
    
    


## Error Codes

The following table lists the error codes for Excel Web Services alerts and the associated messages, explanation, and resolutions. 
  
    
    


|** **Error Code****|** **Message****|** **Explanation****|** **Resolution****|
|:-----|:-----|:-----|:-----|
|ApiInvalidArgument |Invalid value to argument: {0} |An invalid value for an argument was passed into the API call. 0 = name of the argument. Its value is invalid. |Use a valid value for the argument. |
|ApiInvalidCoordinate |The {0} coordinate of {1} is invalid. |0 = coordinate name (row, column, height, width). 1 = name of the argument, which holds the coordinate structure. The contents of the **RangeCoordinates** class or the row\\column\\height\\width parameters on a get or set call are invalid.|Use valid coordinate values for the argument. |
|DimensionAndArrayMismatch |The size of the provided array does not match the size and shape of the destination range. |The caller tried to set a range into a workbook but the parameter that contains the array values does not match the target range. |Make sure the size of the provided array matches the dimensions of the destination range (for example, 2 columns wide by 3 rows high). |
|DiscontiguousRangeNotSupported |The request for the range does not refer to a contiguous range. Excel Services supports contiguous ranges only. |The caller supplied a noncontiguous range when trying to set or get a range of cells. Excel Services does not support noncontiguous ranges. It only supports contiguous ranges. |Enter a contiguous range such as "A1:B7" or "A1" or "MyTable[#Data]" instead of a noncontiguous range such as "A1:B7, B12" or "A1,A3". |
|ExternalDataRefreshFailed |Unable to retrieve external data for the following connections: {0} The data source may be unreachable, may not be responding, or has denied access. |Attempts to refresh a data source inside a workbook failed. 0 is a \\n separated list of connection names. |Make sure the data source is available and that you have permission to access it. |
|FileOpenAccessDenied |You do not have permissions to open this file on Excel Services. |A call to the **OpenWorkbook** method failed because the user does not have access to the file.|Contact your administrator. |
|FileCorrupt |The file you selected cannot be opened because it is corrupt, protected by Information Rights Management, or in a file format not supported by Excel Services. Excel may be able to open this file. |A call to the **OpenWorkbook** method failed because the file is corrupted.|Try to open the file again, or use Excel to open the file. |
|FileOpenNotFound |The file you selected could not be found. Check the spelling of the file name and verify that the location is correct. |A call to the **OpenWorkbook** method failed because the file does not exist.|Make sure that the file has not been renamed, moved, or deleted, that the file is in a trusted location, and that you have access to the file. If the problem persists, contact your administrator. |
|FileOpenSecuritySettings |The file you selected cannot be opened at this time due to security settings for Excel Services. |A call to the **OpenWorkbook** method failed because the administrator's security settings prevented it from opening for various reasons. For example, the file is too big, that is, its size exceeded the limit set by the administrator.|Contact your administrator. |
|FormulaEditingNotEnabled |Editing Formulas is not enabled in this release of Excel Services. |The caller tried to write a formula into the workbook. |Do not try to write a formula because it is not supported in this release of Excel Services. |
|GenericFileOpenError |An error occurred while opening the file you selected. |Excel Services is unable to open the file for an unknown reason. |Wait a few minutes and try to open the file again. If the problem persists, contact your administrator. |
|InvalidSheetName |The worksheet that you requested does not exist in the workbook. |The sheet name was not found or was invalid. |Use a valid value for the name of the sheet. |
|InvalidOrTimedOutSession |The operation you performed cannot be completed at this time because the session is no longer available on the server. You can reload the workbook and create a new session, but any changes you have made have been lost. |The call  _sessionId_ value is either invalid or has since timed out.|Reload the workbook in a new session. |
|IRMedWorkbook |The requested workbook is IRM protected. Excel Services cannot load IRM protected workbooks. |A call to the **OpenWorkbook** method failed because the workbook is protected by Information Rights Management (IRM).|Only pass in workbooks that are not IRM protected. |
|MaxSessionsPerUserExceeded |The maximum number of allowed sessions per user has been exceeded. The operation cannot be completed. |The maximum number of sessions a user can have opened at any given time has been exceeded. This limit is set by the administrator. |Do not exceed the limit or contact your administrator. |
|MultipleRequestsOnSession |An operation is already being processed in this session. Only one operation can be processed in a session at a time. |Multiple requests have been issued on the same session. A session can only process one request at a time (with a few exceptions). |Try performing the operation again. |
|NotMemberOfRole |Access denied. You do not have permission to perform this action or access this resource. |The caller does not have permission to access the server. |Contact your administrator. |
|ObjectTypeNotSupported |One or more object types provided are not supported by Excel Services. The operation was rolled back. |The caller tried to write unsupported object type values into a range. |Try the operation again using one of the supported object types. |
|OperationCanceled |The operation has been canceled. |The operation that is currently taking place is canceled because the user calls the **CancelRequest** method.|Call the **CancelRequest** method only if you want to cancel the current operation.|
|RangeParseError |Excel Services was unable to parse the range request. |The range that was passed into a method with the A1 suffix ( **SetCellA1**, **SetRangeA1**, **GetCellA1**, and **GetRangeA1**) could not be parsed. |Enter a range reference using A1 notation such as "Sheet1!Range("A6:A15")" or a valid structured reference such as "[ShipCity].[#Headers]". |
|RangeRequestAreaExceeded |The area of the requested range exceeds 1,000,000 cells. |The requested range exceeds the 1,000,000 cell limit. |To return ranges that contain more than 1,000,000 cells, use multiple calls. |
|RetryError |Excel Services is unable to process the request. |Excel Services might at times reach a state where its resources are low. When this happens, it might start denying requests. |Wait a few minutes and try to perform this operation again. |
|SaveFailed |An error occurred while saving the file. |A call to the **GetWorkbook** method failed.|Try to save the file again. |
|SetRangeFailure |The requested operation attempted to overwrite the contents of cells that cannot be edited. |The caller tried to write values into a range that has protected cells. For example, the cell contains a formula. |Only empty cells or cells that contain values can be edited by Excel Services. |
|SheetRangeMismatch |The sheet provided as the sheet argument is not the same as the sheet specified in the range argument. |The name of the sheet passed in for a  _sheetName_ parameter does not match the sheet location specified in the _rangeName_ parameter.|When specifying a sheet in both the range and sheet arguments, ensure that the sheet names are the same. For example,  `Calculate(Sheet1, Sheet1!Range("A1"))`. |
|SpecifiedRangeNotFound |The requested range does not exist in the sheet. |The range that was passed into a method with the A1 suffix ( **SetCellA1**, **SetRangeA1**, **GetCellA1**, and **GetRangeA1**) could not be found. |Make sure the range specified exists in the sheet. |
|WorkbookNotSupported |The file you selected cannot be opened because it contains feature(s) that are not supported by Excel Services. One or more of the following unsupported features were detected in the workbook: {0} |The workbook contains unsupported features. 0 = a \\n separated list of unsupported feature names. |Make sure the workbook does not contain features that are not supported by Excel Services. |
   

## See also


#### Tasks


  
    
    
 [How to: Use the SubCode Property to Capture Error Codes](how-to-use-the-subcode-property-to-capture-error-codes.md)
#### Concepts


  
    
    
 [Excel Services Alerts](excel-services-alerts.md)
  
    
    
 [Excel Services Known Issues and Tips](excel-services-known-issues-and-tips.md)
  
    
    
 [Excel Services Best Practices](excel-services-best-practices.md)
