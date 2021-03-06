---
description: Настройка DataFactory
title: Настройка в отношении фактов | Документация Майкрософт
ms.prod: sql
ms.prod_service: connectivity
ms.technology: connectivity
ms.custom: ''
ms.date: 11/09/2018
ms.reviewer: ''
ms.topic: conceptual
helpviewer_keywords:
- DataFactory customization in RDS [ADO]
ms.assetid: 86d77985-a0d0-405a-8587-c85a20540a0e
author: rothja
ms.author: jroth
ms.openlocfilehash: b7ec3707df187e09de92fa42d7ed2b1c1b8e1130
ms.sourcegitcommit: e700497f962e4c2274df16d9e651059b42ff1a10
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/17/2020
ms.locfileid: "88452226"
---
# <a name="datafactory-customization"></a>Настройка DataFactory
Служба Remote Data Service (RDS) позволяет легко выполнять доступ к данным в трехуровневой клиентской и серверной системе. Клиентский элемент управления данными задает параметры соединения и командной строки для выполнения запроса к удаленному источнику данных, а также параметры строки подключения и параметров объекта [набора записей](../../../ado/reference/ado-api/recordset-object-ado.md) для выполнения обновления.  
  
> [!IMPORTANT]
>  Начиная с Windows 8 и Windows Server 2012, компоненты RDS больше не включены в операционную систему Windows (Дополнительные сведения см. в статье о совместимости Windows 8 и [Windows server 2012 Cookbook](https://www.microsoft.com/download/details.aspx?id=27416) ). Клиентские компоненты RDS будут удалены в следующей версии Windows. Избегайте использования этого компонента в новых разработках и запланируйте изменение существующих приложений, в которых он применяется. Приложения, использующие RDS, должны переноситься в [службу данных WCF](https://go.microsoft.com/fwlink/?LinkId=199565).  
  
 Параметры передаются в серверную программу, которая выполняет операцию доступа к данным в удаленном источнике данных. RDS предоставляет серверную программу по умолчанию, именуемую объектом [факта RDSServer.](../../../ado/reference/rds-api/datafactory-object-rdsserver.md) DataObject. Объект **RDSServer.** DataObject возвращает любой объект **набора записей** , созданный запросом к клиенту.  
  
 Однако **RDSServer.. факты** ограничены выполнением запросов и обновлений. Он не может выполнять проверку или обработку строк соединения или команд.  
  
 С помощью ADO можно указать, что объект **фактов** работает совместно с другим типом серверной программы, называемой *обработчиком*. Обработчик может изменить клиентское соединение и строки команд, прежде чем они будут использоваться для доступа к источнику данных. Кроме того, обработчик может применять права доступа, которые управляют возможностью клиента считывать и записывать данные в источник данных.  
  
 Параметры, которые обработчик использует для изменения параметров клиента и прав доступа, указаны в разделах файла настройки.  
  
 В следующих разделах содержатся дополнительные сведения о настройке объекта **фактов** .  
  
-   [Общие сведения о файле настроек](../../../ado/guide/remote-data-service/understanding-the-customization-file.md)  
  
-   [Настройка раздела подключения файла](../../../ado/guide/remote-data-service/customization-file-connect-section.md)  
  
-   [Настройка раздела SQL файла](../../../ado/guide/remote-data-service/customization-file-sql-section.md)  
  
-   [Настройка раздела UserList файла](../../../ado/guide/remote-data-service/customization-file-userlist-section.md)  
  
-   [Настройка раздела журналов файла](../../../ado/guide/remote-data-service/customization-file-logs-section.md)  
  
-   [Требуемые параметры клиента](../../../ado/guide/remote-data-service/required-client-settings.md)  
  
-   [Создание собственного настраиваемого обработчика](../../../ado/guide/remote-data-service/writing-your-own-customized-handler.md)


