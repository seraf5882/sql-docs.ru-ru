---
description: MSsnapshotdeliveryprogress (Transact-SQL)
title: MSsnapshotdeliveryprogress (Transact-SQL) | Документация Майкрософт
ms.custom: ''
ms.date: 03/04/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: replication
ms.topic: language-reference
f1_keywords:
- MSsnapshotdeliveryprogress_TSQL
- MSsnapshotdeliveryprogress
dev_langs:
- TSQL
helpviewer_keywords:
- MSsnapshotdeliveryprogress system table
ms.assetid: 9164bfe2-6fc4-4b52-946a-09ea3cf67041
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: dd50e23578c8da3ca9d0e96a5ad7480f9af6acb4
ms.sourcegitcommit: e700497f962e4c2274df16d9e651059b42ff1a10
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/17/2020
ms.locfileid: "88454615"
---
# <a name="mssnapshotdeliveryprogress-transact-sql"></a>MSsnapshotdeliveryprogress (Transact-SQL)
[!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]

  Таблица **MSsnapshotdeliveryprogress** используется для трассировки файлов, успешно доставленных подписчику при применении моментального снимка. Эти данные используются для возобновления доставки файлов в случае, если во время сеанса агент слияния не смог успешно доставить все файлы, чтобы те же самые файлы не доставлялись повторно при следующем запуске агента слияния. Эта таблица хранится на подписчике в базе данных подписки.  
  
|Имя столбца|Тип данных|Описание|  
|-----------------|---------------|-----------------|  
|**session_token**|**nvarchar(260)**|Определяет путь к папке моментального снимка, откуда файл был успешно доставлен. Для публикаций, использующих параметризованные фильтры, строка **динснап** будет добавлена к значению.|  
|**progress_token_hash**|**int**|Хэш-значение, созданное на основе значения *progress_token* , которое используется для повышения эффективности поиска по заданному *progress_tokenому* значению.|  
|**progress_token**|**nvarchar (500)**|Определяет успешно доставленный файл; значение является сочетанием имени файла и пути.|  
|**progress_timestamp**|**datetime**|Значение **типа DateTime** , указывающее, когда файл моментального снимка был успешно доставлен.|  
  
## <a name="see-also"></a>См. также:  
 [Таблицы репликации &#40;&#41;Transact-SQL ](../../relational-databases/system-tables/replication-tables-transact-sql.md)   
 [Представления репликации (Transact-SQL)](../../relational-databases/system-views/replication-views-transact-sql.md)  
  
  
