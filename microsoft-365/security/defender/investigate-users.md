---
title: Исследование пользователей в Центре безопасности Microsoft 365
description: исследование пользователей в центре безопасности Microsoft 365
keywords: безопасность, вредоносные программы, Microsoft 365, M365, центр безопасности, монитор, отчет, удостоверения, данные, устройства, приложения
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
ms.openlocfilehash: 68fc924ee14932ebdf92ef76306ba00e352b6030
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/16/2021
ms.locfileid: "51861277"
---
# <a name="investigate-users-in-microsoft-365-security-center"></a><span data-ttu-id="71dea-104">Исследование пользователей в Центре безопасности Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="71dea-104">Investigate users in Microsoft 365 security center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="71dea-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="71dea-105">**Applies to:**</span></span>

- <span data-ttu-id="71dea-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="71dea-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="71dea-107">Часть расследования инцидента может включать учетные записи пользователей.</span><span class="sxs-lookup"><span data-stu-id="71dea-107">Part of your incident investigation can include user accounts.</span></span> <span data-ttu-id="71dea-108">Начните со вкладки **"Пользователи"** об инциденте из & оповещений о > *>* **пользователи**.</span><span class="sxs-lookup"><span data-stu-id="71dea-108">Start with the **Users** tab for an incident from **Incidents & alerts >** *incident* **> Users**.</span></span> 

:::image type="content" source="../../media/investigate-incidents/incident-users.png" alt-text="Пример страницы &quot;Пользователи&quot; для инцидента":::

<span data-ttu-id="71dea-110">Чтобы получить краткое описание учетной записи пользователя для инцидента, выберите контрольный знак рядом с именем учетной записи пользователя.</span><span class="sxs-lookup"><span data-stu-id="71dea-110">To get a quick summary of a user account for the incident, select the check mark next to the user account name.</span></span> <span data-ttu-id="71dea-111">Ниже приведен пример.</span><span class="sxs-lookup"><span data-stu-id="71dea-111">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-users/incidents-ss-user-pane.png" alt-text="Пример сводки учетной записи пользователя для инцидента в центре безопасности Microsoft 365":::

<span data-ttu-id="71dea-113">Здесь вы можете выбрать **страницу Перейти на страницу пользователя,** чтобы узнать подробности учетной записи пользователя.</span><span class="sxs-lookup"><span data-stu-id="71dea-113">From here, you can select **Go to user page** to see the details of a user account.</span></span> <span data-ttu-id="71dea-114">Ниже приведен пример.</span><span class="sxs-lookup"><span data-stu-id="71dea-114">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-users/incidents-ss-user-details.png" alt-text="Пример страницы учетной записи пользователя для инцидента в центре безопасности Microsoft 365":::

<span data-ttu-id="71dea-116">Вы также можете увидеть эту страницу, выбрав имя учетной записи пользователя из списка на странице **Пользователи.**</span><span class="sxs-lookup"><span data-stu-id="71dea-116">You can also see this page by selecting the name of the user account from the list on the **Users** page.</span></span>

<span data-ttu-id="71dea-117">Страница пользователя Центра безопасности Microsoft 365 объединяет сведения из Microsoft Defender для конечной точки, Microsoft Defender для удостоверений и Microsoft Cloud App Security (в зависимости от лицензий).</span><span class="sxs-lookup"><span data-stu-id="71dea-117">The Microsoft 365 security center user page combines information from Microsoft Defender for Endpoint, Microsoft Defender for Identity, and Microsoft Cloud App Security (depending on what licenses you have).</span></span> 

<span data-ttu-id="71dea-118">На этой странице показаны сведения, определенные для риска безопасности учетной записи пользователя.</span><span class="sxs-lookup"><span data-stu-id="71dea-118">This page shows information specific to the security risk of a user account.</span></span> <span data-ttu-id="71dea-119">Это включает оценку, которая помогает оценить риски и недавние события и оповещения, которые способствовали общему риску пользователя.</span><span class="sxs-lookup"><span data-stu-id="71dea-119">This includes a score that helps assess risk and recent events and alerts that contributed to the overall risk of the user.</span></span>

<span data-ttu-id="71dea-120">На этой странице можно сделать дополнительные действия:</span><span class="sxs-lookup"><span data-stu-id="71dea-120">From this page, you can do these additional actions:</span></span> 

- <span data-ttu-id="71dea-121">Пометить учетную запись пользователя как скомпрометированную</span><span class="sxs-lookup"><span data-stu-id="71dea-121">Mark the user account as compromised</span></span>
- <span data-ttu-id="71dea-122">Требовать от пользователя снова войти</span><span class="sxs-lookup"><span data-stu-id="71dea-122">Require the user to sign in again</span></span>
- <span data-ttu-id="71dea-123">Приостановка учетной записи пользователя</span><span class="sxs-lookup"><span data-stu-id="71dea-123">Suspend the user account</span></span>
- <span data-ttu-id="71dea-124">См. параметры учетной записи пользователя Azure Active Directory (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="71dea-124">See the Azure Active Directory (Azure AD) user account settings</span></span>
- <span data-ttu-id="71dea-125">Просмотр файлов, которые принадлежат учетной записи пользователя</span><span class="sxs-lookup"><span data-stu-id="71dea-125">View the files owned by the user account</span></span>
- <span data-ttu-id="71dea-126">Просмотр файлов, общих этому пользователю.</span><span class="sxs-lookup"><span data-stu-id="71dea-126">View files shared with this user.</span></span> 

<span data-ttu-id="71dea-127">Ниже приведен пример.</span><span class="sxs-lookup"><span data-stu-id="71dea-127">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-users/incidents-ss-user-details-actions.png" alt-text="Пример действий учетной записи пользователя в центре безопасности Microsoft 365":::


<!--
You can access this page from multiple areas in the Microsoft 365 security center. You can access this page from a specific incident in the **Users** tab. Some alerts might include users as a specific affected asset. You can also search for users.  

Learn more about how to investigate users and potential risk [in this Cloud App Security tutorial](/cloud-app-security/tutorial-ueba#:~:text=To%20identify%20who%20your%20riskiest,user%20page%20to%20investigate%20them).

--> 

## <a name="related-topics"></a><span data-ttu-id="71dea-129">См. также</span><span class="sxs-lookup"><span data-stu-id="71dea-129">Related topics</span></span>

- [<span data-ttu-id="71dea-130">Обзор инцидентов</span><span class="sxs-lookup"><span data-stu-id="71dea-130">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="71dea-131">Управление приоритетом инцидентов</span><span class="sxs-lookup"><span data-stu-id="71dea-131">Prioritize incidents</span></span>](incident-queue.md)
- [<span data-ttu-id="71dea-132">Управление инцидентами</span><span class="sxs-lookup"><span data-stu-id="71dea-132">Manage incidents</span></span>](manage-incidents.md)