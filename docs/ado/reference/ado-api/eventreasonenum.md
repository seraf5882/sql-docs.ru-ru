---
description: EventReasonEnum
title: Евентреасоненум | Документация Майкрософт
ms.prod: sql
ms.prod_service: connectivity
ms.technology: connectivity
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: conceptual
apitype: COM
f1_keywords:
- EventReasonEnum
helpviewer_keywords:
- EventReasonEnum enumeration [ADO]
ms.assetid: 7d4a5496-ec2d-4936-b36a-7049a82be4b4
author: rothja
ms.author: jroth
ms.openlocfilehash: 0dc0c811f989b0fd91c47827718d1d8480ddb769
ms.sourcegitcommit: e700497f962e4c2274df16d9e651059b42ff1a10
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/17/2020
ms.locfileid: "88443926"
---
# <a name="eventreasonenum"></a>EventReasonEnum
Указывает причину возникновения события.  
  
|Константа|Значение|Описание|  
|--------------|-----------|-----------------|  
|**адрснадднев**|1|Операция добавила новую запись.|  
|**adRsnClose**|9|**Набор записей**закрыт операцией.|  
|**adRsnDelete**|2|Операция удалила запись.|  
|**adRsnFirstChange**|11|Операция выполнила первое изменение в записи.|  
|**adRsnMove**|10|Операция переместила указатель записи в **наборе записей**.|  
|**adRsnMoveFirst**|12|Операция переместила указатель записи на первую запись в **наборе записей**.|  
|**adRsnMoveLast**|15|Операция переместила указатель записи на последнюю запись в **наборе записей**.|  
|**adRsnMoveNext**|13|Операция переместила указатель записи на следующую запись в **наборе записей**.|  
|**adRsnMovePrevious**|14|Операция переместила указатель записи на предыдущую запись в **наборе записей**.|  
|**adRsnRequery**|7|Операция запросила [набор записей](../../../ado/reference/ado-api/recordset-object-ado.md).|  
|**adRsnResynch**|8|Операция повторно синхронизирует **набор записей** с базой данных.|  
|**адрснундоадднев**|5|Операция обращается к добавлению новой записи.|  
|**adRsnUndoDelete**|6|Операция обращается к удалению записи.|  
|**adRsnUndoUpdate**|4|Операция обращается к обновлению записи.|  
|**adRsnUpdate**|3|Операция обновила существующую запись.|  
  
## <a name="adowfc-equivalent"></a>Эквивалент ADO/WFC  
 Пакет: **com. MS. WFC. Data**  
  
|Константа|  
|--------------|  
|Адоенумс. Евентреасон. ADDNEW|  
|Адоенумс. Евентреасон. CLOSE|  
|Адоенумс. Евентреасон. DELETE|  
|Адоенумс. Евентреасон. ФИРСТЧАНЖЕ|  
|Адоенумс. Евентреасон. MOVE|  
|Адоенумс. Евентреасон. MOVEFIRST|  
|Адоенумс. Евентреасон. MOVELAST|  
|Адоенумс. Евентреасон. MOVENEXT|  
|Адоенумс. Евентреасон. MOVEPREVIOUS|  
|Адоенумс. Евентреасон. Requery|  
|Адоенумс. Евентреасон. resynch|  
|Адоенумс. Евентреасон. УНДОАДДНЕВ|  
|Адоенумс. Евентреасон. УНДОДЕЛЕТЕ|  
|Адоенумс. Евентреасон. УНДАУПДАТЕ|  
|Адоенумс. Евентреасон. UPDATE|  
  
## <a name="applies-to"></a>Применение  

:::row:::
    :::column:::
        [События WillChangeRecord и RecordChangeComplete (ADO)](../../../ado/reference/ado-api/willchangerecord-and-recordchangecomplete-events-ado.md)  

        [События WillChangeRecordset и RecordsetChangeComplete (ADO)](../../../ado/reference/ado-api/willchangerecordset-and-recordsetchangecomplete-events-ado.md)  
    :::column-end:::
    :::column:::
        [События WillMove и MoveComplete (ADO)](../../../ado/reference/ado-api/willmove-and-movecomplete-events-ado.md)  
    :::column-end:::
:::row-end:::
