---
title: Шаг 3. Выполните после инцидента обзор вашего первого инцидента
description: Проверка первого инцидента в Microsoft 365 Defender.
keywords: инциденты, оповещения, исследование, корреляция, атака, компьютеры, устройства, пользователи, удостоверения, удостоверение, почтовый ящик, электронная почта, 365, microsoft, m365
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 44f583d32de166fe3d68a182406eb3a2ee814084
ms.sourcegitcommit: de5fce90de22ba588e75e1a1d2e87e03b9e25ec7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/10/2021
ms.locfileid: "52297156"
---
# <a name="step-3-perform-a-post-incident-review-of-your-first-incident"></a><span data-ttu-id="d4d06-105">Этап 3.</span><span class="sxs-lookup"><span data-stu-id="d4d06-105">Step 3.</span></span> <span data-ttu-id="d4d06-106">Выполните после инцидента обзор вашего первого инцидента</span><span class="sxs-lookup"><span data-stu-id="d4d06-106">Perform a post-incident review of your first incident</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="d4d06-107">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="d4d06-107">**Applies to:**</span></span>
- <span data-ttu-id="d4d06-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d4d06-108">Microsoft 365 Defender</span></span>

<span data-ttu-id="d4d06-109">Национальный институт стандартов и технологий (NIST) рекомендует, чтобы после того, как были приняты все меры для восстановления после атаки, организации должны проанализировать инцидент, чтобы извлечь из него уроки, изучить и улучшить осанку или процессы безопасности.</span><span class="sxs-lookup"><span data-stu-id="d4d06-109">National Institute of Standards and Technology (NIST) recommends that once all steps have been taken to recover from the attack, organizations must review the incident to learn from it and learn and improve security posture or processes.</span></span> <span data-ttu-id="d4d06-110">При подготовке к следующему инциденту важно оценить различные аспекты обработки инцидентов.</span><span class="sxs-lookup"><span data-stu-id="d4d06-110">Assessing the different aspects of incident-handling becomes important in preparing for the next incident.</span></span>

<span data-ttu-id="d4d06-111">Microsoft 365 Defender может помочь в выполнении действий после инцидента, предоставляя организации оповещения, совпадающие с [MITRE ATT&CK Framework.](https://attack.mitre.org/)</span><span class="sxs-lookup"><span data-stu-id="d4d06-111">Microsoft 365 Defender can assist in performing post-incident activities by providing an organization with alerts that align with [MITRE ATT&CK Framework](https://attack.mitre.org/).</span></span> <span data-ttu-id="d4d06-112">Все решения Microsoft Defender маркировать атаки в соответствии с тактикой&CK.</span><span class="sxs-lookup"><span data-stu-id="d4d06-112">All Microsoft Defender solutions label attacks in accordance with an ATT&CK tactic or technique.</span></span> 

<span data-ttu-id="d4d06-113">Сопоставление оповещений с этой отраслевой структурой можно:</span><span class="sxs-lookup"><span data-stu-id="d4d06-113">By mapping alerts to this industry framework, you can:</span></span>

- <span data-ttu-id="d4d06-114">Анализ пробелов в охвате безопасностью.</span><span class="sxs-lookup"><span data-stu-id="d4d06-114">Conduct an analysis of gaps in security coverage.</span></span>
- <span data-ttu-id="d4d06-115">Определение атрибуции противника и кампании.</span><span class="sxs-lookup"><span data-stu-id="d4d06-115">Determine adversary and campaign attribution.</span></span>
- <span data-ttu-id="d4d06-116">Выполните анализ тенденций.</span><span class="sxs-lookup"><span data-stu-id="d4d06-116">Perform trend analysis.</span></span>
- <span data-ttu-id="d4d06-117">Определение пробелов в навыках в осведомленности о методе атаки.</span><span class="sxs-lookup"><span data-stu-id="d4d06-117">Identify skill gaps in attack method awareness.</span></span>
- <span data-ttu-id="d4d06-118">Создайте Power Automate для более быстрого восстановления.</span><span class="sxs-lookup"><span data-stu-id="d4d06-118">Create a Power Automate Playbook for faster remediation.</span></span> 

<span data-ttu-id="d4d06-119">Действия по проверке после инцидента также могут привести к тонкой настройке конфигурации безопасности и процессов группы безопасности, что повышает возможности реагирования организации.</span><span class="sxs-lookup"><span data-stu-id="d4d06-119">Post-incident review activity can also result in fine-tuning your security configuration and security team's processes, enhancing your organization’s response capabilities.</span></span>

## <a name="next-step"></a><span data-ttu-id="d4d06-120">Следующий шаг</span><span class="sxs-lookup"><span data-stu-id="d4d06-120">Next step</span></span>

<span data-ttu-id="d4d06-121">Дополнительные пути расследования см. в этой версии.</span><span class="sxs-lookup"><span data-stu-id="d4d06-121">See these additional investigation paths:</span></span>

- [<span data-ttu-id="d4d06-122">Фишинговое письмо</span><span class="sxs-lookup"><span data-stu-id="d4d06-122">Phishing email</span></span>](first-incident-path-phishing.md)
- [<span data-ttu-id="d4d06-123">Атака на основе удостоверений</span><span class="sxs-lookup"><span data-stu-id="d4d06-123">Identity-based attack</span></span>](first-incident-path-identity.md)


## <a name="see-also"></a><span data-ttu-id="d4d06-124">См. также</span><span class="sxs-lookup"><span data-stu-id="d4d06-124">See also</span></span>

- [<span data-ttu-id="d4d06-125">Обзор инцидентов</span><span class="sxs-lookup"><span data-stu-id="d4d06-125">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="d4d06-126">Исследование инцидентов</span><span class="sxs-lookup"><span data-stu-id="d4d06-126">Investigate incidents</span></span>](investigate-incidents.md)
- [<span data-ttu-id="d4d06-127">Управление инцидентами</span><span class="sxs-lookup"><span data-stu-id="d4d06-127">Manage incidents</span></span>](manage-incidents.md)
