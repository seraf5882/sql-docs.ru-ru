---
title: Решения для интеллектуального анализа данных | Документация Майкрософт
ms.custom: ''
ms.date: 07/17/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- analysis-services
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- data mining [Analysis Services], about data mining
- data mining [Analysis Services], development
ms.assetid: 84f6548d-ebb0-4e10-9b29-66253fa0a04a
caps.latest.revision: 62
author: minewiskan
ms.author: owend
manager: craigg
ms.openlocfilehash: 57c0dcbc62475cd55b827d9104efe8a8c2db249c
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/02/2018
ms.locfileid: "37263850"
---
# <a name="data-mining-solutions"></a>Решения интеллектуального анализа данных
  Решение по интеллектуальному анализу данных представляет собой решение служб [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] , которое содержит один или несколько проектов интеллектуального анализа данных.  
  
 Подразделы этого раздела содержат сведения о том, как спроектировать и внедрить интегрированное решение по интеллектуальному анализу данных с помощью служб [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)]. Общие сведения о процессе разработки в области интеллектуального анализа данных и связанных с этим средствах см. в разделе [Data Mining Concepts](data-mining-concepts.md).  
  
 Дополнительные сведения о других типах проектов, полезных для интеллектуального анализа данных, см. в разделе [Связанные проекты для решений интеллектуального анализа данных](data-mining-solutions.md).  
  
 [Реляционные и Многомерные решения](#bkmk_RelMD)  
  
 [Развертывание решений интеллектуального анализа данных](#bkmk_Deploy)  
  
 [Пошаговые руководства по решениям](#bkmk_Walkthru)  
  
##  <a name="bkmk_RelMD"></a> Реляционные и многомерные решения  
 Решение по интеллектуальному анализу данных может быть основано либо на многомерных данных (то есть на существующем кубе), либо на чисто реляционных данных, например таблицах и представлениях в хранилище данных, а также на текстовых файлах, таблицах Excel и других внешних источниках данных.  
  
-   Объекты интеллектуального анализа данных можно создать внутри существующего многомерного решения базы данных.  
  
     Обычно подобное решение создается, если куб уже создан и требуется выполнить интеллектуальный анализ данных, используя этот куб в качестве источника данных. При перемещении и резервном копировании моделей на основе куба сам куб также должен перемещаться или копироваться.  
  
-   Можно создать решение по интеллектуальному анализу данных, которое будет содержать только объекты интеллектуального анализа данных, включая поддерживающие источники данных и представления источников данных, и будет использовать только реляционный источник данных.  
  
     Этот способ предпочтителен при создании моделей интеллектуального анализа данных, поскольку обработка и выполнение запросов применительно к реляционным источникам данных обычно выполняются быстрее. Также можно легко перемещать модели и выполнять их резервное копирование между серверами с помощью команд EXPORT и IMPORT.  
  
##  <a name="bkmk_Deploy"></a> Развертывание решений интеллектуального анализа данных  
 Экземпляр служб [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], на котором развертывается решение, должен работать в режиме, поддерживающем многомерные объекты и объекты интеллектуального анализа данных, т. е. невозможно развернуть объекты интеллектуального анализа данных на экземпляре, который содержит данные табличных моделей или данные PowerPivot.  
  
 Поэтому, если решение интеллектуального анализа данных создается в среде Visual Studio, обязательно используйте шаблон **Проект многомерных данных и интеллектуального анализа данных служб Analysis Services**.  
  
 Во время развертывания решения объекты, используемые для интеллектуального анализа данных, создаются на указанном экземпляре служб [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] — в базе данных, имя которой совпадает с именем файла решения.  
  
 Дополнительные сведения о способе развертывания как реляционных, так и многомерных решений см. в разделе [Развертывание решений интеллектуального анализа данных](deployment-of-data-mining-solutions.md).  
  
##  <a name="bkmk_Walkthru"></a> Пошаговое руководство по решениям  
 Содержит обзорные сведения о том, как создавать решения по интеллектуальному анализу данных с помощью мастера интеллектуального анализа данных.  
  
 [Создание реляционной структуры интеллектуального анализа данных](create-a-relational-mining-structure.md)  
 Создание структуры интеллектуального анализа данных на основе реляционных данных, текстовых файлов и других источников, которые можно объединить в представлении источников данных.  
  
 [Создание структуры интеллектуального анализа данных OLAP](create-an-olap-mining-structure.md)  
 Создание структуры интеллектуального анализа данных на основе данных куба OLAP. Модели, создаваемые на основе данных OLAP, можно сохранять в виде измерения интеллектуального анализа данных, или же можно сохранить набор данных и модели в виде нового куба.  
  
## <a name="in-this-section"></a>в этом разделе  
 [Проекты интеллектуального анализа данных](data-mining-projects.md)  
  
 [Обработка объектов интеллектуального анализа данных](processing-data-mining-objects.md)  
  
 [Связанные проекты для решений интеллектуального анализа данных](data-mining-solutions.md)  
  
 [Развертывание решений интеллектуального анализа данных](deployment-of-data-mining-solutions.md)  
  
## <a name="related-tasks-and-topics"></a>Связанные задачи и разделы  
 После создания базового решения по интеллектуальному анализу данных, включая источники данных и структуру интеллектуального анализа данных, можно строить решение дальше, добавляя новые модели, тестируя и сравнивая модели, создавая прогнозы и экспериментируя с подмножествами данных.  
  
 Дополнительные сведения см. в следующих разделах.  
  
|Задания|Подраздел|  
|-----------|------------|  
|Тестирование создаваемых моделей, проверка качества обучающих данных и создание диаграмм, представляющих точность моделей интеллектуального анализа данных.|[Тестирование и проверка &#40;интеллектуального анализа данных&#41;](testing-and-validation-data-mining.md)|  
|Обучение модели путем заполнения структуры и связанных моделей данными. Обновление и расширение моделей новыми данными.|[Обработка объектов интеллектуального анализа данных](processing-data-mining-objects.md)|  
|Настройка модели интеллектуального анализа данных путем применения фильтров к обучающим данным, выбора другого алгоритма или задания расширенных параметров алгоритма.|[Настройка структуры и моделей интеллектуального анализа данных](customize-mining-models-and-structure.md)|  
|Настройка модели интеллектуального анализа данных путем применения фильтров к данным, используемым в обучении модели.|[Добавление моделей интеллектуального анализа данных в структуру &#40;службы Analysis Services — Интеллектуальный анализ данных&#41;](add-mining-models-to-a-structure-analysis-services-data-mining.md)|  
|Обновление решений по интеллектуальному анализу данных и управление ими.|Ссылка подлежит определению|  
  
## <a name="see-also"></a>См. также  
 [Учебники по интеллектуальному анализу данных &#40;служб Analysis Services&#41;](../data-mining-tutorials-analysis-services.md)  
  
  