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
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
description: Обозреватель действий обобщает функции компонента классификации данных, позволяя просматривать и фильтровать действия, выполняемые пользователями над содержимым с метками.
ms.openlocfilehash: 6825c00373617011db28fa484f272086f887ea40
ms.sourcegitcommit: 7ecd10b302b3b3dfa4ba3be3a6986dd3c189fbff
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/21/2021
ms.locfileid: "49921637"
---
# <a name="get-started-with-activity-explorer"></a><span data-ttu-id="5db2e-103">Начало работы с обозревателем действий</span><span class="sxs-lookup"><span data-stu-id="5db2e-103">Get started with activity explorer</span></span>

<span data-ttu-id="5db2e-104">Вкладки "Обзор классификации данных" и "Обозреватель содержимого" позволяют просматривать обнаруженное содержимое с метками, а также его расположение.</span><span class="sxs-lookup"><span data-stu-id="5db2e-104">The data classification overview and content explorer tabs give you visibility into what content has been discovered and labeled, and where that content is.</span></span> <span data-ttu-id="5db2e-105">Обозреватель действий обобщает набор функций, позволяя отслеживать действия над содержимым с метками.</span><span class="sxs-lookup"><span data-stu-id="5db2e-105">Activity explorer rounds out this suite of functionality by allowing you to monitor what's being done with your labeled content.</span></span> <span data-ttu-id="5db2e-106">В обозревателе действий доступно представление журнала.</span><span class="sxs-lookup"><span data-stu-id="5db2e-106">Activity explorer provides a historical view.</span></span>

![снимок экрана: обзор обозревателя действий](../media/data-classification-activity-explorer-1.png)

<span data-ttu-id="5db2e-108">Поддерживается свыше 30 фильтров, доступных для использования, включая следующие:</span><span class="sxs-lookup"><span data-stu-id="5db2e-108">There are over 30 different filters available for use, some are:</span></span>

- <span data-ttu-id="5db2e-109">диапазон дат;</span><span class="sxs-lookup"><span data-stu-id="5db2e-109">date range</span></span>
- <span data-ttu-id="5db2e-110">тип действия;</span><span class="sxs-lookup"><span data-stu-id="5db2e-110">activity type</span></span>
- <span data-ttu-id="5db2e-111">расположение;</span><span class="sxs-lookup"><span data-stu-id="5db2e-111">location</span></span>
- <span data-ttu-id="5db2e-112">пользователь;</span><span class="sxs-lookup"><span data-stu-id="5db2e-112">user</span></span>
- <span data-ttu-id="5db2e-113">метка конфиденциальности;</span><span class="sxs-lookup"><span data-stu-id="5db2e-113">sensitivity label</span></span>
- <span data-ttu-id="5db2e-114">метка хранения;</span><span class="sxs-lookup"><span data-stu-id="5db2e-114">retention label</span></span>
- <span data-ttu-id="5db2e-115">путь к файлу</span><span class="sxs-lookup"><span data-stu-id="5db2e-115">file path</span></span>
- <span data-ttu-id="5db2e-116">Политика защиты от потери данных</span><span class="sxs-lookup"><span data-stu-id="5db2e-116">DLP policy</span></span>


## <a name="prerequisites"></a><span data-ttu-id="5db2e-117">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="5db2e-117">Prerequisites</span></span>

<span data-ttu-id="5db2e-118">Каждой учетной записи, которая осуществляет доступ и использует классификацию данных, необходимо назначить лицензию из одной из следующих подписок:</span><span class="sxs-lookup"><span data-stu-id="5db2e-118">Every account that accesses and uses data classification must have a license assigned to it from one of these subscriptions:</span></span>

- <span data-ttu-id="5db2e-119">Microsoft 365 (E5)</span><span class="sxs-lookup"><span data-stu-id="5db2e-119">Microsoft 365 (E5)</span></span>
- <span data-ttu-id="5db2e-120">Office 365 (E5)</span><span class="sxs-lookup"><span data-stu-id="5db2e-120">Office 365 (E5)</span></span>
- <span data-ttu-id="5db2e-121">Дополнение Advanced Compliance (E5)</span><span class="sxs-lookup"><span data-stu-id="5db2e-121">Advanced Compliance (E5) add-on</span></span>
- <span data-ttu-id="5db2e-122">Дополнение Advanced Threat Intelligence (E5)</span><span class="sxs-lookup"><span data-stu-id="5db2e-122">Advanced Threat Intelligence (E5) add-on</span></span>
- <span data-ttu-id="5db2e-123">Защита информации и управление данными в Microsoft 365 E5 или A5</span><span class="sxs-lookup"><span data-stu-id="5db2e-123">Microsoft 365 E5/A5 Info Protection & Governance</span></span>
- <span data-ttu-id="5db2e-124">Соответствие требованиям Microsoft 365 E5 или A5</span><span class="sxs-lookup"><span data-stu-id="5db2e-124">Microsoft 365 E5/A5 Compliance</span></span>

### <a name="permissions"></a><span data-ttu-id="5db2e-125">Разрешения</span><span class="sxs-lookup"><span data-stu-id="5db2e-125">Permissions</span></span>

 <span data-ttu-id="5db2e-126">Чтобы получить доступ к вкладке обозревателя действий, учетной записи необходимо назначить участие в одной из следующих ролей или групп ролей.</span><span class="sxs-lookup"><span data-stu-id="5db2e-126">In order to get access to the activity explorer tab, an account must be assigned membership in any one of these roles or role groups.</span></span>

<span data-ttu-id="5db2e-127">**Группы ролей Microsoft 365**</span><span class="sxs-lookup"><span data-stu-id="5db2e-127">**Microsoft 365 role groups**</span></span>

- <span data-ttu-id="5db2e-128">Глобальный администратор</span><span class="sxs-lookup"><span data-stu-id="5db2e-128">Global administrator</span></span>
- <span data-ttu-id="5db2e-129">Администратор соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="5db2e-129">Compliance administrator</span></span>
- <span data-ttu-id="5db2e-130">Администратор безопасности</span><span class="sxs-lookup"><span data-stu-id="5db2e-130">Security administrator</span></span>
- <span data-ttu-id="5db2e-131">Администратор данных соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="5db2e-131">Compliance data administrator</span></span>

## <a name="activity-type"></a><span data-ttu-id="5db2e-132">Тип действия</span><span class="sxs-lookup"><span data-stu-id="5db2e-132">Activity type</span></span>

<span data-ttu-id="5db2e-133">Система Microsoft 365 отслеживает различные типы действий в SharePoint Online и OneDrive и создает отчеты для них. В число отслеживаемых типов действий входят следующие:</span><span class="sxs-lookup"><span data-stu-id="5db2e-133">Microsoft 365 monitors and reports on types of activities across SharePoint Online, and OneDrive like:</span></span>

- <span data-ttu-id="5db2e-134">применение метки</span><span class="sxs-lookup"><span data-stu-id="5db2e-134">label applied</span></span>
- <span data-ttu-id="5db2e-135">изменение метки (обновление, возврат к прежней, удаление)</span><span class="sxs-lookup"><span data-stu-id="5db2e-135">label changed (upgraded, downgraded, or removed)</span></span>
- <span data-ttu-id="5db2e-136">моделирование автоматического применения метки</span><span class="sxs-lookup"><span data-stu-id="5db2e-136">auto-labeling simulation</span></span>

<span data-ttu-id="5db2e-137">Ценность понимания того, какие действия выполняются над содержимым с меткой конфиденциальности состоит в том, что вы можете увидеть, эффективны ли примененные элементы управления, например [политики защиты от потери данных](data-loss-prevention-policies.md).</span><span class="sxs-lookup"><span data-stu-id="5db2e-137">The value of understanding what actions are being taken with your sensitive labeled content is that you can see if the controls that you have already put into place, such as [data loss prevention policies](data-loss-prevention-policies.md) are effective or not.</span></span> <span data-ttu-id="5db2e-138">В противном случае или при выявлении чего-то неожиданного, например большого числа элементов, метка которых изменена с `highly confidential` на `general`, вы можете управлять различными политиками и выполнять новые действия, чтобы ограничить нежелательное поведение.</span><span class="sxs-lookup"><span data-stu-id="5db2e-138">If not, or if you discover something unexpected, such as a large number of items that are labeled `highly confidential` and are downgraded `general`, you can manage your various policies and take new actions to restrict the undesired behavior.</span></span>

> [!NOTE]
> <span data-ttu-id="5db2e-139">Обозреватель действий в настоящее время не отслеживает действия по удержанию данных в Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="5db2e-139">Activity explorer doesn't currently monitor retention activities for Exchange Online.</span></span>

## <a name="see-also"></a><span data-ttu-id="5db2e-140">См. также</span><span class="sxs-lookup"><span data-stu-id="5db2e-140">See also</span></span>
- [<span data-ttu-id="5db2e-141">Сведения о метках конфиденциальности</span><span class="sxs-lookup"><span data-stu-id="5db2e-141">Learn about sensitivity labels</span></span>](sensitivity-labels.md)
- [<span data-ttu-id="5db2e-142">Сведения о политиках и метках хранения</span><span class="sxs-lookup"><span data-stu-id="5db2e-142">Learn about retention policies and retention labels</span></span>](retention.md)
- [<span data-ttu-id="5db2e-143">Определения объектов типов конфиденциальной информации</span><span class="sxs-lookup"><span data-stu-id="5db2e-143">Sensitive information type entity definitions</span></span>](sensitive-information-type-entity-definitions.md)

