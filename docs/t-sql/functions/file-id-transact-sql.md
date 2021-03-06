---
description: FILE_ID (Transact-SQL)
title: FILE_ID (Transact-SQL) | Документы Майкрософт
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: sql-database
ms.reviewer: ''
ms.technology: t-sql
ms.topic: language-reference
f1_keywords:
- FILE_ID
- FILE_ID_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- IDs [SQL Server], files
- file IDs [SQL Server]
- FILE_ID function
- names [SQL Server], files
- identification numbers [SQL Server], files
- file names [SQL Server], FILE_ID
ms.assetid: 6a7382cf-a360-4d62-b9d2-5d747f56f076
author: markingmyname
ms.author: maghan
ms.openlocfilehash: 5d3d2d24a9f6c3dc206c550fc780105ad36f4d39
ms.sourcegitcommit: e700497f962e4c2274df16d9e651059b42ff1a10
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/17/2020
ms.locfileid: "88468053"
---
# <a name="file_id-transact-sql"></a>FILE_ID (Transact-SQL)
[!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]

Для указанного логического имени файла компонента текущей базы данных эта функция возвращает идентификатор файла.  
  
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureAvoid](../../includes/ssnotedepfutureavoid-md.md)] Используйте вместо этого функцию [FILE_IDEX](../../t-sql/functions/file-idex-transact-sql.md).  
  
 ![Значок ссылки на раздел](../../database-engine/configure-windows/media/topic-link.gif "Значок ссылки на раздел") [Синтаксические обозначения в Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Синтаксис  
  
```  
FILE_ID ( file_name )  
```  
  
[!INCLUDE[sql-server-tsql-previous-offline-documentation](../../includes/sql-server-tsql-previous-offline-documentation.md)]

## <a name="arguments"></a>Аргументы
*file_name*  
Выражение типа **sysname**, представляющее имя файла, для которого будет возвращено значение идентификатора файла (`FILE_ID`).  
  
## <a name="return-types"></a>Типы возвращаемых данных  
**smallint**  
  
## <a name="remarks"></a>Комментарии  
*file_name* соответствует логическому имени файла, отображенному в столбце name в представлении каталога sys.master_files или sys.database_files.  

`FILE_ID` возвращает `NULL`, если *имя_файла* не соответствует логическому имени файла компонента текущей базы данных.
  
В [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] идентификационный номер файла, присваиваемый полнотекстовым каталогам, превышает 32767. Так как функция `FILE_ID` имеет тип возвращаемого значения **smallint**, `FILE_ID` не будет поддерживать полнотекстовые файлы. Используйте вместо этого функцию [FILE_IDEX](../../t-sql/functions/file-idex-transact-sql.md).  
  
## <a name="examples"></a>Примеры  
Этот пример возвращает значение идентификатора файла для файла `AdventureWorks_Data`, файла компонента из базы данных `ADVENTUREWORKS2012`.  

```sql  
USE AdventureWorks2012;  
GO  
SELECT FILE_ID('AdventureWorks2012_Data')AS 'File ID';  
GO  
```  
  
 [!INCLUDE[ssResult](../../includes/ssresult-md.md)]  
  
```  
File ID   
-------   
1  
(1 row(s) affected)  
```  
  
## <a name="see-also"></a>См. также:  
 [Нерекомендуемые функции ядра СУБД в SQL Server 2016](../../database-engine/deprecated-database-engine-features-in-sql-server-2016.md)   
 [FILE_NAME (Transact-SQL)](../../t-sql/functions/file-name-transact-sql.md)   
 [Функции метаданных (Transact-SQL)](../../t-sql/functions/metadata-functions-transact-sql.md)   
 [sys.database_files (Transact-SQL)](../../relational-databases/system-catalog-views/sys-database-files-transact-sql.md)   
 [sys.master_files (Transact-SQL)](../../relational-databases/system-catalog-views/sys-master-files-transact-sql.md)  
  
  
