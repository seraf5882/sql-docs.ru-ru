---
title: Объект заданий (агент SQL Server) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dbe-cross-instance
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- SQLAgent:Jobs
- Jobs object
ms.assetid: 225b5e2d-4a78-4178-b2b6-b419df83c4aa
caps.latest.revision: 20
author: MikeRayMSFT
ms.author: mikeray
manager: craigg
ms.openlocfilehash: 85cdedd2ffb9bebb4458ef325992e56e93345628
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/02/2018
ms.locfileid: "37305524"
---
# <a name="sql-server-agent-jobs-object"></a>Агент SQL Server, объект Jobs
  Объект производительности **Jobs** агента SQL Server содержит счетчики производительности, отображающие сведения о заданиях агента SQL Server. В следующей таблице перечислены счетчики этого объекта.  
  
 Приведенная ниже таблица содержит счетчики объекта **SQLAgent:Jobs** .  
  
|Имя|Описание|  
|----------|-----------------|  
|**Активные задания**|Данный счетчик отображает количество выполняемых в данный момент заданий.|  
|**Невыполненные задания**|Этот счетчик отображает количество заданий, завершенных с ошибкой.|  
|**Эффективность выполнения заданий**|Этот счетчик отображает процентное соотношение успешно завершенных заданий от общего количества выполняемых заданий.|  
|**Задания, запускаемые за минуту**|Данный счетчик отображает количество заданий, запущенных в течение последней минуты.|  
|**Задания в очереди**|Данный счетчик отображает количество заданий, готовых к выполнению агентом SQL Server, но еще не запущенных.|  
|**Успешно выполненные задания**|Данный счетчик отображает количество успешно завершенных заданий.|  
  
 Каждый из счетчиков объекта содержит следующие экземпляры.  
  
|Экземпляр|Описание|  
|--------------|-----------------|  
|**_Total**|Сведения обо всех заданиях.|  
|**Предупреждения**|Сведения о заданиях, запущенных по предупреждению.|  
|**Прочие**|Сведения о заданиях, запущенных не по предупреждению и не по расписанию. Обычно это задания, запущенные вручную с помощью процедуры **sp_start_job**.|  
|**Расписания**|Сведения о заданиях, запущенных по расписанию.|  
  
## <a name="see-also"></a>См. также  
 [Реализация заданий](../../ssms/agent/implement-jobs.md)   
 [Использование объектов производительности](../../ssms/agent/use-performance-objects.md)   
 [Наблюдение за использованием ресурсов (системный монитор)](monitor-resource-usage-system-monitor.md)  
  
  