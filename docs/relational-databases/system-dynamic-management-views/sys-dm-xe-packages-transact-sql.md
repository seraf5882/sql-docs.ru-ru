---
title: sys. dm_xe_packages (Transact-SQL) | Документация Майкрософт
ms.custom: ''
ms.date: 08/09/2016
ms.prod: sql
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
f1_keywords:
- dm_xe_packages_TSQL
- sys.dm_xe_packages_TSQL
- dm_xe_packages
- sys.dm_xe_packages
dev_langs:
- TSQL
helpviewer_keywords:
- sys.dm_xe_packages dynamic management view
- extended events [SQL Server], views
ms.assetid: 2e5ecbe9-3ea8-45e6-a161-e31671a03e1d
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 3ae80e8db245c5a70db238a17b5d09bb682b09b1
ms.sourcegitcommit: 591bbf4c7e4e2092f8abda6a2ffed263cb61c585
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/22/2020
ms.locfileid: "86942358"
---
# <a name="sysdm_xe_packages-transact-sql"></a>sys.dm_xe_packages (Transact-SQL)
[!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]

  Содержит список всех пакетов, зарегистрированных подсистемой расширенных событий.  
  
 
|Имя столбца|Тип данных|Описание|  
|-----------------|---------------|-----------------|  
|name|**nvarchar(256)**|Имя пакета. Это описание берется из самого пакета. Не допускает значение NULL.|  
|guid|**uniqueidentifier**|Идентификатор GUID пакета. Не допускает значение NULL.|  
|description|**nvarchar (3072)**|Описание пакета. Описание задано автором пакета и не допускает значения NULL.|  
|capabilities|**int**|Битовая карта, описывающая возможности этого пакета. Допускает значение NULL.|  
|capabilities_desc|**nvarchar(256)**|Список всех возможностей, допустимых для этого пакета. Допускает значение NULL.|  
|module_guid|**nvarchar(60)**|Идентификатор GUID модуля, содержащегося в пакете. Не допускает значение NULL.|  
|module_address|**varbinary(8)**|Базовый адрес, по которому загружается модуль, содержащийся в пакете. Один модуль может занимать несколько пакетов. Не допускает значение NULL.|  
  
## <a name="permissions"></a>Разрешения  
 необходимо разрешение VIEW SERVER STATE на сервере.  
  
## <a name="remarks"></a>Комментарии  
 Пакеты, зарегистрированные подсистемой расширенных событий, содержат события; действия, которые могут быть выполнены в ответ на событие; цели как для синхронной, так и асинхронной обработки данных события.  
  
 Эти пакеты могут быть динамически загружены в адресное пространство процесса. Во время загрузки пакета он регистрирует все объекты, предоставляемые подсистеме расширенных событий.  
  
## <a name="relationship-cardinalities"></a>Количество элементов связей  
  
| От | Кому | Связь |
| ---- | -- | ------------ |  
|sys.dm_xe_packages.module_address|sys.dm_os_loaded_modules.base_address|Многие к одному|  
  
## <a name="see-also"></a>См. также статью  
 [Динамические административные представления и функции (Transact-SQL)](~/relational-databases/system-dynamic-management-views/system-dynamic-management-views.md)  
  
  

