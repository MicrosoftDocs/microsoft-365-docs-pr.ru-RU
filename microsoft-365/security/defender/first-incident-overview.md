---
title: Введение в ответ на первый инцидент
description: Основы реагирования на первый инцидент в Microsoft 365 Defender.
keywords: инциденты, оповещения, расследование, корреляция, атака, устройства, пользователи, удостоверения, удостоверения, почтовый ящик, электронная почта, 365, Microsoft, m365, реагирование на инциденты, кибератака
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
ms.openlocfilehash: 6e65a12f42b9f5f75c1a19cb9c4a261c94feaf31
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2021
ms.locfileid: "52841718"
---
# <a name="introduction-to-responding-to-your-first-incident"></a><span data-ttu-id="96877-104">Введение в ответ на первый инцидент</span><span class="sxs-lookup"><span data-stu-id="96877-104">Introduction to responding to your first incident</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="96877-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="96877-105">**Applies to:**</span></span>
- <span data-ttu-id="96877-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="96877-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="96877-107">Стратегия реагирования на инциденты организации определяет ее способность бороться с все более разрушительными инцидентами безопасности и киберпреступностью.</span><span class="sxs-lookup"><span data-stu-id="96877-107">An organization's incident response strategy determines its ability to deal with increasingly disruptive security incidents and cybercrime.</span></span> <span data-ttu-id="96877-108">Несмотря на важное значение профилактических мер, способность быстро действовать для сдерживания, искоренения и восстановления после обнаруженных инцидентов может свести к минимуму ущерб и потери бизнеса.</span><span class="sxs-lookup"><span data-stu-id="96877-108">While taking preventative measures is important, the ability to act quickly to contain, eradicate, and recover from detected incidents can minimize damage and business losses.</span></span>

<span data-ttu-id="96877-109">В этом погонах по реагированию на инциденты показано, как вы, в составе группы операций безопасности, можете выполнять большинство ключевых действий по реагированию на инциденты в Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="96877-109">This incident response walkthrough shows how you, as part of a security operations team, can perform most of the key incident response steps within Microsoft 365 Defender.</span></span> <span data-ttu-id="96877-110">Эти этапы описаны ниже.</span><span class="sxs-lookup"><span data-stu-id="96877-110">Here are the steps:</span></span>

- <span data-ttu-id="96877-111">Подготовка позы безопасности</span><span class="sxs-lookup"><span data-stu-id="96877-111">Preparation of your security posture</span></span>
- <span data-ttu-id="96877-112">Для каждого инцидента:</span><span class="sxs-lookup"><span data-stu-id="96877-112">For each incident:</span></span>
  - <span data-ttu-id="96877-113">Шаг 1. Триадж и анализ</span><span class="sxs-lookup"><span data-stu-id="96877-113">Step 1: Triage and analysis</span></span>
  - <span data-ttu-id="96877-114">Шаг 2. Исправление (сдерживание, ликвидация и восстановление)</span><span class="sxs-lookup"><span data-stu-id="96877-114">Step 2: Remediation (containment, eradication, and recovery)</span></span>
  - <span data-ttu-id="96877-115">Шаг 3. Проверка после инцидента</span><span class="sxs-lookup"><span data-stu-id="96877-115">Step 3: Post-incident review</span></span>

<span data-ttu-id="96877-116">Инцидент с безопасностью определяется Национальным институтом стандартов и технологий (NIST) как "событие, которое фактически или потенциально ставит под угрозу конфиденциальность, целостность или доступность информационной системы; или сведения, которые система обрабатывает, хранит или передает; или это представляет собой нарушение или неминуемую угрозу нарушения политик безопасности, процедур безопасности или политик приемлемого использования".</span><span class="sxs-lookup"><span data-stu-id="96877-116">A security incident is defined by National Institute of Standards and Technology (NIST) as "an occurrence that actually or potentially jeopardizes the confidentiality, integrity, or availability of an information system; or the information the system processes, stores, or transmits; or that constitutes a violation or imminent threat of violation of security policies, security procedures, or acceptable use policies."</span></span>

<span data-ttu-id="96877-117">Инциденты в Microsoft 365 Defender являются логическими отправной точкой для анализа и реагирования на инциденты.</span><span class="sxs-lookup"><span data-stu-id="96877-117">Incidents in Microsoft 365 Defender are the logical starting points for analysis and incident response.</span></span> <span data-ttu-id="96877-118">Анализ и исправление инцидентов обычно составляет большинство задач группы операций безопасности.</span><span class="sxs-lookup"><span data-stu-id="96877-118">Analyzing and remediating incidents typically makes up most of a security operations team's tasks.</span></span>

## <a name="next-step"></a><span data-ttu-id="96877-119">Следующий этап</span><span class="sxs-lookup"><span data-stu-id="96877-119">Next step</span></span>

<span data-ttu-id="96877-120">[![Подготовка организации и Microsoft 365 клиента](../../media/first-incident-overview/first-incident-path.png)](first-incident-prepare.md)</span><span class="sxs-lookup"><span data-stu-id="96877-120">[![Prepare your organization and Microsoft 365 tenant](../../media/first-incident-overview/first-incident-path.png)](first-incident-prepare.md)</span></span>

<span data-ttu-id="96877-121">Убедитесь, что ваша организация и Microsoft 365 готовы [к обработке инцидентов.](first-incident-prepare.md)</span><span class="sxs-lookup"><span data-stu-id="96877-121">Make sure your organization and Microsoft 365 tenant is [prepared for incident handling](first-incident-prepare.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="96877-122">См. также</span><span class="sxs-lookup"><span data-stu-id="96877-122">See also</span></span>

<span data-ttu-id="96877-123">Руководство по реагированию на инциденты для Microsoft 365 Defender:</span><span class="sxs-lookup"><span data-stu-id="96877-123">Incident response guidance for Microsoft 365 Defender:</span></span>

- [<span data-ttu-id="96877-124">Обзор инцидентов</span><span class="sxs-lookup"><span data-stu-id="96877-124">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="96877-125">Исследование инцидентов</span><span class="sxs-lookup"><span data-stu-id="96877-125">Investigate incidents</span></span>](investigate-incidents.md)
- [<span data-ttu-id="96877-126">Управление инцидентами</span><span class="sxs-lookup"><span data-stu-id="96877-126">Manage incidents</span></span>](manage-incidents.md)

<span data-ttu-id="96877-127">Дополнительные примеры первых ответов на инциденты:</span><span class="sxs-lookup"><span data-stu-id="96877-127">Additional examples of first incident responses:</span></span>

- [<span data-ttu-id="96877-128">Фишинговое письмо</span><span class="sxs-lookup"><span data-stu-id="96877-128">Phishing email</span></span>](first-incident-path-phishing.md)
- [<span data-ttu-id="96877-129">Атака на базу удостоверений</span><span class="sxs-lookup"><span data-stu-id="96877-129">Identity-base attack</span></span>](first-incident-path-identity.md)

[<span data-ttu-id="96877-130">Подробные книги ответов на инциденты</span><span class="sxs-lookup"><span data-stu-id="96877-130">Detailed incident response playbooks</span></span>](/security/compass/incident-response-playbooks)


