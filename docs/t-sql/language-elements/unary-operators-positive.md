---
title: + (унарный плюс) (Transact-SQL) | Документы Майкрософт
ms.custom: ''
ms.date: 03/13/2017
ms.prod: sql
ms.prod_service: database-engine, sql-database, sql-data-warehouse
ms.reviewer: ''
ms.technology: t-sql
ms.topic: language-reference
f1_keywords:
- + (positive)
- +
- positive
dev_langs:
- TSQL
helpviewer_keywords:
- + (positive operator)
- positive operator (+)
- positive values [SQL Server]
ms.assetid: 0f31c5cc-3078-4f6a-9870-7eb1a98053fb
author: rothja
ms.author: jroth
monikerRange: '>=aps-pdw-2016||=azuresqldb-current||=azure-sqldw-latest||>=sql-server-2016||=sqlallproducts-allversions||>=sql-server-linux-2017||=azuresqldb-mi-current'
ms.openlocfilehash: bf364168338cb5aaeb60f585f1a3fc8ec016c81d
ms.sourcegitcommit: df1f0f2dfb9452f16471e740273cd1478ff3100c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/29/2020
ms.locfileid: "87396852"
---
# <a name="unary-operators---positive"></a>Унарные операторы — положительное значение
[!INCLUDE [sql-asdb-asdbmi-asa-pdw](../../includes/applies-to-version/sql-asdb-asdbmi-asa.md)]

Возвращает значение числового выражения (унарный оператор). Унарные операторы выполняют операцию только на одном выражении любого типа данных из категории числовых типов данных.   
  
|Оператор|Значение|  
|--------------|-------------|  
|[+ (положительное значение)](../../t-sql/language-elements/unary-operators-positive.md)|Числовое значение положительно.|  
|[- (отрицательное значение)](../../t-sql/language-elements/unary-operators-negative.md)|Числовое значение отрицательно.|  
|[~ (побитовое НЕ)](../../t-sql/language-elements/bitwise-not-transact-sql.md)|Возвращает поразрядное дополнение числа.|  
  
 Операторы + (знак «плюс») и - (знак «минус») можно использовать в любом выражении любого типа данных из категории числовых типов данных. Оператор ~ (побитовое НЕ) можно использовать только в выражениях любого типа данных из категории целочисленных типов данных.  
  
 ![Значок ссылки на раздел](../../database-engine/configure-windows/media/topic-link.gif "Значок ссылки на раздел") [Синтаксические обозначения в Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Синтаксис  
  
```syntaxsql
  
+ numeric_expression  
```  
  
[!INCLUDE[sql-server-tsql-previous-offline-documentation](../../includes/sql-server-tsql-previous-offline-documentation.md)]

## <a name="arguments"></a>Аргументы
 *numeric_expression*  
 Любое допустимое выражение [expression](../../t-sql/language-elements/expressions-transact-sql.md) любого из типов данных категории числовых типов данных, кроме типов данных **datetime** и **smalldatetime**.  
  
## <a name="result-types"></a>Типы результата  
 Возвращает тип данных *numeric_expression*.  
  
## <a name="remarks"></a>Remarks  
 Хотя оператор унарного сложения может стоять перед любым числовым выражением, он не выполняет никаких действий со значением, полученным в результате вычисления выражения. В частности, оно не вернет положительное значение, если значение выражения отрицательно. Для получения положительного значения из отрицательного значения выражения предназначена функция [ABS](../../t-sql/functions/abs-transact-sql.md).  
  
## <a name="examples"></a>Примеры  
  
### <a name="a-setting-a-variable-to-a-positive-value"></a>A. Присваивание переменной положительного значения  
 В следующем примере производится присваивание переменной положительного значения.  
  
```  
DECLARE @MyNumber decimal(10,2);  
SET @MyNumber = +123.45;  
SELECT @MyNumber;  
GO  
```  
  
 Результирующий набор:  
  
```  
-----------   
123.45            
  
(1 row(s) affected)  
```  
  
### <a name="b-using-the-unary-plus-operator-with-a-negative-value"></a>Б. Использование оператора «унарный плюс» с отрицательными значениями  
 Следующий пример показывает, как унарное сложение используется с отрицательными значениями и как с ними же используется функция ABS(). Функция ABS возвращает положительное значение выражения, а унарное сложение никак не влияет на него.  
  
```  
USE tempdb;  
GO  
DECLARE @Num1 int;  
SET @Num1 = -5;  
SELECT +@Num1, ABS(@Num1);  
GO  
```  
  
 Результирующий набор:  
  
```  
----------- -----------  
-5          5  
  
(1 row(s) affected)  
```  
  
## <a name="see-also"></a>См. также:  
 [Типы данных (Transact-SQL)](../../t-sql/data-types/data-types-transact-sql.md)   
 [Выражения (Transact-SQL)](../../t-sql/language-elements/expressions-transact-sql.md)   
 [Операторы (Transact-SQL)](../../t-sql/language-elements/operators-transact-sql.md)   
 [ABS (Transact-SQL)](../../t-sql/functions/abs-transact-sql.md)  
  
  
