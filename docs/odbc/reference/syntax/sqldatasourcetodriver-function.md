---
description: Функция SQLDataSourceToDriver
title: Функция Склдатасаурцетодривер | Документация Майкрософт
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
apiname:
- SQLDataSourceToDriver
apilocation:
- sqlsrv32.dll
apitype: dllExport
f1_keywords:
- SQLDataSourceToDriver
helpviewer_keywords:
- SQLDataSourceToDriver function [ODBC]
ms.assetid: 0d87fcac-30a0-4303-ad8f-a5b53f4b428d
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: 80a9f74f7711e252b1ee947a5ece7088c1a9aa04
ms.sourcegitcommit: e700497f962e4c2274df16d9e651059b42ff1a10
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/17/2020
ms.locfileid: "88461176"
---
# <a name="sqldatasourcetodriver-function"></a>Функция SQLDataSourceToDriver
**Склдатасаурцетодривер** суппортстранслатионс для драйверов ODBC. Эта функция не вызывается приложениями, поддерживающими ODBC; приложения запрашивают преобразование через **SQLSetConnectAttr**. Драйвер, связанный с *коннектионхандле* , указанным в **SQLSetConnectAttr** , вызывает указанную библиотеку DLL для выполнения переводов всех данных, передаваемых из источника данных в драйвер. В файле инициализации ODBC можно указать библиотеку DLL для перевода по умолчанию.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
  
BOOL SQLDataSourceToDriver(  
     UDWORD     fOption,  
     SWORD      fSqlType,  
     PTR        rgbValueIn,  
     SDWORD     cbValueIn,  
     PTR        rgbValueOut,  
     SDWORD     cbValueOutMax,  
     SDWORD *   pcbValueOut,  
     UCHAR *    szErrorMsg,  
     SWORD      cbErrorMsgMax,  
     SWORD *    pcbErrorMsg);  
```  
  
## <a name="arguments"></a>Аргументы  
 *Параметром fOption*  
 Входной Значение параметра.  
  
 *фсклтипе*  
 Входной Тип данных SQL. Этот аргумент указывает драйверу, как преобразовать *ргбвалуеин* в форму, приемлемую для приложения. Список допустимых типов данных SQL см. в разделе [типы данных SQL](../../../odbc/reference/appendixes/sql-data-types.md) в приложении г: типы данных.  
  
 *ргбвалуеин*  
 Входной Значение для преобразования.  
  
 *кбвалуеин*  
 Входной Длина *ргбвалуеин*.  
  
 *ргбвалуеаут*  
 Проверки Результат перевода.  
  
> [!NOTE]  
>  DLL-файл преобразования не имеет значения NULL — завершает это значение.  
  
 *кбвалуеаутмакс*  
 Входной Длина *ргбвалуеаут*.  
  
 *пкбвалуеаут*  
 Проверки Общее число байтов (за исключением байта завершения null), доступных для возврата в *ргбвалуеаут*.  
  
 Для символьных или двоичных данных, если это значение больше или равно *кбвалуеаутмакс*, данные в *Ргбвалуеаут* усекаются до *кбвалуеаутмакс* байт.  
  
 Для всех других типов данных значение *кбвалуеаутмакс* игнорируется, и DLL-библиотека преобразования предполагает, что размер *ргбвалуеаут* равен размеру по умолчанию типа данных C для типа данных SQL, указанного в параметре *фсклтипе*.  
  
 Аргумент *пкбвалуеаут* может быть пустым указателем.  
  
 *сзеррормсг*  
 Проверки Указатель на хранилище для сообщения об ошибке. Это пустая строка, если преобразование выполнить не удалось.  
  
 *кберрормсгмакс*  
 Входной Длина *сзеррормсг*.  
  
 *пкберрормсг*  
 Проверки Указатель на общее число байтов (за исключением байта завершения null), доступного для возврата в *сзеррормсг*. Если это значение больше или равно *кберрормсг*, то данные в *Сзеррормсг* усекаются до *кберрормсгмакс* минус символ завершения null. Аргумент *пкберрормсг* может быть пустым указателем.  
  
## <a name="returns"></a>Возвращаемое значение  
 Значение TRUE, если перевод выполнен успешно, значение FALSE, если преобразование выполнить не удалось.  
  
## <a name="comments"></a>Комментарии  
 Драйвер вызывает **склдатасаурцетодривер** , чтобы перевести аллдата (данные результирующего набора, имена таблиц, количество строк, сообщения об ошибках и т. д.), передавая из источника данных драйверу. DLL-библиотека преобразования может не преобразовывать некоторые данные, в зависимости от типа данных и назначения библиотеки DLL преобразования. Например, Библиотека DLL, преобразующая символьные данные из одной кодовой страницы в другую, игнорирует все числовые и двоичные данные.  
  
 Для параметра *параметром fOption* задается значение *впарам* , заданное с помощью вызова **SQLSetConnectAttr** с атрибутом SQL_ATTR_TRANSLATE_OPTION. Это 32-разрядное значение, которое имеет определенное значение для данной библиотеки DLL преобразования. Например, можно указать преобразование определенного набора символов.  
  
 Если для *ргбвалуеин* и *ргбвалуеаут*указан один и тот же буфер, то перевод данных в буфер будет выполняться на месте.  
  
 Хотя *кбвалуеин*, *кбвалуеаутмакс*и *пкбвалуеаут* относятся к типу сдворд, **склдатасаурцетодривер** не обязательно поддерживает огромные указатели.  
  
 Если **склдатасаурцетодривер** возвращает значение false, то усечение данных может произойти во время преобразования. Если *пкбвалуеаут* (число байт, доступных для возврата в буфере вывода) больше *кбвалуеаутмакс* (длина выходного буфера), то произошло усечение. Драйвер должен определить, является ли усечение приемлемым. Если усечение не произошло, **склдатасаурцетодривер** вернул значение false из-за другой ошибки. В любом случае в *сзеррормсг*возвращается конкретное сообщение об ошибке.  
  
 Дополнительные сведения о переводе данных см. в разделе [DLL-файлы преобразования](../../../odbc/reference/develop-app/translation-dlls.md).  
  
## <a name="related-functions"></a>Связанные функции  
  
|Сведения о|См.|  
|---------------------------|---------|  
|Преобразование данных, отправляемых в источник данных|[склдривертодатасаурце](../../../odbc/reference/syntax/sqldrivertodatasource-function.md)|  
|Возврат значения атрибута соединения|[SQLGetConnectAttr](../../../odbc/reference/syntax/sqlgetconnectattr-function.md)|  
|Установка атрибута соединения|[SQLSetConnectAttr](../../../odbc/reference/syntax/sqlsetconnectattr-function.md)|
