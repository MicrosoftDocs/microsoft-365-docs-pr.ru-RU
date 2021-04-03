---
title: Уменьшение уязвимостей нулевого дня — управление угрозами и уязвимостью
description: Узнайте, как находить и устранять уязвимости нулевого дня в среде с помощью управления угрозами и уязвимостями.
keywords: mdatp tvm zero day vulnerabilities, tvm, threat & vulnerability management, zero day, 0-day, mitigate 0 day vulnerabilities, vulnerable CVE
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 941e4989dcb91ff9240131f5980d0e1eced2b21d
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/01/2021
ms.locfileid: "51501225"
---
# <a name="mitigate-zero-day-vulnerabilities---threat-and-vulnerability-management"></a><span data-ttu-id="626da-104">Уменьшение уязвимостей нулевого дня — управление угрозами и уязвимостью</span><span class="sxs-lookup"><span data-stu-id="626da-104">Mitigate zero-day vulnerabilities - threat and vulnerability management</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="626da-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="626da-105">**Applies to:**</span></span>

- [<span data-ttu-id="626da-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="626da-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="626da-107">Управление угрозами и уязвимостями</span><span class="sxs-lookup"><span data-stu-id="626da-107">Threat and vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="626da-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="626da-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="626da-109">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="626da-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="626da-110">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="626da-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

<span data-ttu-id="626da-111">Уязвимость нулевого дня — это открыто раскрытая уязвимость, для которой не были выпущены официальные исправления или обновления безопасности.</span><span class="sxs-lookup"><span data-stu-id="626da-111">A zero-day vulnerability is a publicly disclosed vulnerability for which no official patches or security updates have been released.</span></span> <span data-ttu-id="626da-112">Уязвимости нулевого дня часто имеют высокий уровень серьезности и активно используются.</span><span class="sxs-lookup"><span data-stu-id="626da-112">Zero-day vulnerabilities often have high severity levels and are actively exploited.</span></span>

<span data-ttu-id="626da-113">Управление угрозами и уязвимостями отображает только уязвимости нулевого дня, о них есть сведения.</span><span class="sxs-lookup"><span data-stu-id="626da-113">Threat and vulnerability management will only display zero-day vulnerabilities it has information about.</span></span>

## <a name="find-information-about-zero-day-vulnerabilities"></a><span data-ttu-id="626da-114">Поиск сведений об уязвимостях нулевого дня</span><span class="sxs-lookup"><span data-stu-id="626da-114">Find information about zero-day vulnerabilities</span></span>

<span data-ttu-id="626da-115">После того, как уязвимость нулевого дня будет найдена, сведения о ней будут переданы в центре безопасности Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="626da-115">Once a zero-day vulnerability has been found, information about it will be conveyed through the following experiences in the Microsoft Defender Security Center.</span></span>

### <a name="threat-and-vulnerability-management-dashboard"></a><span data-ttu-id="626da-116">Панель мониторинга управления угрозами и уязвимостью</span><span class="sxs-lookup"><span data-stu-id="626da-116">Threat and vulnerability management dashboard</span></span>

<span data-ttu-id="626da-117">Найди рекомендации с тегом нулевого дня в карточке "Рекомендации по безопасности".</span><span class="sxs-lookup"><span data-stu-id="626da-117">Look for recommendations with a zero-day tag in the “Top security recommendations” card.</span></span>

![Рекомендации с тегом нулевого дня.](images/tvm-zero-day-top-security-recommendations.png)

<span data-ttu-id="626da-119">Поиск верхнего программного обеспечения с тегом нулевого дня в карточке "Верхнее уязвимое программное обеспечение".</span><span class="sxs-lookup"><span data-stu-id="626da-119">Find top software with the zero-day tag in the "Top vulnerable software" card.</span></span>

![Top vulnerable software with a zero-day tag.](images/tvm-zero-day-top-software.png)

### <a name="weaknesses-page"></a><span data-ttu-id="626da-121">Страница Недостатки</span><span class="sxs-lookup"><span data-stu-id="626da-121">Weaknesses page</span></span>

<span data-ttu-id="626da-122">Ищи уязвимость с именем нулевого дня вместе с описанием и сведениями.</span><span class="sxs-lookup"><span data-stu-id="626da-122">Look for the named zero-day vulnerability along with a description and details.</span></span>

- <span data-ttu-id="626da-123">Если этой уязвимости назначен CVE-ID, рядом с именем CVE будет обозначена метка нулевого дня.</span><span class="sxs-lookup"><span data-stu-id="626da-123">If this vulnerability has a CVE-ID assigned, you’ll see the zero-day label next to the CVE name.</span></span>

- <span data-ttu-id="626da-124">Если эта уязвимость не назначена CVE-ID, ее можно найти под внутренним временным именем, которое выглядит как "TVM-XXXX-XXXX".</span><span class="sxs-lookup"><span data-stu-id="626da-124">If this vulnerability has no CVE-ID assigned, you'll find it under an internal, temporary name that looks like “TVM-XXXX-XXXX”.</span></span> <span data-ttu-id="626da-125">Имя будет обновляться после присвоения официального CVE-ID, но предыдущее внутреннее имя по-прежнему будет искаться и находится в боковой панели.</span><span class="sxs-lookup"><span data-stu-id="626da-125">The name will be updated once an official CVE-ID has been assigned, but the previous internal name will still be searchable and found in the side-panel.</span></span>

![Zero day example for CVE-2020-17087 in weaknesses page.](images/tvm-zero-day-weakness-name.png)

### <a name="software-inventory-page"></a><span data-ttu-id="626da-127">Страница инвентаризации программного обеспечения</span><span class="sxs-lookup"><span data-stu-id="626da-127">Software inventory page</span></span>

<span data-ttu-id="626da-128">И посмотрите на программное обеспечение с тегом нулевого дня.</span><span class="sxs-lookup"><span data-stu-id="626da-128">Look for software with the zero-day tag.</span></span> <span data-ttu-id="626da-129">Фильтр по тегу "нулевой день", чтобы видеть только программное обеспечение с уязвимостями нулевого дня.</span><span class="sxs-lookup"><span data-stu-id="626da-129">Filter by the "zero day" tag to only see software with zero-day vulnerabilities.</span></span>

![Нулевой пример Windows Server 2016 на странице инвентаризации программного обеспечения.](images/tvm-zero-day-software-inventory.png)

### <a name="software-page"></a><span data-ttu-id="626da-131">Страница программного обеспечения</span><span class="sxs-lookup"><span data-stu-id="626da-131">Software page</span></span>

<span data-ttu-id="626da-132">Ищи тег нулевого дня для каждого программного обеспечения, на которое повлияла уязвимость нулевого дня.</span><span class="sxs-lookup"><span data-stu-id="626da-132">Look for a zero-day tag for each software that has been affected by the zero–day vulnerability.</span></span>

![Пример нулевого дня для страницы программного обеспечения Windows Server 2016.](images/tvm-zero-day-software-page.png)

### <a name="security-recommendations-page"></a><span data-ttu-id="626da-134">Страница рекомендации по безопасности</span><span class="sxs-lookup"><span data-stu-id="626da-134">Security recommendations page</span></span>

<span data-ttu-id="626da-135">Просмотр четких предложений о вариантах устранения и смягчения последствий, включая обходные пути, если они существуют.</span><span class="sxs-lookup"><span data-stu-id="626da-135">View clear suggestions about remediation and mitigation options, including workarounds if they exist.</span></span> <span data-ttu-id="626da-136">Фильтр по тегу "нулевой день", чтобы увидеть только рекомендации по безопасности, адресованные уязвимостям нулевого дня.</span><span class="sxs-lookup"><span data-stu-id="626da-136">Filter by the "zero day" tag to only see security recommendations addressing zero-day vulnerabilities.</span></span>

<span data-ttu-id="626da-137">Если есть программное обеспечение с нулевой уязвимостью и дополнительные уязвимости для устранения, вы получите одну рекомендацию обо всех уязвимостях.</span><span class="sxs-lookup"><span data-stu-id="626da-137">If there's software with a zero-day vulnerability and additional vulnerabilities to address, you'll get one recommendation about all vulnerabilities.</span></span>

![Нулевой пример Windows Server 2016 на странице рекомендации по безопасности.](images/tvm-zero-day-security-recommendation.png)

## <a name="addressing-zero-day-vulnerabilities"></a><span data-ttu-id="626da-139">Устранение уязвимостей нулевого дня</span><span class="sxs-lookup"><span data-stu-id="626da-139">Addressing zero-day vulnerabilities</span></span>

<span data-ttu-id="626da-140">Перейдите на страницу рекомендации по безопасности и выберите рекомендацию с нулевой дневным значением.</span><span class="sxs-lookup"><span data-stu-id="626da-140">Go to the security recommendation page and select a recommendation with a zero-day.</span></span> <span data-ttu-id="626da-141">Вылет откроется с информацией о нулевом дне и других уязвимостях для этого программного обеспечения.</span><span class="sxs-lookup"><span data-stu-id="626da-141">A flyout will open with information about the zero-day and other vulnerabilities for that software.</span></span>

<span data-ttu-id="626da-142">Там будет ссылка на варианты смягчения и обходные пути, если они доступны.</span><span class="sxs-lookup"><span data-stu-id="626da-142">There will be a link to mitigation options and workarounds if they are available.</span></span> <span data-ttu-id="626da-143">Обходные пути могут помочь снизить риск, связанный с этой уязвимостью нулевого дня, пока не будет развернуто исправление или обновление безопасности.</span><span class="sxs-lookup"><span data-stu-id="626da-143">Workarounds may help reduce the risk posed by this zero-day vulnerability until a patch or security update can be deployed.</span></span>

<span data-ttu-id="626da-144">Откройте параметры восстановления и выберите тип внимания.</span><span class="sxs-lookup"><span data-stu-id="626da-144">Open remediation options and choose the attention type.</span></span> <span data-ttu-id="626da-145">Для уязвимостей нулевого дня рекомендуется использовать "требуемое внимание", так как обновление еще не выпущено.</span><span class="sxs-lookup"><span data-stu-id="626da-145">An "attention required" remediation option is recommended for the zero-day vulnerabilities, since an update hasn't been released yet.</span></span> <span data-ttu-id="626da-146">Вы не сможете выбрать дату выполнения, так как никаких конкретных действий не выполняется.</span><span class="sxs-lookup"><span data-stu-id="626da-146">You won't be able to select a due date, since there's no specific action to perform.</span></span> <span data-ttu-id="626da-147">Если для этого программного обеспечения существуют более старые уязвимости, которые требуется исправление, можно переопределить параметр "требуемого внимания" и выбрать "обновление".</span><span class="sxs-lookup"><span data-stu-id="626da-147">If there are older vulnerabilities for this software you wish to remediation, you can override the "attention required" remediation option and choose “update.”</span></span>

![Пример вылетов Windows Server 2016 нулевого дня на странице рекомендации по безопасности.](images/tvm-zero-day-recommendation-flyout400.png)

## <a name="track-zero-day-remediation-activities"></a><span data-ttu-id="626da-149">Отслеживание действий по устранению последствий нулевого дня</span><span class="sxs-lookup"><span data-stu-id="626da-149">Track zero-day remediation activities</span></span>

<span data-ttu-id="626da-150">Перейдите на страницу [](tvm-remediation.md) Устранение угроз и устранения уязвимостей, чтобы просмотреть элемент действия по исправлению.</span><span class="sxs-lookup"><span data-stu-id="626da-150">Go to the threat and vulnerability management [Remediation](tvm-remediation.md) page to view the remediation activity item.</span></span> <span data-ttu-id="626da-151">Если вы выбрали параметр "требуемого внимания", то не будет панели прогресса, состояния билета или даты выполнения, так как нет фактических действий, которые мы можем отслеживать.</span><span class="sxs-lookup"><span data-stu-id="626da-151">If you chose the "attention required" remediation option, there will be no progress bar, ticket status, or due date since there's no actual action we can monitor.</span></span> <span data-ttu-id="626da-152">Вы можете фильтровать по типу исправлений, например "обновление программного обеспечения" или "необходимое внимание", чтобы увидеть все элементы активности в одной категории.</span><span class="sxs-lookup"><span data-stu-id="626da-152">You can filter by remediation type, such as "software update" or "attention required," to see all activity items in the same category.</span></span>

## <a name="patching-zero-day-vulnerabilities"></a><span data-ttu-id="626da-153">Исправление уязвимостей нулевого дня</span><span class="sxs-lookup"><span data-stu-id="626da-153">Patching zero-day vulnerabilities</span></span>

<span data-ttu-id="626da-154">Когда исправление будет выпущено в нулевой день, рекомендация будет изменена на "Update" и с синей меткой рядом с ней с надписью "Новое обновление безопасности для нулевого дня".</span><span class="sxs-lookup"><span data-stu-id="626da-154">When a patch is released for the zero-day, the recommendation will be changed to “Update” and a blue label next to it that says “New security update for zero day.”</span></span> <span data-ttu-id="626da-155">Он больше не будет рассматриваться как нулевой день, тег нулевого дня будет удален со всех страниц.</span><span class="sxs-lookup"><span data-stu-id="626da-155">It will no longer consider as a zero-day, the zero-day tag will be removed from all pages.</span></span>

![Рекомендация для "Обновление Microsoft Windows 10" с помощью новой метки исправлений.](images/tvm-zero-day-patch.jpg)

## <a name="related-articles"></a><span data-ttu-id="626da-157">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="626da-157">Related articles</span></span>

- [<span data-ttu-id="626da-158">Обзор управления угрозами и уязвимостью</span><span class="sxs-lookup"><span data-stu-id="626da-158">Threat and vulnerability management overview</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="626da-159">Панель мониторинга</span><span class="sxs-lookup"><span data-stu-id="626da-159">Dashboard</span></span>](tvm-dashboard-insights.md)
- [<span data-ttu-id="626da-160">Рекомендации по безопасности</span><span class="sxs-lookup"><span data-stu-id="626da-160">Security recommendations</span></span>](tvm-security-recommendation.md)
- [<span data-ttu-id="626da-161">Инвентаризация программного обеспечения</span><span class="sxs-lookup"><span data-stu-id="626da-161">Software inventory</span></span>](tvm-software-inventory.md)
- [<span data-ttu-id="626da-162">Уязвимости в моей организации</span><span class="sxs-lookup"><span data-stu-id="626da-162">Vulnerabilities in my organization</span></span>](tvm-weaknesses.md)
