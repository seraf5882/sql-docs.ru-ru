---
description: sys.dm_os_nodes (Transact-SQL)
title: sys. dm_os_nodes (Transact-SQL) | Документация Майкрософт
ms.custom: ''
ms.date: 02/13/2018
ms.prod: sql
ms.prod_service: database-engine, sql-database, sql-data-warehouse, pdw
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
f1_keywords:
- sys.dm_os_nodes
- dm_os_nodes_TSQL
- dm_os_nodes
- sys.dm_os_nodes_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- sys.dm_os_nodes dynamic management view
ms.assetid: c768b67c-82a4-47f5-850b-0ea282358d50
author: CarlRabeler
ms.author: carlrab
monikerRange: '>=aps-pdw-2016||=azuresqldb-current||=azure-sqldw-latest||>=sql-server-2016||=sqlallproducts-allversions||>=sql-server-linux-2017||=azuresqldb-mi-current'
ms.openlocfilehash: 716b3c816bb5246f91c25869de7e2647a10bbc64
ms.sourcegitcommit: e700497f962e4c2274df16d9e651059b42ff1a10
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/17/2020
ms.locfileid: "88447643"
---
# <a name="sysdm_os_nodes-transact-sql"></a>sys.dm_os_nodes (Transact-SQL)
[!INCLUDE [sql-asdb-asdbmi-asa-pdw](../../includes/applies-to-version/sql-asdb-asdbmi-asa-pdw.md)]

Внутренний компонент с именем SQLOS создает структуры узлов, имитирующие аппаратное размещение ЦП. Эти структуры можно изменить с помощью [программной архитектуры NUMA](../../database-engine/configure-windows/soft-numa-sql-server.md) для создания пользовательских макетов узлов.  

> [!NOTE]
> Начиная с [!INCLUDE[ssSQL15](../../includes/sssql15-md.md)] , [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] будет автоматически использовать Soft-NUMA для определенных конфигураций оборудования. Дополнительные сведения см. в разделе [Автоматический программный NUMA](../../database-engine/configure-windows/soft-numa-sql-server.md#automatic-soft-numa).
  
Сведения об указанных узлах приведены в следующей таблице.  
  
> [!NOTE]
> Чтобы вызвать это динамическое административное представление из [!INCLUDE[ssSDWfull](../../includes/sssdwfull-md.md)] или [!INCLUDE[ssPDW](../../includes/sspdw-md.md)] , используйте имя **sys. dm_pdw_nodes_os_nodes**.  
  
|Имя столбца|Тип данных|Описание|  
|-----------------|---------------|-----------------|  
|node_id|**smallint**|Идентификатор узла.|  
|node_state_desc|**nvarchar(256)**|Описание состояния узла. Сначала отображаются взаимоисключающие значения, затем все их комбинации. Например:<br /> «В сети», «Недостаток ресурсов потоков», «Отложенный с вытеснением»<br /><br />Существует четыре взаимоисключающих node_state_desc значений. Ниже перечислены их описания.<br /><ul><li>В сети: узел находится в режиме "в сети"<li>ВНЕ сети: узел находится в автономном режиме<li>Бездействие: узел не имеет ожидающих рабочих запросов и перешел в состояние простоя.<li>IDLE_READY: узел не имеет ожидающих рабочих запросов и готов к переходу в состояние простоя.</li></ul><br />Ниже приведены три значения, которые могут быть node_state_desc.<br /><ul><li>DAC: этот узел зарезервирован для [выделенного административного соединения](../../database-engine/configure-windows/diagnostic-connection-for-database-administrators.md).<li>THREAD_RESOURCES_LOW: на этом узле невозможно создать новые потоки из-за нехватки памяти.<li>"ГОРЯЧее" Добавление: указывает, что узлы были добавлены в ответ на событие ЦП "горячего" добавления.</li></ul>|  
|memory_object_address|**varbinary(8)**|Адрес объекта памяти, связанного с данным узлом. Отношение "один к одному" к [sys. dm_os_memory_objects](../../relational-databases/system-dynamic-management-views/sys-dm-os-memory-objects-transact-sql.md). memory_object_address.|  
|memory_clerk_address|**varbinary(8)**|Адрес клерка памяти, связанного с данным узлом. Отношение "один к одному" к [sys. dm_os_memory_clerks](../../relational-databases/system-dynamic-management-views/sys-dm-os-memory-clerks-transact-sql.md). memory_clerk_address.|  
|io_completion_worker_address|**varbinary(8)**|Адрес исполнителя, связанного с завершением сеанса ввода-вывода для данного узла. Отношение "один к одному" к [sys. dm_os_workers](../../relational-databases/system-dynamic-management-views/sys-dm-os-workers-transact-sql.md). worker_address.|  
|memory_node_id|**smallint**|Идентификатор узла памяти, к которому принадлежит данный узел. Связь «многие к одному» с представлением [sys. dm_os_memory_nodes](../../relational-databases/system-dynamic-management-views/sys-dm-os-memory-nodes-transact-sql.md). memory_node_id.|  
|cpu_affinity_mask|**bigint**|Битовая карта, идентифицирующая процессоры, с которыми связан данный узел.|  
|online_scheduler_count|**smallint**|Число интерактивных планировщиков, управляемых этим узлом.|  
|idle_scheduler_count|**smallint**|Количество планировщиков в сети, не имеющих активных исполнителей.|  
|active_worker_count|**int**|Количество исполнителей, активных на всех планировщиках, управляемых данным узлом.|  
|avg_load_balance|**int**|Среднее количество задач, выполняемых одним планировщиком на данном узле.|  
|timer_task_affinity_mask|**bigint**|Битовая карта, определяющая планировщиков, которым можно назначить временные задачи.|  
|permanent_task_affinity_mask|**bigint**|Битовая карта, определяющая планировщиков, которым можно назначить постоянные задачи.|  
|resource_monitor_state|**bit**|Каждому узлу соответствует отдельный монитор ресурсов. Монитор ресурсов может находиться в состоянии работы или бездействия. Значению 1 соответствует рабочее состояние, значение 0 означает бездействие.|  
|online_scheduler_mask|**bigint**|Идентифицирует маску схожести процессов для этого узла.|  
|processor_group|**smallint**|Идентифицирует группу процессоров для этого узла.|  
|cpu_count |**int** |Число ЦП, доступных для этого узла. |
|pdw_node_id|**int**|Идентификатор узла, на котором находится данное распределение.<br /><br /> **Применимо к**: [!INCLUDE[ssSDWfull](../../includes/sssdwfull-md.md)] , [!INCLUDE[ssPDW](../../includes/sspdw-md.md)]|  
  
## <a name="permissions"></a>Разрешения

В [!INCLUDE[ssNoVersion_md](../../includes/ssnoversion-md.md)] необходимо `VIEW SERVER STATE` разрешение.   
На [!INCLUDE[ssSDS_md](../../includes/sssds-md.md)] уровнях Premium требуется `VIEW DATABASE STATE` разрешение в базе данных. На [!INCLUDE[ssSDS_md](../../includes/sssds-md.md)] уровнях Standard и Basic требуется  **Администратор сервера** или учетная запись **администратора Azure Active Directory** .   

## <a name="see-also"></a>См. также    
 [SQL Server динамические административные представления, связанные с операционной системой &#40;&#41;Transact-SQL ](../../relational-databases/system-dynamic-management-views/sql-server-operating-system-related-dynamic-management-views-transact-sql.md)   
 [Архитектура Soft-NUMA (SQL Server)](../../database-engine/configure-windows/soft-numa-sql-server.md)  
  
