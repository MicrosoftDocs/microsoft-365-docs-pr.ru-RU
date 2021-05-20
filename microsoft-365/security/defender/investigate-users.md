---
title: Расследование пользователей в Microsoft 365 Defender
description: Расследование пользователей инцидента в центре Microsoft 365 безопасности.
keywords: безопасность, вредоносные программы, Microsoft 365, M365, центр безопасности, монитор, отчет, удостоверения личности, данные, устройства, приложения, инциденты, анализ, ответ
ms.prod: m365-security
ms.mktglfcycl: deploy
localization_priority: Normal
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: dansimp
ms.date: ''
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
search.appverid: met150
ms.custom: seo-marvel-jun2020
ms.technology: m365d
ms.openlocfilehash: 72eb111da2f342b78aa6161c7334a7252314b4a5
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572805"
---
# <a name="investigate-users-in-microsoft-365-defender"></a><span data-ttu-id="6ac2d-104">Расследование пользователей в Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6ac2d-104">Investigate users in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="6ac2d-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="6ac2d-105">**Applies to:**</span></span>

- <span data-ttu-id="6ac2d-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6ac2d-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="6ac2d-107">Часть расследования инцидентов может включать учетные записи пользователей.</span><span class="sxs-lookup"><span data-stu-id="6ac2d-107">Part of your incident investigation can include user accounts.</span></span> <span data-ttu-id="6ac2d-108">Начните с **вкладки** Пользователи для инцидента из **инцидентов & оповещения >** *инциденте* **> пользователей.**</span><span class="sxs-lookup"><span data-stu-id="6ac2d-108">Start with the **Users** tab for an incident from **Incidents & alerts >** *incident* **> Users**.</span></span> 

:::image type="content" source="../../media/investigate-incidents/incident-users.png" alt-text="Пример страницы пользователей для инцидента":::

<span data-ttu-id="6ac2d-110">Чтобы получить краткое резюме учетной записи пользователя для инцидента, выберите контрольную отметку рядом с именем учетной записи пользователя.</span><span class="sxs-lookup"><span data-stu-id="6ac2d-110">To get a quick summary of a user account for the incident, select the check mark next to the user account name.</span></span> <span data-ttu-id="6ac2d-111">Ниже приведен пример.</span><span class="sxs-lookup"><span data-stu-id="6ac2d-111">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-users/incidents-ss-user-pane.png" alt-text="Пример сводки учетной записи пользователя для инцидента в центре Microsoft 365 безопасности":::

> [!NOTE]
> <span data-ttu-id="6ac2d-113">На странице пользователя показана Azure Active Directory (Azure AD), а также группы, помогающие вам понять группы и разрешения, связанные с пользователем.</span><span class="sxs-lookup"><span data-stu-id="6ac2d-113">The User page shows Azure Active Directory (Azure AD) organization as well as groups, helping you understand the groups and permissions associated with a user.</span></span>

<span data-ttu-id="6ac2d-114">На этой странице можно просмотреть информацию об угрозах пользователей, включая любые текущие инциденты, активные оповещения и уровень риска, а также экспозицию пользователей, учетные записи, устройства и многое другое.</span><span class="sxs-lookup"><span data-stu-id="6ac2d-114">In this fly-out page, you can review user threat information, including any current incidents, active alerts, and risk level as well as user exposure, accounts, devices, and more.</span></span>

<span data-ttu-id="6ac2d-115">Кроме того, вы можете принять меры непосредственно в центре безопасности Microsoft 365 для решения проблемы скомпрометированного пользователя, подтвердив, что пользователь скомпрометирован, или требуя от них снова войти в систему.</span><span class="sxs-lookup"><span data-stu-id="6ac2d-115">In addition, you can take action directly in the Microsoft 365 security center to address a compromised user, confirming the user is compromised or requiring them to sign in again.</span></span>

<span data-ttu-id="6ac2d-116">Здесь вы можете выбрать Перейти на **страницу пользователя, чтобы** увидеть детали учетной записи пользователя.</span><span class="sxs-lookup"><span data-stu-id="6ac2d-116">From here, you can select **Go to user page** to see the details of a user account.</span></span> <span data-ttu-id="6ac2d-117">Ниже приведен пример.</span><span class="sxs-lookup"><span data-stu-id="6ac2d-117">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-users/incidents-ss-user-details.png" alt-text="Пример страницы учетной записи пользователя для инцидента в центре Microsoft 365 безопасности":::

<span data-ttu-id="6ac2d-119">Вы также можете увидеть эту страницу, выбрав имя учетной записи пользователя из списка на странице **пользователей.**</span><span class="sxs-lookup"><span data-stu-id="6ac2d-119">You can also see this page by selecting the name of the user account from the list on the **Users** page.</span></span>

<span data-ttu-id="6ac2d-120">Страница Microsoft 365 безопасности объединяет информацию от Microsoft Defender for Endpoint, Microsoft Defender for Identity и Microsoft Cloud App Security (в зависимости от того, какие лицензии у вас есть).</span><span class="sxs-lookup"><span data-stu-id="6ac2d-120">The Microsoft 365 security center user page combines information from Microsoft Defender for Endpoint, Microsoft Defender for Identity, and Microsoft Cloud App Security (depending on what licenses you have).</span></span> 

<span data-ttu-id="6ac2d-121">На этой странице показана информация, специфичная для безопасности учетной записи пользователя.</span><span class="sxs-lookup"><span data-stu-id="6ac2d-121">This page shows information specific to the security risk of a user account.</span></span> <span data-ttu-id="6ac2d-122">Это включает в себя оценку, которая помогает оценить риск и последние события и оповещения, которые способствовали общему риску пользователя.</span><span class="sxs-lookup"><span data-stu-id="6ac2d-122">This includes a score that helps assess risk and recent events and alerts that contributed to the overall risk of the user.</span></span>

<span data-ttu-id="6ac2d-123">На этой странице вы можете вы сделать эти дополнительные действия:</span><span class="sxs-lookup"><span data-stu-id="6ac2d-123">From this page, you can do these additional actions:</span></span> 

- <span data-ttu-id="6ac2d-124">Отметь учетную запись пользователя как скомпрометированную</span><span class="sxs-lookup"><span data-stu-id="6ac2d-124">Mark the user account as compromised</span></span>
- <span data-ttu-id="6ac2d-125">Требовать от пользователя снова войти в</span><span class="sxs-lookup"><span data-stu-id="6ac2d-125">Require the user to sign in again</span></span>
- <span data-ttu-id="6ac2d-126">Приостановить учетную запись пользователя</span><span class="sxs-lookup"><span data-stu-id="6ac2d-126">Suspend the user account</span></span>
- <span data-ttu-id="6ac2d-127">Посмотреть Azure Active Directory учетной записи пользователя (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="6ac2d-127">See the Azure Active Directory (Azure AD) user account settings</span></span>
- <span data-ttu-id="6ac2d-128">Просмотр файлов, принадлежащих учетной записи пользователя</span><span class="sxs-lookup"><span data-stu-id="6ac2d-128">View the files owned by the user account</span></span>
- <span data-ttu-id="6ac2d-129">Просмотр файлов, совместно с этим пользователем.</span><span class="sxs-lookup"><span data-stu-id="6ac2d-129">View files shared with this user.</span></span> 

<span data-ttu-id="6ac2d-130">Ниже приведен пример.</span><span class="sxs-lookup"><span data-stu-id="6ac2d-130">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-users/incidents-ss-user-details-actions.png" alt-text="Пример действий в учетной записи пользователя для инцидента в центре Microsoft 365 безопасности":::


<!--
You can access this page from multiple areas in the Microsoft 365 security center. You can access this page from a specific incident in the **Users** tab. Some alerts might include users as a specific affected asset. You can also search for users.  

Learn more about how to investigate users and potential risk [in this Cloud App Security tutorial](/cloud-app-security/tutorial-ueba#:~:text=To%20identify%20who%20your%20riskiest,user%20page%20to%20investigate%20them).

--> 

## <a name="next-steps"></a><span data-ttu-id="6ac2d-132">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="6ac2d-132">Next steps</span></span>

<span data-ttu-id="6ac2d-133">По мере необходимости для инцидентов в процессе, продолжить [расследование](investigate-incidents.md).</span><span class="sxs-lookup"><span data-stu-id="6ac2d-133">As needed for in-process incidents, continue your [investigation](investigate-incidents.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="6ac2d-134">См. также</span><span class="sxs-lookup"><span data-stu-id="6ac2d-134">See also</span></span>

- [<span data-ttu-id="6ac2d-135">Обзор инцидентов</span><span class="sxs-lookup"><span data-stu-id="6ac2d-135">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="6ac2d-136">Управление приоритетом инцидентов</span><span class="sxs-lookup"><span data-stu-id="6ac2d-136">Prioritize incidents</span></span>](incident-queue.md)
- [<span data-ttu-id="6ac2d-137">Управление инцидентами</span><span class="sxs-lookup"><span data-stu-id="6ac2d-137">Manage incidents</span></span>](manage-incidents.md)