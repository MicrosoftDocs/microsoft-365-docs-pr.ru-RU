---
title: Управление правилами подавления конечных точек в Microsoft Defender
description: Возможно, вам потребуется предотвратить появляние оповещений на портале с помощью правил подавления. Узнайте, как управлять правилами подавления в ATP Microsoft Defender.
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
ms.openlocfilehash: d2ff8fa1f07f82c3cc719f49f50ee25937aea243
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2021
ms.locfileid: "51187569"
---
# <a name="manage-suppression-rules"></a><span data-ttu-id="15820-105">Управление правилами подавления</span><span class="sxs-lookup"><span data-stu-id="15820-105">Manage suppression rules</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="15820-106">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="15820-106">**Applies to:**</span></span>
- [<span data-ttu-id="15820-107">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="15820-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="15820-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="15820-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="15820-109">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="15820-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="15820-110">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="15820-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


<span data-ttu-id="15820-111">Возможны сценарии, в которых необходимо подавить появляющиеся на портале оповещения.</span><span class="sxs-lookup"><span data-stu-id="15820-111">There might be scenarios where you need to suppress alerts from appearing in the portal.</span></span> <span data-ttu-id="15820-112">Можно создать правила подавления для определенных оповещений, которые, как известно, являются безобидными, например известных инструментов или процессов в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="15820-112">You can create suppression rules for specific alerts that are known to be innocuous such as known tools or processes in your organization.</span></span> <span data-ttu-id="15820-113">Дополнительные сведения о подавлении оповещений см. в [рублях Suppress alerts.](manage-alerts.md)</span><span class="sxs-lookup"><span data-stu-id="15820-113">For more information on how to suppress alerts, see [Suppress alerts](manage-alerts.md).</span></span>

<span data-ttu-id="15820-114">Вы можете просмотреть список всех правил подавления и управлять ими в одном месте.</span><span class="sxs-lookup"><span data-stu-id="15820-114">You can view a list of all the suppression rules and manage them in one place.</span></span> <span data-ttu-id="15820-115">Вы также можете включить или отключить правило подавления оповещений.</span><span class="sxs-lookup"><span data-stu-id="15820-115">You can also turn an alert suppression rule on or off.</span></span>


1. <span data-ttu-id="15820-116">В области навигации выберите подавление **параметров**  >  **оповещения.**</span><span class="sxs-lookup"><span data-stu-id="15820-116">In the navigation pane, select **Settings** > **Alert suppression**.</span></span> <span data-ttu-id="15820-117">Отображается список правил подавления, созданных пользователями в организации.</span><span class="sxs-lookup"><span data-stu-id="15820-117">The list of suppression rules that users in your organization have created is displayed.</span></span>

2. <span data-ttu-id="15820-118">Выберите правило, щелкнув на чек-окне рядом с именем правила.</span><span class="sxs-lookup"><span data-stu-id="15820-118">Select a rule by clicking on the check-box beside the rule name.</span></span>

3. <span data-ttu-id="15820-119">Нажмите **кнопку Включите правило**, **изменить правило** или  **удалить правило**.</span><span class="sxs-lookup"><span data-stu-id="15820-119">Click **Turn rule on**, **Edit rule**, or  **Delete rule**.</span></span> <span data-ttu-id="15820-120">При внесении изменений в правило можно выбрать выпуск оповещений, которые он уже подавил, независимо от того, соответствуют ли эти оповещения новым критериям.</span><span class="sxs-lookup"><span data-stu-id="15820-120">When making changes to a rule, you can choose to release alerts that it has already suppressed, regardless whether or not these alerts match the new criteria.</span></span> 


## <a name="view-details-of-a-suppression-rule"></a><span data-ttu-id="15820-121">Просмотр сведений о правиле подавления</span><span class="sxs-lookup"><span data-stu-id="15820-121">View details of a suppression rule</span></span>

1. <span data-ttu-id="15820-122">В области навигации выберите подавление **параметров**  >  **оповещения.**</span><span class="sxs-lookup"><span data-stu-id="15820-122">In the navigation pane, select **Settings** > **Alert suppression**.</span></span> <span data-ttu-id="15820-123">Отображается список правил подавления, созданных пользователями в организации.</span><span class="sxs-lookup"><span data-stu-id="15820-123">The list of suppression rules that users in your organization have created is displayed.</span></span>

2. <span data-ttu-id="15820-124">Щелкните имя правила.</span><span class="sxs-lookup"><span data-stu-id="15820-124">Click on a rule name.</span></span> <span data-ttu-id="15820-125">Отображаются сведения о правиле.</span><span class="sxs-lookup"><span data-stu-id="15820-125">Details of the rule is displayed.</span></span> <span data-ttu-id="15820-126">Вы увидите сведения о правилах, таких как состояние, область, действие, количество совпадающих оповещений, созданных по и дате создания правила.</span><span class="sxs-lookup"><span data-stu-id="15820-126">You'll see the rule details such as  status, scope, action, number of matching alerts, created by, and date when the rule was created.</span></span> <span data-ttu-id="15820-127">Вы также можете просматривать связанные оповещения и условия правил.</span><span class="sxs-lookup"><span data-stu-id="15820-127">You can also view associated alerts and the rule conditions.</span></span>

## <a name="related-topics"></a><span data-ttu-id="15820-128">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="15820-128">Related topics</span></span>

- [<span data-ttu-id="15820-129">Управление оповещениями</span><span class="sxs-lookup"><span data-stu-id="15820-129">Manage alerts</span></span>](manage-alerts.md)
