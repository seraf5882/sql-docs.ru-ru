---
title: Установка пакетов управления SCOM
description: Выполните следующие действия, чтобы скачать и установить пакеты управления System Center Operations Manager (SCOM) для SQL Server PDW. Пакеты управления необходимы для отслеживания SQL Server PDW из SCOM.
author: mzaman1
ms.prod: sql
ms.technology: data-warehouse
ms.topic: conceptual
ms.date: 04/17/2018
ms.author: murshedz
ms.reviewer: martinle
ms.custom: seo-dt-2019
ms.openlocfilehash: f3652b767f4628b61f5dd363999838418ff933aa
ms.sourcegitcommit: e042272a38fb646df05152c676e5cbeae3f9cd13
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/27/2020
ms.locfileid: "74401073"
---
# <a name="install-sql-server-operations-manager-scom-management-packs-for-analytics-platform-system"></a>Установка пакетов управления SQL Server Operations Manager (SCOM) для Analytics Platform System
Выполните следующие действия, чтобы скачать и установить пакеты управления System Center Operations Manager (SCOM) для SQL Server PDW. Пакеты управления необходимы для отслеживания SQL Server PDW из SCOM.  
  
## <a name="before-you-begin"></a><a name="BeforeBegin"></a>Перед началом  
**Предварительные условия**  
  
Необходимо установить и запустить System Center Operations Manager. Для SQL Server PDW 2012 требуется System Center Operations Manager 2007 R2, System Center Operations Manager 2012 или System Center Operations Manager 2012 с пакетом обновления 1 (SP1).  
  
## <a name="step-1-download-the-management-packs"></a><a name="Step1"></a>Шаг 1. Скачивание пакетов управления  
В рабочей нагрузке APS PDW Скачайте [пакет управления System Center для Microsoft Analytics Platform System](https://go.microsoft.com/fwlink/?LinkId=396857).  
  
Для управления устройством Скачайте [базовый пакет управления для устройства SQL Server](https://docs.microsoft.com/previous-versions/system-center/packs/gg602398(v=technet.10)).  
  
Для более старых версий PDW без ТД Скачайте[Пакет мониторинга System Center для Microsoft SQL Server 2012 параллельного хранилища данных](https://go.microsoft.com/fwlink/p/?LinkId=282661).  
  
<!-- MISSING LINKS - For the HDInsight workload, download the [System Center Management Pack for HDInsight](https://go.microsoft.com/fwlink/?LinkId=390208).  -->
  
## <a name="step-2-install-the-management-packs"></a><a name="Step2"></a>Шаг 2. Установка пакетов управления  
  
### <a name="install-the-sql-server-appliance-base-management-pack"></a>Установка базового пакета управления для устройств SQL Server  
  
1.  Чтобы запустить установку, дважды щелкните загруженный базовый пакет управления для устройства SQL Server.  
  
2.  Примите условия лицензионного соглашения и нажмите кнопку **Далее**.  
  
    ![Принять лицензионное соглашение](./media/install-the-scom-management-packs/SCOM_licnse_agrmt.png "SCOM_licnse_agrmt")  
  
3.  Выберите собственную папку установки или используйте папку установки пакета управления по умолчанию.  
  
    ![Выбрать папку установки](./media/install-the-scom-management-packs/SCOM_licnse_agrmt2.png "SCOM_licnse_agrmt2")  
  
4.  Щелкните **Install**(Установить).  
  
    ![Подтвердите установку](./media/install-the-scom-management-packs/SCOM_licnse_agrmt3.png "SCOM_licnse_agrmt3")  
  
5.  Нажмите кнопку **Закрыть**.  
  
    ![Нажмите кнопку Закрыть.](./media/install-the-scom-management-packs/SCOM_licnse_agrmt4.png "SCOM_licnse_agrmt4")  
  
### <a name="install-the-monitoring-pack-for-sql-server-pdw-appliance"></a>Установка пакета мониторинга для устройства SQL Server PDW  
  
1.  Чтобы запустить установку, дважды щелкните скачанный пакет управления SQL Server PDW устройством.  
  
2.  Примите условия лицензионного соглашения и нажмите кнопку **Далее**.  
  
    ![Примите лицензионное соглашение](./media/install-the-scom-management-packs/SCOM_licnse_agmtB.png "SCOM_licnse_agmtB")  
  
3.  Выберите каталог, в котором будут храниться извлеченные файлы. Папка установки пакета управления по умолчанию отображается по умолчанию. Выберите значение по умолчанию или выберите собственную папку установки.  
  
    ![Выбор папки установки](./media/install-the-scom-management-packs/SCOM_licnse_agmtB1.png "SCOM_licnse_agmtB1")  
  
4.  Щелкните **Install**(Установить).  
  
    ![Подтвердите установку](./media/install-the-scom-management-packs/SCOM_licnse_agmtB2.png "SCOM_licnse_agmtB2")  
  
5.  Нажмите кнопку **Закрыть**.  
  
    ![Установка завершена](./media/install-the-scom-management-packs/SCOM_licnse_agmtB3.png "SCOM_licnse_agmtB3")  
  
## <a name="next-step"></a>Следующий шаг  
Теперь, когда пакеты управления установлены, перейдите к следующему шагу: [импортируйте пакет управления SCOM для PDW &#40;Analytics Platform System&#41;](import-the-scom-management-pack-for-pdw.md).  
  
<!-- MISSING LINKS ## See Also  
[Common Metadata Query Examples &#40;SQL Server PDW&#41;](../sqlpdw/common-metadata-query-examples-sql-server-pdw.md)  -->  
  
