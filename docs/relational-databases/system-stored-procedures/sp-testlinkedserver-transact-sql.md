---
title: sp_testlinkedserver (Transact-SQL) | Документация Майкрософт
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
f1_keywords:
- sp_testlinkedserver
- sp_testlinkedserver_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- sp_testlinkedserver
ms.assetid: e63ca7d4-47d6-455e-9aac-421f9683dadc
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 01ae2d33ab38b5a3f2720b817a036cd152f2c47f
ms.sourcegitcommit: f7ac1976d4bfa224332edd9ef2f4377a4d55a2c9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/02/2020
ms.locfileid: "85892617"
---
# <a name="sp_testlinkedserver-transact-sql"></a>sp_testlinkedserver (Transact-SQL)
[!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]

  Проверяет соединение со связанным сервером. Если проверка завершилась неуспешно, то процедура вызывает исключение с указанием причины сбоя.  
  
 ![Значок ссылки на раздел](../../database-engine/configure-windows/media/topic-link.gif "Значок ссылки на раздел") [Синтаксические обозначения в Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
sp_testlinkedserver [ @servername ] = servername  
```  
  
## <a name="arguments"></a>Аргументы  
`[ @servername = ]servername`Имя связанного сервера. *ServerName* имеет тип **sysname**и не имеет значения по умолчанию.  
  
## <a name="result-sets"></a>Результирующие наборы  
 None  
  
## <a name="permissions"></a>Разрешения  
 Разрешения не проверяются, однако у вызывающего объекта должно быть соответствующее сопоставление имени входа.  
  
## <a name="examples"></a>Примеры  
 В следующем примере создается связанный сервер с именем `SEATTLESales` и тестируется соединение.  
  
```  
USE master;  
GO  
EXEC sp_addlinkedserver   
    'SEATTLESales',  
    N'SQL Server';  
GO  
sp_testlinkedserver SEATTLESales;  
GO  
```  
  
## <a name="see-also"></a>См. также  
 [sp_addlinkedserver &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/sp-addlinkedserver-transact-sql.md)   
 [sp_addlinkedsrvlogin (Transact-SQL)](../../relational-databases/system-stored-procedures/sp-addlinkedsrvlogin-transact-sql.md)  
  
  
