---
title: Элемент FeatureSet (DTA) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- database-engine
ms.tgt_pltfrm: ''
ms.topic: conceptual
dev_langs:
- XML
helpviewer_keywords:
- FeatureSet element
ms.assetid: f2070c53-4a5c-4c11-ac38-96ee200c84f0
caps.latest.revision: 14
author: stevestein
ms.author: sstein
manager: craigg
ms.openlocfilehash: fb596ca38310bce4b9be6f1061952ebc2756fc73
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/02/2018
ms.locfileid: "37226514"
---
# <a name="featureset-element-dta"></a>Элемент FeatureSet (DTA)
  Содержит структуры физического проектирования (индексы или индексированные представления), которые помощник по настройке ядра СУБД должен использовать во время анализа.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
<DTAInput>  
...code removed...  
    <TuningOptions>  
      <FeatureSet>...</FeatureSet>  
```  
  
## <a name="element-characteristics"></a>Характеристики элемента  
  
|Характеристика|Описание|  
|--------------------|-----------------|  
|**Тип данных и длина**|`string`, без ограничения длины|  
|**Допустимые значения**|**IDX_IV**<br /> Индексы и индексированные представления.<br /><br /> **IDX**<br /> Только индексы.<br /><br /> **IV**<br /> Только индексированные представления.<br /><br /> **NCL_IDX**<br /> Только некластеризованные индексы.<br /><br /> Используйте с данным элементом одно из этих значений.|  
|**Значение по умолчанию**|**IDX**|  
|**Наличие**|Требуется для каждого элемента `TuningOptions`, если не используется элемент `DropOnlyMode`. Если `DropOnlyMode` — используется, вы не можете использовать `FeatureSet`. Эти элементы являются взаимоисключающими.|  
  
## <a name="element-relationships"></a>Связи элемента  
  
|Связь|Элементы|  
|------------------|--------------|  
|**Родительский элемент**|[Элемент TuningOptions &#40;DTA&#41;](tuningoptions-element-dta.md)|  
|**Дочерние элементы**|Нет.|  
  
## <a name="example"></a>Пример  
 Пример использования этого элемента см. в разделе [Образец простого входного файла XML (DTA)](simple-xml-input-file-sample-dta.md).  
  
## <a name="see-also"></a>См. также  
 [Справочник по входным XML-файлам (помощник по настройке ядра СУБД)](xml-input-file-reference-database-engine-tuning-advisor.md)  
  
  