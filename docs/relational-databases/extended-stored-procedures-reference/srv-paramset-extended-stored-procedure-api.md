---
title: srv_paramset (интерфейс API расширенных хранимых процедур) | Документы Майкрософт
description: Узнайте, как srv_paramset в API расширенных хранимых процедур задает значение возвращаемого параметра вызова удаленной хранимой процедуры.
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: stored-procedures
ms.topic: reference
apiname:
- srv_paramset
apilocation:
- opends60.dll
apitype: DLLExport
dev_langs:
- C++
helpviewer_keywords:
- srv_paramset
ms.assetid: 2a509206-a1b8-4b20-b0a2-ef680cef7bd8
author: rothja
ms.author: jroth
ms.openlocfilehash: 645b87be7c1b5955975a370e9e1b49e6608272b3
ms.sourcegitcommit: 216f377451e53874718ae1645a2611cdb198808a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/28/2020
ms.locfileid: "87248390"
---
# <a name="srv_paramset-extended-stored-procedure-api"></a>srv_paramset (API-интерфейс расширенных хранимых процедур)
 [!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] Используйте вместо этого интеграцию со средой CLR.  
  
 Устанавливает значение возвратного параметра вызова удаленной хранимой процедуры. Эта функция заменена функцией **srv_paramsetoutput**.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
int srv_paramset (  
SRV_PROC *  
srvproc  
,  
int  
n  
,   
void *  
data  
,  
int  
len   
);  
```  
  
## <a name="arguments"></a>Аргументы  
 *srvproc*  
 Указатель на структуру SRV_PROC, представляющую собой дескриптор соединения с клиентом (в данном случае — дескриптор, который получил вызов удаленной хранимой процедуры). Эта структура содержит сведения, которые используются библиотекой API-интерфейса расширенных хранимых процедур для управления связью и передачи данных между приложением и клиентом.  
  
 *n*  
 Указывает номер параметра, который должен быть задан. Первый параметр имеет значение 1.  
  
 *data*  
 Указатель на значение данных, которое должно быть отправлено назад клиенту, как возвратный параметр удаленной хранимой процедуры.  
  
 *len*  
 Указывает фактическую длину данных, которые должны быть возвращены. Если тип данных параметра имеет постоянную длину и не допускает значений NULL (например, *srvbit* или *srvint1*), параметр *len* не учитывается.  
  
## <a name="returns"></a>Результаты  
 SUCCEED, если значение параметра было успешно установлено; в противном случае — FAIL. Значение FAIL возвращается, если удаленной хранимой процедуры сейчас не существует, если у нее нет параметра с номером *n*, если параметр не является возвращаемым или если аргумент *len* недопустимый.  
  
 Если *len* имеет значение 0, то возвращается NULL. Единственным способом возвратить значение NULL клиенту является задание параметру *len* значения 0.  
  
 Эта функция возвращает следующие значения, если параметр относится к одному из [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] типов данных.  
  
|Новые типы данных|Длина возвращаемых данных|  
|--------------------|------------------------|  
|**BITN**|**NULL:** _len_ = 0, data = IG, RET = 0<br /><br /> **ZERO:** недоступно<br /><br /> **>= 255:** Н/Д<br /><br /> **<255:** Н/Д|  
|**BIGVARCHAR**|**NULL:** _len_ = 0, data = IG, RET = 1<br /><br /> **ZERO:** _len_ = IG, data = IG, RET = 0<br /><br /> **>=255:** _len_ = max8k, data = valid, RET = 0<br /><br /> **<255:** _len_ = <8k, data = valid, RET = 1|  
|**BIGCHAR**|**NULL:** _len_ = 0, data = IG, RET = 1<br /><br /> **ZERO:** _len_ = IG, data = IG, RET = 0<br /><br /> **>=255:** _len_ = max8k, data = valid, RET = 0<br /><br /> **<255:** _len_ = <8k, data = valid, RET = 1|  
|**BIGBINARY**|**NULL:** _len_ = 0, data = IG, RET = 1<br /><br /> **ZERO:** _len_ = IG, data = IG, RET = 0<br /><br /> **>=255:** _len_ = max8k, data = valid, RET = 0<br /><br /> **<255:** _len_ = <8k, data = valid, RET = 1|  
|**BIGVARBINARY**|**NULL:** _len_ = 0, data = IG, RET = 1<br /><br /> **ZERO:** _len_ = IG, data = IG, RET = 0<br /><br /> **>=255:** _len_ = max8k, data = valid, RET = 0<br /><br /> **<255:** _len_ = <8k, data = valid, RET = 1|  
|NCHAR|**NULL:** _len_ = 0, data = IG, RET = 1<br /><br /> **ZERO:** _len_ = IG, data = IG, RET = 0<br /><br /> **>=255:** _len_ = max8k, data = valid, RET = 0<br /><br /> **<255:** _len_ = <8k, data = valid, RET = 1|  
|NVARCHAR|**NULL:** _len_ = 0, data = IG, RET = 1<br /><br /> **ZERO:** _len_ = IG, data = IG, RET = 0<br /><br /> **>=255:** _len_ = max8k, data = valid, RET = 0<br /><br /> **<255:** _len_ = <8k, data = valid, RET = 1|  
|**ТИПЫ**|**NULL:** _len_ = IG, data = IG, RET = 0<br /><br /> **ZERO:** _len_ = IG, data = IG, RET = 0<br /><br /> **>=255:** _len_ = IG, data = IG, RET = 0<br /><br /> ** \< 255:** _Len_ = и, Data = и, ret = 0|  
|RET = значение, возвращаемое srv_paramset||  
|IG = значение будет пропущено||  
|valid = любой допустимый указатель на данные||  
  
## <a name="remarks"></a>Remarks  
 Параметры содержат данные, передаваемые между клиентами и приложением с удаленной хранимой процедурой. Клиент может указать некоторые параметры в качестве возвращаемых. Эти возвращаемые параметры могут содержать значения, которые серверное приложение служб Open Data Services данных передает клиенту. Использование возвращаемых параметров аналогично передаче параметров по ссылке.  
  
 Возвращаемое значение невозможно задать параметру, который не был запущен как возвращаемый параметр. Определить, как был вызван параметр, можно с помощью функции **srv_paramstatus**.  
  
 Эта функция задает параметру возвращаемое значение, но она не отправляет это значение клиенту. Все возвращаемые параметры, независимо от того, были ли их возвращаемые значения заданы с помощью функции **srv_paramset** или нет, автоматически отправляются клиенту при вызове функции **srv_senddone** с установленным флагом состояния SRV_DONE_FINAL.  
  
 Когда удаленная хранимая процедура вызывается с параметрами, эти параметры могут быть переданы либо по имени, либо по позиции — без указания имени. Если при вызове удаленной хранимой процедуры часть параметров передается по имени, а часть — по позиции, возникает ошибка. Обработчик SRV_RPC по-прежнему вызывается, однако он отображается так, как если бы не имел параметров, а функция **srv_rpcparams** возвращает 0.  
  
> [!IMPORTANT]  
>  Необходимо тщательно просмотреть исходный код расширенных хранимых процедур и проверить скомпилированные библиотеки DLL перед их установкой на рабочий сервер. Сведения о проверке безопасности см. на следующем [веб-сайте Майкрософт](https://www.microsoft.com/msrc?rtc=1).  
  
## <a name="see-also"></a>См. также:  
 [srv_paramsetoutput (интерфейс API расширенных хранимых процедур)](../../relational-databases/extended-stored-procedures-reference/srv-paramsetoutput-extended-stored-procedure-api.md)  
  
  
