---
description: Union (многомерные выражения)
title: Union (многомерные выражения) | Документация Майкрософт
ms.date: 06/04/2018
ms.prod: sql
ms.technology: analysis-services
ms.custom: mdx
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan
ms.openlocfilehash: b0b4240d6c646761c5d962e4b9fa1ca54e0dcc0e
ms.sourcegitcommit: e700497f962e4c2274df16d9e651059b42ff1a10
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/17/2020
ms.locfileid: "88341210"
---
# <a name="union--mdx"></a>Union (многомерные выражения)


  Возвращает набор, порожденный объединением двух наборов, по желанию сохраняя повторяющиеся элементы.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
Standard syntax  
Union(Set_Expression1, Set_Expression2 [,...n][, ALL])  
  
Alternate syntax 1  
Set_Expression1 + Set_Expression2 [+...n]  
  
Alternate syntax 2  
{Set_Expression1 , Set_Expression2 [,...n]}  
```  
  
## <a name="arguments"></a>Аргументы  
 *Задание выражения 1*  
 Допустимое многомерное выражение, возвращающее набор.  
  
 *Задать выражение 2*  
 Допустимое многомерное выражение, возвращающее набор.  
  
## <a name="remarks"></a>Remarks  
 Эта функция возвращает объединение двух или более заданных наборов. В стандартном синтаксисе и с альтернативным синтаксисом 1 дубликаты по умолчанию устраняются. В стандартном синтаксисе при использовании флага **ALL** дубликаты в присоединенном наборе сохраняются. Дубликаты удаляются из конца набора. При использовании второго альтернативного варианта синтаксиса дубликаты всегда сохраняются.  
  
## <a name="examples"></a>Примеры  
 В следующих примерах демонстрируется поведение функции **Union** с использованием каждого синтаксиса.  
  
### <a name="standard-syntax-duplicates-eliminated"></a>Стандартный синтаксис, дубликаты исключаются  
  
```  
SELECT Union   
   ([Date].[Calendar Year].children  
   , {[Date].[Calendar Year].[CY 2002]}  
   , {[Date].[Calendar Year].[CY 2003]}  
   ) ON 0  
FROM [Adventure Works]  
  
```  
  
### <a name="standard-syntax-duplicates-retained"></a>Стандартный синтаксис, дубликаты сохраняются  
  
```  
SELECT Union   
   ([Date].[Calendar Year].children  
   , {[Date].[Calendar Year].[CY 2002]}  
   , {[Date].[Calendar Year].[CY 2003]}  
   , ALL  
   ) ON 0  
FROM [Adventure Works]  
  
```  
  
### <a name="alternate-syntax-1-duplicates-eliminated"></a>Первый альтернативный синтаксис, дубликаты исключаются  
  
```  
SELECT   
   [Date].[Calendar Year].children   
   + {[Date].[Calendar Year].[CY 2002]}   
   + {[Date].[Calendar Year].[CY 2003]} ON 0  
FROM [Adventure Works]  
  
```  
  
### <a name="alternate-syntax-2-duplicates-retained"></a>Второй альтернативный синтаксис, дубликаты сохраняются  
  
```  
SELECT   
   {[Date].[Calendar Year].children  
   , [Date].[Calendar Year].[CY 2002]  
   , [Date].[Calendar Year].[CY 2003]} ON 0  
FROM [Adventure Works]  
  
```  
  
## <a name="see-also"></a>См. также:  
 [+ &#40;Union&#41; &#40;&#41;многомерных выражений ](../mdx/union-mdx-operator-reference.md)   
 [Справочник по функциям многомерных выражений (многомерные выражения)](../mdx/mdx-function-reference-mdx.md)  
  
  
