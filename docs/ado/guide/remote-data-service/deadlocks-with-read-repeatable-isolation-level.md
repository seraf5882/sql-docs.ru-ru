---
description: Взаимоблокировки с уровнем изоляции с повторяющимся чтением
title: Взаимоблокировки с уровнем изоляции read REPEATABLE | Документация Майкрософт
ms.prod: sql
ms.prod_service: connectivity
ms.technology: connectivity
ms.custom: ''
ms.date: 11/09/2018
ms.reviewer: ''
ms.topic: conceptual
helpviewer_keywords:
- deadlocks in RDS [ADO]
- read repeatable in RDS [ADO]
ms.assetid: 29f3683f-12f3-4304-8a54-fe133c25a423
author: rothja
ms.author: jroth
ms.openlocfilehash: 398fd636c7e7ebfce448d5b7ebfae7a62d7c1a2b
ms.sourcegitcommit: e700497f962e4c2274df16d9e651059b42ff1a10
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/17/2020
ms.locfileid: "88452216"
---
# <a name="deadlocks-with-read-repeatable-isolation-level"></a>Взаимоблокировки с уровнем изоляции с повторяющимся чтением
Если пользовательский бизнес-объект использует уровень изоляции REPEATABLE READ для доступа к SQL Server, а бизнес-объект вызывается одновременно двумя клиентами, которые отправляют запрос и обновляются в одной транзакции, взаимоблокировка возможна. Служба удаленных данных разработана таким образом, чтобы один из процессов истечет время ожидания для освобождения взаимоблокировки, но обновление для этого клиента завершится ошибкой.  
  
 Чтобы изменить длину тайм-аута, используйте динамическое свойство **время ожидания команды** [службы курсора](../../../ado/guide/appendixes/microsoft-cursor-service-for-ole-db-ado-service-component.md) .  
  
> [!IMPORTANT]
>  Начиная с Windows 8 и Windows Server 2012, компоненты RDS больше не включены в операционную систему Windows (Дополнительные сведения см. в статье о совместимости Windows 8 и [Windows server 2012 Cookbook](https://www.microsoft.com/download/details.aspx?id=27416) ). Клиентские компоненты RDS будут удалены в следующей версии Windows. Избегайте использования этого компонента в новых разработках и запланируйте изменение существующих приложений, в которых он применяется. Приложения, использующие RDS, должны переноситься в [службу данных WCF](https://go.microsoft.com/fwlink/?LinkId=199565).  
  
## <a name="see-also"></a>См. также:  
 [Основные принципы RDS](../../../ado/guide/remote-data-service/rds-fundamentals.md)



