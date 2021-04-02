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
ms.openlocfilehash: ab6ce0e8572fc20d3e5dd9f36e84ce9894280fe2
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/01/2021
ms.locfileid: "51498196"
---
# <a name="investigate-users-in-microsoft-365-security-center"></a><span data-ttu-id="ebdef-104">Исследование пользователей в Центре безопасности Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="ebdef-104">Investigate users in Microsoft 365 security center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

[!INCLUDE [Prerelease](../includes/prerelease.md)]

<span data-ttu-id="ebdef-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="ebdef-105">**Applies to:**</span></span>

- <span data-ttu-id="ebdef-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ebdef-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="ebdef-107">В ходе расследования может быть установлено, что пользователь был скомпрометирован.</span><span class="sxs-lookup"><span data-stu-id="ebdef-107">As part of your investigation, you might find that a user has been compromised.</span></span>

<span data-ttu-id="ebdef-108">Страница пользователя Центра безопасности Microsoft 365 объединяет сведения из Microsoft Defender для конечной точки, Microsoft Defender для удостоверений и Microsoft Cloud App Security (в зависимости от лицензий).</span><span class="sxs-lookup"><span data-stu-id="ebdef-108">The Microsoft 365 security center user page combines information from Microsoft Defender for Endpoint, Microsoft Defender for Identity, and Microsoft Cloud App Security (depending on what licenses you have).</span></span> <span data-ttu-id="ebdef-109">Эта страница является идеальным начальным местом для расследования пользователей и потенциальных инцидентов.</span><span class="sxs-lookup"><span data-stu-id="ebdef-109">This page is the ideal starting place for investigating users and potential incidents.</span></span>
<span data-ttu-id="ebdef-110">![Страница пользователя](../../media/m3d-userpage.png)</span><span class="sxs-lookup"><span data-stu-id="ebdef-110">![User page](../../media/m3d-userpage.png)</span></span>

<span data-ttu-id="ebdef-111">На этой странице показаны сведения, относяные к риску безопасности пользователя.</span><span class="sxs-lookup"><span data-stu-id="ebdef-111">This page shows information specific to the security risk of a user.</span></span> <span data-ttu-id="ebdef-112">Это включает оценку, которая помогает оценить риск, недавние события и оповещения, которые способствовали общему риску пользователя и другие.</span><span class="sxs-lookup"><span data-stu-id="ebdef-112">This includes a score that helps assess risk, recent events and alerts that contributed to the overall risk of the user, and more.</span></span>

<span data-ttu-id="ebdef-113">Вы можете получить доступ к этой странице из нескольких областей центра безопасности Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ebdef-113">You can access this page from multiple areas in the Microsoft 365 security center.</span></span> <span data-ttu-id="ebdef-114">Вы можете получить доступ к этой странице из определенного инцидента на вкладке **Пользователи.** Некоторые оповещения могут включать пользователей в качестве определенного затронутного актива.</span><span class="sxs-lookup"><span data-stu-id="ebdef-114">You can access this page from a specific incident in the **Users** tab. Some alerts might include users as a specific affected asset.</span></span> <span data-ttu-id="ebdef-115">Вы также можете искать пользователей.</span><span class="sxs-lookup"><span data-stu-id="ebdef-115">You can also search for users.</span></span>  

<span data-ttu-id="ebdef-116">Узнайте больше о том, как исследовать пользователей и потенциальные риски в этом руководстве по безопасности [облачных приложений.](/cloud-app-security/tutorial-ueba#:~:text=To%20identify%20who%20your%20riskiest,user%20page%20to%20investigate%20them)</span><span class="sxs-lookup"><span data-stu-id="ebdef-116">Learn more about how to investigate users and potential risk [in this Cloud App Security tutorial](/cloud-app-security/tutorial-ueba#:~:text=To%20identify%20who%20your%20riskiest,user%20page%20to%20investigate%20them).</span></span>

## <a name="related-topics"></a><span data-ttu-id="ebdef-117">См. также</span><span class="sxs-lookup"><span data-stu-id="ebdef-117">Related topics</span></span>

- [<span data-ttu-id="ebdef-118">Обзор инцидентов</span><span class="sxs-lookup"><span data-stu-id="ebdef-118">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="ebdef-119">Управление приоритетом инцидентов</span><span class="sxs-lookup"><span data-stu-id="ebdef-119">Prioritize incidents</span></span>](incident-queue.md)
- [<span data-ttu-id="ebdef-120">Управление инцидентами</span><span class="sxs-lookup"><span data-stu-id="ebdef-120">Manage incidents</span></span>](manage-incidents.md)