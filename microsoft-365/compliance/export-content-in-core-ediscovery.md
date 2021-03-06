---
title: Экспорт и скачивание контента из дела core eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: Описывает, как экспортировать и скачивать контент из дела core eDiscovery в Microsoft 365.
ms.openlocfilehash: 8eb54e23369ef682e8aa1ebf7e681eb34444f1cd
ms.sourcegitcommit: efb932db63ad3ab4af4b585428d567d069410e4e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2021
ms.locfileid: "52310846"
---
# <a name="export-content-from-a-core-ediscovery-case"></a>Экспорт содержимого из дела Core eDiscovery

После успешного запуска поиска, связанного с делом core eDiscovery, можно экспортировать результаты поиска. При экспорте результатов поиска элементы почтовых ящиков загружаются в PST-файлы или в качестве отдельных сообщений. При экспорте контента SharePoint OneDrive для бизнеса сайтов экспортируются копии Office и других документов. Также экспортируется Results.csv, содержащий сведения о каждом экспортируемом элементе и файл манифеста (в формате XML), содержащий сведения о каждом результате поиска.
  
## <a name="export-search-results"></a>Экспорт результатов поиска

1. Перейдите и войдите в использование учетных данных учетных записей пользователей, которые были назначены соответствующие разрешения на [https://compliance.microsoft.com](https://compliance.microsoft.com) открытие электронных данных.

2. В левой области навигации центра Microsoft 365 нажмите кнопку **Показать** все, а затем нажмите **кнопку eDiscovery > Core**.

3. На странице **Core eDiscovery** щелкните имя случая, в который необходимо создать удержание.

4. На **домашней странице** для дела щелкните вкладку **Поиск.**

5. В меню **Действия** в нижней части страницы вылетов нажмите кнопку **Экспорт результатов**.

   ![Параметр Экспорт результатов в меню Действия](../media/ActionMenuExportResults.png)

   Рабочий процесс по экспорту результатов поиска, связанного с делом об обнаружении основных электронных обнаружений, является таким же, как экспорт результатов поиска для поиска на странице поиска **контента.** Пошаговая инструкция см. в инструкции [по экспорту результатов поиска контента.](export-search-results.md)

   > [!NOTE]
   > При экспорте результатов поиска у вас есть возможность включить дублирование, чтобы экспортировать только одну копию сообщения электронной почты, несмотря на то, что несколько экземпляров одного и того же сообщения можно было найти в почтовых ящиках, которые искали. Дополнительные сведения о де-дублировании и выявлении дублирующих элементов см. в статьи [De-duplication in eDiscovery search results.](de-duplication-in-ediscovery-search-results.md)

   После начала экспорта результаты поиска будут готовы к загрузке, а это значит, что они будут переданы в служба хранилища Azure microsoft в облаке Майкрософт.
  
6. Щелкните **вкладку Экспорт** в этом случае, чтобы отобразить список заданий экспорта.
  
   ![Экспорт заданий на вкладке Экспорт в случае core eDiscovery](../media/CoreeDiscoveryExport.png)

   Возможно, вам придется нажать **кнопку Обновить,** чтобы обновить список рабочих мест экспорта, чтобы он отображал созданное задание экспорта. Задания экспорта имеют то же имя, что и соответствующий **поиск** с _Export к имени поиска.

7. Щелкните задание экспорта, созданное для отображения сведений о состоянии на странице вылетов. Эта информация включает процент элементов, которые были переданы в служба хранилища Azure расположение.

8. После переноса всех элементов нажмите **кнопку Скачать результаты,** чтобы скачать результаты поиска на локальном компьютере. Дополнительные сведения о загрузке результатов поиска см. в шаге 2 в [экспорте результатов поиска контента](export-search-results.md#step-2-download-the-search-results)

### <a name="more-information-about-exporting-searches-from-a-case"></a>Дополнительные сведения об экспорте поисковых запросов из дела

- Дополнительные сведения об экспортных файлах, включенных при экспорте результатов поиска, см. в отчете по экспорту поиска [контента.](export-a-content-search-report.md#whats-included-in-the-report)

- При перезапуске экспорта любые изменения в запросах поисковых запросов, которые составляют задание экспорта, не повлияют на полученные результаты поиска. При перезапуске экспорта будет снова запускаться одно и то же совместное задание запроса поиска, которое было создано при экспорте.

- Кроме того, при перезапуске экспорта результаты поиска, скопированные в служба хранилища Azure, перезаписывать предыдущие результаты. Предыдущие скопированные результаты будут недоступны для скачивания.
