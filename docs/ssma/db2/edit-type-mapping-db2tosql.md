---
description: Изменение сопоставления типов (DB2ToSQL)
title: Изменение сопоставления типов (DB2ToSQL) | Документация Майкрософт
ms.prod: sql
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.technology: ssma
ms.topic: conceptual
ms.assetid: f93c4b7d-74fc-4856-bf42-035289918e83
author: nahk-ivanov
ms.author: alexiva
ms.openlocfilehash: 3e31f1422415a14c4e1fb497ff56806feeb9439e
ms.sourcegitcommit: e700497f962e4c2274df16d9e651059b42ff1a10
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/17/2020
ms.locfileid: "88463541"
---
# <a name="edit-type-mapping-db2tosql"></a>Изменение сопоставления типов (DB2ToSQL)
Диалоговое окно **Изменение сопоставления типов** позволяет указать, как типы сопоставляются между исходным и целевым объектами базы данных.  
  
Доступ к этому диалоговому окну можно получить в нескольких местах:  
  
-   При выборе базы данных-источника или объекта базы данных справа от обозревателя метаданных появляется вкладка **Сопоставление типов** . Нажмите кнопку **Добавить** , чтобы добавить новое сопоставление типов, или кнопку **изменить** , чтобы изменить существующее сопоставление типов.  
  
-   В меню **Сервис** выберите пункт **Параметры проекта** или **Параметры проекта по умолчанию**. В появившемся диалоговом окне выберите **Сопоставление типов**. Нажмите кнопку **Добавить** , чтобы добавить новое сопоставление типов, или кнопку **изменить** , чтобы изменить существующее сопоставление типов.  
  
Сопоставления типов, связанных с таблицами, переопределяют сопоставления типов базы данных и проекта. Сопоставления, зависящие от базы данных, переопределяют сопоставления проектов.  
  
## <a name="options"></a>Варианты  
**Тип источника**  
Выберите исходный тип данных для соотнесения с [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] типом данных.  
  
Если тип данных имеет переменную длину, в разделе **тип источника**будут отображаться следующие поля:  
  
**От**  
Укажите минимальную длину для этого сопоставления. Например, для типа данных **nchar** можно ввести значение 10, чтобы указать, что это сопоставление предназначено для диапазона, начиная с **nchar (10)**.  
  
**Чтобы**  
Укажите максимальную длину для этого сопоставления. Например, для типа данных **nchar** можно ввести значение 20, чтобы указать, что это сопоставление относится к диапазону, завершающему значение **nchar (20)**.  
  
**Тип целевого объекта**  
Выберите [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] тип данных, с которым сопоставлен исходный тип данных. Когда SSMA создает таблицу или хранимую процедуру в [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , тип данных источника изменится на этот тип данных.  
  
Если тип данных имеет переменную длину, в разделе **целевой тип**появится следующее поле:  
  
**Replace with**  
Укажите целевую длину для этого сопоставления. Например, для типа данных **nvarchar** можно ввести значение 20, чтобы указать, что указанный исходный тип данных должен быть сопоставлен с типом **nvarchar (20)**.  
  
