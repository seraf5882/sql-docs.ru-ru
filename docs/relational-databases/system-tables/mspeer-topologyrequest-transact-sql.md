---
description: MSpeer_topologyrequest (Transact-SQL)
title: MSpeer_topologyrequest (Transact-SQL) | Документация Майкрософт
ms.custom: ''
ms.date: 03/03/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: replication
ms.topic: language-reference
f1_keywords:
- MSpeer_topologyrequest_TSQL
- MSpeer_topologyrequest
dev_langs:
- TSQL
helpviewer_keywords:
- MSpeer_topologyrequest
ms.assetid: c644814b-4e40-44d7-b6b4-5954b0d4db7c
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 613f84235f07daceab86300bc72528bd21693175
ms.sourcegitcommit: e700497f962e4c2274df16d9e651059b42ff1a10
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/17/2020
ms.locfileid: "88469042"
---
# <a name="mspeer_topologyrequest-transact-sql"></a>MSpeer_topologyrequest (Transact-SQL)
[!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]

  Используется в одноранговой репликации для отслеживания запросов состояния топологии для публикации. Эта таблица хранится в базе данных публикации.  
  
|Имя столбца|Тип данных|Описание|  
|-----------------|---------------|-----------------|  
|идентификатор|**int**|Идентифицирует запрос состояния топологии. Столбец request_id в [MSpeer_topologyresponse](../../relational-databases/system-tables/mspeer-topologyresponse-transact-sql.md) использует это значение.|  
|публикация|**sysname**|Имя публикации, из которой был сформирован запрос состояния топологии.|  
|sent_date|**datetime**|Дата и время выдачи запроса состояния топологии.|  
  
## <a name="see-also"></a>См. также:  
 [Таблицы репликации &#40;&#41;Transact-SQL ](../../relational-databases/system-tables/replication-tables-transact-sql.md)   
 [Представления репликации (Transact-SQL)](../../relational-databases/system-views/replication-views-transact-sql.md)  
  
  
