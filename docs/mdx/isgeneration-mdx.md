---
description: IsGeneration (многомерные выражения)
title: Generation (многомерные выражения) | Документация Майкрософт
ms.date: 06/04/2018
ms.prod: sql
ms.technology: analysis-services
ms.custom: mdx
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan
ms.openlocfilehash: e7b7f3df41af6af51a826352814fc6aef52ef0a0
ms.sourcegitcommit: e700497f962e4c2274df16d9e651059b42ff1a10
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/17/2020
ms.locfileid: "88471836"
---
# <a name="isgeneration-mdx"></a>IsGeneration (многомерные выражения)


  Возвращает значение, сообщающее, принадлежит ли заданный элемент указанному поколению.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
IsGeneration(Member_Expression, Generation_Number)   
```  
  
## <a name="arguments"></a>Аргументы  
 *Member_Expression*  
 Допустимое многомерное выражение, возвращающее элемент.  
  
 *Generation_Number*  
 Допустимое числовое выражение, указывающее поколение, для которого заданный элемент будет вычисляться.  
  
## <a name="remarks"></a>Remarks  
 Функция **формирования** возвращает **значение true** , если указанный элемент имеет указанный номер поколения. В противном случае функция возвращает **значение false**. Кроме того, если указанный элемент равен пустому элементу **, функция IsEmpty** возвращает **значение false**.  
  
 При индексировании поколения конечные элементы имеют индекс поколения 0. Индекс поколения неконечных элементов определяется путем получения наибольшего индекса поколения из объединения всех потомков заданного элемента и прибавления 1 к этому значению. В зависимости от способа определения индекса поколения неконечных элементов конкретный неконечный элемент может принадлежать нескольким поколениям.  
  
## <a name="example"></a>Пример  
 В следующем примере возвращается значение TRUE, если элемент [Date].[Fiscal].CurrentMember принадлежит ко второму поколению:  
  
 `WITH MEMBER MEASURES.ISGENERATIONDEMO AS`  
  
 `IsGeneration([Date].[Fiscal].CURRENTMEMBER, 2)`  
  
 `SELECT {MEASURES.ISGENERATIONDEMO} ON 0,`  
  
 `[Date].[Fiscal].MEMBERS ON 1`  
  
 `FROM [Adventure Works]`  
  
## <a name="see-also"></a>См. также:  
 [Справочник по функциям многомерных выражений (многомерные выражения)](../mdx/mdx-function-reference-mdx.md)  
  
  
