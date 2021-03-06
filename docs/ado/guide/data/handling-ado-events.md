---
description: Обработка событий ADO
title: Обработка событий ADO | Документация Майкрософт
ms.prod: sql
ms.prod_service: connectivity
ms.technology: connectivity
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: conceptual
helpviewer_keywords:
- events [ADO]
- ADO, events
- event handlers [ADO]
ms.assetid: e9003457-0762-48b3-942f-0820266b158f
author: rothja
ms.author: jroth
ms.openlocfilehash: 76af7a55c0f3a6e4de2caea7eb3da67e9c27c5cc
ms.sourcegitcommit: e700497f962e4c2274df16d9e651059b42ff1a10
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/17/2020
ms.locfileid: "88453316"
---
# <a name="handling-ado-events"></a>Обработка событий ADO
Модель событий ADO поддерживает определенные синхронные и асинхронные операции ADO, которые выдают *события*или уведомления до начала или после завершения операции. Событие фактически является вызовом подпрограммы обработчика событий, определяемой в приложении.  
  
 Если вы предоставляете функции или процедуры обработчика для группы событий, которые происходят до начала операции, можно проверить или изменить параметры, переданные в операцию. Так как он еще не выполнялся, можно либо отменить операцию, либо разрешить ее выполнение.  
  
 События, происходящие после завершения операции, особенно важны при асинхронном использовании ADO. Например, приложение, запускающее асинхронный [набор записей. операция открытия](../../../ado/reference/ado-api/open-method-ado-recordset.md) получает уведомления о завершении выполнения операции, когда операция завершается.  
  
 Использование модели событий ADO увеличивает нагрузку на приложение, но предоставляет гораздо большую гибкость, чем другие методы работы с асинхронными операциями, такие как мониторинг свойства [State](../../../ado/reference/ado-api/state-property-ado.md) объекта с помощью цикла.  
  
> [!NOTE]
>  Для обработки событий ADO должен иметь конвейер сообщений или использоваться в модели однопотокового подразделения (STA). События ADO внутренне обрабатываются путем создания скрытого окна. ADO отправляет сообщения в это окно, когда необходимо инициировать события. Это делается для того, чтобы обеспечить отправку событий в поток, который вызвал метод **IConnectionPoint:: Advise** в точке соединения. Эта архитектура может вызвать проблемы, когда поток, который должен получать уведомления, не будет передавать сообщения окна. К потенциальным проблемам относятся события ADO, которые не доставляются в поток, а также время ожидания широковещательных рассылок, что может замедлить работу всей системы, так как скрытые окна не обрабатывают сообщения. В потоках STA обычно используется конвейер сообщений, поэтому эта проблема не является манифестом для потоков STA. Однако потоки MTA обычно не имеют конвейера сообщений, поэтому эта ошибка, как правило, является манифестом для потоков MTA.  
  
 Этот раздел содержит следующие подразделы.  
  
-   [Общие сведения об обработчике событий ADO](../../../ado/guide/data/ado-event-handler-summary.md)  
  
-   [Типы событий](../../../ado/guide/data/types-of-events.md)  
  
-   [Параметры события](../../../ado/guide/data/event-parameters.md)  
  
-   [Совместная работа обработчиков событий](../../../ado/guide/data/how-event-handlers-work-together.md)  
  
-   [Создание экземпляра события ADO на различных языках](../../../ado/guide/data/ado-event-instantiation-by-language.md)  
  
## <a name="see-also"></a>См. также  
 [Сводка по обработчику событий ADO](../../../ado/guide/data/ado-event-handler-summary.md)   
 [Создание экземпляра события ADO по языку](../../../ado/guide/data/ado-event-instantiation-by-language.md)   
 [События ADO](../../../ado/reference/ado-api/ado-events.md)   
 [Параметры события](../../../ado/guide/data/event-parameters.md)   
 [Типы событий](../../../ado/guide/data/types-of-events.md)
