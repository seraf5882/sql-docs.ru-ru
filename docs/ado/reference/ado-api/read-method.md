---
description: Метод Read
title: Метод Read | Документация Майкрософт
ms.prod: sql
ms.technology: connectivity
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: conceptual
apitype: COM
f1_keywords:
- Stream::raw_Read
- _Stream::Read
helpviewer_keywords:
- Read method [ADO]
ms.assetid: 838502de-80f1-4eeb-8838-dd3d9403e567
author: rothja
ms.author: jroth
ms.openlocfilehash: 6600c02af5c24fc1ce27a04422678f8a3f40a179
ms.sourcegitcommit: e700497f962e4c2274df16d9e651059b42ff1a10
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/17/2020
ms.locfileid: "88442556"
---
# <a name="read-method"></a>Метод Read
Считывает указанное число байтов из объекта двоичного [потока](../../../ado/reference/ado-api/stream-object-ado.md) .  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
Variant = Stream.Read ( NumBytes)  
```  
  
#### <a name="parameters"></a>Параметры  
 *нумбитес*  
 Необязательный параметр. Значение **типа Long** , указывающее количество байтов для чтения из файла или значения [стреамреаденум](../../../ado/reference/ado-api/streamreadenum.md) **адреадалл**, которое является значением по умолчанию.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Метод **Read** считывает указанное число байтов или весь поток из объекта **потока** и возвращает результирующие данные в виде **Variant**.  
  
## <a name="remarks"></a>Remarks  
 Если *нумбитес* больше числа байтов, остающихся в **потоке**, возвращаются только оставшиеся байты. Чтение данных не дополняется в соответствии с длиной, заданной параметром *нумбитес*. Если не осталось байтов для чтения, возвращается Variant со значением NULL. **Чтение** не может быть использовано для чтения в обратном направлении.  
  
> [!NOTE]
>  *Нумбитес* всегда измеряет байты. Для объектов текстового **потока** ([Type](../../../ado/reference/ado-api/type-property-ado-stream.md) — **адтипетекст**) используйте [ReadText](../../../ado/reference/ado-api/readtext-method.md).  
  
## <a name="applies-to"></a>Применение  
 [Объект Stream (ADO)](../../../ado/reference/ado-api/stream-object-ado.md)  
  
## <a name="see-also"></a>См. также:  
 [Метод ReadText](../../../ado/reference/ado-api/readtext-method.md)
