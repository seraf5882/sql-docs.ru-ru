---
description: Пример метода Find (Visual Basic)
title: Пример метода Find (Visual Basic) | Документация Майкрософт
ms.prod: sql
ms.prod_service: connectivity
ms.technology: connectivity
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: conceptual
dev_langs:
- VB
helpviewer_keywords:
- Find method [ADO], Visual Basic example
ms.assetid: bbf27dcc-9815-4e2f-8ea8-b8c9fe6dedd6
author: rothja
ms.author: jroth
ms.openlocfilehash: b57772085e93d03c7ca40364e3074e3bc8228e02
ms.sourcegitcommit: e700497f962e4c2274df16d9e651059b42ff1a10
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/17/2020
ms.locfileid: "88443626"
---
# <a name="find-method-example-vb"></a>Пример метода Find (Visual Basic)
В этом примере используется метод [Find](../../../ado/reference/ado-api/find-method-ado.md) объекта [Recordset](../../../ado/reference/ado-api/recordset-object-ado.md) для поиска и подсчета количества названий бизнес-объектов в базе данных ***pubs*** . В этом примере предполагается, что базовый поставщик не поддерживает аналогичные функции.  
  
```  
'BeginFindVB  
  
    'To integrate this code  
    'replace the data source and initial catalog values  
    'in the connection string  
  
Public Sub Main()  
    On Error GoTo ErrorHandler  
  
     ' connection and recordset variables  
    Dim Cnxn As New ADODB.Connection  
    Dim rstTitles As New ADODB.Recordset  
    Dim strCnxn As String  
    Dim strSQLTitles As String  
  
     ' record variables  
    Dim mark As Variant  
    Dim count As Integer  
  
     ' open connection  
    Set Cnxn = New ADODB.Connection  
    strCnxn = "Provider='sqloledb';Data Source='MySqlServer';" & _  
        "Initial Catalog='Pubs';Integrated Security='SSPI';"  
    Cnxn.Open strCnxn  
  
    ' open recordset with default parameters which are  
    ' sufficient to search forward through a Recordset  
    Set rstTitles = New ADODB.Recordset  
    strSQLTitles = "SELECT title_id FROM titles"  
    rstTitles.Open strSQLTitles, Cnxn, adOpenStatic, adLockReadOnly, adCmdText  
  
    count = 0  
    rstTitles.Find "title_id LIKE 'BU%'"  
  
    Do While Not rstTitles.EOF  
        'continue if last find succeeded  
        Debug.Print "Title ID: "; rstTitles!title_id  
        'count the last title found  
        count = count + 1  
        ' note current position  
        mark = rstTitles.Bookmark  
        rstTitles.Find "title_id LIKE 'BU%'", 1, adSearchForward, mark  
        ' above code skips current record to avoid finding the same row repeatedly;  
        ' last arg (bookmark) is redundant because Find searches from current position  
    Loop  
  
    Debug.Print "The number of business titles is " & count  
  
    ' clean up  
    rstTitles.Close  
    Cnxn.Close  
    Set rstTitles = Nothing  
    Set Cnxn = Nothing  
    Exit Sub  
  
ErrorHandler:  
    ' clean up  
    If Not rstTitles Is Nothing Then  
        If rstTitles.State = adStateOpen Then rstTitles.Close  
    End If  
    Set rstTitles = Nothing  
  
    If Not Cnxn Is Nothing Then  
        If Cnxn.State = adStateOpen Then Cnxn.Close  
    End If  
    Set Cnxn = Nothing  
  
    If Err <> 0 Then  
        MsgBox Err.Source & "-->" & Err.Description, , "Error"  
    End If  
End Sub  
'EndFindVB  
```  
  
## <a name="see-also"></a>См. также:  
 [Метод Find (ADO)](../../../ado/reference/ado-api/find-method-ado.md)   
 [Объект Recordset (ADO)](../../../ado/reference/ado-api/recordset-object-ado.md)
