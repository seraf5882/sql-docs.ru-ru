---
description: Метод Delete (коллекция Parameters ADO)
title: Метод Delete (Коллекция параметров ADO) | Документация Майкрософт
ms.prod: sql
ms.prod_service: connectivity
ms.technology: connectivity
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: conceptual
apitype: COM
f1_keywords:
- _DynaCollection::Delete
- _DynaCollection::raw_Delete
helpviewer_keywords:
- Delete method [ADO]
ms.assetid: 160c575e-df63-4ade-a2d3-5fd8f72e70cc
author: rothja
ms.author: jroth
ms.openlocfilehash: a76353f62fc2b30ea8e7eae16c97469027a98110
ms.sourcegitcommit: e700497f962e4c2274df16d9e651059b42ff1a10
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/17/2020
ms.locfileid: "88444166"
---
# <a name="delete-method-ado-parameters-collection"></a>Метод Delete (коллекция Parameters ADO)
Удаляет объект из коллекции [параметров](../../../ado/reference/ado-api/parameters-collection-ado.md) .  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
Parameters.Delete Index  
```  
  
#### <a name="parameters"></a>Параметры  
 *Index*  
 **Строковое** значение, содержащее имя объекта, который необходимо удалить, или порядковый номер (индекс) объекта в коллекции.  
  
## <a name="remarks"></a>Remarks  
 Использование метода **Delete** в коллекции позволяет удалить один из объектов в коллекции. Этот метод доступен только для коллекции **Parameters** объекта [Command](../../../ado/reference/ado-api/command-object-ado.md) . При вызове метода **Delete** необходимо использовать свойство [Name](../../../ado/reference/ado-api/name-property-ado.md) объекта [Parameter](../../../ado/reference/ado-api/parameter-object.md) или его индекс коллекции. переменная объекта не является допустимым аргументом.  
  
## <a name="applies-to"></a>Применение  
 [Коллекция Parameters (ADO)](../../../ado/reference/ado-api/parameters-collection-ado.md)  
  
## <a name="see-also"></a>См. также:  
 [Метод Delete (коллекция полей ADO)](../../../ado/reference/ado-api/delete-method-ado-fields-collection.md)   
 [Метод Delete (набор записей ADO)](../../../ado/reference/ado-api/delete-method-ado-recordset.md)   
 [Метод DeleteRecord (ADO)](../../../ado/reference/ado-api/deleterecord-method-ado.md)
