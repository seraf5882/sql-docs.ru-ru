---
title: sp_getqueuedrows (Transact-SQL) | Документация Майкрософт
ms.custom: ''
ms.date: 03/04/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: replication
ms.topic: language-reference
f1_keywords:
- sp_getqueuedrows_TSQL
- sp_getqueuedrows
helpviewer_keywords:
- sp_getqueuedrows
ms.assetid: 139e834f-1988-4b4d-ac81-db1f89ea90e8
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 57e4551743a535c78e33b4682f8ea19132bc75a9
ms.sourcegitcommit: f7ac1976d4bfa224332edd9ef2f4377a4d55a2c9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/02/2020
ms.locfileid: "85881589"
---
# <a name="sp_getqueuedrows-transact-sql"></a>sp_getqueuedrows (Transact-SQL)
[!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]

  Извлекает строки на подписчике, имеющие отложенные обновления в очереди. Эта хранимая процедура выполняется на подписчике в базе данных подписки.  
  
 ![Значок ссылки на раздел](../../database-engine/configure-windows/media/topic-link.gif "Значок ссылки на раздел") [Синтаксические обозначения в Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
sp_getqueuedrows [ @tablename = ] 'tablename'  
    [ , [ @owner = ] 'owner'  
    [ , [ @tranid = ] 'transaction_id' ]  
```  
  
## <a name="arguments"></a>Аргументы  
`[ @tablename = ] 'tablename'`Имя таблицы. *TableName* имеет тип **sysname**и не имеет значения по умолчанию. Таблица должна быть частью очереди подписок.  
  
`[ @owner = ] 'owner'`Владелец подписки. Аргумент *owner* имеет тип **sysname**и значение по умолчанию NULL.  
  
`[ @tranid = ] 'transaction_id'`Позволяет фильтровать выходные данные по ИДЕНТИФИКАТОРу транзакции. *transaction_id* имеет тип **nvarchar (70)** и значение по умолчанию NULL. Если указан, будет отображен идентификатор транзакции, связанный с командой в очереди. Если указать значение NULL, будут отображены все команды в очереди.  
  
## <a name="return-code-values"></a>Значения кода возврата  
 **0** (успешное завершение) или **1** (сбой)  
  
## <a name="result-sets"></a>Результирующие наборы  
 Показывает все строки, которые в настоящее время имеют по крайней мере одну транзакцию в очереди для подписанной таблицы.  
  
|Имя столбца|Тип данных|Описание|  
|-----------------|---------------|-----------------|  
|**Действие**|**nvarchar (10)**|Тип операции для выполнения при синхронизации.<br /><br /> INS= вставка.<br /><br /> DEL = удаление.<br /><br /> UPD = обновление.|  
|**транид**|**nvarchar (70)**|Идентификатор транзакции, под которым выполнялась команда.|  
|**table column1...n**||Значение для каждого столбца таблицы, указанного в *TableName*.|  
|**msrepl_tran_version**|**uniqueidentifier**|Этот столбец используется для отслеживания изменений для реплицируемых данных и для обнаружения конфликтов на издателе. Этот столбец добавлен к таблице автоматически.|  
  
## <a name="remarks"></a>Комментарии  
 **sp_getqueuedrows** используется на подписчиках, участвующих в обновлении посредством очередей.  
  
 **sp_getqueuedrows** находит строки заданной таблицы в базе данных подписки, которая участвовала в обновлении в очереди, но в настоящее время не разрешено агентом чтения очереди.  
  
## <a name="permissions"></a>Разрешения  
 **sp_getqueuedrows** требует разрешения SELECT для таблицы, указанной в *TableName*.  
  
## <a name="see-also"></a>См. также  
 [Обновляемые подписки для репликации транзакций](../../relational-databases/replication/transactional/updatable-subscriptions-for-transactional-replication.md)   
 [Обнаружение и разрешение конфликтов обновления посредством очередей](../../relational-databases/replication/transactional/updatable-subscriptions-queued-updating-conflict-resolution.md)   
 [Системные хранимые процедуры (Transact-SQL)](../../relational-databases/system-stored-procedures/system-stored-procedures-transact-sql.md)  
  
  
