---
description: Примеры методов примеры BeginTrans, CommitTrans и RollbackTrans (Visual Basic)
title: Примеры методов примеры BeginTrans, CommitTrans и RollbackTrans (Visual Basic) | Документация Майкрософт
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
- RollbackTrans method [ADO], Visual Basic example
- CommitTrans method [ADO], Visual Basic example
- BeginTrans method [ADO], Visual Basic example
ms.assetid: aa7de324-cd71-4bd0-8043-24229f4a785e
author: rothja
ms.author: jroth
ms.openlocfilehash: 8cc23406c3c9ad7c2455d0efc7f11aeee107bb52
ms.sourcegitcommit: e700497f962e4c2274df16d9e651059b42ff1a10
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/17/2020
ms.locfileid: "88451186"
---
# <a name="begintrans-committrans-and-rollbacktrans-methods-example-vb"></a>Примеры методов примеры BeginTrans, CommitTrans и RollbackTrans (Visual Basic)
В этом примере изменяется тип книги всех книг психологии в таблице ***titles*** базы данных. После того как метод [примеры BeginTrans](../../../ado/reference/ado-api/begintrans-committrans-and-rollbacktrans-methods-ado.md) запускает транзакцию, которая изолирует все изменения, внесенные в таблицу ***titles*** , метод [CommitTrans](../../../ado/reference/ado-api/begintrans-committrans-and-rollbacktrans-methods-ado.md) сохраняет изменения. Для отмены изменений, сохраненных с помощью метода [Update](../../../ado/reference/ado-api/update-method.md) , можно использовать метод [RollbackTrans](../../../ado/reference/ado-api/begintrans-committrans-and-rollbacktrans-methods-ado.md) .  
  
```  
'BeginBeginTransVB  
  
    'To integrate this code  
    'replace the data source and initial catalog values  
    'in the connection string  
  
Public Sub Main()  
    On Error GoTo ErrorHandler  
  
    'recordset and connection variables  
    Dim Cnxn As ADODB.Connection  
    Dim strCnxn As String  
    Dim rstTitles As ADODB.Recordset  
    Dim strSQLTitles As String  
    'record variables  
    Dim strTitle As String  
    Dim strMessage As String  
  
    ' Open connection  
    strCnxn = "Provider='sqloledb';Data Source='MySqlServer';" & _  
        "Initial Catalog='Pubs';Integrated Security='SSPI';"  
    Set Cnxn = New ADODB.Connection  
    Cnxn.Open strCnxn  
  
    ' Open recordset dynamic to allow for changes  
    Set rstTitles = New ADODB.Recordset  
    strSQLTitles = "Titles"  
    rstTitles.Open strSQLTitles, Cnxn, adOpenDynamic, adLockPessimistic, adCmdTable  
  
    Cnxn.BeginTrans  
  
    ' Loop through recordset and prompt user  
    ' to change the type for a specified title  
  
    rstTitles.MoveFirst  
  
    Do Until rstTitles.EOF  
        If Trim(rstTitles!Type) = "psychology" Then  
            strTitle = rstTitles!Title  
            strMessage = "Title: " & strTitle & vbCr & _  
            "Change type to self help?"  
  
            ' If yes, change type for the specified title  
            If MsgBox(strMessage, vbYesNo) = vbYes Then  
                rstTitles!Type = "self_help"  
                rstTitles.Update  
            End If  
        End If  
    rstTitles.MoveNext  
    Loop  
  
    ' Prompt user to commit all changes made  
    If MsgBox("Save all changes?", vbYesNo) = vbYes Then  
        Cnxn.CommitTrans  
    Else  
        Cnxn.RollbackTrans  
    End If  
  
    ' Print recordset  
    rstTitles.Requery  
    rstTitles.MoveFirst  
    Do While Not rstTitles.EOF  
        Debug.Print rstTitles!Title & " - " & rstTitles!Type  
        rstTitles.MoveNext  
    Loop  
  
    ' Restore original data as this is a demo  
    rstTitles.MoveFirst  
  
    Do Until rstTitles.EOF  
        If Trim(rstTitles!Type) = "self_help" Then  
            rstTitles!Type = "psychology"  
            rstTitles.Update  
        End If  
        rstTitles.MoveNext  
    Loop  
  
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
  
'EndBeginTransVB  
```  
  
## <a name="see-also"></a>См. также:  
 [Методы примеры BeginTrans, CommitTrans и RollbackTrans (ADO)](../../../ado/reference/ado-api/begintrans-committrans-and-rollbacktrans-methods-ado.md)   
 [Объект Connection (ADO)](../../../ado/reference/ado-api/connection-object-ado.md)
