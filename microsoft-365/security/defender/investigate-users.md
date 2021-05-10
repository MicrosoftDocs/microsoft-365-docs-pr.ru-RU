---
title: Исследование пользователей в Центре безопасности Microsoft 365
description: Исследование пользователей в центре Microsoft 365 безопасности
keywords: безопасность, вредоносные программы, Microsoft 365, M365, центр безопасности, монитор, отчет, удостоверения, данные, устройства, приложения, инциденты, анализ, ответ
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
ms.openlocfilehash: c03e4d5bd94eb6105ffab91c6dad2b74d7159dde
ms.sourcegitcommit: de5fce90de22ba588e75e1a1d2e87e03b9e25ec7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/10/2021
ms.locfileid: "52300065"
---
# <a name="investigate-users-in-microsoft-365-security-center"></a><span data-ttu-id="0c80a-104">Исследование пользователей в Центре безопасности Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="0c80a-104">Investigate users in Microsoft 365 security center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="0c80a-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="0c80a-105">**Applies to:**</span></span>

- <span data-ttu-id="0c80a-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0c80a-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="0c80a-107">Часть расследования инцидента может включать учетные записи пользователей.</span><span class="sxs-lookup"><span data-stu-id="0c80a-107">Part of your incident investigation can include user accounts.</span></span> <span data-ttu-id="0c80a-108">Начните со вкладки **"Пользователи"** об инциденте из & оповещений о > *>* **пользователи**.</span><span class="sxs-lookup"><span data-stu-id="0c80a-108">Start with the **Users** tab for an incident from **Incidents & alerts >** *incident* **> Users**.</span></span> 

:::image type="content" source="../../media/investigate-incidents/incident-users.png" alt-text="Пример страницы &quot;Пользователи&quot; для инцидента":::

<span data-ttu-id="0c80a-110">Чтобы получить краткое описание учетной записи пользователя для инцидента, выберите контрольный знак рядом с именем учетной записи пользователя.</span><span class="sxs-lookup"><span data-stu-id="0c80a-110">To get a quick summary of a user account for the incident, select the check mark next to the user account name.</span></span> <span data-ttu-id="0c80a-111">Ниже приведен пример.</span><span class="sxs-lookup"><span data-stu-id="0c80a-111">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-users/incidents-ss-user-pane.png" alt-text="Пример сводки учетной записи пользователя для инцидента в центре Microsoft 365 безопасности":::

> [!NOTE]
> <span data-ttu-id="0c80a-113">На странице Пользователя Azure Active Directory организации и группы, помогающие понять группы и разрешения, связанные с пользователем.</span><span class="sxs-lookup"><span data-stu-id="0c80a-113">The User page shows Azure Active Directory (AD) organization as well as groups, helping you understand the groups and permissions associated with a user.</span></span>

<span data-ttu-id="0c80a-114">На этой странице вылетов вы можете просмотреть сведения об угрозах пользователей, включая текущие инциденты, активные оповещения и уровень риска, а также экспозицию пользователей, учетные записи, устройства и т. д.</span><span class="sxs-lookup"><span data-stu-id="0c80a-114">In this fly-out page, you can review user threat information, including any current incidents, active alerts, and risk level as well as user exposure, accounts, devices, and more.</span></span>

<span data-ttu-id="0c80a-115">Кроме того, вы можете принять меры непосредственно в центре Microsoft 365 безопасности, чтобы обратиться к скомпрометированного пользователя, подтвердив, что пользователь скомпрометирован или требует от него снова войти.</span><span class="sxs-lookup"><span data-stu-id="0c80a-115">In addition, you can take action directly in the Microsoft 365 security center to address a compromised user, confirming the user is compromised or requiring them to sign in again.</span></span>

<span data-ttu-id="0c80a-116">Здесь вы можете выбрать **страницу Перейти на страницу пользователя,** чтобы узнать подробности учетной записи пользователя.</span><span class="sxs-lookup"><span data-stu-id="0c80a-116">From here, you can select **Go to user page** to see the details of a user account.</span></span> <span data-ttu-id="0c80a-117">Ниже приведен пример.</span><span class="sxs-lookup"><span data-stu-id="0c80a-117">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-users/incidents-ss-user-details.png" alt-text="Пример страницы учетной записи пользователя для инцидента в центре Microsoft 365 безопасности":::

<span data-ttu-id="0c80a-119">Вы также можете увидеть эту страницу, выбрав имя учетной записи пользователя из списка на странице **Пользователи.**</span><span class="sxs-lookup"><span data-stu-id="0c80a-119">You can also see this page by selecting the name of the user account from the list on the **Users** page.</span></span>

<span data-ttu-id="0c80a-120">Страница Microsoft 365 центра безопасности объединяет сведения из Microsoft Defender for Endpoint, Microsoft Defender for Identity и Microsoft Cloud App Security (в зависимости от лицензий).</span><span class="sxs-lookup"><span data-stu-id="0c80a-120">The Microsoft 365 security center user page combines information from Microsoft Defender for Endpoint, Microsoft Defender for Identity, and Microsoft Cloud App Security (depending on what licenses you have).</span></span> 

<span data-ttu-id="0c80a-121">На этой странице показаны сведения, определенные для риска безопасности учетной записи пользователя.</span><span class="sxs-lookup"><span data-stu-id="0c80a-121">This page shows information specific to the security risk of a user account.</span></span> <span data-ttu-id="0c80a-122">Это включает оценку, которая помогает оценить риски и недавние события и оповещения, которые способствовали общему риску пользователя.</span><span class="sxs-lookup"><span data-stu-id="0c80a-122">This includes a score that helps assess risk and recent events and alerts that contributed to the overall risk of the user.</span></span>

<span data-ttu-id="0c80a-123">На этой странице можно сделать дополнительные действия:</span><span class="sxs-lookup"><span data-stu-id="0c80a-123">From this page, you can do these additional actions:</span></span> 

- <span data-ttu-id="0c80a-124">Пометить учетную запись пользователя как скомпрометированную</span><span class="sxs-lookup"><span data-stu-id="0c80a-124">Mark the user account as compromised</span></span>
- <span data-ttu-id="0c80a-125">Требовать от пользователя снова войти</span><span class="sxs-lookup"><span data-stu-id="0c80a-125">Require the user to sign in again</span></span>
- <span data-ttu-id="0c80a-126">Приостановка учетной записи пользователя</span><span class="sxs-lookup"><span data-stu-id="0c80a-126">Suspend the user account</span></span>
- <span data-ttu-id="0c80a-127">См. Azure Active Directory параметров учетной записи пользователя Azure AD</span><span class="sxs-lookup"><span data-stu-id="0c80a-127">See the Azure Active Directory (Azure AD) user account settings</span></span>
- <span data-ttu-id="0c80a-128">Просмотр файлов, которые принадлежат учетной записи пользователя</span><span class="sxs-lookup"><span data-stu-id="0c80a-128">View the files owned by the user account</span></span>
- <span data-ttu-id="0c80a-129">Просмотр файлов, общих этому пользователю.</span><span class="sxs-lookup"><span data-stu-id="0c80a-129">View files shared with this user.</span></span> 

<span data-ttu-id="0c80a-130">Ниже приведен пример.</span><span class="sxs-lookup"><span data-stu-id="0c80a-130">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-users/incidents-ss-user-details-actions.png" alt-text="Пример действий учетной записи пользователя для инцидента в центре Microsoft 365 безопасности":::


<!--
You can access this page from multiple areas in the Microsoft 365 security center. You can access this page from a specific incident in the **Users** tab. Some alerts might include users as a specific affected asset. You can also search for users.  

Learn more about how to investigate users and potential risk [in this Cloud App Security tutorial](/cloud-app-security/tutorial-ueba#:~:text=To%20identify%20who%20your%20riskiest,user%20page%20to%20investigate%20them).

--> 

## <a name="next-steps"></a><span data-ttu-id="0c80a-132">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="0c80a-132">Next steps</span></span>

<span data-ttu-id="0c80a-133">По мере необходимости для инцидентов в процессе продолжайте [расследование.](investigate-incidents.md)</span><span class="sxs-lookup"><span data-stu-id="0c80a-133">As needed for in-process incidents, continue your [investigation](investigate-incidents.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="0c80a-134">См. также</span><span class="sxs-lookup"><span data-stu-id="0c80a-134">See also</span></span>

- [<span data-ttu-id="0c80a-135">Обзор инцидентов</span><span class="sxs-lookup"><span data-stu-id="0c80a-135">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="0c80a-136">Управление приоритетом инцидентов</span><span class="sxs-lookup"><span data-stu-id="0c80a-136">Prioritize incidents</span></span>](incident-queue.md)
- [<span data-ttu-id="0c80a-137">Управление инцидентами</span><span class="sxs-lookup"><span data-stu-id="0c80a-137">Manage incidents</span></span>](manage-incidents.md)