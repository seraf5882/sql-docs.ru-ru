---
description: Позиционирование в наборе записей
title: Позиционирование набора записей | Документация Майкрософт
ms.prod: sql
ms.prod_service: connectivity
ms.technology: connectivity
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: conceptual
helpviewer_keywords:
- record positioning [ADO]
- Recordset object [ADO]
- repositioning record [ADO]
- AbsolutePosition property [ADO]
ms.assetid: c8f6fbcb-6675-4133-b37e-430de43949c1
author: rothja
ms.author: jroth
ms.openlocfilehash: 9d5cdea25dbf14ef5f26d02612f357768acdad61
ms.sourcegitcommit: e700497f962e4c2274df16d9e651059b42ff1a10
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/17/2020
ms.locfileid: "88452966"
---
# <a name="recordset-positioning"></a>Позиционирование в наборе записей
Используйте свойство **примеры AbsolutePosition** для перемещения к записи, основанной на ее порядковом положении в объекте **набора записей** , или для определения порядкового номера текущей записи. Чтобы это свойство было доступно, поставщик должен поддерживать соответствующие функциональные возможности.  
  
 **Примеры AbsolutePosition** является 1 и равно 1, если текущая запись является первой записью в **наборе записей**. Как упоминалось ранее, можно получить общее число записей в объекте **набора записей** из свойства **RecordCount** .  
  
 Если задать свойство **примеры AbsolutePosition** , даже если оно относится к записи в текущем КЭШЕ, ADO перезагружает кэш с новой группой записей, начиная с указанной записи. Свойство **CacheSize** определяет размер этой группы.  
  
> [!NOTE]
>  Не следует использовать свойство **примеры AbsolutePosition** в качестве номера суррогатной записи. При удалении предыдущей записи изменяется ее расположение. Кроме того, не гарантируется, что данная запись будет иметь тот же **примеры AbsolutePosition** при повторном запросе или открытии объекта **набора записей** . Закладки — это рекомендуемый способ удержания и возврата к заданной должности, который является единственным способом позиционирования всех типов объектов **набора записей** .
