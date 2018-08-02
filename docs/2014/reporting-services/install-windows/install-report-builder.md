---
title: Установка изолированной версии построителя отчетов (построитель отчетов) | Документация Майкрософт
ms.custom: ''
ms.date: 12/29/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- reporting-services-native
ms.tgt_pltfrm: ''
ms.topic: conceptual
ms.assetid: 6b2291bb-1d20-4d08-81cb-a16dd8e01faf
caps.latest.revision: 10
author: maggiesMSFT
ms.author: maggies
manager: craigg
ms.openlocfilehash: 0fb9e6b43faf8b3ff7e0b91ccb500b94547436aa
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/02/2018
ms.locfileid: "37305084"
---
# <a name="install-the-stand-alone-version-of-report-builder-report-builder"></a>Установка изолированной версии построителя отчетов (построитель отчетов)
  Можно установить построитель отчетов из [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] пакет дополнительных компонентов на [центра загрузки Майкрософт](http://go.microsoft.com/fwlink/?LinkID=168472) или расположения как общая папка, к которому имеет файл ReportBuilder3_x86.msi — пакет установщика Windows для построителя отчетов было загружено.  
  
 Также можно установить построитель отчетов из командной строки, задав аргументы для настройки установки. В дополнение к стандартным внутренним параметрам MSI, можно использовать пользовательские параметры, предоставляемые построителем отчетов: RBINSTALLDIR и REPORTSERVERURL. RBINSTALLDIR указывает корневой каталог установки для построителя отчетов. REPORTSERVERURL указывает сервер отчетов по умолчанию, используемый построителем отчетов для сохранения отчетов на сервере.  
  
 Если необходимо произвести установку в полностью автоматическом режиме, без какого-либо взаимодействия с пользовательским интерфейсом, укажите параметр **/quiet** . Флаг параметра подавляет сообщения об ошибках установки. В связи с этим при использовании автоматической установки рекомендуется включить параметр **/l** , указывающий необходимость ведения журнала.  
  
> [!IMPORTANT]  
>  Для запуска операций из командной строки в Windows Vista и Windows 7 требуются повышенные разрешения безопасности; эти ОС будут запрашивать разрешения на выполнение командной строки. Эта установка выполняется не автоматически. Для проведения автоматической установки необходимо запустить командную строку от имени администратора.  
  
### <a name="to-install-report-builder-from-the-download-site"></a>Установка построителя отчетов с сайта загрузки  
  
1.  Перейдите к [построитель отчетов Microsoft SQL Server 2012](http://go.microsoft.com/fwlink/?LinkID=219138) и найдите раздел построителя отчетов, веб-страницы.  
  
2.  Нажмите кнопку **X86 пакета**.  
  
3.  В **Загрузка файла** диалоговом окне щелкните **запуска**.  
  
    > [!IMPORTANT]  
    >  Файлы следует загружать только из доверенных источников.  
  
4.  В диалоговом окне Internet Explorer щелкните **запуска**.  
  
    > [!IMPORTANT]  
    >  Файлы следует запускать только из доверенных источников.  
  
5.  Будет запущен мастер построителя отчетов Microsoft SQL Server.  
  
6.  На **Добро пожаловать в мастер установки** щелкните **Далее**.  
  
7.  На **лицензионное соглашение** странице, прочтите соглашение и выберите **я принимаю условия лицензионного соглашения** параметр. Нажмите кнопку **Далее**.  
  
8.  Приведите свое личное имя и имя компании. Нажмите кнопку **Далее**.  
  
9. На **Выбор компонентов** при необходимости щелкните **Обзор** или **место на диске**. Нажмите кнопку **Далее**.  
  
    -   Нажмите кнопку **Обзор** чтобы увидеть место по умолчанию для построителя отчетов и обновить его.  
  
        > [!NOTE]  
        >  Папка установки по умолчанию для построителя отчетов \<диск > Program Files\Microsoft SQL Server.  
  
    -   Нажмите кнопку **место на диске** чтобы узнать объем дискового пространства построитель отчетов использует.  
  
        > [!NOTE]  
        >  Если на томе недостаточно свободного места, то он будет выделен.  
  
10. На странице **Целевой сервер по умолчанию** можно по желанию привести URL-адрес целевого сервера отчетов, если он отличается от адреса по умолчанию. Нажмите кнопку **Далее**.  
  
    > [!NOTE]  
    >  Если планируется работать с построителем отчетов в соединении с сервером отчетов, то будет удобнее предоставить URL-адрес сервера на данном этапе. Тем не менее, вы можете также сделать это в **параметры** диалоговое окно, если вы работаете в построителе отчетов.  
  
11. Нажмите кнопку **установить** для завершения установки построителя отчетов.  
  
### <a name="to-install-report-builder-from-a-share"></a>Установка построителя отчетов из общей папки  
  
1.  Свяжитесь с администратором, чтобы узнать расположение файла ReportBuilder3_x86.msi.msi, который нужно запустить для установки построителя отчетов на локальном компьютере.  
  
2.  Перейдите к файлу ReportBuilder3_x86.msi.msi, который представляет собой пакет установщика Windows (MSI) для построителя отчетов, и щелкните его.  
  
     Будет запущен мастер построителя отчетов Microsoft SQL Server.  
  
3.  На **Добро пожаловать в мастер установки** щелкните **Далее**.  
  
4.  На **лицензионное соглашение** странице, прочтите соглашение и выберите **я принимаю условия лицензионного соглашения** параметр. Нажмите кнопку **Далее**.  
  
5.  Приведите свое личное имя и имя компании. Нажмите кнопку **Далее**.  
  
6.  На **Выбор компонентов** при необходимости щелкните **Обзор** или **место на диске**. Нажмите кнопку **Далее**.  
  
    -   Нажмите кнопку **Обзор** чтобы увидеть место по умолчанию для построителя отчетов и обновить его.  
  
        > [!NOTE]  
        >  Папка установки по умолчанию для построителя отчетов \<диск > Program Files\Microsoft SQL Server.  
  
    -   Нажмите кнопку **место на диске** чтобы узнать объем дискового пространства построитель отчетов использует.  
  
        > [!NOTE]  
        >  Если на томе недостаточно свободного места, то он будет выделен.  
  
7.  На странице **Целевой сервер по умолчанию** можно по желанию привести URL-адрес целевого сервера отчетов, если он отличается от адреса по умолчанию. Нажмите кнопку **Далее**.  
  
    > [!NOTE]  
    >  Если планируется работать с построителем отчетов в соединении с сервером отчетов, то будет удобнее предоставить URL-адрес сервера на данном этапе. Тем не менее, вы можете также сделать это в **параметры** диалоговое окно, если вы работаете в построителе отчетов.  
  
8.  Нажмите кнопку **установить** для завершения установки построителя отчетов.  
  
### <a name="to-install-report-builder-from-the-command-line"></a>Установка построителя отчетов из командной строки  
  
1.  Перейдите к [построитель отчетов Microsoft SQL Server 2012](http://go.microsoft.com/fwlink/?LinkID=219138) и найдите раздел «построитель отчетов».  
  
2.  Нажмите кнопку **X86 пакета**.  
  
3.  Нажмите кнопку «Сохранить».  
  
4.  При необходимости перейдите в расположение для сохранения, убедитесь, **Сохранить как** вариант — **пакет установщика Windows**, а затем нажмите кнопку **Сохранить**.  
  
5.  В меню **Пуск** выберите команду **Выполнить**.  
  
6.  Введите в поле Открыть введите `cmd.`  
  
7.  В окне командной строки перейдите к папке, в которой был сохранен файл ReportBuilder3_x86.msi.  
  
8.  Введите команду в следующем формате:  
  
     `msiexec/i ReportBuilder3_.msi /option [value] [/option [value]]`  
  
     Ниже приведены два конкретных варианта установки построителя отчетов: RBINSTALLDIR и REPORTSERVERURL. Присутствие этих аргументов в командной строке необязательно. Ниже приведена базовая команда:  
  
     `msiexec /i ReportBuilder3_x86.msi /quiet`  
  
9. Нажмите клавишу ВВОД, чтобы выполнить команду.  
  
## <a name="see-also"></a>См. также  
 [Установка, удаление и поддержка построителя отчетов](../install-uninstall-and-report-builder-support.md)   
 [Удаление изолированной версии построителя отчетов &#40;построитель отчетов&#41;](install-report-builder.md)  
  
  