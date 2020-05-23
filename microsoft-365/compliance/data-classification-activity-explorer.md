---
title: Начало работы с обозревателем действий
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
ms.openlocfilehash: 5cb6a8dbfa570b3b0e0d1ce39648d12050d2af81
ms.sourcegitcommit: f6840dfcfdbcadc53cda591fd6cf9ddcb749d303
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2020
ms.locfileid: "44327845"
---
# <a name="get-started-with-activity-explorer"></a><span data-ttu-id="cc1ee-103">Начало работы с обозревателем действий</span><span class="sxs-lookup"><span data-stu-id="cc1ee-103">Get started with activity explorer</span></span>

<span data-ttu-id="cc1ee-104">Вкладки "Обзор классификации данных" и "Обозреватель содержимого" позволяют просматривать обнаруженное содержимое с метками, а также его расположение.</span><span class="sxs-lookup"><span data-stu-id="cc1ee-104">The data classification overview and content explorer tabs give you visibility into what content has been discovered and labeled, and where that content is.</span></span> <span data-ttu-id="cc1ee-105">Обозреватель действий обобщает набор функций, позволяя отслеживать действия над содержимым с метками.</span><span class="sxs-lookup"><span data-stu-id="cc1ee-105">Activity explorer rounds out this suite of functionality by allowing you to monitor what's being done with your labeled content.</span></span> <span data-ttu-id="cc1ee-106">В обозревателе действий доступно представление журнала.</span><span class="sxs-lookup"><span data-stu-id="cc1ee-106">Activity explorer provides a historical view.</span></span>

![снимок экрана: обзор обозревателя действий](../media/data-classification-activity-explorer-1.png)

<span data-ttu-id="cc1ee-108">Поддерживается свыше 30 фильтров, доступных для использования, включая следующие:</span><span class="sxs-lookup"><span data-stu-id="cc1ee-108">There are over 30 different filters available for use, some are:</span></span>

- <span data-ttu-id="cc1ee-109">диапазон дат;</span><span class="sxs-lookup"><span data-stu-id="cc1ee-109">date range</span></span>
- <span data-ttu-id="cc1ee-110">тип действия;</span><span class="sxs-lookup"><span data-stu-id="cc1ee-110">activity type</span></span>
- <span data-ttu-id="cc1ee-111">расположение;</span><span class="sxs-lookup"><span data-stu-id="cc1ee-111">location</span></span>
- <span data-ttu-id="cc1ee-112">пользователь;</span><span class="sxs-lookup"><span data-stu-id="cc1ee-112">user</span></span>
- <span data-ttu-id="cc1ee-113">метка конфиденциальности;</span><span class="sxs-lookup"><span data-stu-id="cc1ee-113">sensitivity label</span></span>
- <span data-ttu-id="cc1ee-114">метка хранения;</span><span class="sxs-lookup"><span data-stu-id="cc1ee-114">retention label</span></span>
- <span data-ttu-id="cc1ee-115">путь к файлу</span><span class="sxs-lookup"><span data-stu-id="cc1ee-115">file path</span></span>
- <span data-ttu-id="cc1ee-116">Политика защиты от потери данных</span><span class="sxs-lookup"><span data-stu-id="cc1ee-116">DLP policy</span></span>


## <a name="prerequisites"></a><span data-ttu-id="cc1ee-117">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="cc1ee-117">Prerequisites</span></span>

<span data-ttu-id="cc1ee-118">Каждой учетной записи, которая осуществляет доступ и использует классификацию данных, необходимо назначить лицензию из одной из следующих подписок:</span><span class="sxs-lookup"><span data-stu-id="cc1ee-118">Every account that accesses and uses data classification must have a license assigned to it from one of these subscriptions:</span></span>

- <span data-ttu-id="cc1ee-119">Microsoft 365 (E5)</span><span class="sxs-lookup"><span data-stu-id="cc1ee-119">Microsoft 365 (E5)</span></span>
- <span data-ttu-id="cc1ee-120">Office 365 (E5)</span><span class="sxs-lookup"><span data-stu-id="cc1ee-120">Office 365 (E5)</span></span>
- <span data-ttu-id="cc1ee-121">Дополнение Advanced Compliance (E5)</span><span class="sxs-lookup"><span data-stu-id="cc1ee-121">Advanced Compliance (E5) add-on</span></span>
- <span data-ttu-id="cc1ee-122">Дополнение Advanced Threat Intelligence (E5)</span><span class="sxs-lookup"><span data-stu-id="cc1ee-122">Advanced Threat Intelligence (E5) add-on</span></span>

### <a name="permissions"></a><span data-ttu-id="cc1ee-123">Разрешения</span><span class="sxs-lookup"><span data-stu-id="cc1ee-123">Permissions</span></span>

 <span data-ttu-id="cc1ee-124">Чтобы получить доступ к вкладке обозревателя действий, учетной записи необходимо назначить участие в одной из следующих ролей или групп ролей.</span><span class="sxs-lookup"><span data-stu-id="cc1ee-124">In order to get access to the activity explorer tab, an account must be assigned membership in any one of these roles or role groups.</span></span>

<span data-ttu-id="cc1ee-125">**Группы ролей Microsoft 365**</span><span class="sxs-lookup"><span data-stu-id="cc1ee-125">**Microsoft 365 role groups**</span></span>

- <span data-ttu-id="cc1ee-126">Глобальный администратор</span><span class="sxs-lookup"><span data-stu-id="cc1ee-126">Global administrator</span></span>
- <span data-ttu-id="cc1ee-127">Администратор соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="cc1ee-127">Compliance administrator</span></span>
- <span data-ttu-id="cc1ee-128">Администратор безопасности</span><span class="sxs-lookup"><span data-stu-id="cc1ee-128">Security administrator</span></span>
- <span data-ttu-id="cc1ee-129">Администратор данных соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="cc1ee-129">Compliance data administrator</span></span>

## <a name="activity-type"></a><span data-ttu-id="cc1ee-130">Тип действия</span><span class="sxs-lookup"><span data-stu-id="cc1ee-130">Activity type</span></span>

<span data-ttu-id="cc1ee-131">Система Microsoft 365 отслеживает различные типы действий в SharePoint Online и OneDrive и создает отчеты для них. В число отслеживаемых типов действий входят следующие:</span><span class="sxs-lookup"><span data-stu-id="cc1ee-131">Microsoft 365 monitors and reports on types of activities across SharePoint Online, and OneDrive like:</span></span>

- <span data-ttu-id="cc1ee-132">применение метки</span><span class="sxs-lookup"><span data-stu-id="cc1ee-132">label applied</span></span>
- <span data-ttu-id="cc1ee-133">изменение метки (обновление, возврат к прежней, удаление)</span><span class="sxs-lookup"><span data-stu-id="cc1ee-133">label changed (upgraded, downgraded, or removed)</span></span>
- <span data-ttu-id="cc1ee-134">моделирование автоматического применения метки</span><span class="sxs-lookup"><span data-stu-id="cc1ee-134">auto-labeling simulation</span></span>

<span data-ttu-id="cc1ee-135">Ценность понимания того, какие действия выполняются над содержимым с меткой конфиденциальности состоит в том, что вы можете увидеть, эффективны ли примененные элементы управления, например [политики защиты от потери данных](data-loss-prevention-policies.md).</span><span class="sxs-lookup"><span data-stu-id="cc1ee-135">The value of understanding what actions are being taken with your sensitive labeled content is that you can see if the controls that you have already put into place, such as [data loss prevention policies](data-loss-prevention-policies.md) are effective or not.</span></span> <span data-ttu-id="cc1ee-136">В противном случае или при выявлении чего-то неожиданного, например большого числа элементов, метка которых изменена с `highly confidential` на `general`, вы можете управлять различными политиками и выполнять новые действия, чтобы ограничить нежелательное поведение.</span><span class="sxs-lookup"><span data-stu-id="cc1ee-136">If not, or if you discover something unexpected, such as a large number of items that are labeled `highly confidential` and are downgraded `general`, you can manage your various policies and take new actions to restrict the undesired behavior.</span></span>

> [!NOTE]
> <span data-ttu-id="cc1ee-137">Обозреватель действий в настоящее время не отслеживает действия по удержанию данных в Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="cc1ee-137">Activity explorer doesn't currently monitor retention activities for Exchange Online.</span></span>

## <a name="see-also"></a><span data-ttu-id="cc1ee-138">См. также</span><span class="sxs-lookup"><span data-stu-id="cc1ee-138">See also</span></span>
- [<span data-ttu-id="cc1ee-139">Метки конфиденциальности</span><span class="sxs-lookup"><span data-stu-id="cc1ee-139">Sensitivity labels</span></span>](sensitivity-labels.md)
- [<span data-ttu-id="cc1ee-140">Метки хранения</span><span class="sxs-lookup"><span data-stu-id="cc1ee-140">Retention labels</span></span>](labels.md)
- [<span data-ttu-id="cc1ee-141">Определения объектов типов конфиденциальной информации</span><span class="sxs-lookup"><span data-stu-id="cc1ee-141">Sensitive information type entity definitions</span></span>](sensitive-information-type-entity-definitions.md)
- [<span data-ttu-id="cc1ee-142">Обзор политик хранения</span><span class="sxs-lookup"><span data-stu-id="cc1ee-142">Overview of retention policies</span></span>](retention-policies.md)
