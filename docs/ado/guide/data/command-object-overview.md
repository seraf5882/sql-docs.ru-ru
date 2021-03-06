---
description: Обзор объекта Command
title: Общие сведения об объекте Command | Документация Майкрософт
ms.prod: sql
ms.prod_service: connectivity
ms.technology: connectivity
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: conceptual
helpviewer_keywords:
- command object [ADO]
ms.assetid: e84a14b1-3c2a-4f7d-a966-9e08a93948df
author: rothja
ms.author: jroth
ms.openlocfilehash: d44c727a69dc74bf243bc2f2c0204cb41cd9f585
ms.sourcegitcommit: e700497f962e4c2274df16d9e651059b42ff1a10
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/17/2020
ms.locfileid: "88453686"
---
# <a name="command-object-overview"></a>Обзор объекта Command
С помощью объекта **Command** можно выполнять следующие действия.  
  
-   Определите исполняемый текст команды (например, инструкцию SQL или хранимую процедуру) с помощью свойства **CommandText** .  
  
-   Определите параметризованные запросы или аргументы хранимой процедуры с помощью объектов **параметров** и коллекции **Parameters** .  
  
-   Выполните команду и при необходимости верните объект **набора записей** с помощью метода **EXECUTE** .  
  
-   Укажите тип команды с помощью свойства **CommandType** перед выполнением, чтобы оптимизировать производительность.  
  
-   Укажите конкретные сведения о тексте команды с помощью свойства **диалекта** объекта **Command** .  
  
-   Контролируйте, сохраняет ли поставщик подготовленную (или скомпилированную) версию команды перед выполнением с помощью **подготовленного** свойства.  
  
-   Задайте количество секунд, в течение которых поставщик будет ожидать выполнения команды с помощью свойства **CommandTimeout** .  
  
-   Свяжите открытое соединение с объектом **Command** , задав свойство **ActiveConnection** .  
  
-   Задайте свойство **Name** , чтобы определить объект **команды** в качестве метода для связанного объекта **соединения** .  
  
-   Передайте объект **команды** в свойство **Source** **набора записей** , чтобы получить данные.  
  
-   Передайте объект **потока** , содержащий команду (например, команду XML), поставщику, который его поддерживает.
