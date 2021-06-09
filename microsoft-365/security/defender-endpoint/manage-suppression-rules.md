---
title: Управление правилами подавления конечных точек в Microsoft Defender
description: Возможно, вам потребуется предотвратить появляние оповещений на портале с помощью правил подавления. Узнайте, как управлять правилами подавления в Microsoft Defender для конечной точки.
keywords: управление подавлением, правилами, именем правила, областью, действием, оповещениями, включите, отключите
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: f1549512a02fe3af71d32c6b33c69cc705de99a8
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/16/2021
ms.locfileid: "51862131"
---
# <a name="manage-suppression-rules"></a><span data-ttu-id="5ea2e-105">Управление правилами подавления</span><span class="sxs-lookup"><span data-stu-id="5ea2e-105">Manage suppression rules</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="5ea2e-106">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="5ea2e-106">**Applies to:**</span></span>
- [<span data-ttu-id="5ea2e-107">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="5ea2e-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="5ea2e-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5ea2e-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="5ea2e-109">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="5ea2e-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="5ea2e-110">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="5ea2e-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


<span data-ttu-id="5ea2e-111">Возможны сценарии, в которых необходимо подавить появляющиеся на портале оповещения.</span><span class="sxs-lookup"><span data-stu-id="5ea2e-111">There might be scenarios where you need to suppress alerts from appearing in the portal.</span></span> <span data-ttu-id="5ea2e-112">Можно создать правила подавления для определенных оповещений, которые, как известно, являются безобидными, например известных инструментов или процессов в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="5ea2e-112">You can create suppression rules for specific alerts that are known to be innocuous such as known tools or processes in your organization.</span></span> <span data-ttu-id="5ea2e-113">Дополнительные сведения о подавлении оповещений см. в [рублях Suppress alerts.](manage-alerts.md)</span><span class="sxs-lookup"><span data-stu-id="5ea2e-113">For more information on how to suppress alerts, see [Suppress alerts](manage-alerts.md).</span></span>

<span data-ttu-id="5ea2e-114">Вы можете просмотреть список всех правил подавления и управлять ими в одном месте.</span><span class="sxs-lookup"><span data-stu-id="5ea2e-114">You can view a list of all the suppression rules and manage them in one place.</span></span> <span data-ttu-id="5ea2e-115">Вы также можете включить или отключить правило подавления оповещений.</span><span class="sxs-lookup"><span data-stu-id="5ea2e-115">You can also turn an alert suppression rule on or off.</span></span>


1. <span data-ttu-id="5ea2e-116">В области навигации выберите **Параметры**  >  **оповещение.**</span><span class="sxs-lookup"><span data-stu-id="5ea2e-116">In the navigation pane, select **Settings** > **Alert suppression**.</span></span> <span data-ttu-id="5ea2e-117">Отображается список правил подавления, созданных пользователями в организации.</span><span class="sxs-lookup"><span data-stu-id="5ea2e-117">The list of suppression rules that users in your organization have created is displayed.</span></span>

2. <span data-ttu-id="5ea2e-118">Выберите правило, щелкнув на чек-окне рядом с именем правила.</span><span class="sxs-lookup"><span data-stu-id="5ea2e-118">Select a rule by clicking on the check-box beside the rule name.</span></span>

3. <span data-ttu-id="5ea2e-119">Нажмите **кнопку Включите правило**, **изменить правило** или  **удалить правило**.</span><span class="sxs-lookup"><span data-stu-id="5ea2e-119">Click **Turn rule on**, **Edit rule**, or  **Delete rule**.</span></span> <span data-ttu-id="5ea2e-120">При внесении изменений в правило можно выбрать выпуск оповещений, которые он уже подавил, независимо от того, соответствуют ли эти оповещения новым критериям.</span><span class="sxs-lookup"><span data-stu-id="5ea2e-120">When making changes to a rule, you can choose to release alerts that it has already suppressed, regardless whether or not these alerts match the new criteria.</span></span> 


## <a name="view-details-of-a-suppression-rule"></a><span data-ttu-id="5ea2e-121">Просмотр сведений о правиле подавления</span><span class="sxs-lookup"><span data-stu-id="5ea2e-121">View details of a suppression rule</span></span>

1. <span data-ttu-id="5ea2e-122">В области навигации выберите **Параметры**  >  **оповещение.**</span><span class="sxs-lookup"><span data-stu-id="5ea2e-122">In the navigation pane, select **Settings** > **Alert suppression**.</span></span> <span data-ttu-id="5ea2e-123">Отображается список правил подавления, созданных пользователями в организации.</span><span class="sxs-lookup"><span data-stu-id="5ea2e-123">The list of suppression rules that users in your organization have created is displayed.</span></span>

2. <span data-ttu-id="5ea2e-124">Щелкните имя правила.</span><span class="sxs-lookup"><span data-stu-id="5ea2e-124">Click on a rule name.</span></span> <span data-ttu-id="5ea2e-125">Отображаются сведения о правиле.</span><span class="sxs-lookup"><span data-stu-id="5ea2e-125">Details of the rule is displayed.</span></span> <span data-ttu-id="5ea2e-126">Вы увидите сведения о правилах, таких как состояние, область, действие, количество совпадающих оповещений, созданных по и дате создания правила.</span><span class="sxs-lookup"><span data-stu-id="5ea2e-126">You'll see the rule details such as  status, scope, action, number of matching alerts, created by, and date when the rule was created.</span></span> <span data-ttu-id="5ea2e-127">Вы также можете просматривать связанные оповещения и условия правил.</span><span class="sxs-lookup"><span data-stu-id="5ea2e-127">You can also view associated alerts and the rule conditions.</span></span>

## <a name="related-topics"></a><span data-ttu-id="5ea2e-128">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="5ea2e-128">Related topics</span></span>

- [<span data-ttu-id="5ea2e-129">Управление оповещениями</span><span class="sxs-lookup"><span data-stu-id="5ea2e-129">Manage alerts</span></span>](manage-alerts.md)
