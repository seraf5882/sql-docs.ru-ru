---
title: M (тип данных geometry) | Документы Майкрософт
ms.custom: ''
ms.date: 08/03/2017
ms.prod: sql
ms.prod_service: database-engine, sql-database
ms.reviewer: ''
ms.technology: t-sql
ms.topic: language-reference
f1_keywords:
- M (geometry Data Type)
- M_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- M (geometry Data Type)
ms.assetid: 443ae2ea-739b-41ef-96cc-ac5dfd65e10b
author: MladjoA
ms.author: mlandzic
ms.openlocfilehash: b8d0c4dd1b813ce5da8f0272a0c2e19e7beab1c6
ms.sourcegitcommit: b57d98e9b2444348f95c83a24b8eea0e6c9da58d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/21/2020
ms.locfileid: "86555693"
---
# <a name="m-geometry-data-type"></a>M (тип данных geometry)
[!INCLUDE [SQL Server SQL Database](../../includes/applies-to-version/sql-asdb.md)]

  Возвращает значение **M** (мера) для экземпляра **geometry**. Семантика значения этой меры определяется пользователем.  

## <a name="syntax"></a>Синтаксис  
  
```  
  
.M  
```  
  
[!INCLUDE[sql-server-tsql-previous-offline-documentation](../../includes/sql-server-tsql-previous-offline-documentation.md)]

## <a name="arguments"></a>Аргументы
  
## <a name="return-types"></a>Типы возвращаемых данных  
 Тип [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]: **float**  
  
 Тип CLR: **SqlDouble**  
  
## <a name="remarks"></a>Remarks  
 Значение этого свойства равно NULL, если экземпляр **geometry** не имеет тип **Point**, а также для любого экземпляра **Point**, для которого он не установлен.  
  
 Это свойство доступно только для чтения.  
  
 Значения **M** не используются в библиотечных вычислениях и поэтому не будут передаваться в библиотеку.  
  
## <a name="examples"></a>Примеры  
 В следующем примере создается экземпляр `Point` со значениями Z (уровень) и M (мера), а также используется выражение `M` для выборки значения M экземпляра.  
  
```  
DECLARE @g geometry;  
SET @g = geometry::STGeomFromText('POINT(1 2 3 4)', 0);  
SELECT @g.M;  
```  
  
## <a name="see-also"></a>См. также:  
 [Расширенные методы экземпляров Geometry](../../t-sql/spatial-geometry/extended-methods-on-geometry-instances.md)   
 [Z (тип данных geometry)](../../t-sql/spatial-geometry/z-geometry-data-type.md)   
 [AsTextZM (тип данных geometry)](../../t-sql/spatial-geometry/astextzm-geometry-data-type.md)  
  
  

