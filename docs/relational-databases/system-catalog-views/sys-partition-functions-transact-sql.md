---
description: sys.partition_functions (Transact-SQL)
title: sys. partition_functions (Transact-SQL) | Документация Майкрософт
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: database-engine, sql-database, sql-data-warehouse, pdw
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
f1_keywords:
- sys.partition_functions_TSQL
- partition_functions
- sys.partition_functions
- partition_functions_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- sys.partition_functions catalog view
ms.assetid: 96515727-728b-4bea-804a-36ce915b8b75
author: CarlRabeler
ms.author: carlrab
monikerRange: '>=aps-pdw-2016||=azuresqldb-current||=azure-sqldw-latest||>=sql-server-2016||=sqlallproducts-allversions||>=sql-server-linux-2017||=azuresqldb-mi-current'
ms.openlocfilehash: d962b18caaaa8f573f58456ebbd1b7a1f71b5afe
ms.sourcegitcommit: e700497f962e4c2274df16d9e651059b42ff1a10
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/17/2020
ms.locfileid: "88401620"
---
# <a name="syspartition_functions-transact-sql"></a>sys.partition_functions (Transact-SQL)
[!INCLUDE [sql-asdb-asdbmi-asa-pdw](../../includes/applies-to-version/sql-asdb-asdbmi-asa-pdw.md)]

  Содержит по одной строке для каждой функции секционирования в [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].  
  
|Имя столбца|Тип данных|Описание|  
|-----------------|---------------|-----------------|  
|**name**|**sysname**|Имя функции секционирования. Уникален в пределах базы данных.|  
|**function_id**|**int**|Идентификатор функции секционирования. Уникален в пределах базы данных.|  
|**type**|**char(2)**|Тип функции.<br /><br /> R = диапазон|  
|**type_desc**|**nvarchar(60)**|Тип функции.<br /><br /> RANGE|  
|**ветвление**|**int**|Число секций, создаваемых функцией.|  
|**boundary_value_on_right**|**bit**|Для секционирования по диапазонам.<br /><br /> 1 = граничное значение включается в правый (RIGHT) диапазон границы.<br /><br /> 0 = LEFT (левый).|  
|**is_system**||**Область применения**: [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] и более поздних версий.<br /><br /> 1 = объект используется для фрагментов полнотекстового индекса.<br /><br /> 0 = объект не используется для фрагментов полнотекстового индекса.|  
|**create_date**|**datetime**|Дата создания функции.|  
|**modify_date**|**datetime**|Дата последнего изменения функции с помощью инструкции ALTER.|  
  
## <a name="permissions"></a>Разрешения  
 Необходимо быть членом роли **public**. Дополнительные сведения см. в разделе [Metadata Visibility Configuration](../../relational-databases/security/metadata-visibility-configuration.md).  
  
## <a name="see-also"></a>См. также:  
 [Представления каталога функции секционирования &#40;&#41;Transact-SQL ](../../relational-databases/system-catalog-views/partition-function-catalog-views-transact-sql.md)   
 [Представления каталога (Transact-SQL)](../../relational-databases/system-catalog-views/catalog-views-transact-sql.md)   
 [sys. partition_range_values &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/sys-partition-range-values-transact-sql.md)   
 [sys.partition_parameters (Transact-SQL)](../../relational-databases/system-catalog-views/sys-partition-parameters-transact-sql.md)  
  
  
