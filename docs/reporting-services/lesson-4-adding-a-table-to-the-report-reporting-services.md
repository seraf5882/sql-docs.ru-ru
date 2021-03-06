---
title: 'Занятие 4: Добавление таблицы в отчет | Документация Майкрософт'
description: Чтобы создать макет отчета, перетаскивайте объекты отчета, например таблицу, из панели элементов в область конструктора.
ms.date: 12/16/2019
ms.prod: reporting-services
ms.prod_service: reporting-services-native
ms.technology: reporting-services
ms.topic: conceptual
ms.assetid: 5ddf2914-bcdd-427d-8cba-0ccb8342f819
author: maggiesMSFT
ms.author: maggies
ms.openlocfilehash: 0194591ffec572c7d079c70233de45977a38d130
ms.sourcegitcommit: 216f377451e53874718ae1645a2611cdb198808a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/28/2020
ms.locfileid: "87246313"
---
# <a name="lesson-4-add-a-table-to-the-report-reporting-services"></a>Занятие 4: Добавление таблицы в отчет (Reporting Services)

Определив набор данных, вы можете приступать к конструированию отчета с разбивкой на страницы. Чтобы создать макет отчета, вы можете перетаскивать *объекты отчета* из **Панели элементов** в рабочую **область конструктора**. Ниже перечислены некоторые типы объектов отчета.

- Таблица
- Текстовое поле
- Образ —
- график;
- Прямоугольник
- Диаграмма
- Схема

Элементы, содержащие повторяющиеся строки данных из базовых наборов данных, называются *областями данных*. После добавления области данных можно добавлять в нее поля. Простой отчет имеет только одну область данных. Вы можете добавить еще несколько, чтобы отображать дополнительные сведения, например диаграммы.

## <a name="add-a-table-data-region-and-fields-to-a-report-layout"></a>Добавление табличных областей данных и полей в макет отчета

1. Выберите вкладку **Панель элементов** на панели конструктора отчетов слева. С помощью мыши выберите объект **Таблица** и перетащите его в область конструктора отчета. В конструкторе отчетов будет отображена табличная область данных с тремя столбцами, расположенными по центру области конструктора. Если вкладка **Панель элементов** не отображается, воспользуйтесь пунктом меню **Вид** > **Панель элементов**.

    ![ssrs_ssdt_addtable](media/ssrs-ssdt-addtable.png)

    Таблицу можно также добавить в отчет из области конструктора. Щелкните правой кнопкой мыши область конструктора и выберите **Вставить** > **Таблица**.

2. В области **Данные отчета** разверните узел AdventureWorksDataset, чтобы отобразить его поля.

3. Перетащите поле `[Date]` из панели **Данные отчета** в первый столбец таблицы.

    > [!IMPORTANT]
    > После такого перетаскивания происходят два действия. Во-первых, конструктор отчетов отображает в ячейке данных имя поля (*выражение поля*) в квадратных скобках: `[Date]`. Во-вторых, он добавляет заголовок столбца в строку заголовка непосредственно над выражением поля. По умолчанию метка столбца получает значение имени поля. Вы можете выбрать заголовок столбца и ввести другое значение, если хотите изменить его.

4. Перетащите поле `[Order]` из панели **Данные отчета** во второй столбец таблицы.

5. Перетащите поле `[Product]` из панели **Данные отчета** в третий столбец таблицы.

6. Перетащите поле `[Qty]` к правому краю третьего столбца, где появляется вертикальный курсор, а указатель мыши изменяется на знак "плюс" (+). Теперь отпустите кнопку мыши. Будет создан четвертый столбец для выражения поля `[Qty]`.

    ![ssrs_tutorial_addcolumn](media/ssrs-tutorial-addcolumn.png)

7. Добавьте поле `[LineTotal]` тем же способом, создав пятый столбец. Метка этого столбца получит значение Line Total (Линейный итог). Конструктор отчетов автоматически создает для столбца понятное имя, разбивая строку LineTotal на два слова.

На следующей диаграмме показана табличная область данных, в которой заполнены следующие поля: Date (Дата), Order (Заказ), Product (Продукт), Qty (Кол-во) и Line Total (Итог строки).
![rs_BasicTableDetailsDesign](media/rs-basictabledetailsdesign.png)

## <a name="preview-your-report"></a>Предварительный просмотр отчета

Предварительный просмотр отчета позволяет просматривать подготовленный отчет без его предварительной публикации на сервере отчетов. Не забывайте регулярно просматривать отчет по ходу разработки. Это позволит вам проверять все изменения структуры и данных, а значит вовремя исправлять ошибки и проблемы в ходе работы.

### <a name="to-preview-a-report"></a>Предварительный просмотр отчета

- Выберите вкладку **Предварительный просмотр**. Конструктор отчетов запустит отчет и отобразит его в представлении **Предварительный просмотр**.

    ![ssrs_ssdt_preview](media/ssrs-ssdt-preview.png)

На следующей схеме показана часть отчета в представлении **Предварительный просмотр**.

   ![Просмотр, строки детализации таблицы с пятью столбцами](media/rs-basictabledetailspreview.png "Просмотр, строки детализации таблицы с пятью столбцами")

Обратите внимание на значения Date (Дата) и Line Total (Линейный итог). В следующем уроке вы научитесь форматировать их для более точного отображения.

> [!NOTE]
> В меню **Файл** выберите **Сохранить все**, чтобы сохранить отчет.

## <a name="next-steps"></a>Дальнейшие действия

Итак, вы успешно добавили в отчет табличную область, затем добавили поля в эту область данных и выполнили предварительный просмотр отчета. В следующем уроке вы научитесь форматировать заголовки столбцов и выражения полей. Переходите к статье [Занятие 5. Форматирование отчета (службы Reporting Services)](lesson-5-formatting-a-report-reporting-services.md).
  
## <a name="see-also"></a>См. также раздел

[Таблицы (построитель отчетов и службы SSRS)](report-design/tables-report-builder-and-ssrs.md)  
[Коллекция полей набора данных (построитель отчетов и службы SSRS)](report-data/dataset-fields-collection-report-builder-and-ssrs.md)  
