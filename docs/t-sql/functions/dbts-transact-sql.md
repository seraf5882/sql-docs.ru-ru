---
title: '@@DBTS (Transact-SQL) | Документы Майкрософт'
ms.custom: ''
ms.date: 09/18/2017
ms.prod: sql
ms.prod_service: database-engine, sql-database
ms.reviewer: ''
ms.technology: t-sql
ms.topic: language-reference
f1_keywords:
- '@@DBTS_TSQL'
- '@@DBTS'
dev_langs:
- TSQL
helpviewer_keywords:
- '@@DBTS function'
- timestamp data type
ms.assetid: 91842ddd-91c0-4445-a03f-116f6bc991d0
author: markingmyname
ms.author: maghan
ms.openlocfilehash: 5493589b7a87af2ea856a63e81c3b366eb410d9e
ms.sourcegitcommit: da88320c474c1c9124574f90d549c50ee3387b4c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85682948"
---
# <a name="x40x40dbts-transact-sql"></a>&#x40;&#x40;DBTS (Transact-SQL)
[!INCLUDE [SQL Server SQL Database](../../includes/applies-to-version/sql-asdb.md)]

Эта функция возвращает значение текущего типа данных **timestamp** для текущей базы данных. У текущей базы данных будет гарантированно уникальное значение отметки времени.
  
![Значок ссылки на раздел](../../database-engine/configure-windows/media/topic-link.gif "Значок ссылки на раздел") [Синтаксические обозначения в Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)
  
## <a name="syntax"></a>Синтаксис  
  
```
@@DBTS  
```  
  
## <a name="return-types"></a>Типы возвращаемых данных
**varbinary**
  
## <a name="remarks"></a>Remarks  
@@DBTS возвращает последнее использованное значение отметки времени для текущей базы данных. Новое значение отметки времени формируется при вставке или обновлении строки со столбцом **timestamp**.
  
Функция @@DBTS не затрагивается изменениями на уровнях изоляции транзакции.
  
## <a name="examples"></a>Примеры  
В этом примере возвращается текущее значение **timestamp** из базы данных [!INCLUDE[ssSampleDBnormal](../../includes/sssampledbnormal-md.md)].
  
```sql
USE AdventureWorks2012;  
GO  
SELECT @@DBTS;  
```  
  
## <a name="see-also"></a>См. также раздел
[Функции настройки (Transact-SQL)](../../t-sql/functions/configuration-functions-transact-sql.md)  
[Параллелизм курсоров (ODBC)](../../relational-databases/native-client-odbc-cursors/properties/cursor-concurrency-odbc.md)  
[Типы данных (Transact-SQL)](../../t-sql/data-types/data-types-transact-sql.md)  
[MIN_ACTIVE_ROWVERSION (Transact-SQL)](../../t-sql/functions/min-active-rowversion-transact-sql.md)
  
  
