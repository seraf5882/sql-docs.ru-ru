---
description: sys.dm_io_pending_io_requests (Transact-SQL)
title: sys. dm_io_pending_io_requests (Transact-SQL) | Документация Майкрософт
ms.custom: ''
ms.date: 03/30/2017
ms.prod: sql
ms.prod_service: database-engine, sql-database, sql-data-warehouse, pdw
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
f1_keywords:
- sys.dm_io_pending_io_requests
- dm_io_pending_io_requests
- dm_io_pending_io_requests_TSQL
- sys.dm_io_pending_io_requests_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- sys.dm_io_pending_io_requests dynamic management view
ms.assetid: d1fb46dd-5c74-4c04-9ecf-8934b1bedb5b
author: CarlRabeler
ms.author: carlrab
monikerRange: '>=aps-pdw-2016||=azuresqldb-current||=azure-sqldw-latest||>=sql-server-2016||=sqlallproducts-allversions||>=sql-server-linux-2017||=azuresqldb-mi-current'
ms.openlocfilehash: 69f544c80718611ab56d8535a714c360a58870ee
ms.sourcegitcommit: e700497f962e4c2274df16d9e651059b42ff1a10
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/17/2020
ms.locfileid: "88419678"
---
# <a name="sysdm_io_pending_io_requests-transact-sql"></a>sys.dm_io_pending_io_requests (Transact-SQL)
[!INCLUDE [sql-asdb-asdbmi-asa-pdw](../../includes/applies-to-version/sql-asdb-asdbmi-asa-pdw.md)]

  Возвращает по строке для каждого ожидающего выполнения запроса ввода-вывода в [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].  
  
> [!NOTE]  
>  Чтобы вызвать эту функцию из [!INCLUDE[ssSDWfull](../../includes/sssdwfull-md.md)] или [!INCLUDE[ssPDW](../../includes/sspdw-md.md)] , используйте имя **sys. dm_pdw_nodes_io_pending_io_requests**.  
  
|Имя столбца|Тип данных|Описание|  
|-----------------|---------------|-----------------|  
|**io_completion_request_address**|**varbinary(8)**|Адрес запроса ввода-вывода в памяти. Не допускает значение NULL.|  
|**io_type**|**nvarchar(60)**|Тип запроса ввода-вывода, ожидающего выполнения. Не допускает значение NULL.|  
|**io_pending_ms_ticks**|**bigint**|Только для внутреннего применения. Не допускает значение NULL.| 
|**io_pending**|**int**|Указывает, ожидает ли запрос ввода-вывода выполнения или он завершен Windows. Запрос может продолжать ожидать выполнения, даже если операционная система Windows уже завершила соответствующий ввод-вывод, но [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] еще не выполнил переключение контекста, при котором запрос ввода-вывода должен быть обработан и удален из этого списка. Не допускает значение NULL.|  
|**io_completion_routine_address**|**varbinary(8)**|Внутренняя функция, которая должна вызываться по завершении запроса ввода-вывода. Допускает значение NULL.|  
|**io_user_data_address**|**varbinary(8)**|Только для внутреннего применения. Допускает значение NULL.|  
|**scheduler_address**|**varbinary(8)**|Планировщик, которым был назначен данный запрос ввода-вывода. Запрос ввода-вывода появляется в списке планировщика запросов ввода-вывода, ожидающих выполнения. Дополнительные сведения см. в разделе [sys. dm_os_schedulers &#40;&#41;Transact-SQL ](../../relational-databases/system-dynamic-management-views/sys-dm-os-schedulers-transact-sql.md). Не допускает значение NULL.|  
|**io_handle**|**varbinary(8)**|Дескриптор файла, используемый в запросе ввода-вывода. Допускает значение NULL.|  
|**io_offset**|**bigint**|Смещение при выполнении запроса ввода-вывода. Не допускает значение NULL.|  
|**io_handle_path**|**nvarchar(256)**| Путь к файлу, используемому в запросе ввода-вывода. Допускает значение NULL.|
|**pdw_node_id**|**int**|**Применимо к**: [!INCLUDE[ssSDWfull](../../includes/sssdwfull-md.md)] , [!INCLUDE[ssPDW](../../includes/sspdw-md.md)]<br /><br /> Идентификатор узла, на котором находится данное распределение.|  
  
## <a name="permissions"></a>Разрешения  

В [!INCLUDE[ssNoVersion_md](../../includes/ssnoversion-md.md)] необходимо `VIEW SERVER STATE` разрешение.   
На [!INCLUDE[ssSDS_md](../../includes/sssds-md.md)] уровнях Premium требуется `VIEW DATABASE STATE` разрешение в базе данных. На [!INCLUDE[ssSDS_md](../../includes/sssds-md.md)] уровнях Standard и Basic требуется  **Администратор сервера** или учетная запись **администратора Azure Active Directory** .   
  
## <a name="see-also"></a>См. также:  
 [Динамические административные представления и функции (Transact-SQL)](~/relational-databases/system-dynamic-management-views/system-dynamic-management-views.md)   
 [Динамические административные представления и функции, связанные с I O &#40;языке Transact-SQL&#41;](../../relational-databases/system-dynamic-management-views/i-o-related-dynamic-management-views-and-functions-transact-sql.md)  
  
  


