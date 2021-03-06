---
title: Глобальные параметры (диалоговые окна) (SybaseToSQL) | Документация Майкрософт
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.reviewer: ''
ms.technology: ssma
ms.topic: conceptual
ms.assetid: e11452b7-ba94-4367-a745-5ccf1764acec
author: nahk-ivanov
ms.author: alexiva
ms.openlocfilehash: 4dc7bf9bf6b8f2e20fb8254a3a27ca2e293a0174
ms.sourcegitcommit: e8f6c51d4702c0046aec1394109bc0503ca182f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/07/2020
ms.locfileid: "87931465"
---
# <a name="global-settings-dialogs--sybasetosql"></a>Глобальные параметры (диалоговые окна) (SybaseToSQL)
Используйте страницу диалоговые окна диалогового окна **глобальные параметры** , чтобы указать параметры действия пользователя и предупреждения по умолчанию для SSMA.  
  
Для доступа к параметрам диалогового окна в меню **Сервис** выберите **глобальные параметры**, щелкните **графический интерфейс** в нижней части левой панели, а затем выберите **диалоговые окна**.  
  
## <a name="options"></a>Параметры  
**Предупреждать перед перезаписью объектов**  
Когда SSMA преобразует объекты в SQL Server, некоторые объекты уже могут существовать в метаданных SQL Server проекта. Эти объекты могли быть уже преобразованы, или объекты могут просто иметь то же имя в целевой схеме, что и объекты, которые вы собираетесь преобразовать.  
  
Используйте этот параметр, чтобы указать, должна ли SSMA запрашивать перезапись определений дубликатов объектов:  
  
-   Если выбрано **значение true**, при обнаружении повторяющегося объекта SSMA будет отображать диалоговое окно с предупреждением. В этом диалоговом окне можно задать перезапись отдельных объектов или всех повторяющихся объектов либо пропустить отдельные объекты или все дубликаты объектов.  
  
-   Если выбрано **значение false**, то при указании действия по умолчанию отображается параметр **объект перезаписать действие по умолчанию** .  
  
**Действие по умолчанию перезаписи объекта**  
Этот параметр отображается, если в параметре **Предупреждать перед перезаписью объектов** выбрано **значение false** .  
  
Используйте этот параметр, чтобы указать поведение перезаписи объекта по умолчанию:  
  
-   Если выбрано **значение true**, SSMA автоматически перезапишет объекты в метаданных проекта SQL Server с тем же именем и в той же целевой схеме, что и объект для преобразования.  
  
-   Если выбрано **значение false**, SSMA не перезаписывает метаданные объекта во время преобразования.  
  
