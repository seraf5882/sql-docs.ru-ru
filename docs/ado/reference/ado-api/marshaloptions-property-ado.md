---
description: Свойство MarshalOptions (ADO)
title: Свойство MarshalOptions (ADO) | Документация Майкрософт
ms.prod: sql
ms.prod_service: connectivity
ms.technology: connectivity
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: conceptual
apitype: COM
f1_keywords:
- Recordset15::MarshalOptions
helpviewer_keywords:
- MarshalOptions property [ADO]
ms.assetid: 390c8abf-133e-40da-8b99-8f748a983e4f
author: rothja
ms.author: jroth
ms.openlocfilehash: 59f44093725321ef5f5b445d0edad6caec8c2113
ms.sourcegitcommit: e700497f962e4c2274df16d9e651059b42ff1a10
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/17/2020
ms.locfileid: "88443326"
---
# <a name="marshaloptions-property-ado"></a>Свойство MarshalOptions (ADO)
Указывает, какие записи [набора записей](../../../ado/reference/ado-api/recordset-object-ado.md) необходимо маршалировать обратно на сервер.  
  
## <a name="settings-and-return-values"></a>Параметры и возвращаемые значения  
 Задает или возвращает значение [маршалоптионсенум](../../../ado/reference/ado-api/marshaloptionsenum.md) . Значение по умолчанию — **адмаршалалл**.  
  
## <a name="remarks"></a>Remarks  
 При использовании [набора записей](../../../ado/reference/ado-api/recordset-object-ado.md)на стороне клиента записи, которые были изменены на клиенте, записываются обратно на средний уровень или на веб-сервер с помощью метода, называемого упаковкой, процесс упаковки и отправки параметров метода интерфейса через границы потока или процесса. Установка свойства **MarshalOptions** может повысить производительность при передаче измененных удаленных данных для обновления на среднем уровне или на веб-сервере.  
  
> [!NOTE]
>  **Использование удаленной службы данных** Это свойство используется только в **наборе записей**на стороне клиента.  
  
## <a name="applies-to"></a>Применение  
 [Объект Recordset (ADO)](../../../ado/reference/ado-api/recordset-object-ado.md)  
  
## <a name="see-also"></a>См. также:  
 [Пример свойства MarshalOptions (Visual Basic)](../../../ado/reference/ado-api/marshaloptions-property-example-vb.md)   
 [Пример свойства MarshalOptions (Visual C++)](../../../ado/reference/ado-api/marshaloptions-property-example-vc.md)   
