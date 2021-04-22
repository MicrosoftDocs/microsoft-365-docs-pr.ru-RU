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
ms.openlocfilehash: 1fb5a4eee41384ef1afc9b46e5bf538344718fe9
ms.sourcegitcommit: 4076b43a4b661de029f6307ddc1a989ab3108edb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2021
ms.locfileid: "51939734"
---
# <a name="analyze-users-in-microsoft-365-security-center"></a><span data-ttu-id="e62f2-104">Анализ пользователей в центре безопасности Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="e62f2-104">Analyze users in Microsoft 365 security center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="e62f2-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="e62f2-105">**Applies to:**</span></span>

- <span data-ttu-id="e62f2-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e62f2-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="e62f2-107">Часть анализа инцидентов может включать учетные записи пользователей.</span><span class="sxs-lookup"><span data-stu-id="e62f2-107">Part of your incident analysis can include user accounts.</span></span> <span data-ttu-id="e62f2-108">Начните со вкладки **"Пользователи"** об инциденте из & оповещений о > *>* **пользователи**.</span><span class="sxs-lookup"><span data-stu-id="e62f2-108">Start with the **Users** tab for an incident from **Incidents & alerts >** *incident* **> Users**.</span></span> 

:::image type="content" source="../../media/investigate-incidents/incident-users.png" alt-text="Пример страницы &quot;Пользователи&quot; для инцидента":::

<span data-ttu-id="e62f2-110">Чтобы получить краткое описание учетной записи пользователя для инцидента, выберите контрольный знак рядом с именем учетной записи пользователя.</span><span class="sxs-lookup"><span data-stu-id="e62f2-110">To get a quick summary of a user account for the incident, select the check mark next to the user account name.</span></span> <span data-ttu-id="e62f2-111">Ниже приведен пример.</span><span class="sxs-lookup"><span data-stu-id="e62f2-111">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-users/incidents-ss-user-pane.png" alt-text="Пример сводки учетной записи пользователя для инцидента в центре безопасности Microsoft 365":::

<span data-ttu-id="e62f2-113">Здесь вы можете выбрать **страницу Перейти на страницу пользователя,** чтобы узнать подробности учетной записи пользователя.</span><span class="sxs-lookup"><span data-stu-id="e62f2-113">From here, you can select **Go to user page** to see the details of a user account.</span></span> <span data-ttu-id="e62f2-114">Ниже приведен пример.</span><span class="sxs-lookup"><span data-stu-id="e62f2-114">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-users/incidents-ss-user-details.png" alt-text="Пример страницы учетной записи пользователя для инцидента в центре безопасности Microsoft 365":::

<span data-ttu-id="e62f2-116">Вы также можете увидеть эту страницу, выбрав имя учетной записи пользователя из списка на странице **Пользователи.**</span><span class="sxs-lookup"><span data-stu-id="e62f2-116">You can also see this page by selecting the name of the user account from the list on the **Users** page.</span></span>

<span data-ttu-id="e62f2-117">Страница пользователя Центра безопасности Microsoft 365 объединяет сведения из Microsoft Defender для конечной точки, Microsoft Defender для удостоверений и Microsoft Cloud App Security (в зависимости от лицензий).</span><span class="sxs-lookup"><span data-stu-id="e62f2-117">The Microsoft 365 security center user page combines information from Microsoft Defender for Endpoint, Microsoft Defender for Identity, and Microsoft Cloud App Security (depending on what licenses you have).</span></span> 

<span data-ttu-id="e62f2-118">На этой странице показаны сведения, определенные для риска безопасности учетной записи пользователя.</span><span class="sxs-lookup"><span data-stu-id="e62f2-118">This page shows information specific to the security risk of a user account.</span></span> <span data-ttu-id="e62f2-119">Это включает оценку, которая помогает оценить риски и недавние события и оповещения, которые способствовали общему риску пользователя.</span><span class="sxs-lookup"><span data-stu-id="e62f2-119">This includes a score that helps assess risk and recent events and alerts that contributed to the overall risk of the user.</span></span>

<span data-ttu-id="e62f2-120">На этой странице можно сделать дополнительные действия:</span><span class="sxs-lookup"><span data-stu-id="e62f2-120">From this page, you can do these additional actions:</span></span> 

- <span data-ttu-id="e62f2-121">Пометить учетную запись пользователя как скомпрометированную</span><span class="sxs-lookup"><span data-stu-id="e62f2-121">Mark the user account as compromised</span></span>
- <span data-ttu-id="e62f2-122">Требовать от пользователя снова войти</span><span class="sxs-lookup"><span data-stu-id="e62f2-122">Require the user to sign in again</span></span>
- <span data-ttu-id="e62f2-123">Приостановка учетной записи пользователя</span><span class="sxs-lookup"><span data-stu-id="e62f2-123">Suspend the user account</span></span>
- <span data-ttu-id="e62f2-124">См. параметры учетной записи пользователя Azure Active Directory (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="e62f2-124">See the Azure Active Directory (Azure AD) user account settings</span></span>
- <span data-ttu-id="e62f2-125">Просмотр файлов, которые принадлежат учетной записи пользователя</span><span class="sxs-lookup"><span data-stu-id="e62f2-125">View the files owned by the user account</span></span>
- <span data-ttu-id="e62f2-126">Просмотр файлов, общих этому пользователю.</span><span class="sxs-lookup"><span data-stu-id="e62f2-126">View files shared with this user.</span></span> 

<span data-ttu-id="e62f2-127">Ниже приведен пример.</span><span class="sxs-lookup"><span data-stu-id="e62f2-127">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-users/incidents-ss-user-details-actions.png" alt-text="Пример действий учетной записи пользователя в центре безопасности Microsoft 365":::


<!--
You can access this page from multiple areas in the Microsoft 365 security center. You can access this page from a specific incident in the **Users** tab. Some alerts might include users as a specific affected asset. You can also search for users.  

Learn more about how to investigate users and potential risk [in this Cloud App Security tutorial](/cloud-app-security/tutorial-ueba#:~:text=To%20identify%20who%20your%20riskiest,user%20page%20to%20investigate%20them).

--> 

## <a name="related-topics"></a><span data-ttu-id="e62f2-129">См. также</span><span class="sxs-lookup"><span data-stu-id="e62f2-129">Related topics</span></span>

- [<span data-ttu-id="e62f2-130">Обзор инцидентов</span><span class="sxs-lookup"><span data-stu-id="e62f2-130">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="e62f2-131">Управление приоритетом инцидентов</span><span class="sxs-lookup"><span data-stu-id="e62f2-131">Prioritize incidents</span></span>](incident-queue.md)
- [<span data-ttu-id="e62f2-132">Управление инцидентами</span><span class="sxs-lookup"><span data-stu-id="e62f2-132">Manage incidents</span></span>](manage-incidents.md)