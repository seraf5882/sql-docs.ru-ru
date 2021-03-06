---
description: Вопросы безопасности при работе с XML
title: Вопросы безопасности XML | Документация Майкрософт
ms.prod: sql
ms.prod_service: connectivity
ms.technology: connectivity
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: conceptual
helpviewer_keywords:
- XML security in ADO
ms.assetid: fadbd38e-6e7b-4b81-96ea-85169c664374
author: rothja
ms.author: jroth
ms.openlocfilehash: 76ec899a26485a81a5ec81006d0dbd4c838738dd
ms.sourcegitcommit: e700497f962e4c2274df16d9e651059b42ff1a10
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/17/2020
ms.locfileid: "88452496"
---
# <a name="xml-security-considerations"></a>Вопросы безопасности при работе с XML
Методы сохранения и открытия объектов ADO в объекте набора записей не считаются безопасными операциями для запуска в Internet Explorer. Таким образом, если эти методы используются в коде скрипта, который выполняется в приложении или элементе управления, размещенном в браузере, конфигурация безопасности браузера будет оказывать воздействие на его поведение.  
  
 Internet Explorer 5 предоставляет ограничения безопасности для таких операций по умолчанию в зонах Интернета. В такой конфигурации набор записей не может предоставить доступ к локальной файловой системе на клиенте или получить доступ к любым источникам данных вне домена сервера, с которого была загружена страница. В частности, при выполнении внутри узла браузера набор записей можно сохранить обратно в файл только в том случае, если он находится на том же сервере, с которого была загружена страница. Аналогичным образом набор записей можно открыть, загрузив его из файла, только если этот файл находится на том же сервере, на котором была загружена страница.  
  
## <a name="see-also"></a>См. также  
 [Сохранение записей в формате XML](../../../ado/guide/data/persisting-records-in-xml-format.md)
