---
description: Коллекция Tables (ADOX)
title: Коллекция Tables (ADOX) | Документация Майкрософт
ms.prod: sql
ms.prod_service: connectivity
ms.technology: connectivity
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: conceptual
apitype: COM
f1_keywords:
- Catalog::Tables
- Tables
helpviewer_keywords:
- Tables collection [ADOX]
ms.assetid: 38d750e7-f3fb-426e-b4b4-55eea4f1a654
author: rothja
ms.author: jroth
ms.openlocfilehash: 9d959578d647e74248fdb58b8c27269c0454c304
ms.sourcegitcommit: e700497f962e4c2274df16d9e651059b42ff1a10
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/17/2020
ms.locfileid: "88439476"
---
# <a name="tables-collection-adox"></a>Коллекция Tables (ADOX)
Содержит все [табличные](../../../ado/reference/adox-api/table-object-adox.md) объекты каталога.  
  
## <a name="remarks"></a>Remarks  
 Метод [append](../../../ado/reference/adox-api/append-method-adox-tables.md) для коллекции **ТАБЛИЦ** уникален для ADOX. Вы можете:  
  
-   Добавьте новую таблицу в коллекцию с помощью метода **append** .  
  
 Остальные свойства и методы являются стандартными для коллекций ADO. Вы можете:  
  
-   Доступ к таблице в коллекции со свойством [Item](../../../ado/reference/ado-api/item-property-ado.md) .  
  
-   Возвращает количество таблиц, содержащихся в коллекции, с помощью свойства [Count](../../../ado/reference/ado-api/count-property-ado.md) .  
  
-   Удалите таблицу из коллекции с помощью метода [Delete](../../../ado/reference/adox-api/delete-method-adox-collections.md) .  
  
-   Обновите объекты в коллекции, чтобы отразить текущую схему базы данных методом [Refresh](../../../ado/reference/ado-api/refresh-method-ado.md) .  
  
 Некоторые поставщики могут возвращать другие объекты схемы, например представления, в коллекцию **таблиц** . Таким образом, некоторые коллекции ADOX могут содержать несколько ссылок на один и тот же объект. Если объект удаляется из одной коллекции, это изменение не будет отображаться в другой коллекции, ссылающейся на удаленный объект, до тех пор, пока для коллекции не вызывается метод **Refresh** . Например, при использовании поставщика OLE DB для Microsoft Jet представления возвращаются с помощью коллекции **таблиц** . При удалении представления необходимо обновить коллекцию **Tables** , прежде чем коллекция будет отражать изменение.  
  
 Этот раздел содержит следующий раздел.  
  
-   [Свойства, методы и события коллекции Tables](../../../ado/reference/adox-api/tables-collection-properties-methods-and-events.md)  
  
## <a name="see-also"></a>См. также:  
 [Пример свойства ActiveConnection каталога (Visual Basic)](../../../ado/reference/adox-api/catalog-activeconnection-property-example-vb.md)   
 [Методы добавления столбцов и таблиц, пример свойства Name (Visual Basic)](../../../ado/reference/adox-api/columns-and-tables-append-methods-name-property-example-vb.md)   
 [Пример метода Close соединения, свойство типа таблицы (Visual Basic)](../../../ado/reference/adox-api/connection-close-method-table-type-property-example-vb.md)   
 [Пример свойств для добавления ключей, типа ключа, RelatedColumn, RelatedTable и UpdateRule (Visual Basic)](../../../ado/reference/adox-api/keys-append-method-key-type-relatedcolumn-relatedtable-example-vb.md)   
 [Объект каталога (ADOX)](../../../ado/reference/adox-api/catalog-object-adox.md)   
 [Объект Table (ADOX)](../../../ado/reference/adox-api/table-object-adox.md)
