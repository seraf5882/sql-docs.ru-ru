---
description: RecordCreateOptionsEnum
title: Рекордкреатеоптионсенум | Документация Майкрософт
ms.prod: sql
ms.prod_service: connectivity
ms.technology: connectivity
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: conceptual
apitype: COM
f1_keywords:
- RecordCreateOptionsEnum
helpviewer_keywords:
- RecordCreateOptionsEnum enumeration [ADO]
ms.assetid: 6d746670-0850-4065-9cd4-168dea1d3ea9
author: rothja
ms.author: jroth
ms.openlocfilehash: 0ef305aefbd3c606f433bfd85b1b10ac2dd94db1
ms.sourcegitcommit: e700497f962e4c2274df16d9e651059b42ff1a10
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/17/2020
ms.locfileid: "88442476"
---
# <a name="recordcreateoptionsenum"></a>RecordCreateOptionsEnum
Указывает, следует ли открыть существующую **запись** или создать новую **запись** для метода [открытия](../../../ado/reference/ado-api/open-method-ado-record.md) объекта [записи](../../../ado/reference/ado-api/record-object-ado.md) . Значения можно сочетать с оператором AND.  
  
|Константа|Значение|Описание|  
|--------------|-----------|-----------------|  
|**adCreateCollection**|0x2000|Создает новую **запись** в узле, указанном параметром *Source* , вместо того, чтобы открывать существующую **запись**. Если источник указывает на существующий узел, возникает ошибка времени выполнения, если **адкреатеколлектион** не объединен с **адопенифексистс** или **адкреатеоверврите**.|  
|**adCreateNonCollection**|0|Создает новую **запись** типа [адсимплерекорд](../../../ado/reference/ado-api/recordtypeenum.md).|  
|**adCreateOverwrite**|0x4000000|Изменяет флаги создания **адкреатеколлектион**, **адкреатенонколлектион**и **адкреатеструктдок**. Если параметр или используется с этим значением и одним из значений флагов создания, если исходный URL-адрес указывает на существующий узел или **запись**, то существующая **запись** перезаписывается, а на ее месте создается новая. Это значение нельзя использовать вместе с **адопенифексистс**.|  
|**adCreateStructDoc**|0x80000000|Создает новую **запись** типа [адструктдок](../../../ado/reference/ado-api/recordtypeenum.md)вместо открытия существующей **записи**.|  
|**адфаилифнотексистс**|-1|По умолчанию. Приводит к ошибке времени выполнения, если *источник* указывает на несуществующий узел.|  
|**адопенифексистс**|0x2000000|Изменяет флаги создания **адкреатеколлектион**, **адкреатенонколлектион**и **адкреатеструктдок**. Если параметр или используется с этим значением и одним из значений флагов создания, если исходный URL-адрес указывает на существующий узел или объект **записи** , то поставщик должен открыть существующую **запись** вместо создания новой. Это значение нельзя использовать вместе с **адкреатеоверврите**.|  
  
## <a name="adowfc-equivalent"></a>Эквивалент ADO/WFC  
 Эти константы не имеют эквивалентов ADO/WFC.  
  
## <a name="applies-to"></a>Применение  
 [Метод Open (объект Record ADO)](../../../ado/reference/ado-api/open-method-ado-record.md)
