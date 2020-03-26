---
title: Начало работы с обозревателем действий (предварительная версия)
f1.keywords:
- NOCSH
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
ms.openlocfilehash: 68304bc75d33c993db52895828ec49e3b5203a4c
ms.sourcegitcommit: 3b2fdf159d7dd962493a3838e3cf0cf429ee2bf2
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "42929463"
---
# <a name="get-started-with-activity-explorer-preview"></a><span data-ttu-id="50b0b-103">Начало работы с обозревателем действий (предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="50b0b-103">Get started with activity explorer (preview)</span></span>

<span data-ttu-id="50b0b-104">Вкладки "Обзор классификации данных" и "Обозреватель содержимого" позволяют просматривать обнаруженное содержимое с метками, а также его расположение.</span><span class="sxs-lookup"><span data-stu-id="50b0b-104">The data classification overview and content explorer tabs give you visibility into what content has been discovered and labeled, and where that content is.</span></span> <span data-ttu-id="50b0b-105">Обозреватель действий обобщает набор функций, позволяя отслеживать действия над содержимым с метками.</span><span class="sxs-lookup"><span data-stu-id="50b0b-105">Activity explorer rounds out this suite of functionality by allowing you to monitor what's being done with your labeled content.</span></span> <span data-ttu-id="50b0b-106">В обозревателе действий доступно представление журнала.</span><span class="sxs-lookup"><span data-stu-id="50b0b-106">Activity explorer provides a historical view.</span></span>

![снимок экрана: обзор обозревателя действий](../media/data-classification-activity-explorer-1.png)

<span data-ttu-id="50b0b-108">Вы можете фильтровать данные по следующим параметрам:</span><span class="sxs-lookup"><span data-stu-id="50b0b-108">You can filter the data by:</span></span>

- <span data-ttu-id="50b0b-109">диапазон дат;</span><span class="sxs-lookup"><span data-stu-id="50b0b-109">date range</span></span>
- <span data-ttu-id="50b0b-110">тип действия;</span><span class="sxs-lookup"><span data-stu-id="50b0b-110">activity type</span></span>
- <span data-ttu-id="50b0b-111">расположение;</span><span class="sxs-lookup"><span data-stu-id="50b0b-111">location</span></span>
- <span data-ttu-id="50b0b-112">пользователь;</span><span class="sxs-lookup"><span data-stu-id="50b0b-112">user</span></span>
- <span data-ttu-id="50b0b-113">метка конфиденциальности;</span><span class="sxs-lookup"><span data-stu-id="50b0b-113">sensitivity label</span></span>
- <span data-ttu-id="50b0b-114">метка хранения;</span><span class="sxs-lookup"><span data-stu-id="50b0b-114">retention label</span></span>


<span data-ttu-id="50b0b-115">Вы можете просматривать данные в виде списка или гистограммы.</span><span class="sxs-lookup"><span data-stu-id="50b0b-115">You can view the data either as a list or a bar graph.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="50b0b-116">Необходимые компоненты</span><span class="sxs-lookup"><span data-stu-id="50b0b-116">Prerequisites</span></span>

<span data-ttu-id="50b0b-117">Каждой учетной записи, которая обращается к обозревателю действий и использует его, должна быть назначена лицензия одной из следующих подписок:</span><span class="sxs-lookup"><span data-stu-id="50b0b-117">Every account that accesses and uses activity explorer must have a license assigned to it from one of these subscriptions:</span></span>

- <span data-ttu-id="50b0b-118">Microsoft 365 (E5)</span><span class="sxs-lookup"><span data-stu-id="50b0b-118">Microsoft 365 (E5)</span></span>
- <span data-ttu-id="50b0b-119">Office 365 (E5)</span><span class="sxs-lookup"><span data-stu-id="50b0b-119">Office 365 (E5)</span></span>
- <span data-ttu-id="50b0b-120">Дополнение Advanced Compliance (E5)</span><span class="sxs-lookup"><span data-stu-id="50b0b-120">Advanced Compliance (E5) add-on</span></span>
- <span data-ttu-id="50b0b-121">Дополнение Advanced Threat Intelligence (E5)</span><span class="sxs-lookup"><span data-stu-id="50b0b-121">Advanced Threat Intelligence (E5) add-on</span></span>

## <a name="activity-type"></a><span data-ttu-id="50b0b-122">Тип действия</span><span class="sxs-lookup"><span data-stu-id="50b0b-122">Activity type</span></span>

<span data-ttu-id="50b0b-123">В Microsoft 365 отслеживаются и составляются отчеты для 12 типов действий в SharePoint Online, OneDrive и конечных точках.</span><span class="sxs-lookup"><span data-stu-id="50b0b-123">Microsoft 365 monitors and reports on 12 types of activities across SharePoint Online, OneDrive and endpoints.</span></span> <span data-ttu-id="50b0b-124">Конечные точки — это пользовательские устройства под управлением Windows 10.</span><span class="sxs-lookup"><span data-stu-id="50b0b-124">Endpoints are user devices running Windows 10.</span></span>

- <span data-ttu-id="50b0b-125">Файл создан</span><span class="sxs-lookup"><span data-stu-id="50b0b-125">File created</span></span>
- <span data-ttu-id="50b0b-126">Файл изменен</span><span class="sxs-lookup"><span data-stu-id="50b0b-126">File modified</span></span>
- <span data-ttu-id="50b0b-127">Файл переименован</span><span class="sxs-lookup"><span data-stu-id="50b0b-127">File renamed</span></span>
- <span data-ttu-id="50b0b-128">Файл скопирован в облако</span><span class="sxs-lookup"><span data-stu-id="50b0b-128">File copied to cloud</span></span>
- <span data-ttu-id="50b0b-129">К файлу получен доступ неразрешенным приложением</span><span class="sxs-lookup"><span data-stu-id="50b0b-129">File accessed by unallowed app</span></span>
- <span data-ttu-id="50b0b-130">Файл распечатан</span><span class="sxs-lookup"><span data-stu-id="50b0b-130">File printed</span></span>
- <span data-ttu-id="50b0b-131">Файл скопирован на съемный носитель</span><span class="sxs-lookup"><span data-stu-id="50b0b-131">File copied to removable media</span></span>
- <span data-ttu-id="50b0b-132">Файл скопирован в общую сетевую папку</span><span class="sxs-lookup"><span data-stu-id="50b0b-132">File copied to network share</span></span>
- <span data-ttu-id="50b0b-133">Файл прочитан</span><span class="sxs-lookup"><span data-stu-id="50b0b-133">File read</span></span>
- <span data-ttu-id="50b0b-134">Файл скопирован в буфер обмена</span><span class="sxs-lookup"><span data-stu-id="50b0b-134">file copied to clipboard</span></span>
- <span data-ttu-id="50b0b-135">Метка применена</span><span class="sxs-lookup"><span data-stu-id="50b0b-135">Label applied</span></span>
- <span data-ttu-id="50b0b-136">Метка изменена (обновление, возврат к предыдущей или удаление)</span><span class="sxs-lookup"><span data-stu-id="50b0b-136">Label changed (upgraded, downgraded, or removed)</span></span>

<span data-ttu-id="50b0b-137">Ценность понимания того, какие действия выполняются над содержимым с меткой конфиденциальности состоит в том, что вы можете увидеть, эффективны ли примененные элементы управления, например [политики защиты от потери данных](data-loss-prevention-policies.md).</span><span class="sxs-lookup"><span data-stu-id="50b0b-137">The value of understanding what actions are being taken with your sensitive labeled content is that you can see if the controls that you have already put into place, such as [data loss prevention policies](data-loss-prevention-policies.md) are effective or not.</span></span> <span data-ttu-id="50b0b-138">В противном случае или при выявлении чего-то неожиданного, например большого числа элементов, метка которых изменена с `highly confidential` на `general`, вы можете управлять различными политиками и выполнять новые действия, чтобы ограничить нежелательное поведение.</span><span class="sxs-lookup"><span data-stu-id="50b0b-138">If not, or if you discover something unexpected, such as a large number of items that are labeled `highly confidential` and are downgraded `general`, you can manage your various policies and take new actions to restrict the undesired behavior.</span></span>

<span data-ttu-id="50b0b-139">После настройки фильтров вы можете:</span><span class="sxs-lookup"><span data-stu-id="50b0b-139">Once your filters are set, you can:</span></span>

- <span data-ttu-id="50b0b-140">навести указатель мыши на сегмент линейчатой диаграммы, чтобы увидеть число элементов, входящих в эту категорию; ![наведение указателя в обозревателе действий](../media/data-classification-activity-explorer-hover-over-2.png)</span><span class="sxs-lookup"><span data-stu-id="50b0b-140">hover over a segment of the bar chart to see the number of items that fall into that category ![activity explorer hover over](../media/data-classification-activity-explorer-hover-over-2.png)</span></span>
- <span data-ttu-id="50b0b-141">экспортировать данные;</span><span class="sxs-lookup"><span data-stu-id="50b0b-141">export the data</span></span>
- <span data-ttu-id="50b0b-142">выбрать любой элемент из списка и просмотреть сведения о действии во всплывающем окне.</span><span class="sxs-lookup"><span data-stu-id="50b0b-142">select any given item from the list and view the details of the action in the fly-out</span></span>

![всплывающее окно со сведениями в обозревателе действий](../media/data-classification-activity-explorer-fly-out-3.png)

## <a name="see-also"></a><span data-ttu-id="50b0b-144">См. также</span><span class="sxs-lookup"><span data-stu-id="50b0b-144">See also</span></span>
- [<span data-ttu-id="50b0b-145">Метки конфиденциальности</span><span class="sxs-lookup"><span data-stu-id="50b0b-145">Sensitivity labels</span></span>](sensitivity-labels.md)
- [<span data-ttu-id="50b0b-146">Метки хранения</span><span class="sxs-lookup"><span data-stu-id="50b0b-146">Retention labels</span></span>](labels.md)
- [<span data-ttu-id="50b0b-147">Что позволяют искать типы конфиденциальной информации</span><span class="sxs-lookup"><span data-stu-id="50b0b-147">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)
- [<span data-ttu-id="50b0b-148">Обзор политик хранения</span><span class="sxs-lookup"><span data-stu-id="50b0b-148">Overview of retention policies</span></span>](retention-policies.md)
