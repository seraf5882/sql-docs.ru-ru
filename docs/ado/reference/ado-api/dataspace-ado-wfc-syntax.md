---
description: DataSpace (ADO — синтаксис WFC)
title: Пространство (ADO — синтаксис WFC) | Документация Майкрософт
ms.prod: sql
ms.prod_service: connectivity
ms.technology: connectivity
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: conceptual
apitype: COM
helpviewer_keywords:
- DataSpace collection [ADO], ADO/WFC syntax
ms.assetid: 950d45d8-07de-467b-b255-f9a7b997204c
author: rothja
ms.author: jroth
ms.openlocfilehash: 5e5160e0fb52b0208899f30715d7821c71b26dda
ms.sourcegitcommit: e700497f962e4c2274df16d9e651059b42ff1a10
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/17/2020
ms.locfileid: "88444216"
---
# <a name="dataspace-ado---wfc-syntax"></a>DataSpace (ADO — синтаксис WFC)
Метод **CreateObject** класса **пространства** данных определяет как бизнес-объект для обработки запросов клиентских приложений (*ProgID*), так и протокол связи и сервер (*соединение*). Функция **CreateObject** возвращает объект [обжектпрокси](../../../ado/reference/ado-api/objectproxy-ado-wfc-syntax.md) , представляющий сервер.  
  
## <a name="package-commswfcdata"></a>упаковать com. MS. WFC. Data  
  
### <a name="constructor"></a>Конструктор  
  
```  
public DataSpace()  
```  
  
### <a name="methods"></a>Методы  
  
```  
public static ObjectProxy DataSpace.createObject(String  
    progid, String connection)  
```  
  
### <a name="properties"></a>Свойства  
  
```  
public static int getInternetTimeout()  
public static void setInternetTimeout(int plInetTimeout)  
```  
  
## <a name="see-also"></a>См. также:  
 [Объект DataSpace (служба удаленных рабочих столов)](../../../ado/reference/rds-api/dataspace-object-rds.md)
