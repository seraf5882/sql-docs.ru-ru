---
description: sys. pdw_health_component_properties (Transact-SQL)
title: sys. pdw_health_component_properties (Transact-SQL) | Документация Майкрософт
ms.custom: ''
ms.date: 03/04/2017
ms.prod: sql
ms.reviewer: ''
ms.technology: system-objects
ms.topic: conceptual
ms.assetid: 66999c0c-dc43-4327-99fb-8366f465e69d
author: ronortloff
ms.author: rortloff
monikerRange: '>= aps-pdw-2016 || = sqlallproducts-allversions'
ms.openlocfilehash: b39e099e2b76c740621fa6844409955d2452d936
ms.sourcegitcommit: e700497f962e4c2274df16d9e651059b42ff1a10
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/17/2020
ms.locfileid: "88475401"
---
# <a name="syspdw_health_component_properties-transact-sql"></a>sys. pdw_health_component_properties (Transact-SQL)
[!INCLUDE [pdw](../../includes/applies-to-version/pdw.md)]

  Хранит свойства, описывающие устройство. Некоторые свойства отображают состояние устройства, а некоторые свойства описывают само устройство.  
  
|Имя столбца|Тип данных|Description|Диапазон|  
|-----------------|---------------|-----------------|-----------|  
|property_id|**int**|Уникальный идентификатор свойства компонента.<br /><br /> property_id и component_id формируют ключ для этого представления.|NOT NULL|  
|component_id|**int**|Идентификатор компонента. См. раздел [sys. pdw_health_components &#40;&#41;Transact-SQL ](../../relational-databases/system-catalog-views/sys-pdw-health-components-transact-sql.md).<br /><br /> property_id и component_id формируют ключ для этого представления.|NOT NULL|  
|property_name|**nvarchar(255)**|Имя свойства.|NOT NULL|  
|physical_name|**nvarchar(32)**|Имя свойства в соответствии с определением изготовителя.|NOT NULL|  
|is_key|**bit**|Определяет, является ли экземпляр устройства уникальным или неуникальным.|NOT NULL<br /><br /> 0 — экземпляр устройства уникален.<br /><br /> 1 — экземпляр устройства не является уникальным.|  
  
## <a name="see-also"></a>См. также  
 [SQL Data Warehouse and Parallel Data Warehouse Catalog Views](../../relational-databases/system-catalog-views/sql-data-warehouse-and-parallel-data-warehouse-catalog-views.md) (Представления каталога в службе "Хранилище данных SQL" и Parallel Data Warehouse)  
  
  
