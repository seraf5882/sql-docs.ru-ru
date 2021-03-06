---
title: Функция Склремоведриверманажер | Документация Майкрософт
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
apiname:
- SQLRemoveDriverManager
apilocation:
- sqlsrv32.dll
apitype: dllExport
f1_keywords:
- SQLRemoveDriverManager
helpviewer_keywords:
- SQLRemoveDriverManager function function [ODBC]
ms.assetid: 3a41511f-6603-4b81-a815-7883874023c4
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: c94765dfe76bc5a1ef188328a6fe27e96671efb1
ms.sourcegitcommit: 99f61724de5edf6640efd99916d464172eb23f92
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/28/2020
ms.locfileid: "87363137"
---
# <a name="sqlremovedrivermanager-function"></a>Функция SQLRemoveDriverManager
**Соответствия**  
 Введенная версия: ODBC 3,0: не рекомендуется в Windows XP с пакетом обновления 2, Windows Server 2003 с пакетом обновления 1 (SP1) и более поздних операционных системах.  
  
 **Сводка**  
 **Склремоведриверманажер** изменяет или удаляет сведения о компонентах ODBC Core из записи Odbcinst.ini в сведениях о системе.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
  
BOOL SQLRemoveDriverManager(  
     LPDWORD     pdwUsageCount);  
```  
  
## <a name="arguments"></a>Аргументы  
 *пдвусажекаунт*  
 Проверки Число использований диспетчера драйверов после вызова этой функции.  
  
## <a name="returns"></a>Результаты  
 Функция возвращает TRUE, если она успешна, и FALSE в случае сбоя. Если при вызове этой функции в системной информации не существует записи, функция возвращает значение FALSE.  
  
## <a name="diagnostics"></a>Диагностика  
 Когда **склремоведриверманажер** возвращает значение false, связанное значение * \* пферроркоде* может быть получено путем вызова **склинсталлереррор**. В следующей таблице перечислены значения * \* пферроркоде* , которые могут быть возвращены **склинсталлереррор** , и объясняется каждый из них в контексте этой функции.  
  
|*\*пферроркоде*|Error|Описание|  
|---------------------|-----------|-----------------|  
|ODBC_ERROR_GENERAL_ERR|Общая ошибка установщика|Произошла ошибка, для которой не возникала конкретная ошибка установщика.|  
|ODBC_ERROR_COMPONENT_NOT_FOUND|Компонент не найден в реестре|Установщику не удалось удалить сведения о диспетчере драйверов, поскольку они не существовали в реестре или не найдены в реестре.|  
|ODBC_ERROR_USAGE_UPDATE_FAILED|Не удалось увеличить или уменьшить счетчик использования компонентов|Установщику не удалось уменьшить число использований диспетчера драйверов.|  
|ODBC_ERROR_OUT_OF_MEM|Нет памяти|Установщику не удалось выполнить функцию из-за нехватки памяти.|  
  
## <a name="comments"></a>Комментарии  
 **Склремоведриверманажер** дополняет функцию **склинсталлдриверманажер** и обновляет счетчик использования компонентов в системных сведениях. Эта функция должна вызываться только из приложения установки.  
  
 **Склремоведриверманажер** уменьшит число использований основных компонентов на 1. Если счетчик использования компонентов переходит в значение 0, то сведения о системе записи будут удалены. Запись основного компонента находится в следующем расположении в разделе "сведения о системе" под заголовком "ODBC Core":  
  
 `HKEY_LOCAL_MACHINE`  
  
 `SOFTWARE`  
  
 `ODBC`  
  
 `Odbcinst.ini`  
  
> [!CAUTION]  
>  Приложение не должно физически удалять файлы диспетчера драйверов, если счетчик использования компонента и число использований файлов достигли нуля.  
  
 **Склремоведриверманажер** на самом деле не удаляет никакие файлы. Вызывающая программа отвечает за удаление файлов и поддержку счетчиков использования файлов. Однако файлы диспетчера драйверов не должны удаляться, если счетчик использования компонентов и счетчик использования файлов достигли нуля, так как эти файлы могут использоваться другими приложениями, которые не увеличивают счетчик использования файлов.  
  
 **Склремоведриверманажер** вызывается как часть процесса удаления. Компоненты ODBC Core (в том числе диспетчер драйверов, Библиотека курсоров, установщик, библиотека языка, администратор, файлы преобразователя и т. д.) удаляются в целом. Следующие файлы не удаляются при вызове **склремоведриверманажер** в ходе процесса удаления:  

:::row:::
    :::column:::
        ODBC32DLL  
        ODBCCR32.DLL  
        ODBCCU32.DLL  
        ODBCINT.DLL  
        ODBCTRAC.DLL  
        MSVCRT40.DLL  
        ODBCCP32.CPL  
    :::column-end:::
    :::column:::
        ODBCCP32.DLL  
        ODBC16GT.DLL  
        ODBC32GT.DLL  
        DS16GT.DLL  
        DS32GT.DLL  
        ODBCAD32.EXE  
    :::column-end:::
:::row-end:::

 **Склремоведриверманажер** также вызывается как часть процесса обновления. Если приложение обнаруживает, что оно должно выполнить обновление и ранее установило драйвер, драйвер следует удалить, а затем установить заново.  
  
 Сначала необходимо вызвать **склремоведриверманажер** , чтобы уменьшить число использований компонента. Чтобы увеличить число использований компонента, необходимо вызвать **склинсталлдриверекс** . Программа установки приложения должна заменить старые файлы основных компонентов новыми файлами. Счетчики использования файлов останутся прежними, а другие приложения, использующие старые файлы компонентов версии Core, теперь будут использовать более новые версии файлов.  
  
## <a name="related-functions"></a>Связанные функции  
  
|Сведения о|См.|  
|---------------------------|---------|  
|Установка диспетчера драйверов|[склинсталлдриверманажер](../../../odbc/reference/syntax/sqlinstalldrivermanager-function.md)|
