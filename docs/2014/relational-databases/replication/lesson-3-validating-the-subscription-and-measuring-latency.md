---
title: Занятие 3. Проверка подписки и измерение задержки | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- replication
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- replication [SQL Server], tutorials
ms.assetid: 147f7b93-1804-4e0b-9e17-57a51d035b2a
caps.latest.revision: 11
author: craigg-msft
ms.author: craigg
manager: craigg
ms.openlocfilehash: beb76874d66e6808b2ec0e31bbdf22624d73edab
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/02/2018
ms.locfileid: "37284920"
---
# <a name="lesson-3-validating-the-subscription-and-measuring-latency"></a>Занятие 3. Проверка подписки и измерение задержки
  На этом занятии изучаются трассировочные токены для проверки реплицируемых для подписчика изменений и определения задержки, т.е. времени, когда изменение, внесенное на стороне издателя, должно перейти на сторону подписчика. Приступать к этому занятию нужно только по завершении предыдущего: [Занятие 2. Создание подписки на публикацию транзакций](lesson-2-creating-a-subscription-to-the-transactional-publication.md).  
  
### <a name="to-insert-a-tracer-token-and-view-information-on-the-token"></a>Вставка трассировочного токена и просмотр сведений о токене  
  
1.  Подключитесь к издателю в среде [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], разверните узел сервера, щелкните правой кнопкой мыши папку **Репликация** и выберите пункт **Запустить монитор репликации**.  
  
     Запустится монитор репликации.  
  
2.  Раскройте группу издателей на левой панели, затем экземпляр издателя и выберите публикацию **AdvWorksProductTrans** .  
  
3.  Щелкните вкладку **Трассировочные токены** .  
  
4.  Выберите команду **Вставить трассировочный маркер**.  
  
5.  Просмотрите затраченное время для трассировочного маркера в следующих столбцах: **От издателя к распространителю**, **От распространителя к подписчику**, **Общая задержка**. Значение **Ожидание** указывает на то, что токен еще не достиг указанной точки.  
  
## <a name="next-steps"></a>Следующие шаги  
 На этом занятии показывается, как использовать трассировочные токены для проверки изменений, реплицируемых от издателя подписчику. Кроме того, показывается, как вставлять, обновлять и удалять данные из таблицы **Product** на стороне издателя и строить запрос к таблице **Product** на стороне подписчика для проверки изменений после репликации.  
  
 На этом учебник «Репликация данных между постоянно соединенными серверами» завершается. Похожий учебник, использующий репликацию слиянием, см. в разделе [Tutorial: Replicating Data with Mobile Clients](tutorial-replicating-data-with-mobile-clients.md).  
  
## <a name="see-also"></a>См. также  
 [Измерение задержки и проверка правильности соединений для репликации транзакций](monitor/measure-latency-and-validate-connections-for-transactional-replication.md)  
  
  