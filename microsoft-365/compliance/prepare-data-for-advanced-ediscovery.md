---
title: Подготовка данных для Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
titleSuffix: Office 365
ms.date: 9/14/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 2fb94c23-1846-4a0e-994d-da6d02445f15
description: Узнайте, как использовать Центр соответствия требованиям безопасности для подготовки данных для &amp; анализа с помощью Advanced eDiscovery.
ms.openlocfilehash: 43253a3908925bc188568f020f48c62a94552403
ms.sourcegitcommit: 47de4402174c263ae8d70c910ca068a7581d04ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662884"
---
# <a name="prepare-data-for-advanced-ediscovery-classic"></a>Подготовка данных для Advanced eDiscovery (классическая)

В этом разделе описывается загрузка результатов поиска контента в дело в Advanced eDiscovery (классическая). 
  
> [!IMPORTANT]
> Продолжая инвестировать в разработку новых версий Advanced eDiscovery, мы сообщаем о прекращении поддержки версии Advanced eDiscovery, также известной как *Advanced eDiscovery (классическая версия)* или *Advanced eDiscovery 1.0*. Если вы все еще используете Advanced eDiscovery 1.0, перейдите на версию [Advanced eDiscovery 2.0](overview-ediscovery-20.md) (также известную как *решение Advanced eDiscovery в Microsoft 365*) как можно скорее. Advanced eDiscovery 2.0 имеет те же функции, что и Advanced eDiscovery 1.0, а также множество новых возможностей, таких как управление для хранителя, управление коммуникацией и наборы для проверки. Дополнительные сведения о прекращении поддержки Advanced eDiscovery 1.0 см. в статье [Прекращение поддержки средств прежних версий eDiscovery](legacy-ediscovery-retirement.md#advanced-ediscovery-v10).  
  
## <a name="step-1-prepare-data-for-advanced-ediscovery"></a>Шаг 1. Подготовка данных для Advanced eDiscovery

Для анализа данных с помощью Advanced eDiscovery можно использовать результаты поиска контента, который вы запустите в Центре соответствия требованиям безопасности Microsoft 365 (перечислены на странице поиска контента в Центре соответствия требованиям безопасности Microsoft 365) или поиск, связанный с делом eDiscovery (перечислены на странице &amp;  &amp; **eDiscovery** в Центре соответствия требованиям &amp; безопасности). 
  
Подробные инструкции по подготовке результатов поиска для анализа в Advanced eDiscovery см. в подготовьте результаты поиска для [Advanced eDiscovery.](prepare-search-results-for-advanced-ediscovery.md)
  
> [!NOTE]
> Если у вас есть данные за пределами Microsoft 365 и вы хотите импортировать их в Microsoft 365, чтобы подготовить и проанализировать их в Advanced eDiscovery, см. обзор импорта [PST-файлов](https://www.microsoft.com/?ref=go)в [Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/importing-pst-files-to-office-365) и архивировать сторонние данные. 
  
## <a name="step-2-load-search-result-data-in-to-a-case-in-advanced-ediscovery"></a>Шаг 2. Загрузка данных результатов поиска в дело в Advanced eDiscovery

После подготовки результатов поиска в Центре соответствия требованиям безопасности для анализа необходимо загрузить результаты поиска в дело в &amp; Advanced eDiscovery. Дополнительные сведения см. в [описании модуля "Запуск процесса".](run-the-process-module-in-advanced-ediscovery.md)
  
1. Перейдите по ссылке [https://protection.office.com](https://protection.office.com).
    
2. Выполните вход с помощью рабочей или учебной учетной записи.
    
3. Чтобы отобразился список дел в организации, в Центре безопасности и соответствия требованиям выберите **Поиск и исследование** \> **Обнаружение электронных данных**. 
    
4. Нажмите **кнопку "Открыть"** рядом с делом, в которое требуется загрузить данные, в Advanced eDiscovery. 
    
5. На странице **Главная** для этого дела выберите **Перейти на Advanced eDiscovery**. 
    
    ![Click Switch to Advanced eDiscovery to open the case in Advanced eDiscovery](../media/8e34ba23-62e3-4e68-a530-b6ece39b54be.png)
  
    Отображается план хода выполнения подключения к **Advanced eDiscovery.** Когда вы подключены к Advanced eDiscovery, на странице настройки для дела отображается список контейнеров. 
    
    ![Дело отображается в Advanced eDiscovery](../media/8036e152-70dc-4bb7-9379-61c1ed8326b4.png)
  
     Эти контейнеры представляют результаты поиска, которые вы подготовили для анализа в Advanced eDiscovery на шаге 1. Обратите внимание, что имя контейнера имеет то же имя, что и в случае с поиском контента в Центре соответствия &amp; требованиям безопасности. Контейнеры в списке — это контейнеры, которые вы подготовили. Если другой пользователь подготовил результаты поиска для Advanced eDiscovery, соответствующие контейнеры не будут включены в список. 
    
6. Чтобы загрузить данные результатов поиска из контейнера в дело в Advanced eDiscovery, выберите контейнер и нажмите кнопку **"Процесс".**
    
После того как результаты поиска из Центра соответствия требованиям безопасности будут добавлены в дело в Advanced eDiscovery, следующим шагом будет использование средств &amp; в Advanced eDiscovery для анализа и сбора данных, соответствующих делу. 
  
## <a name="see-also"></a>См. также

[Advanced eDiscovery (классическая версия)](office-365-advanced-ediscovery.md)
  
[Настройка пользователей и дел](set-up-users-and-cases-in-advanced-ediscovery.md)
  
[Анализ данных дела](analyze-case-data-with-advanced-ediscovery.md)
  
[Управление настройкой релевантности](manage-relevance-setup-in-advanced-ediscovery.md)
  
[Использование модуля релевантности](use-relevance-in-advanced-ediscovery.md)
  
[Экспорт данных дела](export-case-data-in-advanced-ediscovery.md)

