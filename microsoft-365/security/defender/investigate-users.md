---
title: Анализ пользователей в центре безопасности Microsoft 365
description: Анализ пользователей в центре безопасности Microsoft 365
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
ms.openlocfilehash: 2fd9b958cdbdaf22346f8171c789f2ca9a8336d1
ms.sourcegitcommit: b6763a8ab240fbdd56078a7c9452445d0c4b9545
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2021
ms.locfileid: "51957611"
---
# <a name="analyze-users-in-microsoft-365-security-center"></a><span data-ttu-id="d58f3-104">Анализ пользователей в центре безопасности Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="d58f3-104">Analyze users in Microsoft 365 security center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="d58f3-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="d58f3-105">**Applies to:**</span></span>

- <span data-ttu-id="d58f3-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d58f3-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="d58f3-107">Часть анализа инцидентов может включать учетные записи пользователей.</span><span class="sxs-lookup"><span data-stu-id="d58f3-107">Part of your incident analysis can include user accounts.</span></span> <span data-ttu-id="d58f3-108">Начните со вкладки **"Пользователи"** об инциденте из & оповещений о > *>* **пользователи**.</span><span class="sxs-lookup"><span data-stu-id="d58f3-108">Start with the **Users** tab for an incident from **Incidents & alerts >** *incident* **> Users**.</span></span> 

:::image type="content" source="../../media/investigate-incidents/incident-users.png" alt-text="Пример страницы &quot;Пользователи&quot; для инцидента":::

<span data-ttu-id="d58f3-110">Чтобы получить краткое описание учетной записи пользователя для инцидента, выберите контрольный знак рядом с именем учетной записи пользователя.</span><span class="sxs-lookup"><span data-stu-id="d58f3-110">To get a quick summary of a user account for the incident, select the check mark next to the user account name.</span></span> <span data-ttu-id="d58f3-111">Ниже приведен пример.</span><span class="sxs-lookup"><span data-stu-id="d58f3-111">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-users/incidents-ss-user-pane.png" alt-text="Пример сводки учетной записи пользователя для инцидента в центре безопасности Microsoft 365":::

> [!NOTE]
> <span data-ttu-id="d58f3-113">На странице Пользователя показана организация Azure Active Directory (AD), а также группы, помогающие понять группы и разрешения, связанные с пользователем.</span><span class="sxs-lookup"><span data-stu-id="d58f3-113">The User page shows Azure Active Directory (AD) organization as well as groups, helping you understand the groups and permissions associated with a user.</span></span>

<span data-ttu-id="d58f3-114">На этой странице вылетов вы можете просмотреть сведения об угрозах пользователей, включая текущие инциденты, активные оповещения и уровень риска, а также экспозицию пользователей, учетные записи, устройства и т. д.</span><span class="sxs-lookup"><span data-stu-id="d58f3-114">In this fly-out page, you can review user threat information, including any current incidents, active alerts, and risk level as well as user exposure, accounts, devices, and more.</span></span>

<span data-ttu-id="d58f3-115">Кроме того, вы можете принять меры непосредственно в центре безопасности Microsoft 365, чтобы обратиться к скомпрометированного пользователя, подтвердив, что пользователь скомпрометирован или требует от него снова войти.</span><span class="sxs-lookup"><span data-stu-id="d58f3-115">In addition, you can take action directly in the Microsoft 365 security center to address a compromised user, confirming the user is compromised or requiring them to sign in again.</span></span>

<span data-ttu-id="d58f3-116">Здесь вы можете выбрать **страницу Перейти на страницу пользователя,** чтобы узнать подробности учетной записи пользователя.</span><span class="sxs-lookup"><span data-stu-id="d58f3-116">From here, you can select **Go to user page** to see the details of a user account.</span></span> <span data-ttu-id="d58f3-117">Ниже приведен пример.</span><span class="sxs-lookup"><span data-stu-id="d58f3-117">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-users/incidents-ss-user-details.png" alt-text="Пример страницы учетной записи пользователя для инцидента в центре безопасности Microsoft 365":::

<span data-ttu-id="d58f3-119">Вы также можете увидеть эту страницу, выбрав имя учетной записи пользователя из списка на странице **Пользователи.**</span><span class="sxs-lookup"><span data-stu-id="d58f3-119">You can also see this page by selecting the name of the user account from the list on the **Users** page.</span></span>

<span data-ttu-id="d58f3-120">Страница пользователя Центра безопасности Microsoft 365 объединяет сведения из Microsoft Defender для конечной точки, Microsoft Defender для удостоверений и Microsoft Cloud App Security (в зависимости от лицензий).</span><span class="sxs-lookup"><span data-stu-id="d58f3-120">The Microsoft 365 security center user page combines information from Microsoft Defender for Endpoint, Microsoft Defender for Identity, and Microsoft Cloud App Security (depending on what licenses you have).</span></span> 

<span data-ttu-id="d58f3-121">На этой странице показаны сведения, определенные для риска безопасности учетной записи пользователя.</span><span class="sxs-lookup"><span data-stu-id="d58f3-121">This page shows information specific to the security risk of a user account.</span></span> <span data-ttu-id="d58f3-122">Это включает оценку, которая помогает оценить риски и недавние события и оповещения, которые способствовали общему риску пользователя.</span><span class="sxs-lookup"><span data-stu-id="d58f3-122">This includes a score that helps assess risk and recent events and alerts that contributed to the overall risk of the user.</span></span>

<span data-ttu-id="d58f3-123">На этой странице можно сделать дополнительные действия:</span><span class="sxs-lookup"><span data-stu-id="d58f3-123">From this page, you can do these additional actions:</span></span> 

- <span data-ttu-id="d58f3-124">Пометить учетную запись пользователя как скомпрометированную</span><span class="sxs-lookup"><span data-stu-id="d58f3-124">Mark the user account as compromised</span></span>
- <span data-ttu-id="d58f3-125">Требовать от пользователя снова войти</span><span class="sxs-lookup"><span data-stu-id="d58f3-125">Require the user to sign in again</span></span>
- <span data-ttu-id="d58f3-126">Приостановка учетной записи пользователя</span><span class="sxs-lookup"><span data-stu-id="d58f3-126">Suspend the user account</span></span>
- <span data-ttu-id="d58f3-127">См. параметры учетной записи пользователя Azure Active Directory (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="d58f3-127">See the Azure Active Directory (Azure AD) user account settings</span></span>
- <span data-ttu-id="d58f3-128">Просмотр файлов, которые принадлежат учетной записи пользователя</span><span class="sxs-lookup"><span data-stu-id="d58f3-128">View the files owned by the user account</span></span>
- <span data-ttu-id="d58f3-129">Просмотр файлов, общих этому пользователю.</span><span class="sxs-lookup"><span data-stu-id="d58f3-129">View files shared with this user.</span></span> 

<span data-ttu-id="d58f3-130">Ниже приведен пример.</span><span class="sxs-lookup"><span data-stu-id="d58f3-130">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-users/incidents-ss-user-details-actions.png" alt-text="Пример действий учетной записи пользователя в центре безопасности Microsoft 365":::


<!--
You can access this page from multiple areas in the Microsoft 365 security center. You can access this page from a specific incident in the **Users** tab. Some alerts might include users as a specific affected asset. You can also search for users.  

Learn more about how to investigate users and potential risk [in this Cloud App Security tutorial](/cloud-app-security/tutorial-ueba#:~:text=To%20identify%20who%20your%20riskiest,user%20page%20to%20investigate%20them).

--> 

## <a name="related-topics"></a><span data-ttu-id="d58f3-132">См. также</span><span class="sxs-lookup"><span data-stu-id="d58f3-132">Related topics</span></span>

- [<span data-ttu-id="d58f3-133">Обзор инцидентов</span><span class="sxs-lookup"><span data-stu-id="d58f3-133">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="d58f3-134">Управление приоритетом инцидентов</span><span class="sxs-lookup"><span data-stu-id="d58f3-134">Prioritize incidents</span></span>](incident-queue.md)
- [<span data-ttu-id="d58f3-135">Управление инцидентами</span><span class="sxs-lookup"><span data-stu-id="d58f3-135">Manage incidents</span></span>](manage-incidents.md)