---
title: Быстрая настройка Advanced eDiscovery
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
localization_priority: Priority
search.appverid:
- MOE150
- MET150
ms.assetid: d7ccd944-9698-41c7-a21b-677dc62973c4
description: Сведения о том, как получать доступ к Advanced eDiscovery из Центра безопасности и соответствия требованиям и просматривать типичный рабочий процесс для использования Advanced eDiscovery.
ms.openlocfilehash: 9aca86d59b3f6b5f77ea5b6eb4c5d0bbe156beb1
ms.sourcegitcommit: 47de4402174c263ae8d70c910ca068a7581d04ae
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662854"
---
# <a name="quick-setup-advanced-ediscovery-classic"></a><span data-ttu-id="b4cf2-103">Быстрая настройка Advanced eDiscovery (классическая версия)</span><span class="sxs-lookup"><span data-stu-id="b4cf2-103">Quick setup Advanced eDiscovery (classic)</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b4cf2-104">Продолжая инвестировать в разработку новых версий Advanced eDiscovery, мы сообщаем о прекращении поддержки версии Advanced eDiscovery, также известной как *Advanced eDiscovery (классическая версия)* или *Advanced eDiscovery 1.0*.</span><span class="sxs-lookup"><span data-stu-id="b4cf2-104">As we continue to invest in newer versions of Advanced eDiscovery, we are announcing the retirement of Advanced eDiscovery, also known as *Advanced eDiscovery (classic)* or *Advanced eDiscovery v1.0*.</span></span> <span data-ttu-id="b4cf2-105">Если вы все еще используете Advanced eDiscovery 1.0, перейдите на версию [Advanced eDiscovery 2.0](overview-ediscovery-20.md) (также известную как *решение Advanced eDiscovery в Microsoft 365*) как можно скорее.</span><span class="sxs-lookup"><span data-stu-id="b4cf2-105">If you're still using Advanced eDiscovery v1.0, please transition to [Advanced eDiscovery v2.0](overview-ediscovery-20.md) (also known as the *Advanced eDiscovery solution in Microsoft 365*) as soon as possible.</span></span> <span data-ttu-id="b4cf2-106">Advanced eDiscovery 2.0 имеет те же функции, что и Advanced eDiscovery 1.0, а также множество новых возможностей, таких как управление для хранителя, управление коммуникацией и наборы для проверки.</span><span class="sxs-lookup"><span data-stu-id="b4cf2-106">Advanced eDiscovery 2.0 contains similar functionality found in Advanced eDiscovery v1.0, but also offers many new features such as custodian management, communications management, and review sets.</span></span> <span data-ttu-id="b4cf2-107">Дополнительные сведения о прекращении поддержки Advanced eDiscovery 1.0 см. в статье [Прекращение поддержки средств прежних версий eDiscovery](legacy-ediscovery-retirement.md#advanced-ediscovery-v10).</span><span class="sxs-lookup"><span data-stu-id="b4cf2-107">To learn more about the retirement of Advanced eDiscovery v1.0, see [Retirement of legacy eDiscovery tools](legacy-ediscovery-retirement.md#advanced-ediscovery-v10).</span></span> 

<span data-ttu-id="b4cf2-108">Этот раздел о настройках содержит сведения для менеджера обнаружения электронных данных в Центре безопасности и соответствия требованиям Microsoft 365 о том, как начать работу с Advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="b4cf2-108">This setup section shows an Microsoft 365 Security &amp; Compliance Center eDiscovery manager how to get started with Advanced eDiscovery.</span></span> <span data-ttu-id="b4cf2-109">Предполагается, что есть общее представление об обеих службах.</span><span class="sxs-lookup"><span data-stu-id="b4cf2-109">A working knowledge of both is assumed.</span></span>
  
## <a name="accessing-a-case-in-advanced-ediscovery"></a><span data-ttu-id="b4cf2-110">Получение доступа к делу в Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="b4cf2-110">Accessing a case in Advanced eDiscovery</span></span>

<span data-ttu-id="b4cf2-p103">Доступ к Advanced eDiscovery можно получить в Центре безопасности и соответствия требованиям Office 365. Но нужно быть участником дела обнаружения электронных данных в Центре безопасности и соответствия требованиям, чтобы получить доступ к этому делу в Advanced eDiscovery. Сведения о предоставлении разрешений в отношении дела обнаружения электронных данных и добавлении пользователей для такого дела см. в статье [Управление делами обнаружения электронных данных в Office 365](ediscovery-cases.md).</span><span class="sxs-lookup"><span data-stu-id="b4cf2-p103">You access Advanced eDiscovery from the Security &amp; Compliance Center. You have to be a member of an eDiscovery case in the Security &amp; Compliance Center to access the case in Advanced eDiscovery. For instructions about assigning eDiscovery case permissions and adding users to an eDiscovery case, see [Manage eDiscovery cases in Office 365](ediscovery-cases.md).</span></span> 
  
<span data-ttu-id="b4cf2-114">Чтобы перейти к делу в Advanced eDiscovery:</span><span class="sxs-lookup"><span data-stu-id="b4cf2-114">To go to a case in Advanced eDiscovery:</span></span> 
  
1. <span data-ttu-id="b4cf2-115">[Откройте Центр безопасности и соответствия требованиям](go-to-the-securitycompliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="b4cf2-115">[Go to the Security &amp; Compliance Center](go-to-the-securitycompliance-center.md) .</span></span> 
    
2. <span data-ttu-id="b4cf2-116">Чтобы отобразился список дел в организации, в Центре безопасности и соответствия требованиям выберите **Поиск и исследование** \> **Обнаружение электронных данных**.</span><span class="sxs-lookup"><span data-stu-id="b4cf2-116">In the Security &amp; Compliance Center, click **Search &amp; investigation** \> **eDiscovery** to display the list of cases in your organization.</span></span> 
    
3. <span data-ttu-id="b4cf2-117">На странице **Обнаружение электронных данных** нажмите кнопку **Открыть** рядом с названием дела, к которому хотите перейти в Advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="b4cf2-117">On the **eDiscovery** page, click **Open** next to the case that you want to go to in Advanced eDiscovery.</span></span>
    
4. <span data-ttu-id="b4cf2-118">На странице **Главная** для этого дела выберите **Перейти на Advanced eDiscovery**.</span><span class="sxs-lookup"><span data-stu-id="b4cf2-118">On the **Home** page for the case, click **Switch to Advanced eDiscovery**.</span></span>
    
    <span data-ttu-id="b4cf2-p104">Отобразится индикатор выполнения **Подключение к Advanced eDiscovery**. После подключения дело откроется в Advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="b4cf2-p104">The **Connecting to Advanced eDiscovery** progress bar is displayed. When you're connected, the case is opened in Advanced eDiscovery.</span></span> 
    
## <a name="workflow"></a><span data-ttu-id="b4cf2-121">Рабочий процесс</span><span class="sxs-lookup"><span data-stu-id="b4cf2-121">Workflow</span></span>

<span data-ttu-id="b4cf2-122">На приведенной ниже схеме показан типичный рабочий процесс для использования дел обнаружения электронных данных и управления ими в Центре безопасности и соответствия требованиям и Advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="b4cf2-122">The following diagram illustrates the common workflow for managing and using eDiscovery cases in the Security &amp; Compliance Center and Advanced eDiscovery.</span></span>
  
![На схеме показан рабочий процесс Advanced eDiscovery, состоящий из четырех этапов (настройки пользователей и дел, определения данных дела, экспорта и обработки), а также этапов анализа и экспорта на локальный компьютер.](../media/76589ccc-789d-4581-b3a8-98d339b05979.png)
  
<span data-ttu-id="b4cf2-p105">Этот раздел о настройках содержит сведения о первых четырех этапах рабочего процесса. Описание других этапов см. далее.</span><span class="sxs-lookup"><span data-stu-id="b4cf2-p105">This setup section describes the first four steps in the workflow. For a description of the other steps in the workflow, see the following.</span></span>
  
## <a name="analyze"></a><span data-ttu-id="b4cf2-126">Анализ</span><span class="sxs-lookup"><span data-stu-id="b4cf2-126">Analyze</span></span>

<span data-ttu-id="b4cf2-p106">[Анализ данных дела](analyze-case-data-with-advanced-ediscovery.md) идентифицирует и упорядочивает файлы по различным параметрам, обеспечивает использование категории "Темы", отображает результаты. Для получения улучшенных результатов можно настроить функциональность анализа с учетом пользователя.</span><span class="sxs-lookup"><span data-stu-id="b4cf2-p106">[Analyzing case data](analyze-case-data-with-advanced-ediscovery.md) Identifies and organizes the files by various parameters, enables the use of Themes, and displays the results. Analyze functionality can be customized by the user in order to achieve enhanced results.</span></span> 
  
## <a name="relevance-setup-and-relevance"></a><span data-ttu-id="b4cf2-129">Настройка релевантности и модуль релевантности</span><span class="sxs-lookup"><span data-stu-id="b4cf2-129">Relevance Setup and Relevance</span></span>

<span data-ttu-id="b4cf2-p107">[Настройка релевантности](manage-relevance-setup-in-advanced-ediscovery.md) и [Использование модуля релевантности](use-relevance-in-advanced-ediscovery.md) обеспечивают оценку и обучение релевантности на основе случайной выборки файлов и используют их для реализации решений в процессе прогнозирующего кодирования. Вычисляют и отображают промежуточные результаты, отслеживая статистическую достоверность процесса. Отображают результаты для помощи в принятии решений при просмотре.</span><span class="sxs-lookup"><span data-stu-id="b4cf2-p107">[Relevance Setup](manage-relevance-setup-in-advanced-ediscovery.md) and [Using the Relevance module](use-relevance-in-advanced-ediscovery.md) Enables assessment and relevance training based on a random sample of files and uses them to apply decisions to the predictive coding process. Calculates and displays interim results while monitoring statistical validity of the process. Displays the results to facilitate in making review decisions.</span></span> 
  
## <a name="export"></a><span data-ttu-id="b4cf2-133">Экспорт</span><span class="sxs-lookup"><span data-stu-id="b4cf2-133">Export</span></span>

<span data-ttu-id="b4cf2-134">[Экспорт данных дела](export-case-data-in-advanced-ediscovery.md) обеспечивает экспорт результатов и содержимого Advanced eDiscovery для внешней проверки.</span><span class="sxs-lookup"><span data-stu-id="b4cf2-134">[Exporting case data](export-case-data-in-advanced-ediscovery.md) Enables the exporting of Advanced eDiscovery content and results for external review.</span></span> 
  
## <a name="report"></a><span data-ttu-id="b4cf2-135">Отчет</span><span class="sxs-lookup"><span data-stu-id="b4cf2-135">Report</span></span>

<span data-ttu-id="b4cf2-136">[Создание отчетов](run-reports-in-advanced-ediscovery.md) обеспечивает создание выбранных отчетов, связанных с обработкой Advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="b4cf2-136">[Running reports](run-reports-in-advanced-ediscovery.md) Enables the generation of selected reports related to Advanced eDiscovery processing.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="b4cf2-137">См. также</span><span class="sxs-lookup"><span data-stu-id="b4cf2-137">See also</span></span>

[<span data-ttu-id="b4cf2-138">Advanced eDiscovery (классическая версия)</span><span class="sxs-lookup"><span data-stu-id="b4cf2-138">Advanced eDiscovery (classic)</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="b4cf2-139">Настройка пользователей и дел</span><span class="sxs-lookup"><span data-stu-id="b4cf2-139">Setting up users and cases</span></span>](set-up-users-and-cases-in-advanced-ediscovery.md)
  
[<span data-ttu-id="b4cf2-140">Подготовка данных</span><span class="sxs-lookup"><span data-stu-id="b4cf2-140">Preparing data</span></span>](prepare-data-for-advanced-ediscovery.md)

