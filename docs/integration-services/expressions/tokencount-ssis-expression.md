---
description: TOKENCOUNT (выражение служб SSIS)
title: TOKENCOUNT (выражение служб SSIS) | Документы Майкрософт
ms.custom: ''
ms.date: 03/01/2017
ms.prod: sql
ms.prod_service: integration-services
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 1c0efed1-c2b3-4f20-a3a1-ad91283b7c0a
author: chugugrace
ms.author: chugu
ms.openlocfilehash: aa242e7ab52115239554af8a74c71f9eea47dd49
ms.sourcegitcommit: e700497f962e4c2274df16d9e651059b42ff1a10
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/17/2020
ms.locfileid: "88391360"
---
# <a name="tokencount-ssis-expression"></a>TOKENCOUNT (выражение служб SSIS)

[!INCLUDE[sqlserver-ssis](../../includes/applies-to-version/sqlserver-ssis.md)]


  Возвращает несколько токенов в строке, в которой они разделены указанными символами.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
TOKENCOUNT(character_expression, delimiter_string)  
```  
  
## <a name="arguments"></a>Аргументы  
 *character_expression*  
 Строка, содержащая токены, разделенные соответствующими символами.  
  
 *delimiter_string*  
 Строка, содержащая символы разделения. Например, строка "; ," содержит три символа разделения: точку с запятой, пробел и запятую.  
  
## <a name="result-types"></a>Типы результата  
 DT_I4  
  
## <a name="remarks"></a>Комментарии  
 Следующие примечания относятся к функции TOKEN.  
  
-   Строка разделения может содержать один или несколько символов разделения.  
  
-   Первые разделители пропускаются.  
  
-   TOKENCOUNT работает только с типом данных DT_WSTR. Аргумент *character_expression* , являющийся строковым литералом или столбцом данных с типом данных DT_STR, неявно приведен к типу данных DT_WSTR до выполнения функции TOKEN. Прочие типы данных должны быть явно приведены к типу данных DT_WSTR.  
  
-   Функция TOKENCOUNT возвращает результат 0 (нуль), если строка character_expression имеет значение NULL.  
  
-   Переменные и столбцы могут использоваться в качестве аргументов для этого выражения.  
  
## <a name="expression-examples"></a>Примеры выражений  
 В следующем примере функция TOKENCOUNT возвращает значение 3, потому что строка содержит три токена: "01", "12", "2011".  
  
```  
TOKENCOUNT("01/12/2011", "/")  
```  
  
 В следующем примере функция TOKENCOUNT возвращает 4, потому что в строке четыре токена ("a", "little", "white", "dog").  
  
```  
TOKENCOUNT("a little white dog"," ")  
```  
  
 В следующем примере функция TOKENCOUNT возвращает значение 1. Функция выполняет синтаксический анализ входной строки на предмет разделителей, и, поскольку их в строке нет, добавляет всю строку как первый токен.  
  
```  
TOKENCOUNT("a little white dog","|")  
```  
  
 В следующем примере функция TOKENCOUNT возвращает значение 4. Строка разделителя в этом примере содержит 5 разделителей. Входная строка содержит 4 токена: "a", "little", "white", "dog".  
  
```  
TOKENCOUNT("a:little|white dog","| ,.:")  
```  
  
 В следующем примере функция TOKENCOUNT возвращает значение 4. Функция пропускает все пробелы в начале строки.  
  
```  
TOKENCOUNT("        a little white dog", " ")  
```  
  
## <a name="see-also"></a>См. также:  
 [Функции (выражение служб SSIS)](../../integration-services/expressions/functions-ssis-expression.md)  
  
  
