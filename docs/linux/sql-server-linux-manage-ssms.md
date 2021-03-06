---
title: Управление SQL Server на Linux с помощью SSMS
description: В этой статье вы познакомитесь с SQL Server Management Studio. Это интегрированная среда для доступа, настройки, администрирования и разработки всех компонентов SQL Server и управления ими.
author: VanMSFT
ms.author: vanto
ms.date: 05/21/2018
ms.topic: conceptual
ms.prod: sql
ms.technology: linux
ms.assetid: b2fcf858-21c3-462a-8d49-50c85647d092
ms.openlocfilehash: 8520c3741102597ac3b7e93aceabc3ec6c114230
ms.sourcegitcommit: f7ac1976d4bfa224332edd9ef2f4377a4d55a2c9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/02/2020
ms.locfileid: "85883917"
---
# <a name="use-sql-server-management-studio-on-windows-to-manage-sql-server-on-linux"></a>Использование SQL Server Management Studio в Windows для управления SQL Server на базе Linux

[!INCLUDE [SQL Server - Linux](../includes/applies-to-version/sql-linux.md)]

В этой статье рассматривается [SQL Server Management Studio (SSMS)](../ssms/sql-server-management-studio-ssms.md) и приводится несколько типичных задач. SSMS — это приложение Windows, поэтому используйте SSMS при наличии компьютера Windows, который может подключаться к удаленному экземпляру SQL Server в Linux.

> [!TIP]
> Если у вас нет компьютера Windows для запуска SSMS, обратите внимание на новое решение [Azure Data Studio](../azure-data-studio/index.yml). Оно предоставляет графическое средство для управления SQL Server и работает как в Linux, так и в Windows.

[SQL Server Management Studio (SSMS)](../ssms/sql-server-management-studio-ssms.md) входит в набор средств SQL, который корпорация Майкрософт предлагает бесплатно для ваших задач разработки и управления. SSMS — это интегрированная среда для доступа, настройки, администрирования и разработки всех компонентов SQL Server и управления ими. Это решение может подключаться к SQL Server, запущенному на любой платформе в локальной среде, в контейнерах Docker и в облаке. Оно также подключается к Базе данных SQL Azure и Хранилищу данных SQL Azure. SSMS сочетает в себе обширный набор графических инструментов с рядом отличных редакторов скриптов, обеспечивая разработчикам и администраторам любой квалификации доступ к SQL Server.

SSMS предлагает широкий набор возможностей разработки и управления для SQL Server, включая средства для следующих задач.

- Настройка, мониторинг и администрирование экземпляров SQL Server
- Развертывание, мониторинг и обновление компонентов уровня данных, таких как базы и хранилища данных
- Резервное копирование и восстановление баз данных
- Создание и выполнение скриптов и запросов T-SQL и просмотр результатов
- Создание скриптов T-SQL для объектов базы данных
- Просмотр и изменение данных в базах данных
- Визуальный дизайн запросов T-SQL и объектов базы данных, таких как представления, таблицы и хранимые процедуры

Дополнительные сведения о SSMS см. в статье [Что такое SSMS?](../ssms/sql-server-management-studio-ssms.md)

## <a name="install-the-newest-version-of-sql-server-management-studio-ssms"></a>Установка актуальной версии SQL Server Management Studio (SSMS)

При работе с SQL Server следует всегда использовать последнюю версию SQL Server Management Studio (SSMS). Актуальная версия SSMS постоянно обновляется и оптимизируется и  сейчас работает с SQL Server на базе Linux. Чтобы скачать и установить актуальную версию, перейдите на страницу [скачивания SQL Server Management Studio](../ssms/download-sql-server-management-studio-ssms.md). Чтобы вы были в курсе последних новостей, актуальная версия SSMS выводит запрос при наличии новой версии, доступной для скачивания.

> [!NOTE]
> Прежде чем использовать SSMS для управления Linux, ознакомьтесь с [известными проблемами](sql-server-linux-release-notes.md) для SSMS в Linux.

## <a name="connect-to-sql-server-on-linux"></a>Подключение к SQL Server в Linux

Чтобы подключиться, выполните следующие основные шаги.

1. Запустите SSMS, введя **Microsoft SQL Server Management Studio** в поле поиска Windows, а затем щелкните классическое приложение.

    ![SQL Server Management Studio](./media/sql-server-linux-manage-ssms/ssms.png)

1. В окне **Подключение к серверу** введите следующие сведения (если среда SSMS уже запущена, щелкните **Подключить > Ядро СУБД**, чтобы открыть окно **Подключение к серверу**).

   | Параметр | Описание |
   |-----|-----|
   | **Тип сервера** | По умолчанию используется ядро СУБД, не изменяйте это значение. |
   | **Имя сервера** | Введите имя целевого компьютера SQL Server на базе Linux или его IP-адрес и порт в формате `IP,port`. |
   | **Аутентификация** | Для SQL Server на базе Linux используйте **проверку подлинности SQL Server**. |
   | **Имя входа** | Введите имя пользователя с доступом к базе данных на сервере (например, учетную запись **SA** по умолчанию, созданную во время установки). |
   | **Пароль** | Введите пароль для указанного пользователя (для учетной записи **SA**, созданной во время установки). |

    ![SQL Server Management Studio: подключение к серверу базы данных SQL](./media/sql-server-linux-manage-ssms/connect.png)

1. Нажмите кнопку **Соединить**.

    > [!TIP]
    > Если произойдет сбой подключения, сначала попробуйте узнать проблему по сообщению об ошибке. Затем ознакомьтесь с [рекомендациями по устранению неполадок с подключением](sql-server-linux-troubleshooting-guide.md#connection).
 
1. После успешного подключения к SQL Server открывается **обозреватель объектов** и вы можете обратиться к базе данных для выполнения административных задач или запроса данных.

## <a name="run-transact-sql-queries"></a>Выполнение запросов Transact-SQL

После подключения к серверу можно подключиться к базе данных и выполнить запросы Transact-SQL. Запросы Transact-SQL можно использовать почти для любой задачи базы данных.

1. В **обозревателе объектов** перейдите к целевой базе данных на сервере. Например, разверните узел **Системные базы данных**  для работы с базой данных **master**.

1. Щелкните базу данных правой кнопкой мыши и выберите пункт **Создать запрос**.

1. В окне запроса напишите запрос Transact-SQL, чтобы выбрать и возвратить имена всех баз данных на сервере.

   ```sql
   SELECT [Name]
   FROM sys.Databases
   ```

   Если вы не знакомы с написанием запросов, см. статью [Написание инструкций Transact-SQL](../t-sql/tutorial-writing-transact-sql-statements.md).

1. Нажмите кнопку **Выполнить**, чтобы выполнить запрос и просмотреть результаты.

   ![Успешно. Подключение к серверу базы данных SQL: SQL Server Management Studio](./media/sql-server-linux-manage-ssms/execute-query.png)

Хотя с помощью запросов Transact-SQL можно выполнить практически любую задачу управления, SSMS — это графическое средство, упрощающее управление SQL Server. В следующих разделах приведено несколько примеров использования графического пользовательского интерфейса.

## <a name="create-and-manage-databases"></a>Создание баз данных и управление ими

При подключении к базе данных *master* можно создавать базы данных на сервере, а также изменять или удалять существующие базы данных. Следующие шаги описывают выполнение нескольких распространенных задач управления базами данных с помощью Management Studio. Чтобы выполнить эти задачи, убедитесь, что вы подключены к базе данных *master* с именем входа субъекта уровня сервера, созданным при настройке SQL Server в Linux.

### <a name="create-a-new-database"></a>Создание базы данных

1. Запустите SSMS и подключитесь к серверу в SQL Server в Linux.

2. В обозревателе объектов щелкните правой кнопкой мыши папку *Базы данных* и выберите "Создать базу данных".

3. В диалоговом окне *Создание базы данных* введите имя новой базы данных и нажмите кнопку *ОК*.

Новая база данных успешно создана на сервере. Если вы предпочитаете создать базу данных с помощью T-SQL, см. статью [CREATE DATABASE (SQL Server Transact-SQL)](../t-sql/statements/create-database-sql-server-transact-sql.md).

### <a name="drop-a-database"></a>Удаление базы данных

1. Запустите SSMS и подключитесь к серверу в SQL Server в Linux.

2. В обозревателе объектов разверните *папку базы данных*, чтобы просмотреть список всех баз данных на сервере.

3. В обозревателе объектов щелкните правой кнопкой мыши базу данных, которую нужно удалить, и выберите команду *Удалить*.

4. В диалоговом окне *Удаление объекта* установите флажок *Закрыть существующие соединения* и нажмите кнопку *ОК*.

База данных успешно удалена с сервера. Если вы предпочитаете удалить базу данных с помощью T-SQL, см. статью [DROP DATABASE (SQL Server Transact-SQL)](../t-sql/statements/drop-database-transact-sql.md).

## <a name="use-activity-monitor-to-see-information-about-sql-server-activity"></a>Использование монитора активности для просмотра сведений о действиях SQL Server

[Монитор активности](../relational-databases/performance-monitor/activity-monitor.md) встроен в SQL Server Management Studio (SSMS) и отображает сведения о процессах SQL Server и о том, как функционирование этих процессов влияет на текущий экземпляр SQL Server.

1. Запустите SSMS и подключитесь к серверу в SQL Server в Linux.

1. В обозревателе объектов щелкните правой кнопкой мыши узел *сервер* и выберите *Монитор активности*.

Монитор активности отображает развертываемые и свертываемые области со следующими сведениями.

- Обзор
- Процессы
- Ожидания ресурсов
- Ввод-вывод в файле данных
- Последние ресурсоемкие запросы
- Активные ресурсоемкие запросы

После развертывания панели монитор активности выполняет запрос к экземпляру для получения необходимых сведений. При свертывании панели выполнение всех операций запроса для этой панели приостанавливается. Можно одновременно развернуть одну или более панелей для просмотра различных типов активности в экземпляре.

## <a name="see-also"></a>См. также раздел
- [Что такое SSMS?](../ssms/sql-server-management-studio-ssms.md)
- [Экспорт и импорт базы данных с помощью SSMS](sql-server-linux-migrate-ssms.md)
- [Руководство. SQL Server Management Studio](../ssms/tutorials/tutorial-sql-server-management-studio.md)
- [Руководство. Составление инструкций Transact-SQL](../t-sql/tutorial-writing-transact-sql-statements.md)
- [Мониторинг производительности и действий сервера](../relational-databases/performance/server-performance-and-activity-monitoring.md)
