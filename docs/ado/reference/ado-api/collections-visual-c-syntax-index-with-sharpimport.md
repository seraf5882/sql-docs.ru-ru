---
description: 'Коллекции (Visual C++ индекс синтаксиса с #import)'
title: 'Коллекции (Visual C++ индекс синтаксиса с #import) | Документация Майкрософт'
ms.prod: sql
ms.prod_service: connectivity
ms.technology: connectivity
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: conceptual
apitype: COM
dev_langs:
- C++
helpviewer_keywords:
- 'syntax indexes [ADO], ADO for Visual C++ syntax with #import'
- 'collections [ADO], ADO for Visual C++ syntax with #import'
- 'ADO for Visual C++ syntax with #import [ADO]'
- '#import [ADO]'
ms.assetid: 36fbca8e-1884-44b5-806b-d15e30f42fe6
author: rothja
ms.author: jroth
ms.openlocfilehash: 58f7761cc67cd1320594988ba50bfcc79bcfc0d9
ms.sourcegitcommit: e700497f962e4c2274df16d9e651059b42ff1a10
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/17/2020
ms.locfileid: "88450916"
---
# <a name="collections-visual-c-syntax-index-with-import"></a>Коллекции (Visual C++ индекс синтаксиса с #import)
Полезно помнить, что коллекции наследуют определенные общие методы и свойства.  
  
 Все коллекции наследуют свойство **Count** и метод **Refresh** , а все коллекции добавляют свойство **Item** . Коллекция **Errors** добавляет метод **clear** . Коллекция **Parameters** наследует методы **append** и **Delete** , в то время как коллекция **Fields** добавляет методы **добавления**, **удаления**и **обновления** .  
  
## <a name="properties-collection"></a>Коллекция Properties  
  
### <a name="methods"></a>Методы  
  
```  
HRESULT Refresh( );  
```  
  
### <a name="properties"></a>Свойства  
  
```  
long GetCount( ); __declspec(property(get=GetCount)) long Count;  
PropertyPtr GetItem( const _variant_t & Index ); __declspec(property(get=GetItem)) PropertyPtr Item[];  
```  
  
## <a name="errors-collection"></a>Коллекция ошибок  
  
### <a name="methods"></a>Методы  
  
```  
HRESULT Clear( );  
HRESULT Refresh( );  
```  
  
### <a name="properties"></a>Свойства  
  
```  
long GetCount( ); __declspec(property(get=GetCount)) long Count;  
PropertyPtr GetItem( const _variant_t & Index ); __declspec(property(get=GetItem)) PropertyPtr Item[];  
```  
  
## <a name="parameters-collection"></a>Коллекция Parameters  
  
### <a name="methods"></a>Методы  
  
```  
HRESULT Append( IDispatch * Object );  
HRESULT Delete( const _variant_t & Index );  
HRESULT Refresh( );  
```  
  
### <a name="properties"></a>Свойства  
  
```  
long GetCount( ); __declspec(property(get=GetCount)) long Count;  
PropertyPtr GetItem( const _variant_t & Index ); __declspec(property(get=GetItem)) PropertyPtr Item[];  
```  
  
## <a name="fields-collection"></a>Коллекция Fields  
  
### <a name="methods"></a>Методы  
  
```  
HRESULT Append( _bstr_t Name, enum DataTypeEnum Type, long DefinedSize, enum FieldAttributeEnum Attrib, const _variant_t & FieldValue = vtMissing );  
HRESULT Delete( const _variant_t & Index );  
HRESULT Refresh( );  
HRESULT Update( );  
```  
  
### <a name="properties"></a>Свойства  
  
```  
long GetCount( ); __declspec(property(get=GetCount)) long Count;  
PropertyPtr GetItem( const _variant_t & Index ); __declspec(property(get=GetItem)) PropertyPtr Item[];  
```  
  
## <a name="see-also"></a>См. также:  
 [Коллекция Errors (ADO)](../../../ado/reference/ado-api/errors-collection-ado.md)   
 [Коллекция Fields (ADO)](../../../ado/reference/ado-api/fields-collection-ado.md)   
 [Коллекция Parameters (ADO)](../../../ado/reference/ado-api/parameters-collection-ado.md)   
 [Коллекция Properties (ADO)](../../../ado/reference/ado-api/properties-collection-ado.md)
