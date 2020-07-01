---
title: Быстрая настройка Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
titleSuffix: Office 365
ms.date: 9/14/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MOE150
- MET150
ms.assetid: d7ccd944-9698-41c7-a21b-677dc62973c4
description: Сведения о том, как получать доступ к Advanced eDiscovery из Центра безопасности и соответствия требованиям и просматривать типичный рабочий процесс для использования Advanced eDiscovery.
ms.openlocfilehash: 5bd183f0f5f1c2f091fb374aab1e54f191665ce6
ms.sourcegitcommit: c43ebb915fa0eb7eb720b21b62c0d1e58e7cde3d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/30/2020
ms.locfileid: "44936262"
---
# <a name="quick-setup-advanced-ediscovery-classic"></a>Быстрая настройка Advanced eDiscovery (классическая версия)

> [!IMPORTANT]
> Продолжая инвестировать в разработку новых версий Advanced eDiscovery, мы сообщаем о прекращении поддержки версии Advanced eDiscovery, также известной как *Advanced eDiscovery (классическая версия)* или *Advanced eDiscovery 1.0*. Если вы все еще используете Advanced eDiscovery 1.0, перейдите на версию [Advanced eDiscovery 2.0](overview-ediscovery-20.md) (также известную как *решение Advanced eDiscovery в Microsoft 365*) как можно скорее. Advanced eDiscovery 2.0 имеет те же функции, что и Advanced eDiscovery 1.0, а также множество новых возможностей, таких как управление для хранителя, управление коммуникацией и наборы для проверки. Дополнительные сведения о прекращении поддержки Advanced eDiscovery 1.0 см. в статье [Прекращение поддержки средств прежних версий eDiscovery](legacy-ediscovery-retirement.md#advanced-ediscovery-v10). 

Этот раздел о настройках содержит сведения для менеджера обнаружения электронных данных в Центре безопасности и соответствия требованиям Microsoft 365 о том, как начать работу с Advanced eDiscovery. Предполагается, что есть общее представление об обеих службах.
  
## <a name="accessing-a-case-in-advanced-ediscovery"></a>Получение доступа к делу в Advanced eDiscovery

You access Advanced eDiscovery from the Security &amp; Compliance Center. You have to be a member of an eDiscovery case in the Security &amp; Compliance Center to access the case in Advanced eDiscovery. For instructions about assigning eDiscovery case permissions and adding users to an eDiscovery case, see [Manage eDiscovery cases in Office 365](ediscovery-cases.md). 
  
Чтобы перейти к делу в Advanced eDiscovery: 
  
1. [Откройте Центр безопасности и соответствия требованиям](go-to-the-securitycompliance-center.md). 
    
2. Чтобы отобразился список дел в организации, в Центре безопасности и соответствия требованиям выберите **Поиск и исследование** \> **Обнаружение электронных данных**. 
    
3. На странице **Обнаружение электронных данных** нажмите кнопку **Открыть** рядом с названием дела, к которому хотите перейти в Advanced eDiscovery.
    
4. На странице **Главная** для этого дела выберите **Перейти на Advanced eDiscovery**.
    
    The **Connecting to Advanced eDiscovery** progress bar is displayed. When you're connected, the case is opened in Advanced eDiscovery. 
    
## <a name="workflow"></a>Рабочий процесс

На приведенной ниже схеме показан типичный рабочий процесс для использования дел обнаружения электронных данных и управления ими в Центре безопасности и соответствия требованиям и Advanced eDiscovery.
  
![На схеме показан рабочий процесс Advanced eDiscovery, состоящий из четырех этапов (настройки пользователей и дел, определения данных дела, экспорта и обработки), а также этапов анализа и экспорта на локальный компьютер.](../media/76589ccc-789d-4581-b3a8-98d339b05979.png)
  
This setup section describes the first four steps in the workflow. For a description of the other steps in the workflow, see the following.
  
## <a name="analyze"></a>Анализ

[Analyzing case data](analyze-case-data-with-advanced-ediscovery.md) Identifies and organizes the files by various parameters, enables the use of Themes, and displays the results. Analyze functionality can be customized by the user in order to achieve enhanced results. 
  
## <a name="relevance-setup-and-relevance"></a>Настройка релевантности и модуль релевантности

[Relevance Setup](manage-relevance-setup-in-advanced-ediscovery.md) and [Using the Relevance module](use-relevance-in-advanced-ediscovery.md) Enables assessment and relevance training based on a random sample of files and uses them to apply decisions to the predictive coding process. Calculates and displays interim results while monitoring statistical validity of the process. Displays the results to facilitate in making review decisions. 
  
## <a name="export"></a>Экспорт

[Экспорт данных дела](export-case-data-in-advanced-ediscovery.md) обеспечивает экспорт результатов и содержимого Advanced eDiscovery для внешней проверки. 
  
## <a name="report"></a>Отчет

[Создание отчетов](run-reports-in-advanced-ediscovery.md) обеспечивает создание выбранных отчетов, связанных с обработкой Advanced eDiscovery. 
  
## <a name="see-also"></a>См. также

[Advanced eDiscovery (классическая версия)](office-365-advanced-ediscovery.md)
  
[Настройка пользователей и дел](set-up-users-and-cases-in-advanced-ediscovery.md)
  
[Подготовка данных](prepare-data-for-advanced-ediscovery.md)

