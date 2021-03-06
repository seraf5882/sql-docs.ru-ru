---
description: sp_cycle_agent_errorlog (Transact-SQL)
title: sp_cycle_agent_errorlog (Transact-SQL) | Документация Майкрософт
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
f1_keywords:
- sp_cycle_agent_errorlog
- sp_cycle_agent_errorlog_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- sp_cycle_agent_errorlog
ms.assetid: 8aa96182-60b7-4d7b-b2a7-ccce70378c6e
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: d289ef03ea7404a149d8b644d8dc2dee7f25f78b
ms.sourcegitcommit: e700497f962e4c2274df16d9e651059b42ff1a10
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/17/2020
ms.locfileid: "88464380"
---
# <a name="sp_cycle_agent_errorlog-transact-sql"></a>sp_cycle_agent_errorlog (Transact-SQL)
[!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]

  Закрывает текущий файл журнала ошибок агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] и циклически меняет номера расширений журнала ошибок агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], как при перезапуске системы. Новый журнал ошибок агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] содержит строку, указывающую на создание нового журнала.  
  
 ![Значок ссылки на раздел](../../database-engine/configure-windows/media/topic-link.gif "Значок ссылки на раздел") [Синтаксические обозначения в Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
sp_cycle_agent_errorlog  
```  
  
## <a name="return-code-values"></a>Значения кода возврата  
 **0** (успешное завершение) или **1** (сбой)  
  
## <a name="result-sets"></a>Результирующие наборы  
 None  
  
## <a name="remarks"></a>Remarks  
 Каждый раз [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , когда запускается агент, текущий [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] журнал ошибок агента переименовывается в объект **. 1**; «В». **1** превращается в «а. **2**» **, то есть** «в». **3**и т. д. **sp_cycle_agent_errorlog** позволяет циклически запускать файлы журнала ошибок без остановки и запуска сервера.  
  
 Эта хранимая процедура должна запускаться из базы данных **msdb** .  
  
## <a name="permissions"></a>Разрешения  
 Разрешения на выполнение **sp_cycle_agent_errorlog** ограничены членами предопределенной роли сервера **sysadmin** .  
  
## <a name="examples"></a>Примеры  
 На следующем примере показано, как производится циклическое переименование журнала ошибок агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].  
  
```  
USE msdb ;  
GO  
  
EXEC dbo.sp_cycle_agent_errorlog ;  
GO  
```  
  
## <a name="see-also"></a>См. также  
 [sp_cycle_errorlog &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/sp-cycle-errorlog-transact-sql.md)  
  
  
