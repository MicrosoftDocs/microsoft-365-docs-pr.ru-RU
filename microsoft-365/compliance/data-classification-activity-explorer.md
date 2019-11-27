---
title: Использование обозревателя действий по классификации данных
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Обозреватель действий обобщает функции компонента классификации данных, позволяя просматривать и фильтровать действия, выполняемые пользователями над содержимым с метками.
ms.openlocfilehash: 272de0400e89f9829b3ead5d4523db27789c0c44
ms.sourcegitcommit: 9d0a025ea9e265d515a034de0102eabcf47d11f5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2019
ms.locfileid: "39268981"
---
# <a name="view-activity-on-your-labeled-content-preview"></a><span data-ttu-id="dab7d-103">Просмотр действий над содержимым с метками (предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="dab7d-103">View activity on your labeled content (preview)</span></span>

<span data-ttu-id="dab7d-104">Вкладки "Обзор классификации данных" и "Обозреватель содержимого" позволяют просматривать обнаруженное содержимое с метками, а также его расположение.</span><span class="sxs-lookup"><span data-stu-id="dab7d-104">The data classification overview and content explorer tabs give you visibility into what content has been discovered and labeled, and where that content is.</span></span> <span data-ttu-id="dab7d-105">Обозреватель действий обобщает набор функций, позволяя отслеживать действия над содержимым с метками.</span><span class="sxs-lookup"><span data-stu-id="dab7d-105">Activity explorer rounds out this suite of functionality by allowing you to monitor what's being done with your labeled content.</span></span> <span data-ttu-id="dab7d-106">В обозревателе действий доступно представление журнала.</span><span class="sxs-lookup"><span data-stu-id="dab7d-106">Activity explorer provides a historical view.</span></span>

![снимок экрана: обзор обозревателя действий](media/data-classification-activity-explorer-1.png)

<span data-ttu-id="dab7d-108">Вы можете фильтровать данные по следующим параметрам:</span><span class="sxs-lookup"><span data-stu-id="dab7d-108">You can filter the data by:</span></span>

- <span data-ttu-id="dab7d-109">диапазон дат;</span><span class="sxs-lookup"><span data-stu-id="dab7d-109">Date range</span></span>
- <span data-ttu-id="dab7d-110">тип действия;</span><span class="sxs-lookup"><span data-stu-id="dab7d-110">Activity type</span></span>
- <span data-ttu-id="dab7d-111">расположение;</span><span class="sxs-lookup"><span data-stu-id="dab7d-111">location</span></span>
- <span data-ttu-id="dab7d-112">пользователь;</span><span class="sxs-lookup"><span data-stu-id="dab7d-112">user</span></span>
- <span data-ttu-id="dab7d-113">метка конфиденциальности;</span><span class="sxs-lookup"><span data-stu-id="dab7d-113">For sensitivity label usage:</span></span>
- <span data-ttu-id="dab7d-114">метка хранения;</span><span class="sxs-lookup"><span data-stu-id="dab7d-114">Retention Label</span></span>


<span data-ttu-id="dab7d-115">Вы можете просматривать данные в виде списка или гистограммы.</span><span class="sxs-lookup"><span data-stu-id="dab7d-115">You can view the data either as a list or a bar graph.</span></span>

## <a name="activity-type"></a><span data-ttu-id="dab7d-116">Тип действия</span><span class="sxs-lookup"><span data-stu-id="dab7d-116">Activity type</span></span>

<span data-ttu-id="dab7d-117">В Microsoft 365 отслеживаются и составляются отчеты для 12 типов действий в SharePoint Online, OneDrive и конечных точках.</span><span class="sxs-lookup"><span data-stu-id="dab7d-117">Microsoft 365 monitors and reports on 12 types of activities across SharePoint Online, OneDrive and endpoints.</span></span> <span data-ttu-id="dab7d-118">Конечные точки — это пользовательские устройства под управлением Windows 10.</span><span class="sxs-lookup"><span data-stu-id="dab7d-118">Endpoints are user devices running Windows 10.</span></span>

- <span data-ttu-id="dab7d-119">Файл создан</span><span class="sxs-lookup"><span data-stu-id="dab7d-119">File is created</span></span>
- <span data-ttu-id="dab7d-120">Файл изменен</span><span class="sxs-lookup"><span data-stu-id="dab7d-120">File Modified</span></span>
- <span data-ttu-id="dab7d-121">Файл переименован</span><span class="sxs-lookup"><span data-stu-id="dab7d-121">File renamed</span></span>
- <span data-ttu-id="dab7d-122">Файл скопирован в облако</span><span class="sxs-lookup"><span data-stu-id="dab7d-122">File copied to cloud</span></span>
- <span data-ttu-id="dab7d-123">К файлу получен доступ неразрешенным приложением</span><span class="sxs-lookup"><span data-stu-id="dab7d-123">File accessed by unallowed app</span></span>
- <span data-ttu-id="dab7d-124">Файл распечатан</span><span class="sxs-lookup"><span data-stu-id="dab7d-124">File printed</span></span>
- <span data-ttu-id="dab7d-125">Файл скопирован на съемный носитель</span><span class="sxs-lookup"><span data-stu-id="dab7d-125">File copied to removable media</span></span>
- <span data-ttu-id="dab7d-126">Файл скопирован в общую сетевую папку</span><span class="sxs-lookup"><span data-stu-id="dab7d-126">File copied to network share</span></span>
- <span data-ttu-id="dab7d-127">Файл прочитан</span><span class="sxs-lookup"><span data-stu-id="dab7d-127">File read</span></span>
- <span data-ttu-id="dab7d-128">Файл скопирован в буфер обмена</span><span class="sxs-lookup"><span data-stu-id="dab7d-128">file copied to clipboard</span></span>
- <span data-ttu-id="dab7d-129">Метка применена</span><span class="sxs-lookup"><span data-stu-id="dab7d-129">Label protection is applied</span></span>
- <span data-ttu-id="dab7d-130">Метка изменена (обновление, возврат к предыдущей или удаление)</span><span class="sxs-lookup"><span data-stu-id="dab7d-130">Label changed (upgraded, downgraded, or removed)</span></span>

<span data-ttu-id="dab7d-131">Ценность понимания того, какие действия выполняются над содержимым с меткой конфиденциальности состоит в том, что вы можете увидеть, эффективны ли примененные элементы управления, например [политики защиты от потери данных](data-loss-prevention-policies.md).</span><span class="sxs-lookup"><span data-stu-id="dab7d-131">The value of understanding what actions are being taken with your sensitive labeled content is that you can see if the controls that you have already put into place, such as [data loss prevention policies](data-loss-prevention-policies.md) are effective or not.</span></span> <span data-ttu-id="dab7d-132">В противном случае или при выявлении чего-то неожиданного, например большого числа элементов, метка которых изменена с `highly confidential` на `general`, вы можете управлять различными политиками и выполнять новые действия, чтобы ограничить нежелательное поведение.</span><span class="sxs-lookup"><span data-stu-id="dab7d-132">If not, or if you discover something unexpected, such as a large number of items that are labeled `highly confidential` and are downgraded `general`, you can manage your various policies and take new actions to restrict the undesired behavior.</span></span>

<span data-ttu-id="dab7d-133">После настройки фильтров вы можете:</span><span class="sxs-lookup"><span data-stu-id="dab7d-133">Once your filters are set, you can:</span></span>

- <span data-ttu-id="dab7d-134">навести указатель мыши на сегмент линейчатой диаграммы, чтобы увидеть число элементов, входящих в эту категорию; ![наведение указателя в обозревателе действий](media/data-classification-activity-explorer-hover-over-2.png)</span><span class="sxs-lookup"><span data-stu-id="dab7d-134">hover over a segment of the bar chart to see the number of items that fall into that category ![activity explorer hover over](media/data-classification-activity-explorer-hover-over-2.png)</span></span>
- <span data-ttu-id="dab7d-135">экспортировать данные;</span><span class="sxs-lookup"><span data-stu-id="dab7d-135">export the data</span></span>
- <span data-ttu-id="dab7d-136">выбрать любой элемент из списка и просмотреть сведения о действии во всплывающем окне.</span><span class="sxs-lookup"><span data-stu-id="dab7d-136">select any given item from the list and view the details of the action in the fly-out</span></span>

![всплывающее окно со сведениями в обозревателе действий](media/data-classification-activity-explorer-fly-out-3.png)

## <a name="see-also"></a><span data-ttu-id="dab7d-138">См. также</span><span class="sxs-lookup"><span data-stu-id="dab7d-138">See also</span></span>
- [<span data-ttu-id="dab7d-139">Метки конфиденциальности</span><span class="sxs-lookup"><span data-stu-id="dab7d-139">Sensitivity labels</span></span>](sensitivity-labels.md)
- [<span data-ttu-id="dab7d-140">Метки хранения</span><span class="sxs-lookup"><span data-stu-id="dab7d-140">Retention labels</span></span>](labels.md)
- [<span data-ttu-id="dab7d-141">Что позволяют искать типы конфиденциальной информации</span><span class="sxs-lookup"><span data-stu-id="dab7d-141">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)
- [<span data-ttu-id="dab7d-142">Обзор политик хранения</span><span class="sxs-lookup"><span data-stu-id="dab7d-142">Overview of retention policies</span></span>](retention-policies.md)