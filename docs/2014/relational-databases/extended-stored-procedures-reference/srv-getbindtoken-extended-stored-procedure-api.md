---
title: srv_getbindtoken (интерфейс API расширенных хранимых процедур) | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- database-engine
- docset-sql-devref
ms.tgt_pltfrm: ''
ms.topic: reference
api_name:
- srv_getbindtoken
api_location:
- opends60.dll
topic_type:
- apiref
dev_langs:
- C++
helpviewer_keywords:
- srv_getbindtoken
ms.assetid: c947d011-08ac-4fb8-b925-3da6e0999277
caps.latest.revision: 36
author: rothja
ms.author: jroth
manager: craigg
ms.openlocfilehash: 4404a17649f8d9b59317ece6b77e7ab0c789a587
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/02/2018
ms.locfileid: "37305544"
---
# <a name="srvgetbindtoken-extended-stored-procedure-api"></a>srv_getbindtoken (API-интерфейс расширенных хранимых процедур)
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] Используйте вместо этого интеграцию со средой CLR.  
  
 Получает токен привязки транзакции в текущем сеансе клиента, который вызывает расширенную хранимую процедуру.  
  
 После этого расширенная хранимая процедура может использовать **sp_bindsession** для привязки любого созданного ею на том же сервере сеанса к существующей транзакции, чтобы новый сеанс мог совместно использовать одно пространство блокировки транзакций с клиентским сеансом, вызвавшим расширенную хранимую процедуру.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
int srv_getbindtoken (  
SRV_PROC*  
srvproc  
,  
char*  
bindtoken  
);  
  
```  
  
## <a name="arguments"></a>Аргументы  
 *srvproc*  
 Указатель на структуру SRV_PROC, который представляет собой дескриптор соединения с клиентом. В этой структуре содержатся все сведения, которые библиотека API-интерфейса расширенных хранимых процедур использует для управления обменом данными между приложением и клиентом.  
  
 *bindtoken*  
 Указатель на буфер, в который будет скопирован токен привязки. Токен привязки представлен как строка, оканчивающаяся нулевым байтом. Указываемый буфер должен иметь длину не менее 255 байт.  
  
## <a name="returns"></a>Возвращает  
 SUCCEED или FAIL.  
  
## <a name="remarks"></a>Примечания  
  
### <a name="to-bind-an-extended-stored-procedure-session-to-the-client-session-that-called-it-so-they-share-the-same-transaction-lock-space"></a>Привязка сеанса расширенной хранимой процедуры к сеансу вызывающего ее клиента для совместного использования пространства блокировки транзакций  
  
1.  Расширенная хранимая процедура вызывает функцию **svr_getbindtoken**, чтобы получить токен привязки для текущей транзакции в сеансе. Токен возвращается в параметре *bindtoken*.  
  
2.  Расширенная хранимая процедура открывает новый сеанс на том же сервере. В этом сеансе расширенная хранимая процедура использует токен привязки в хранимой процедуре **sp_bindsession** для привязки нового сеанса к той же транзакции. Расширенная хранимая процедура может создать несколько сеансов и привязать их к одной транзакции.  
  
3.  Связанный сеанс освобождается при возврате из расширенной хранимой процедуры или когда **sp_bindsession** вызывается с пустой строкой.  
  
    > [!NOTE]  
    >  Только один связанный сеанс может получить доступ к общему соединению в один момент времени. Если один сеанс в настоящий момент выполняет инструкцию на сервере или ожидает результаты с сервера, то никакой другой сеанс, совместно использующий это связанное соединение, не может получить доступ к серверу, пока текущий сеанс не завершит выполнение инструкции. Если сеанс пытается получить доступ к соединению, пока сервер занят, то для этого сеанса возвращается ошибка, указывающая, что соединение используется, и конфликтующему сеансу следует повторить попытку позже.  
  
> [!IMPORTANT]  
>  Необходимо тщательно просмотреть исходный код расширенных хранимых процедур и проверить скомпилированные библиотеки DLL перед их установкой на рабочий сервер. Сведения о проверке безопасности см. на следующем [веб-сайте Майкрософт](http://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409http://msdn.microsoft.com/security/).  
  
## <a name="see-also"></a>См. также  
 [sp_bindsession (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-bindsession-transact-sql)   
 [sp_getbindtoken (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-getbindtoken-transact-sql)  
  
  