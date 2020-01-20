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
ms.openlocfilehash: ab80de0e1be3a164da8414ef3791fb9717bcc190
ms.sourcegitcommit: 48a45b0d2c60d4d79669174f462603a43f272875
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/18/2020
ms.locfileid: "41233700"
---
# <a name="view-activity-on-your-labeled-content-preview"></a><span data-ttu-id="44677-103">Просмотр действий над содержимым с метками (предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="44677-103">View activity on your labeled content (preview)</span></span>

<span data-ttu-id="44677-104">Вкладки "Обзор классификации данных" и "Обозреватель содержимого" позволяют просматривать обнаруженное содержимое с метками, а также его расположение.</span><span class="sxs-lookup"><span data-stu-id="44677-104">The data classification overview and content explorer tabs give you visibility into what content has been discovered and labeled, and where that content is.</span></span> <span data-ttu-id="44677-105">Обозреватель действий обобщает набор функций, позволяя отслеживать действия над содержимым с метками.</span><span class="sxs-lookup"><span data-stu-id="44677-105">Activity explorer rounds out this suite of functionality by allowing you to monitor what's being done with your labeled content.</span></span> <span data-ttu-id="44677-106">В обозревателе действий доступно представление журнала.</span><span class="sxs-lookup"><span data-stu-id="44677-106">Activity explorer provides a historical view.</span></span>

![снимок экрана: обзор обозревателя действий](media/data-classification-activity-explorer-1.png)

<span data-ttu-id="44677-108">Вы можете фильтровать данные по следующим параметрам:</span><span class="sxs-lookup"><span data-stu-id="44677-108">You can filter the data by:</span></span>

- <span data-ttu-id="44677-109">диапазон дат;</span><span class="sxs-lookup"><span data-stu-id="44677-109">date range</span></span>
- <span data-ttu-id="44677-110">тип действия;</span><span class="sxs-lookup"><span data-stu-id="44677-110">activity type</span></span>
- <span data-ttu-id="44677-111">расположение;</span><span class="sxs-lookup"><span data-stu-id="44677-111">location</span></span>
- <span data-ttu-id="44677-112">пользователь;</span><span class="sxs-lookup"><span data-stu-id="44677-112">user</span></span>
- <span data-ttu-id="44677-113">метка конфиденциальности;</span><span class="sxs-lookup"><span data-stu-id="44677-113">sensitivity label</span></span>
- <span data-ttu-id="44677-114">метка хранения;</span><span class="sxs-lookup"><span data-stu-id="44677-114">retention label</span></span>


<span data-ttu-id="44677-115">Вы можете просматривать данные в виде списка или гистограммы.</span><span class="sxs-lookup"><span data-stu-id="44677-115">You can view the data either as a list or a bar graph.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="44677-116">Необходимые компоненты</span><span class="sxs-lookup"><span data-stu-id="44677-116">Prerequisites</span></span>

<span data-ttu-id="44677-117">Каждой учетной записи, которая обращается к обозревателю действий и использует его, должна быть назначена лицензия одной из следующих подписок:</span><span class="sxs-lookup"><span data-stu-id="44677-117">Every account that accesses and uses activity explorer must have a license assigned to it from one of these subscriptions:</span></span>

- <span data-ttu-id="44677-118">Microsoft 365 (E5)</span><span class="sxs-lookup"><span data-stu-id="44677-118">Microsoft 365 E5</span></span>
- <span data-ttu-id="44677-119">Office 365 (E5)</span><span class="sxs-lookup"><span data-stu-id="44677-119">Office 365 E5</span></span>
- <span data-ttu-id="44677-120">Дополнение Advanced Compliance (E5)</span><span class="sxs-lookup"><span data-stu-id="44677-120">Advanced Compliance (E5) add-on</span></span>
- <span data-ttu-id="44677-121">Дополнение Advanced Threat Intelligence (E5)</span><span class="sxs-lookup"><span data-stu-id="44677-121">Advanced Threat Intelligence (E5) add-on</span></span>
- <span data-ttu-id="44677-122">Дополнение Advanced Threat Protection (E5)</span><span class="sxs-lookup"><span data-stu-id="44677-122">Advanced Threat Protection (E5) add-on</span></span>

## <a name="activity-type"></a><span data-ttu-id="44677-123">Тип действия</span><span class="sxs-lookup"><span data-stu-id="44677-123">Activity type</span></span>

<span data-ttu-id="44677-124">В Microsoft 365 отслеживаются и составляются отчеты для 12 типов действий в SharePoint Online, OneDrive и конечных точках.</span><span class="sxs-lookup"><span data-stu-id="44677-124">Microsoft 365 monitors and reports on 12 types of activities across SharePoint Online, OneDrive and endpoints.</span></span> <span data-ttu-id="44677-125">Конечные точки — это пользовательские устройства под управлением Windows 10.</span><span class="sxs-lookup"><span data-stu-id="44677-125">Endpoints are user devices running Windows 10.</span></span>

- <span data-ttu-id="44677-126">Файл создан</span><span class="sxs-lookup"><span data-stu-id="44677-126">File created</span></span>
- <span data-ttu-id="44677-127">Файл изменен</span><span class="sxs-lookup"><span data-stu-id="44677-127">File modified</span></span>
- <span data-ttu-id="44677-128">Файл переименован</span><span class="sxs-lookup"><span data-stu-id="44677-128">File renamed</span></span>
- <span data-ttu-id="44677-129">Файл скопирован в облако</span><span class="sxs-lookup"><span data-stu-id="44677-129">File copied to cloud</span></span>
- <span data-ttu-id="44677-130">К файлу получен доступ неразрешенным приложением</span><span class="sxs-lookup"><span data-stu-id="44677-130">File accessed by unallowed app</span></span>
- <span data-ttu-id="44677-131">Файл распечатан</span><span class="sxs-lookup"><span data-stu-id="44677-131">File printed</span></span>
- <span data-ttu-id="44677-132">Файл скопирован на съемный носитель</span><span class="sxs-lookup"><span data-stu-id="44677-132">File copied to removable media</span></span>
- <span data-ttu-id="44677-133">Файл скопирован в общую сетевую папку</span><span class="sxs-lookup"><span data-stu-id="44677-133">File copied to network share</span></span>
- <span data-ttu-id="44677-134">Файл прочитан</span><span class="sxs-lookup"><span data-stu-id="44677-134">File read</span></span>
- <span data-ttu-id="44677-135">Файл скопирован в буфер обмена</span><span class="sxs-lookup"><span data-stu-id="44677-135">file copied to clipboard</span></span>
- <span data-ttu-id="44677-136">Метка применена</span><span class="sxs-lookup"><span data-stu-id="44677-136">Label applied</span></span>
- <span data-ttu-id="44677-137">Метка изменена (обновление, возврат к предыдущей или удаление)</span><span class="sxs-lookup"><span data-stu-id="44677-137">Label changed (upgraded, downgraded, or removed)</span></span>

<span data-ttu-id="44677-138">Ценность понимания того, какие действия выполняются над содержимым с меткой конфиденциальности состоит в том, что вы можете увидеть, эффективны ли примененные элементы управления, например [политики защиты от потери данных](data-loss-prevention-policies.md).</span><span class="sxs-lookup"><span data-stu-id="44677-138">The value of understanding what actions are being taken with your sensitive labeled content is that you can see if the controls that you have already put into place, such as [data loss prevention policies](data-loss-prevention-policies.md) are effective or not.</span></span> <span data-ttu-id="44677-139">В противном случае или при выявлении чего-то неожиданного, например большого числа элементов, метка которых изменена с `highly confidential` на `general`, вы можете управлять различными политиками и выполнять новые действия, чтобы ограничить нежелательное поведение.</span><span class="sxs-lookup"><span data-stu-id="44677-139">If not, or if you discover something unexpected, such as a large number of items that are labeled `highly confidential` and are downgraded `general`, you can manage your various policies and take new actions to restrict the undesired behavior.</span></span>

<span data-ttu-id="44677-140">После настройки фильтров вы можете:</span><span class="sxs-lookup"><span data-stu-id="44677-140">Once your filters are set, you can:</span></span>

- <span data-ttu-id="44677-141">навести указатель мыши на сегмент линейчатой диаграммы, чтобы увидеть число элементов, входящих в эту категорию; ![наведение указателя в обозревателе действий](media/data-classification-activity-explorer-hover-over-2.png)</span><span class="sxs-lookup"><span data-stu-id="44677-141">hover over a segment of the bar chart to see the number of items that fall into that category ![activity explorer hover over](media/data-classification-activity-explorer-hover-over-2.png)</span></span>
- <span data-ttu-id="44677-142">экспортировать данные;</span><span class="sxs-lookup"><span data-stu-id="44677-142">export the data</span></span>
- <span data-ttu-id="44677-143">выбрать любой элемент из списка и просмотреть сведения о действии во всплывающем окне.</span><span class="sxs-lookup"><span data-stu-id="44677-143">select any given item from the list and view the details of the action in the fly-out</span></span>

![всплывающее окно со сведениями в обозревателе действий](media/data-classification-activity-explorer-fly-out-3.png)

## <a name="see-also"></a><span data-ttu-id="44677-145">См. также</span><span class="sxs-lookup"><span data-stu-id="44677-145">See also</span></span>
- [<span data-ttu-id="44677-146">Метки конфиденциальности</span><span class="sxs-lookup"><span data-stu-id="44677-146">Sensitivity labels</span></span>](sensitivity-labels.md)
- [<span data-ttu-id="44677-147">Метки хранения</span><span class="sxs-lookup"><span data-stu-id="44677-147">Retention labels</span></span>](labels.md)
- [<span data-ttu-id="44677-148">Что позволяют искать типы конфиденциальной информации</span><span class="sxs-lookup"><span data-stu-id="44677-148">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)
- [<span data-ttu-id="44677-149">Обзор политик хранения</span><span class="sxs-lookup"><span data-stu-id="44677-149">Overview of retention policies</span></span>](retention-policies.md)