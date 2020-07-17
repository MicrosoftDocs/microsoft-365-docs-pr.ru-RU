---
title: Определение выделенных ключевых слов и дополнительных параметров в Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
titleSuffix: Office 365
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 03cc4387-2c7d-4058-8a44-0deefb58f011
description: Узнайте, как добавлять определяемые пользователем ключевые слова в релевантность для определения релевантных файлов при разметке в расширенном режиме обнаружения электронных данных, а также для указания параметров затрат.
ms.openlocfilehash: 61ec74109f13d8056047e0aaf14aaa87c846e17f
ms.sourcegitcommit: c43ebb915fa0eb7eb720b21b62c0d1e58e7cde3d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/30/2020
ms.locfileid: "44936458"
---
# <a name="define-highlighted-keywords-and-advanced-options-in-advanced-ediscovery-classic"></a><span data-ttu-id="4703f-103">Определение выделенных ключевых слов и дополнительных параметров в Advanced eDiscovery (классический)</span><span class="sxs-lookup"><span data-stu-id="4703f-103">Define highlighted keywords and advanced options in Advanced eDiscovery (classic)</span></span>

> [!NOTE]
> <span data-ttu-id="4703f-p101">Чтобы можно было использовать Advanced eDiscovery, требуется подписка на Office 365 E3 с надстройкой Advanced Compliance или E5 для организации. Если у вас этого плана нет и вы хотите попробовать Advanced eDiscovery, можете [зарегистрироваться для получения пробной версии Office 365 корпоративный E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span><span class="sxs-lookup"><span data-stu-id="4703f-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="4703f-106">В Advanced eDiscovery можно добавлять определяемые пользователем ключевые слова в релевантность, чтобы помочь определить релевантные файлы при разметке тегами.</span><span class="sxs-lookup"><span data-stu-id="4703f-106">In Advanced eDiscovery, it's possible to add user-defined keywords to Relevance in order to help you identify relevant files while tagging.</span></span> <span data-ttu-id="4703f-107">Ключевые слова будут отображаться в заданных цветах **в \> теге релевантности**.</span><span class="sxs-lookup"><span data-stu-id="4703f-107">Keywords will be displayed in the specified colors in **Relevance \> Tag**.</span></span> 
  
<span data-ttu-id="4703f-108">Как описано ниже, можно добавлять списки ключевых слов, а также цвета, назначенные списку ключевых слов, и связанные с ними проблемы.</span><span class="sxs-lookup"><span data-stu-id="4703f-108">As described below, keyword lists can be added, and colors assigned to the Keywords list and the related issues.</span></span> <span data-ttu-id="4703f-109">Всплывающая подсказка отображает описание ключевого слова, если оно указано двойным подчеркиванием.</span><span class="sxs-lookup"><span data-stu-id="4703f-109">A tooltip displays the keyword's description, if one exists, as indicated by a double underline.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="4703f-110">Выделение совпадений по релевантности и просмотр результатов нажатия ключевых слов в документах во время тегирования соответствия не работает в наборах двухбайтовых символов, китайского и корейского иероглифов.</span><span class="sxs-lookup"><span data-stu-id="4703f-110">Hit highlighting in Relevance and viewing keyword hit results within documents during Relevance tagging does not work for the Japanese, Chinese, and Korean double-byte character sets.</span></span> 
  
## <a name="adding-highlighted-keywords"></a><span data-ttu-id="4703f-111">Добавление выделенных ключевых слов</span><span class="sxs-lookup"><span data-stu-id="4703f-111">Adding highlighted keywords</span></span>

1. <span data-ttu-id="4703f-112">На вкладке \*\* \> Настройка релевантности\*\* выберите **выделенные ключевые слова**.</span><span class="sxs-lookup"><span data-stu-id="4703f-112">In the **Relevance \> Relevance setup** tab, select **Highlighted keywords**.</span></span>
    
2. <span data-ttu-id="4703f-113">Щелкните **+** значок, чтобы добавить ключевые слова.</span><span class="sxs-lookup"><span data-stu-id="4703f-113">Click the **+** icon to add keywords.</span></span> <span data-ttu-id="4703f-114">Откроется диалоговое окно **Добавление новых ключевых слов** .</span><span class="sxs-lookup"><span data-stu-id="4703f-114">The **Add new keywords** dialog is displayed.</span></span> 
    
3. <span data-ttu-id="4703f-115">В разделе **Ключевые слова**введите список ключевые слова, разделяя ключевые слова запятыми.</span><span class="sxs-lookup"><span data-stu-id="4703f-115">In **Keywords**, type the keywords list, separating keywords with commas.</span></span> 
    
4. <span data-ttu-id="4703f-116">В списке **Цвет** выберите цвет, чтобы выделить введенный список ключевых слов.</span><span class="sxs-lookup"><span data-stu-id="4703f-116">In the **Color** list, select the color to highlight the entered keywords list.</span></span> 
    
5. <span data-ttu-id="4703f-117">В списке **Выбор проблемы** выберите, следует ли применить список ключевых слов к "всем проблемам" или к выбранным проблемам.</span><span class="sxs-lookup"><span data-stu-id="4703f-117">In the **Select issue** list, select whether to apply the keywords list to "All issues" or to selected issues.</span></span> 
    
6. <span data-ttu-id="4703f-118">В поле **Описание**введите список ключевых слов (необязательно).</span><span class="sxs-lookup"><span data-stu-id="4703f-118">In **Description**, type the keywords list (optional).</span></span>
    
    ![Добавление ключевых слов](../media/1683a71f-0875-48fc-b4ef-01f3b0e8e8e9.png)
  
7. <span data-ttu-id="4703f-120">По завершении нажмите кнопку **ОК** .</span><span class="sxs-lookup"><span data-stu-id="4703f-120">Click **OK** when done.</span></span> <span data-ttu-id="4703f-121">Созданный список добавляется в таблицу список ключевых слов и может быть изменен или удален.</span><span class="sxs-lookup"><span data-stu-id="4703f-121">The created list is added to the keywords list table and can be edited or deleted.</span></span> 
    
    ![Список ключевых слов на вкладке "Настройка релевантности"](../media/a05d5ec0-8bde-470d-97e2-456b169281d6.png)
  
<span data-ttu-id="4703f-123">Будут отображены заданные пользователем ключевые слова в заданных цветах в теге релевантности \> .</span><span class="sxs-lookup"><span data-stu-id="4703f-123">The user-defined keywords will be displayed, in the specified colors in Relevance \> Tag.</span></span> 
  
## <a name="specifying-relevance-setup-advanced-settings"></a><span data-ttu-id="4703f-124">Задание дополнительных параметров настройки релевантности</span><span class="sxs-lookup"><span data-stu-id="4703f-124">Specifying Relevance setup advanced settings</span></span>

<span data-ttu-id="4703f-125">Эти параметры влияют на отслеживание и выбор диаграмм по релевантности.</span><span class="sxs-lookup"><span data-stu-id="4703f-125">These settings affect the Track and Decide graphs in Relevance.</span></span>
  
1. <span data-ttu-id="4703f-126">На вкладке \*\* \> Настройка релевантности\*\* выберите **Дополнительные параметры**.</span><span class="sxs-lookup"><span data-stu-id="4703f-126">In the **Relevance \> Relevance setup** tab, select **Advanced settings**.</span></span>
    
2. <span data-ttu-id="4703f-127">В диалоговом окне **параметры стоимости** сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="4703f-127">In the **Cost parameters** dialog, make the following selections:</span></span> 
    
1. <span data-ttu-id="4703f-128">В списке **Оценка затрат в час ($)** выберите сумму в долларах или примите значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="4703f-128">In the **Cost review per hour ($)** list, select the amount in dollars or accept the default.</span></span> 
    
2. <span data-ttu-id="4703f-129">В списке **количество файлов, просмотренных по часам** выберите значение или примите значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="4703f-129">In the **Number of files reviewed by hour** list, select the amount or accept the default.</span></span> 
    
    ![Параметры для указания затрат на вкладке "Настройка релевантности"](../media/bab7b5b7-6297-4e7c-b0a6-ba5aa8b21787.png)
  
3. <span data-ttu-id="4703f-131">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="4703f-131">Click **Save**.</span></span> <span data-ttu-id="4703f-132">Выбранные параметры будут сохранены.</span><span class="sxs-lookup"><span data-stu-id="4703f-132">The selected settings are saved.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="4703f-133">См. также</span><span class="sxs-lookup"><span data-stu-id="4703f-133">See also</span></span>

[<span data-ttu-id="4703f-134">Advanced eDiscovery (классическая версия)</span><span class="sxs-lookup"><span data-stu-id="4703f-134">Advanced eDiscovery (classic)</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="4703f-135">Определение вопросов и назначение пользователей</span><span class="sxs-lookup"><span data-stu-id="4703f-135">Defining issues and assigning users</span></span>](define-issues-and-assign-users.md)
  
[<span data-ttu-id="4703f-136">Настройка полных пакетов для добавления импортированных файлов</span><span class="sxs-lookup"><span data-stu-id="4703f-136">Setting up loads to add imported files</span></span>](set-up-loads-to-add-imported-files.md)

