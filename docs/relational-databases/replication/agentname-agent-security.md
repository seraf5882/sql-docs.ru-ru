---
description: Защита агента &lt;Имя_агента&gt;
title: Защита агента &lt;Имя_агента&gt; | Документация Майкрософт
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql13.rep.newsubwizard.agentnameagentsecurity.f1
ms.assetid: d34c7ef8-cf77-4ffd-887f-3c4214dfd71e
author: MashaMSFT
ms.author: mathoma
monikerRange: =azuresqldb-mi-current||>=sql-server-2016||=sqlallproducts-allversions
ms.openlocfilehash: 283f19912bcb5f3c57f84c845d9bf051a7c211d0
ms.sourcegitcommit: e700497f962e4c2274df16d9e651059b42ff1a10
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/17/2020
ms.locfileid: "88470376"
---
# <a name="ltagentnamegt-agent-security"></a>Защита агента &lt;Имя_агента&gt;
[!INCLUDE [SQL Server SQL MI](../../includes/applies-to-version/sql-asdbmi.md)]
  На странице **\<AgentName>Безопасность агента**  можно указать учетные записи, от имени которых выполняется агент распространителя (для репликации транзакций или репликации моментальных снимков) или агент слияния (для репликации слиянием), а также создать подключения к компьютерам в топологии репликации. Сведения о разрешениях, требуемых агентами, и об оптимальных методах защиты репликации см. в статьях [Модель безопасности агента репликации](../../relational-databases/replication/security/replication-agent-security-model.md) и [Рекомендации по защите репликации](../../relational-databases/replication/security/replication-security-best-practices.md).  
  
## <a name="options"></a>Параметры  
 Нажмите кнопку свойств ( **...** ) в строке для каждого подписчика, чтобы открыть диалоговое окно **Безопасность агента распространителя** или **Безопасность агента слияния** . Для получения дополнительных сведений о разрешениях, необходимых для учетных записей агентов, нажмите кнопку **Справка** в появившемся диалоговом окне.  
  
 После ввода параметров в одном из диалоговых окон в сетке будут отображены сведения о соединении для подписчика.  
  
 **Агент для подписчика**  
 Имя каждого подписчика.  
  
 **Соединение с распространителем**  
 Отображается для репликации транзакций и репликации моментальных снимков. Контекст, в котором устанавливается соединение с распространителем. Локальные соединения всегда создаются с помощью контекста учетной записи [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows, под которой работает агент.  
  
-   Для принудительных подписок локальным соединением является соединение с распространителем, поэтому в этом поле всегда будет отображаться следующая строка: **Impersonate '\<Domain>\\<имя_для_входа\>'** или **Impersonate '\<Computer>\\<имя_для_входа\>'** для принудительных подписок.  
  
-   Для подписок по запросу соединения также могут быть созданы в контексте имени входа [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]. В поле отображается одна из следующих строк: **Использовать имя для входа '\<Login>'** , **Выполнить олицетворение '\<Domain>\\<Login\>'** или **Выполнить олицетворение '\<Computer>\\<Login\>'** . [!INCLUDE[msCoName](../../includes/msconame-md.md)] рекомендует выполнять соединение в контексте учетной записи Windows.  
  
 **Соединение с издателем и распространителем**  
 Отображается для репликации слиянием. Контекст, под которым созданы соединения с издателем и распространителем. Локальные соединения всегда создаются с помощью контекста учетной записи Windows, под которой работает агент.  
  
-   Для принудительных подписок локальным соединением является соединение с издателем и распространителем, поэтому в этом поле всегда будет отображаться следующая строка: **Impersonate '\<Domain>\\<имя_для_входа\>'** или **Impersonate '\<Computer>\\<имя_для_входа\>'** для принудительных подписок.  
  
-   Для подписок по запросу соединения также могут быть созданы в контексте имени входа [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] . В поле отображается одна из следующих строк: **Использовать имя для входа '\<Login>'** , **Выполнить олицетворение '\<Domain>\\<Login\>'** или **Выполнить олицетворение '\<Computer>\\<Login\>'** . [!INCLUDE[msCoName](../../includes/msconame-md.md)] рекомендует выполнять соединение в контексте учетной записи Windows.  
  
 **Соединение с подписчиком**  
 Контекст, в котором устанавливается соединение с подписчиком. Локальные соединения всегда создаются с помощью контекста учетной записи Windows, под которой работает агент.  
  
-   Для подписок по запросу локальным соединением является соединение с подписчиком, поэтому в этом поле всегда будет отображаться следующая строка: **Impersonate '\<Domain>\\<имя_для_входа\>'** или **Impersonate '\<Computer>\\<имя_для_входа\>'** для принудительных подписок.  
  
-   Для принудительных подписок соединения также могут быть созданы в контексте имени входа [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] . В поле отображается одна из следующих строк: **Использовать имя для входа '\<Login>'** , **Выполнить олицетворение '\<Domain>\\<Login\>'** или **Выполнить олицетворение '\<Computer>\\<Login\>'** . [!INCLUDE[msCoName](../../includes/msconame-md.md)] рекомендует выполнять соединение в контексте учетной записи Windows.  
  
## <a name="see-also"></a>См. также:  
 [Просмотр и изменение свойств подписки по запросу](../../relational-databases/replication/view-and-modify-pull-subscription-properties.md)   
 [Просмотр и изменение свойств принудительной подписки](../../relational-databases/replication/view-and-modify-push-subscription-properties.md)   
 [Идентификатор и управление доступом для репликации](../../relational-databases/replication/security/identity-and-access-control-replication.md)   
 [Replication Agent Security Model](../../relational-databases/replication/security/replication-agent-security-model.md)  (Модель безопасности агента репликации)  
 [Просмотр и изменение параметров безопасности репликации](../../relational-databases/replication/security/view-and-modify-replication-security-settings.md)  
  
  
