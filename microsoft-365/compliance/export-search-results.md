---
title: Экспорт результатов поиска контента
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: how-to
f1_keywords:
- ms.o365.cc.CustomizeExport
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: ed48d448-3714-4c42-85f5-10f75f6a4278
description: Экспорт результатов поиска из поиска контента в Центр соответствия требованиям Microsoft 365 на локальный компьютер. Результаты электронной почты экспортируются в качестве PST-файлов. Контент из SharePoint и OneDrive для бизнеса экспортируется в качестве родных Office документов.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: d3ae14fc0ac31e50d579668c7fafba5390c5b8fc
ms.sourcegitcommit: 8b79d276f71f22bcaeb150e78e35101cb1ae0375
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/24/2021
ms.locfileid: "53114768"
---
# <a name="export-content-search-results"></a>Экспорт результатов поиска контента

После успешного запуска поиска контента можно экспортировать результаты поиска на локальный компьютер. При экспорте результатов для почты они будут скачаны на ваш компьютер в виде PST-файлов. При экспорте контента SharePoint и OneDrive для бизнеса сайтов экспортируются копии Office документов. Существуют другие документы и отчеты, включенные в экспортируемую результаты поиска.
  
Экспорт результатов поиска контента включает подготовку результатов, а затем их загрузку на локальный компьютер. Эти действия для экспорта результатов поиска также применяются к экспорту результатов поиска, связанного с случаями поиска Core eDiscovery.
  
## <a name="before-you-export-search-results"></a>Перед экспортом результатов поиска

- Чтобы экспортировать результаты поиска, вам необходимо на роль управления экспортом в Центре & соответствия требованиям. Эта роль назначается встроенной группе ролей "Руководитель службы обнаружения электронных данных". По умолчанию эта роль не назначена группе ролей "Управление организацией". Дополнительные сведения см. в статье [Назначение разрешений на обнаружение электронных данных](assign-ediscovery-permissions.md).

- Компьютер, используемый для экспорта результатов поиска, должен соответствовать указанным ниже требованиям к системе.
  
  - Последняя версия Windows (32-битная или 64-битная)
  
  - Microsoft .NET Framework 4.7
  
- Для запуска экспортного средства eDiscovery 1 необходимо использовать один из следующих поддерживаемых<sup>браузеров.</sup>

  - Microsoft Edge <sup>2</sup>
  
    ИЛИ

  - Internet Explorer версии не ниже 10.
  
  > [!NOTE]
  > <sup>1</sup> Корпорация Майкрософт не производит сторонние расширения или надстройки для ClickOnce приложений. Экспорт результатов поиска с помощью неподдермеченного браузера с сторонними расширениями или надстройки не поддерживается.<br/>
  > <sup>2</sup> В результате недавних изменений Microsoft Edge ClickOnce по умолчанию поддержка больше не включена. Инструкции по включению ClickOnce поддержки в Edge см. в инструкции [Use the eDiscovery Export Tool in Microsoft Edge.](configure-edge-to-export-search-results.md)
  
- Средство экспорта электронных обнаружений, которое используется в шаге 2 для скачивания результатов поиска, не поддерживает автоматизацию (с помощью скрипта или запускаемых комлетов). Настоятельно рекомендуется не автоматизировать процесс подготовки на шаге 1 или процесс загрузки в шаге 2. Если вы автоматизируете любой из этих процессов, microsoft Support не будет оказывать помощь, если у вас будут проблемы.

- Рекомендуется скачивать результаты поиска на локальный компьютер. Чтобы устранить проблемы с брандмауэром или прокси-инфраструктурой вашей компании при скачиве результатов поиска, можно скачать результаты поиска на виртуальный рабочий стол за пределами сети. Это может привести к уменьшению времени, которое возникает в подключениях к данным Azure при экспорте большого количества файлов. Дополнительные сведения о виртуальных настольных компьютерах [см. в Windows Virtual Desktop.](https://azure.microsoft.com/services/virtual-desktop)

- Чтобы повысить производительность при загрузке результатов поиска, необходимо разделить поиски, возвращающие большой набор результатов на меньшие. Например, диапазоны дат можно использовать в поисковых запросах, чтобы вернуть меньший набор результатов, которые можно скачать быстрее.
  
- При экспорте результатов поиска данные временно хранятся в локальном служба хранилища Azure в облаке Майкрософт перед загрузкой на локальный компьютер. Убедитесь, что ваша организация может подключиться к конечной точке Azure, которая **\* является .blob.core.windows.net** (подмывка представляет уникальный идентификатор для экспорта). Данные результатов поиска удаляются из служба хранилища Azure через две недели после создания. 
  
- Если ваша организация использует прокси-сервер для связи с Интернетом, необходимо определить параметры прокси-сервера на компьютере, который используется для экспорта результатов поиска (чтобы средство экспорта можно было проверить на прокси-сервере). Для этого откройте файл *machine.config* в расположении, которое соответствует вашей версии Windows. 
  
  - **32-битная:**`%windir%\Microsoft.NET\Framework\[version]\Config\machine.config`
  
  - **64-битная:**`%windir%\Microsoft.NET\Framework64\[version]\Config\machine.config`
  
    Добавьте следующие строки  *в файлmachine.config*  между  `<configuration>`  `</configuration>` тегами и тегами. Обязательно замените  `ProxyServer`  `Port` и правильные значения для организации; `proxy01.contoso.com:80` например. 
  
    ```xml
    <system.net>
       <defaultProxy enabled="true" useDefaultCredentials="true">
         <proxy proxyaddress="https://ProxyServer :Port " 
                usesystemdefault="False" 
                bypassonlocal="True" 
                autoDetect="False" />
       </defaultProxy>
    </system.net>
    ```

- Если результаты поиска старше 7 дней и вы представляете задание экспорта, отображается сообщение об ошибке, в результате которое будет отображаться запрос на повторное повторение поиска для обновления результатов поиска. Если это произойдет, отмените экспорт, повторно запустите поиск и снова запустите экспорт.

## <a name="step-1-prepare-search-results-for-export"></a>Шаг 1. Подготовка результатов поиска к экспорту

Прежде всего необходимо подготовить результаты поиска для экспорта. При подготовке результатов они загружаются в служба хранилища Azure майкрософт. Содержимое из почтовых ящиков и сайтов загружается с максимальной скоростью 2 ГБ в час.
  
1. В Центр соответствия требованиям Microsoft 365 выберите поиск контента, который необходимо экспортировать.
  
2. В меню **Действия** в нижней части страницы вылетов нажмите кнопку **Экспорт результатов**.

   ![Параметр Экспорт результатов в меню Действия](../media/ActionMenuExportResults.png)

   Отображается **страница** вылетов результатов экспорта. Параметры экспорта, доступные для экспорта контента, зависят от того, находятся ли результаты поиска в почтовых ящиках или на сайтах или в сочетании обоих.

3. В **параметрах Output** выберите один из следующих вариантов:
  
   ![Параметры вывода экспорта](../media/ExportOutputOptions.png)

    - **Все элементы, за исключением** элементов непризнаного формата, шифруются или не индексируются по другим причинам. Этот параметр экспортирует только индексные элементы.
  
    - **Все элементы, в** том числе непризнаваемого формата, шифруются или не индексируются по другим причинам. Этот параметр экспортирует индексные и неиндексуалные элементы.
  
    - **Шифруются** только элементы, которые имеют непризнаненный формат или не индексируются по другим причинам. Этот параметр экспортирует только неиндексы.

      Дополнительные [сведения см.](#more-information) в разделе Описание экспорта частично индексных элементов. Дополнительные сведения о частично индексациях элементов см. в статьи Частично индексация элементов [в поиске контента.](partially-indexed-items-in-content-search.md)

4. В **статье Экспорт Exchange как** выберите один из следующих вариантов:
  
   ![Параметры Exchange](../media/ExchangeExportOptions.png)

    - **Один PST-файл для каждого почтового ящика:** экспортирует по одному PST-файлу для каждого почтового ящика пользователя, содержащем результаты поиска. Все результаты из архивного почтового ящика пользователя включаются в один файл PST. Этот параметр воспроизводит структуру папок почтового ящика из исходных почтовых ящиков.
  
    - **Один PST-файл,** содержащий все сообщения: экспортирует один PST-файл (с именем *Exchange.pst),* содержащий результаты поиска из всех исходных почтовых ящиков, включенных в поиск. Этот параметр воспроизводит структуру папок почтовых ящиков для каждого сообщения.
  
    - **Один PST-файл,** содержащий все сообщения в одной папке: экспортирует результаты поиска в один PST-файл, где все сообщения находятся в одной папке верхнего уровня. Этот параметр позволяет рецензентам рассматривать элементы в хронологическом порядке (элементы сортироваться по дате рассылки) без необходимости перемещаться по исходной структуре папок почтовых ящиков для каждого элемента.
  
    - **Отдельные сообщения.** Экспортирует результаты поиска в виде отдельных сообщений электронной почты с помощью формата .msg. При выборе этого параметра результаты поиска по электронной почте экспортируются в папку в файловой системе. Путь папки для отдельных сообщений тот же, что и при экспорте результатов в PST-файл.
  
5. Настройка следующих дополнительных параметров:

   ![Настройка других вариантов экспорта](../media/OtherExportOptions.png)

   1. Чтобы **исключить дубликат** сообщений, выберите Exchange для Exchange.
  
      Если вы выберете этот параметр, будет экспортирована только одна копия сообщения, даже если в почтовых ящиках, которые были найдены, находятся несколько копий одного и того же сообщения. Отчет о результатах экспорта (это файл с именем Results.csv) будет содержать строку для каждой копии дублируемого сообщения, чтобы можно было идентифицировать почтовые ящики (или общедоступные папки), содержащие копию дубликата сообщения. Дополнительные сведения о де-дублировании и выявлении дублирующих элементов см. в статьи [De-duplication in eDiscovery search results.](de-duplication-in-ediscovery-search-results.md)
  
   2. Выберите **версии Include для SharePoint файлов** для экспорта всех версий SharePoint документов. Этот параметр отображается только в том случае, если источники контента поиска включают SharePoint или OneDrive для бизнеса сайты.
  
   3. Выберите файлы **Export в сжатой (сжатой) папке. Включает только отдельные сообщения и SharePoint для** экспорта результатов поиска в сжатые папки. Этот параметр отображается только при экспорте Exchange в качестве отдельных сообщений и когда результаты поиска включают SharePoint или OneDrive документы. Этот параметр используется в основном для работы с ограничением 260 символов в Windows при экспорте элементов. Дополнительные сведения см. в разделе "Имена экспортных [элементов".](#more-information)
   > [!IMPORTANT]
   > Экспорт файлов в сжатой (сжатой) папке увеличит время экспорта.
  
6. Нажмите **кнопку Экспорт,** чтобы запустить процесс экспорта. Результаты поиска подготовлены для скачивания, а это значит, что они собираются из исходных местоположений контента, а затем загружаются в служба хранилища Azure в облаке Майкрософт. Это может занять несколько минут.

В следующем разделе указаны инструкции по загрузке экспортных результатов поиска.
  
## <a name="step-2-download-the-search-results"></a>Шаг 2. Скачивание результатов поиска

Следующий шаг — скачивание результатов поиска с служба хранилища Azure на локальный компьютер.
  
1. На странице **поиска контента** в Центр соответствия требованиям Microsoft 365 выберите вкладку **Экспорт**
  
   Возможно, вам придется нажать **кнопку Обновить,** чтобы обновить список рабочих мест экспорта, чтобы он отображал созданное задание экспорта. Задания экспорта имеют то же имя, что и соответствующий **поиск** с _Export к имени поиска.
  
2. Выберите задание экспорта, созданное в шаге 1.

3. На странице вылет под **ключом Экспорт** нажмите **Копировать** в буфер обмена . Этот ключ используется в шаге 6 для скачивания результатов поиска.
  
   > [!IMPORTANT]
   > Так как любой пользователь может установить и запустить средство экспорта службы обнаружения электронных данных, а затем использовать этот ключ для скачивания результатов поиска, то для защиты ключа необходимо предпринять такие же меры, как и для защиты паролей и другой информации, связанной с обеспечением безопасности. 

4. В верхней части страницы вылет нажмите кнопку **Скачать результаты**.

5. Если вам предложено установить средство экспорта **электронных** обнаружений, нажмите кнопку **Установите**.

6. В **средстве экспорта электронных открытий** сделайте следующее:

   ![Средство экспорта электронных открытий](../media/eDiscoveryExportTool.png)

   1. Вклеить клавишу экспорта, скопированную на шаге 3, в соответствующем поле.
  
   2. Нажмите кнопку **Обзор** и укажите расположение, в которое вы хотите скачать файлы результатов поиска.
  
      > [!IMPORTANT]
      >  Из-за высокой сетевой активности во время скачивания результаты поиска следует скачивать только в расположение на внутреннем диске на локальном компьютере. Для наилучшего скачивания выполните следующие рекомендации: <br/>
      >- Не скачайте результаты поиска на путь UNC, сетевой диск, внешний USB-накопитель или синхронизированную OneDrive для бизнеса учетную запись.<br/>
      >- Отключить антивирусное сканирование для папки, в которую загружается результат поиска.<br/>
      >- Скачайте результаты поиска в разные папки для одновременной загрузки заданий.

7. Нажмите кнопку **Пуск**, чтобы скачать результаты поиска на свой компьютер.
  
    **Средство экспорта службы обнаружения электронных данных** отображает сведения о состоянии процесса экспорта, в том числе о предполагаемом количестве (и размере) элементов, которые осталось скачать. После завершения экспорта вы получаете доступ к файлам в расположении, в которое они были скачаны.

## <a name="more-information"></a>Дополнительные сведения

Дополнительные сведения об экспорте результатов поиска.
  
[Ограничения экспорта](#export-limits)
  
[Отчеты об экспорте](#export-reports)
  
[Экспорт частично индексированных элементов](#exporting-partially-indexed-items)

[Экспорт отдельных сообщений или PST-файлов](#exporting-individual-messages-or-pst-files)

[Расшифровка сообщений электронной почты с защитой от RMS и вложений в зашифрованные файлы](#decrypting-rms-protected-email-messages-and-encrypted-file-attachments)

[Имена файлов экспортных элементов](#filenames-of-exported-items)  
  
[Разное](#miscellaneous)
  
### <a name="export-limits"></a>Ограничения экспорта

Сведения об ограничениях при экспорте результатов поиска контента см. в разделе "Ограничения экспорта" в разделе [Ограничения для поиска контента.](limits-for-content-search.md#export-limits)

### <a name="export-reports"></a>Отчеты об экспорте
  
- При экспорте результатов поиска в дополнение к результатам поиска включаются следующие отчеты.
  
  - **Сводка экспорта** Документ Excel, содержащий сводку экспорта. Это включает такие сведения, как количество поисковых источников контента, предполагаемые и загруженные размеры результатов поиска, а также предполагаемое и загруженное число экспортируемого содержимого.
  
  - **Манифест** Файл манифеста (в формате XML), содержащий сведения о каждом элементе, включенном в результаты поиска.
  
  - **Результаты** Документ Excel, содержащий сведения о каждом элементе, скачаемом в результате поиска. При выполнении поиска в почте журнал результатов содержит сведения о каждом сообщении, включая указанные ниже.
  
    - Расположение сообщения в исходном почтовом ящике (включая сведения о том, в каком почтовом ящике находится сообщение, в основном или в архивном).
  
    - Дата отправки или получения сообщения.

    - Тема сообщения.

    - Отправитель и получатели сообщения.

    - Является ли сообщение дублирующим сообщением, если вы включили параметр de-duplication при экспорте результатов поиска. Дубликаты сообщений имеют значение в столбце **Дубликат** к элементу, который определяет сообщение как дубликат. Значение в столбце **Дубликат** к элементу содержит идентификатор элемента экспортируемого сообщения. Дополнительные сведения см. в [таблице De-duplication in eDiscovery search results.](de-duplication-in-ediscovery-search-results.md)

      Для документов с SharePoint OneDrive для бизнеса сайтов журнал результатов содержит сведения о каждом документе, в том числе:

      - URL-адрес документа.

      - URL-адрес семейства веб-сайтов, в котором расположен документ.

      - Дата последнего изменения документа.

      - Имя документа (которое указано в столбце "Тема" журнала результатов).

  - **Неиндексуалные элементы** Документ Excel, содержащий сведения о любых частично индексациях элементов, которые будут включены в результаты поиска. Если при генерации отчета о результатах поиска не будут включены частично индексные элементы, этот отчет по-прежнему будет загружен, но будет пустым.

  - **Ошибки и предупреждения** Содержит ошибки и предупреждения для файлов, с которыми сталкиваются при экспорте. Сведения об ошибках см. в статье Сведения об ошибках для сведений, характерных для каждой отдельной ошибки или предупреждения.

  - **Пропущенные элементы** При экспорте результатов поиска с SharePoint и OneDrive для бизнеса сайтов экспорт обычно включает отчет о пропущенных товарах (SkippedItems.csv). Элементы, приведенные в этом отчете, обычно являются элементами, которые не будут загружены, например папка или набор документов. Не экспортировать эти типы элементов по проекту. Для других пропущенных элементов поле "Тип ошибки" и "Сведения об ошибках" в отчете о пропущенных элементах показывает причину пропуска элемента и не было загружено с другими результатами поиска.

  - **Trace.log** содержит подробные сведения о процессе экспорта и может помочь в обнаружении проблем при экспорте. Если вы откроете билет в Службе поддержки Майкрософт по поводу проблемы, связанной с экспортом результатов поиска, вам может потребоваться предоставить этот журнал трассировки.
  
    > [!NOTE]
    > Вы можете просто экспортировать эти документы, не экспортировать фактические результаты поиска. См. [отчет об экспорте поиска контента.](export-a-content-search-report.md)
  
### <a name="exporting-partially-indexed-items"></a>Экспорт частично индексированных элементов
  
- Если вы экспортируете элементы почтовых ящиков из поиска контента, который возвращает все элементы почтовых ящиков в результатах поиска (так как ключевые слова, включенные в поисковый запрос), частично индексированные элементы не будут скопироваться в PST-файл, содержащий неидексированные элементы. Это происходит потому, что все элементы, в том числе частично индексируются, автоматически включаются в регулярные результаты поиска. Это означает, что частично индексация элементов будет включена в PST-файл (или в качестве отдельных сообщений), который содержит другие индексные элементы.

    Если вы экспортируете как индексируемые, так и частично индексируемые элементы или экспортируете только индексные элементы из поиска контента, который возвращает все элементы, будет загружено одинаковое количество элементов. Это происходит, несмотря на то, что предполагаемые результаты поиска контента (отображаются в статистике поиска в Центре соответствия требованиям безопасности &) по-прежнему включают отдельную оценку количества частично индексных элементов. Например, предположим, что оценка поиска, включаемая все элементы (без ключевых слов в поисковом запросе), показывает, что было найдено 1000 элементов, а также найдено 200 частично индексных элементов. В этом случае 1000 элементов включают частично индексные элементы, так как поиск возвращает все элементы. Другими словами, поиск возвращает 1000 элементов, а не 1200 (как можно ожидать). Если вы экспортируете результаты этого поиска и решите экспортировать индексные и частично индексируемые элементы (или экспортировать только частично индексные элементы), то будет загружено 1000 элементов. Опять же, это происходит из-за того, что частично индексные элементы включаются в регулярные (индексные) результаты при использовании пустого запроса поиска для возврата всех элементов. В этом же примере, если вы решите экспортировать только частично индексируемые элементы, будет загружено только 200 неиндексуальных элементов.

    Кроме того, обратите внимание, что в предыдущем примере (при экспорте индексных и частично индексных элементов или экспорте только индексных элементов) отчет Export **Summary,** включенный с экспортом результатов поиска, будет включать в себя 1000 элементов с оценками элементов и 1000 загруженных элементов по тем же причинам, что и описано выше. 

- Если при экспорте результатов поиска был поиск определенных местоположений контента или всех местоположений контента в организации, экспортируются только частичные элементы из расположения контента, содержащие элементы, которые соответствуют критериям поиска. Другими словами, если результаты поиска не найдены в почтовом ящике или на сайте, то никакие частично индексируемые элементы в этом почтовом ящике или на сайте не будут экспортироваться. Причина этого заключается в том, что экспорт частично индексных элементов из большого числа местоположений в организации может повысить вероятность ошибок экспорта и увеличить время, необходимое для экспорта и скачивания результатов поиска.

    Чтобы экспортировать частично индексируемые элементы из всех местоположений контента для поиска, настройте поиск, чтобы вернуть все элементы (удалив ключевые слова из поискового запроса), а затем экспортировать только частично индексируемые элементы при экспорте результатов поиска.

    ![Используйте третий вариант экспорта для экспорта только неиндексуальных элементов](../media/5d7be338-a0e5-425f-8ba5-92769c24bf75.png)
  
- При экспорте результатов поиска с SharePoint или OneDrive для бизнеса сайтов возможность экспорта неиндексуальных элементов также зависит от выбранного варианта экспорта и от того, содержит ли сайт, который был выбран, индексируемого элемента, который соответствует критериям поиска. Например, если вы ищете конкретные сайты SharePoint или OneDrive для бизнеса и результаты поиска не найдены, не будут экспортироваться неидексные элементы с этих сайтов, если вы выберете второй вариант экспорта для экспорта как индексных, так и неиндексуальных элементов. Если индексируемого элемента с сайта соответствует критериям поиска, то все неиндексуалные элементы с этого сайта будут экспортироваться при экспорте как индексных, так и неиндексуальных элементов. На следующей иллюстрации описываются варианты экспорта, основанные на том, содержит ли сайт индексируемый элемент, который соответствует критериям поиска.

    ![Выберите вариант экспорта в зависимости от того, содержит ли сайт индексируемого элемента, который соответствует критериям поиска](../media/94f78786-c6bb-42fb-96b3-7ea3998bcd39.png)

    а. Экспортируются только индексные элементы, которые соответствуют критериям поиска. Частично индексируемые элементы не экспортируются.

    б. Если никакие индексируемые элементы сайта не соответствуют критериям поиска, то частично индексируемые элементы с этого же сайта не экспортируются. Если индексируемые элементы с сайта возвращаются в результатах поиска, то частично индексируемые элементы с этого сайта экспортируются. Другими словами, экспортируются только частично индексируемые элементы с сайтов, содержащих элементы, которые соответствуют критериям поиска.

    в. Все частично индексируемые элементы со всех сайтов в поиске экспортируются независимо от того, содержит ли сайт элементы, которые соответствуют критериям поиска.

    Если вы решите экспортировать частично индексируемые элементы, элементы частично индексируемого почтового ящика экспортируются в отдельный PST-файл независимо от параметра, который вы выбираете в статье **Export Exchange** как .

- Если частично индексируемые элементы возвращаются в результатах поиска (так как другие свойства частично индексных элементов соответствуют критериям поиска), то эти частично индексируемые элементы экспортируются с обычными результатами поиска. Таким образом, если вы решите экспортировать как индексные элементы, так и частично индексированы (выбрав все **элементы,** в том числе непризнаненные, шифруются или не индексируются по другим причинам), частично индексируемые элементы, экспортируемые с регулярными результатами, будут указаны в отчете Results.csv. Они не будут перечислены в отчете items.csv Unindexed.
  
### <a name="exporting-individual-messages-or-pst-files"></a>Экспорт отдельных сообщений или PST-файлов
  
- Если имя пути файла сообщения превышает максимальное ограничение символов для Windows, имя пути файла усечено. Но исходное имя пути файла будет перечислены в Манифесте и ResultsLog.
  
- Как объяснялось ранее, результаты поиска по электронной почте экспортируются в папку в файловой системе. Путь папки для отдельных сообщений будет реплицировать путь папки в почтовом ящике пользователя. Например, для поиска с именем "ContosoCase101" сообщения в почтовом ящике пользователя будут расположены в пути папки  `~ContosoCase101\\<date of export\Exchange\user@contoso.com (Primary)\Top of Information Store\Inbox` .

- Если вы решите экспортировать сообщения электронной почты в один PST-файл, содержащий все  сообщения в одной папке, папка "Удаленные элементы" и папка "Папки поиска" включены в верхний уровень папки PST.  Эти папки пусты.

- Как уже говорилось ранее, для расшифровки сообщений, защищенных от RMS, при их экспорте необходимо экспортировать результаты поиска электронной почты в качестве отдельных сообщений. Зашифрованные сообщения останутся зашифрованными, если вы экспортируете результаты поиска электронной почты в виде PST-файла.
  
### <a name="decrypting-rms-protected-email-messages-and-encrypted-file-attachments"></a>Расшифровка сообщений электронной почты с защитой от RMS и вложений в зашифрованные файлы

Все защищенные правами сообщения электронной почты, включенные в результаты поиска контента, будут расшифрованы при экспорте. Кроме того, любой файл, зашифрованный с помощью технологии шифрования [Майкрософт](encryption.md) и присоединенный к сообщению электронной почты, включенному в результаты поиска, также будет расшифровываться при экспорте. Эта возможность расшифровки включена по умолчанию для членов группы ролей диспетчера электронных данных. Это потому, что роль управления расшифровка RMS назначена этой группе ролей по умолчанию. Следует помнить о следующих вещах при экспорте зашифрованных сообщений электронной почты и вложений:
  
- Как объяснялось ранее, для расшифровки сообщений, защищенных от RMS при экспорте, необходимо экспортировать результаты поиска в качестве отдельных сообщений. Если вы экспортируете результаты поиска в PST-файл, защищенные от RMS сообщения остаются зашифрованными.

- Расшифровка сообщений идентифицирована в **отчете ResultsLog.** В этом отчете содержится столбец с  именем **"Состояние** декодирования", а значение декодированной в этом столбце определяет расшифровку сообщений.

- Помимо расшифровки вложений файлов при экспорте результатов поиска вы также можете просмотреть расшифрованный файл при предварительном просмотре результатов поиска. Вы можете просматривать защищенное правами сообщение электронной почты только после его экспорта.

- В настоящее время возможность расшифровки при экспорте результатов поиска не включает зашифрованное содержимое с SharePoint и OneDrive для бизнеса сайтов. Однако скоро появится поддержка документов, зашифрованных с помощью технологий шифрования Майкрософт и хранимых в SharePoint Online и OneDrive для бизнеса.

- Если необходимо предотвратить расшифровку сообщений с защитой RMS и зашифрованных вложений файлов, необходимо создать настраиваемую группу ролей (скопируя встроенную группу ролей диспетчера электронных данных), а затем удалить роль управления расшифровкой RMS из настраиваемой группы ролей. Затем добавьте человека, который не хочет расшифровывать сообщения в качестве члена настраиваемой группы ролей.
  
### <a name="filenames-of-exported-items"></a>Имена файлов экспортных элементов
  
- Существует ограничение в 260 символов (навязано операционной системой) для полного имени пути для сообщений электронной почты и документов сайта, экспортируемого на локальный компьютер. Полное имя пути для экспортных элементов включает исходное расположение элемента и расположение папки на локальном компьютере, на который загружаются результаты поиска. Например, если вы указываете для скачивания результатов поиска в средство экспорта электронных открытий, полное имя пути для загруженного элемента электронной почты  `C:\Users\Admin\Desktop\SearchResults` будет  `C:\Users\Admin\Desktop\SearchResults\ContentSearch1\03.15.2017-1242PM\Exchange\sarad@contoso.com (Primary)\Top of Information Store\Inbox\Insider trading investigation.msg` .

- Если ограничение в 260 символов превышено, полное имя пути элемента будет усечено на основе следующих ниже:

  - Если полное имя пути больше 260 символов, имя файла будет сокращено, чтобы попасть под ограничение; обратите внимание, что усеченное имя файла (за исключением расширения файла) не будет меньше восьми символов.

  - Если полное имя пути еще слишком долго после сокращения имени файла, элемент перемещается из текущего расположения в родительную папку. Если имя пути еще слишком длинное, процесс повторяется: сокращается имя файла и при необходимости снова перемещается в родительную папку. Этот процесс повторяется до тех пор, пока полное имя пути не будет под ограничением 260 символов.

  - Если усеченное полное имя пути уже существует, к концу имени файла добавляется номер версии; например, `statusmessage(2).msg` .

    Чтобы устранить эту проблему, рассмотрите возможность скачивания результатов поиска в расположение с коротким именем пути; например, загрузка результатов поиска в именуемую папку добавит меньше символов к именам путей экспортных элементов, чем их загрузка в папку с именем  `C:\Results`  `C:\Users\Admin\Desktop\Results` .

- При экспорте документов сайта также возможно изменение исходного имени файла документа. Это происходит специально для документов, удаленных с SharePoint или OneDrive для бизнеса сайта, который был помещен на удержание. После удаления документа на сайте, который находится на удержании, удаленный документ автоматически перемещается в библиотеку хранения сохранения для сайта (который был создан при удержании сайта). При перемещении удаленного документа в библиотеку хранения хранения случайным образом создается уникальный ИД к исходному имени файла документа. Например, если имя файла для документа и этот документ позже удаляется и перемещается в библиотеку хранения сохранения, имя файла документа, перемещенного в библиотеку хранения сохранения, изменено на что-то подобное  `FY2017Budget.xlsx`  `FY2017Budget_DEAF727D-0478-4A7F-87DE-5487F033C81A2000-07-05T10-37-55.xlsx` . Если документ в библиотеке хранения хранения соответствует запросу поиска контента и вы экспортируете результаты этого поиска, экспортируемого файла имеет измененное имя файла; в этом примере имя файла экспортируемого документа будет  `FY2017Budget_DEAF727D-0478-4A7F-87DE-5487F033C81A2000-07-05T10-37-55.xlsx` .

    При внесении изменений в документ на сайте с удержанием (и включена версия библиотеки документов на сайте), копия файла автоматически создается в библиотеке хранения сохранения. В этом случае случайный и уникальный ID также примыкает к имени файла документа, скопированного в библиотеку хранения сохранения.

    Причина, по которой имена файлов перемещаются или копируется в библиотеку хранения сохранения, заключается в предотвращении конфликтующих имен файлов. Дополнительные сведения о размещении удержания на сайтах и библиотеке хранения см. в обзоре удержания на месте в [SharePoint Server 2016.](https://support.office.com/article/5e400d68-cd51-444a-8fe6-e4df1d20aa95)

### <a name="miscellaneous"></a>Разное
  
- При загрузке результатов поиска с помощью экспортного средства eDiscovery можно получить следующую ошибку: это преходящая ошибка, которая обычно возникает в служба хранилища Azure `System.Net.WebException: The remote server returned an error: (412) The condition specified using HTTP conditional header(s) is not met.` расположении. Чтобы устранить эту проблему, повторите скачивание результатов [поиска,](#step-2-download-the-search-results)которые перезапустят средство экспорта электронных обнаружений.

- Все результаты поиска и отчеты об экспорте включены в папку с тем же именем, что и поиск контента. Экспортированные письма расположены в папке с именем **Exchange**. Документы расположены в папке с именем **SharePoint**.

- Метаданные файловой системы для документов на SharePoint и OneDrive для бизнеса сохраняются при экспорте документов на локальный компьютер. Это означает, что при экспорте документов их свойства, например даты создания и последнего изменения, не изменяются.

- Если результаты поиска включают элемент списка из SharePoint, который соответствует запросу поиска, все строки в списке будут экспортироваться в дополнение к элементу, который соответствует запросу поиска и любым вложениям в списке. Причиной такого поведения является предоставление контекста для элементов списка, возвращаемого в результатах поиска. Дополнительные элементы списка и вложения могут привести к тому, что количество экспортных элементов отличается от первоначальной оценки результатов поиска.
