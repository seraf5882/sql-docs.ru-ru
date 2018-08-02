---
title: Восстановление файлов и файловых групп (SQL Server) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology: backup-restore
ms.tgt_pltfrm: ''
ms.topic: conceptual
f1_keywords:
- sql12.swb.restorefilesandfilegrps.general.f1
- sql12.swb.restorefilesandfilegrps.options.f1
- sql12.swb.bselectfilegrpsfiles.f1
helpviewer_keywords:
- SQL Server Management Studio [SQL Server], restoring files and filegroups
- restoring [SQL Server], files
ms.assetid: 72603b21-3065-4b56-8b01-11b707911b05
caps.latest.revision: 24
author: MikeRayMSFT
ms.author: mikeray
manager: craigg
ms.openlocfilehash: 59eb0adb6acd224388528857636b049fa6ecf4bf
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/02/2018
ms.locfileid: "37162935"
---
# <a name="restore-files-and-filegroups-sql-server"></a>Восстановление файлов и файловых групп (SQL Server)
  В этом разделе описывается восстановление файлов и файловых групп в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] с помощью среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] или [!INCLUDE[tsql](../../includes/tsql-md.md)].  
  
 **В этом разделе**  
  
-   **Перед началом работы**  
  
     [Ограничения](#Restrictions)  
  
-   [безопасность](#Security)  
  
-   **Восстановление файлов и файловых групп с помощью следующих средств**  
  
     [Среда SQL Server Management Studio](#SSMSProcedure)  
  
     [Transact-SQL](#TsqlProcedure)  
  
##  <a name="BeforeYouBegin"></a> Перед началом  
  
###  <a name="Restrictions"></a> Ограничения  
  
-   Системный администратор, восстанавливающий файлы и файловые группы, должен быть единственным лицом, использующим восстанавливаемую базу данных в данный момент.  
  
-   Инструкция RESTORE недопустима в явной или неявной транзакции.  
  
-   При использовании простой модели восстановления файл должен принадлежать к файловой группе, находящейся в режиме только для чтения.  
  
-   Перед началом восстановления файлов по модели полного восстановления или модели восстановления с неполным протоколированием необходимо выполнить резервное копирование активного журнала транзакций (который называется заключительным фрагментом журнала). Дополнительные сведения см. в разделе [Создание резервной копии журнала транзакций (SQL Server)](back-up-a-transaction-log-sql-server.md).  
  
-   Чтобы восстановить зашифрованную базу данных, необходимо иметь доступ к сертификату или асимметричному ключу, который использовался для шифрования базы данных. Без сертификата или асимметричного ключа восстановить базу данных нельзя. Поэтому сертификат, используемый для шифрования ключа шифрования базы данных, должен храниться в течение всего времени, пока есть необходимость в резервной копии. Дополнительные сведения см. в статье [SQL Server Certificates and Asymmetric Keys](../security/sql-server-certificates-and-asymmetric-keys.md).  
  
###  <a name="Security"></a> безопасность  
  
####  <a name="Permissions"></a> Permissions  
 Если восстанавливаемая база данных не существуют, для выполнения инструкции RESTORE у пользователя должны быть разрешения CREATE DATABASE. Если база данных существует, разрешения на выполнение инструкции RESTORE по умолчанию предоставлены членам предопределенных ролей сервера **sysadmin** и **dbcreator** , а также владельцу базы данных (**dbo**) (для параметра FROM DATABASE_SNAPSHOT база данных всегда существует).  
  
 Разрешения на выполнение инструкции RESTORE даются ролям, в которых данные о членстве всегда доступны серверу. Так как членство в предопределенной роли базы данных может быть проверено только тогда, когда база данных доступна и не повреждена, что не всегда имеет место при выполнении инструкции RESTORE, члены предопределенной роли базы данных **db_owner** не имеют разрешений RESTORE.  
  
##  <a name="SSMSProcedure"></a> Использование среды SQL Server Management Studio  
  
#### <a name="to-restore-files-and-filegroups"></a>Восстановление файлов и файловых групп  
  
1.  После подключения к соответствующему экземпляру компонента [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]в обозревателе объектов разверните дерево сервера, щелкнув имя сервера.  
  
2.  Разверните узел **Базы данных**. В зависимости от типа восстанавливаемой базы данных выберите пользовательскую базу данных или раскройте узел **Системные базы данных**и выберите системную базу данных.  
  
3.  Щелкните правой кнопкой мыши базу данных, укажите **Задачи**и выберите **Восстановить**.  
  
4.  Щелкните **Файлы и файловые группы**, после чего откроется диалоговое окно **Восстановление файлов и файловых групп** .  
  
5.  На странице **Общие** в списке **В базу данных** введите имя восстанавливаемой базы данных. Можно ввести новую базу данных или выбрать уже существующую из раскрывающегося списка. Список включает все базы данных на сервере кроме системных баз данных **master** и **tempdb**.  
  
6.  Чтобы указать источник и расположение восстанавливаемых резервных наборов данных, выберите один из следующих вариантов.  
  
    -   **Из базы данных**  
  
         Введите имя базы данных в списке. Данный список содержит только базы данных, резервное копирование которых было выполнено в соответствии с журналом резервного копирования **msdb** .  
  
    -   **С устройства**  
  
         Нажмите кнопку обзора. В диалоговом окне **Указание устройств резервного копирования** выберите один из перечисленных типов устройств в списке **Тип носителя резервной копии** . Чтобы выбрать одно или несколько устройств в списке **Носитель резервной копии** , нажмите кнопку **Добавить**.  
  
         После добавления нужных устройств в списке **Носитель резервной копии** нажмите кнопку **ОК** для возвращения на страницу **Общие** .  
  
7.  В сетке **Выберите резервные наборы данных для восстановления** выберите нужные резервные наборы. В этой сетке отображаются резервные копии, доступные в указанном месте. По умолчанию предлагается план восстановления. Чтобы переопределить предложенный план восстановления, можно изменить выбранные элементы в сетке. Если выбор каких-то резервных копий отменяется, то автоматически отменяется и выбор зависящих от них резервных копий.  
  
    |Заголовок столбца|Значения|  
    |-----------------|------------|  
    |**Восстановить**|Установленные флажки обозначают резервные наборы данных, отмеченные для восстановления.|  
    |**Название**|Имя резервного набора данных.|  
    |**Тип файла**|Задает тип данных в резервной копии: **Данные**, **Журнал**или **Данные Filestream**. Данные, содержащиеся в таблицах, хранятся в файлах типа **Данные** . Данные журнала транзакций хранятся в файлах типа **Журнал** . Данные больших двоичных объектов (BLOB), которые хранятся в файловой системе, находятся в файлах типа **Данные Filestream** .|  
    |**Тип**|Тип выполненного резервного копирования: **Полное**, **Разностное**или **Журнал транзакций**.|  
    |**Server**|Имя экземпляра ядра СУБД, выполнившего операцию резервного копирования.|  
    |**Логическое имя файла**|Логическое имя файла.|  
    |**База данных**|Имя базы данных, участвовавшей в операции резервного копирования.|  
    |**Дата начала**|Дата и время начала операции резервного копирования, указанные в региональных настройках клиента.|  
    |**Дата завершения**|Дата и время завершения операции резервного копирования, указанные в формате, соответствующем региональным настройкам клиента.|  
    |**Размер**|Размер резервного набора данных в байтах.|  
    |**Имя пользователя**|Имя пользователя, выполнившего операцию резервного копирования.|  
  
8.  Для просмотра или выбора дополнительных параметров нажмите кнопку **Параметры** на панели **Выбор страницы**.  
  
9. На панели **Параметры восстановления** можно выбрать любой из следующих параметров, если он подходит к данной ситуации.  
  
     **Восстановление файловой группы**  
     Указывает, что восстанавливается вся файловая группа.  
  
     **Перезаписать существующую базу данных**  
     Указывает, что операция восстановления должна переписать все существующие базы данных и связанные с ними файлы, даже если база данных или файл с указанным именем уже существуют.  
  
     Выбор этой функции равнозначен использованию параметра REPLACE в инструкции RESTORE языка [!INCLUDE[tsql](../../includes/tsql-md.md)] .  
  
     **Выдавать приглашение перед восстановлением каждой резервной копии**  
     Запрашивает подтверждение перед восстановлением из копии каждого резервного набора данных.  
  
     Этот параметр особенно полезен, когда для использования различных наборов носителей необходимо менять ленты (например, если на сервере существует одно ленточное устройство).  
  
     **Ограничить доступ к восстановленной базе данных**  
     Доступ к восстановленной базе данных будет только у пользователей **db_owner**, **dbcreator**или **sysadmin**.  
  
     Выбор этой функции равнозначен использованию параметра RESTRICTED_USER в инструкции RESTORE языка [!INCLUDE[tsql](../../includes/tsql-md.md)] .  
  
10. По желанию можно восстановить базу данных в новое местоположение, задав новое назначение для каждого файла в сетке **Восстановить файлы базы данных как** .  
  
    |Заголовок столбца|Значения|  
    |-----------------|------------|  
    |**Имя исходного файла**|Полный путь исходного файла резервной копии.|  
    |**Тип файла**|Задает тип данных в резервной копии: **Данные**, **Журнал**или **Данные Filestream**. Данные, содержащиеся в таблицах, хранятся в файлах типа **Данные** . Данные журнала транзакций хранятся в файлах типа **Журнал** . Данные больших двоичных объектов (BLOB), которые хранятся в файловой системе, находятся в файлах типа **Данные Filestream** .|  
    |**Восстановить как**|Полный путь к файлу базы данных, который нужно восстановить. Чтобы указать новый восстанавливаемый файл, щелкните текстовое поле и измените предложенные путь и имя файла. Изменение пути или имени файла в столбце **Восстановить как** равнозначно использованию параметра MOVE в инструкции RESTORE языка [!INCLUDE[tsql](../../includes/tsql-md.md)] .|  
  
11. В качестве значения параметра **Состояние восстановления** укажите состояние базы данных после операции восстановления.  
  
     **Оставить базу данных готовой к использованию, выполнив откат незафиксированных транзакций. Невозможно восстановить дополнительные журналы транзакций. (RESTORE WITH RECOVERY)**  
     Восстанавливает базу данных. Это поведение по умолчанию. Выберите этот параметр для восстановления всех необходимых резервных копий. Этот параметр равнозначен указанию предложения WITH RECOVERY в инструкции RESTORE языка [!INCLUDE[tsql](../../includes/tsql-md.md)] .  
  
     **Оставить базу данных в нерабочем состоянии и не выполнять откат незавершенных транзакций. Можно восстановить дополнительные журналы транзакций. (RESTORE WITH NORECOVERY)**  
     Оставляет базу данных в состоянии восстановления. Чтобы восстановить базу данных, необходимо выполнить еще одно восстановление с использованием предыдущего параметра RESTORE WITH RECOVERY (см. выше). Этот параметр равнозначен указанию предложения WITH NORECOVERY в инструкции RESTORE языка [!INCLUDE[tsql](../../includes/tsql-md.md)] .  
  
     Если выбран этот параметр, то параметр **Сохранить настройки репликации** недоступен.  
  
     **Оставить базу данных в режиме «только для чтения». Выполнить откат незавершенных транзакций с сохранением операции отката в файле, чтобы можно было отменить операцию восстановления. (RESTORE WITH STANDBY)**  
     Оставляет базу данных в резервном состоянии. Этот параметр равнозначен указанию предложения WITH STANDBY в инструкции RESTORE языка [!INCLUDE[tsql](../../includes/tsql-md.md)] .  
  
     При выборе этого параметра необходимо указать резервный файл.  
  
     **Файл отмены отката**  
     Укажите имя резервного файла в текстовом поле **Файл отмены отката** . Этот параметр необходим, если нужно оставить базу данных в режиме «только для чтения» (RESTORE WITH STANDBY).  
  
##  <a name="TsqlProcedure"></a> Использование Transact-SQL  
  
#### <a name="to-restore-files-and-filegroups"></a>Восстановление файлов и файловых групп  
  
1.  Выполните инструкцию RESTORE DATABASE для восстановления резервной копии файлов и файловых групп, указав следующее:  
  
    -   Имя базы данных для восстановления.  
  
    -   Устройство резервного копирования, откуда будет восстановлена полная резервная копия.  
  
    -   предложение FILE для каждого восстанавливаемого файла;  
  
    -   предложение FILEGROUP для каждой восстанавливаемой файловой группы;  
  
    -   Предложение NORECOVERY. (если файлы не изменялись со времени создания резервной копии, укажите предложение RECOVERY).  
  
2.  Если файлы были изменены после создания резервной копии, выполните инструкцию RESTORE LOG для применения резервной копии журнала транзакций, указав следующее:  
  
    -   Имя базы данных, к которой будет применен журнал транзакций.  
  
    -   Устройство резервного копирования, с которого будет восстановлена резервная копия журнала транзакций.  
  
    -   Предложение NORECOVERY, если существует другая резервная копия журналов транзакций для применения после текущего; в противном случае укажите предложение RECOVERY.  
  
         В случае применения резервных копий журналов транзакций они должны охватывать время резервного копирования файлов и их групп вплоть до конца журналов (если только не восстанавливаются ВСЕ файлы базы данных).  
  
###  <a name="TsqlExample"></a> Примеры (Transact-SQL)  
 В этом примере восстанавливаются файлы и файловые группы базы данных `MyDatabase` . При восстановлении базы данных до текущего момента будут применены два журнала транзакций.  
  
```tsql  
USE master;  
GO  
-- Restore the files and filesgroups for MyDatabase.  
RESTORE DATABASE MyDatabase  
   FILE = 'MyDatabase_data_1',  
   FILEGROUP = 'new_customers',  
   FILE = 'MyDatabase_data_2',  
   FILEGROUP = 'first_qtr_sales'  
   FROM MyDatabase_1  
   WITH NORECOVERY;  
GO  
-- Apply the first transaction log backup.  
RESTORE LOG MyDatabase  
   FROM MyDatabase_log1  
   WITH NORECOVERY;  
GO  
-- Apply the last transaction log backup.  
RESTORE LOG MyDatabase  
   FROM MyDatabase_log2  
   WITH RECOVERY;  
GO  
```  
  
## <a name="see-also"></a>См. также  
 [Восстановление резервной копии базы данных &#40;SQL Server Management Studio&#41;](restore-a-database-backup-using-ssms.md)   
 [Создание резервных копий файлов и файловых групп (SQL Server)](back-up-files-and-filegroups-sql-server.md)   
 [Создание полной резервной копии базы данных (SQL Server)](create-a-full-database-backup-sql-server.md)   
 [Создание резервной копии журнала транзакций (SQL Server)](back-up-a-transaction-log-sql-server.md)   
 [Восстановление резервной копии журнала транзакций (SQL Server)](restore-a-transaction-log-backup-sql-server.md)   
 [RESTORE (Transact-SQL)](/sql/t-sql/statements/restore-statements-transact-sql)  
  
  