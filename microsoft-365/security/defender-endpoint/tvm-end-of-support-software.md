---
title: Планирование конечных версий программного обеспечения и программного обеспечения
description: Откройте и запланируйте для версий программного обеспечения и программного обеспечения, которые больше не поддерживаются и не будут получать обновления безопасности.
keywords: управление угрозами и уязвимостью, рекомендация по безопасности mdatp tvm, рекомендация по кибербезопасности, рекомендация по обеспечению безопасности
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
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 29adf8a542d97a981a07dac167343f3774aa5af4
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/01/2021
ms.locfileid: "51500156"
---
# <a name="plan-for-end-of-support-software-and-software-versions-with-threat-and-vulnerability-management"></a><span data-ttu-id="eade3-104">Планирование конечных версий программного обеспечения и программного обеспечения с управлением угрозами и уязвимостью</span><span class="sxs-lookup"><span data-stu-id="eade3-104">Plan for end-of-support software and software versions with threat and vulnerability management</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="eade3-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="eade3-105">**Applies to:**</span></span>

- [<span data-ttu-id="eade3-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="eade3-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="eade3-107">Управление угрозами и уязвимостями</span><span class="sxs-lookup"><span data-stu-id="eade3-107">Threat and vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="eade3-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="eade3-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="eade3-109">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="eade3-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="eade3-110">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="eade3-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

<span data-ttu-id="eade3-111">End-of-support (EOS), иначе известный как end-of-life (EOL), для программных или программных версий означает, что они больше не будут поддерживаться и не будут получать обновления безопасности.</span><span class="sxs-lookup"><span data-stu-id="eade3-111">End-of-support (EOS), otherwise known as end-of-life (EOL), for software or software versions means that they will no longer be supported or serviced, and will not receive security updates.</span></span> <span data-ttu-id="eade3-112">При использовании программных или программных версий с законченной поддержкой вы подвергаете свою организацию уязвимостям безопасности, юридическим и финансовым рискам.</span><span class="sxs-lookup"><span data-stu-id="eade3-112">When you use software or software versions with ended support, you're exposing your organization to security vulnerabilities, legal, and financial risks.</span></span>

<span data-ttu-id="eade3-113">Важно, чтобы администраторы безопасности и ИТ-администраторы работали вместе и обеспечивали настройку инвентаризации программного обеспечения организации для оптимальных результатов, соответствия требованиям и здоровой сетевой экосистемы.</span><span class="sxs-lookup"><span data-stu-id="eade3-113">It's crucial for Security and IT Administrators to work together and ensure that the organization's software inventory is configured for optimal results, compliance, and a healthy network ecosystem.</span></span> <span data-ttu-id="eade3-114">Они должны изучить варианты удаления или замены приложений, которые достигли конечной поддержки и обновления версий, которые больше не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="eade3-114">They should examine the options to remove or replace apps that have reached end-of-support and update versions that are no longer supported.</span></span> <span data-ttu-id="eade3-115">Лучше всего создать и реализовать план **до** окончания сроков поддержки.</span><span class="sxs-lookup"><span data-stu-id="eade3-115">It's best to create and implement a plan **before** the end of support dates.</span></span>

## <a name="find-software-or-software-versions-that-are-no-longer-supported"></a><span data-ttu-id="eade3-116">Поиск версий программного обеспечения или программного обеспечения, которые больше не поддерживаются</span><span class="sxs-lookup"><span data-stu-id="eade3-116">Find software or software versions that are no longer supported</span></span>

1. <span data-ttu-id="eade3-117">Из меню управления угрозами и уязвимостями перейдите к [**рекомендациям по безопасности.**](tvm-security-recommendation.md)</span><span class="sxs-lookup"><span data-stu-id="eade3-117">From the threat and vulnerability management menu, navigate to [**Security recommendations**](tvm-security-recommendation.md).</span></span>
2. <span data-ttu-id="eade3-118">Перейдите к **панели Фильтры** и найдите раздел теги.</span><span class="sxs-lookup"><span data-stu-id="eade3-118">Go to the **Filters** panel and look for the tags section.</span></span> <span data-ttu-id="eade3-119">Выберите один или несколько параметров тегов EOS.</span><span class="sxs-lookup"><span data-stu-id="eade3-119">Select one or more of the EOS tag options.</span></span> <span data-ttu-id="eade3-120">Затем **применить**.</span><span class="sxs-lookup"><span data-stu-id="eade3-120">Then **Apply**.</span></span>

    ![Снимок экрана тегов, которые говорят программное обеспечение EOS, версии EOS и предстоящие версии EOS.](images/tvm-eos-tag.png)

3. <span data-ttu-id="eade3-122">Вы увидите список рекомендаций, связанных с программным обеспечением с конечной поддержкой, версиями программного обеспечения, завершающим поддержку, или версиями с предстоящим завершением поддержки.</span><span class="sxs-lookup"><span data-stu-id="eade3-122">You'll see a list of recommendations related to software with ended support, software versions that are end of support, or versions with upcoming end of support.</span></span> <span data-ttu-id="eade3-123">Эти теги также видны на странице инвентаризации [программного](tvm-software-inventory.md) обеспечения.</span><span class="sxs-lookup"><span data-stu-id="eade3-123">These tags are also visible in the [software inventory](tvm-software-inventory.md) page.</span></span>

    ![Рекомендации с тегом EOS.](images/tvm-eos-tags-column.png)

## <a name="list-of-versions-and-dates"></a><span data-ttu-id="eade3-125">Список версий и дат</span><span class="sxs-lookup"><span data-stu-id="eade3-125">List of versions and dates</span></span>

<span data-ttu-id="eade3-126">Чтобы просмотреть список версий, которые скоро достигли окончания поддержки или окончания или поддержки, а также эти даты, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="eade3-126">To view a list of versions that have reached end of support, or end or support soon, and those dates, follow the below steps:</span></span>

1. <span data-ttu-id="eade3-127">Сообщение появится в вылете рекомендации по безопасности для программного обеспечения с версиями, которые достигли конца поддержки или скоро достигнут конца поддержки.</span><span class="sxs-lookup"><span data-stu-id="eade3-127">A message will appear in the security recommendation flyout for software with versions that have reached end of support, or will reach end of support soon.</span></span>

    ![Снимок экрана ссылки на рассылку версий.](images/eos-upcoming-eos.png)

2. <span data-ttu-id="eade3-129">Выберите **ссылку на рассылку** версий, чтобы перейти на страницу сверла программного обеспечения.</span><span class="sxs-lookup"><span data-stu-id="eade3-129">Select the **version distribution** link to go to the software drill-down page.</span></span> <span data-ttu-id="eade3-130">Там можно увидеть фильтрованный список версий с тегами, идентифицирующие их как конец поддержки или предстоящий конец поддержки.</span><span class="sxs-lookup"><span data-stu-id="eade3-130">There, you can see a filtered list of versions with tags identifying them as end of support, or upcoming end of support.</span></span>

    ![Снимок экрана страницы сверления программного обеспечения с окончанием программного обеспечения поддержки.](images/software-drilldown-eos.png)

3. <span data-ttu-id="eade3-132">Выберите одну из версий в таблице для открытия.</span><span class="sxs-lookup"><span data-stu-id="eade3-132">Select one of the versions in the table to open.</span></span> <span data-ttu-id="eade3-133">Например, версия 10.0.18362.1.</span><span class="sxs-lookup"><span data-stu-id="eade3-133">For example, version 10.0.18362.1.</span></span> <span data-ttu-id="eade3-134">Вылет появится с окончанием даты поддержки.</span><span class="sxs-lookup"><span data-stu-id="eade3-134">A flyout will appear with the end of support date.</span></span>

    ![Снимок экрана даты окончания поддержки.](images/version-eos-date.png)

<span data-ttu-id="eade3-136">После того как вы определите, какие версии программного обеспечения и программного обеспечения уязвимы из-за их состояния поддержки, необходимо решить, обновлять или удалять их из организации.</span><span class="sxs-lookup"><span data-stu-id="eade3-136">Once you identify which software and software versions are vulnerable due to their end-of-support status, you must decide whether to update or remove them from your organization.</span></span> <span data-ttu-id="eade3-137">Это позволит снизить уровень уязвимостей и постоянных угроз для организаций.</span><span class="sxs-lookup"><span data-stu-id="eade3-137">Doing so will lower your organizations exposure to vulnerabilities and advanced persistent threats.</span></span>

## <a name="related-topics"></a><span data-ttu-id="eade3-138">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="eade3-138">Related topics</span></span>

- [<span data-ttu-id="eade3-139">Обзор управления угрозами и уязвимостью</span><span class="sxs-lookup"><span data-stu-id="eade3-139">Threat and vulnerability management overview</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="eade3-140">Рекомендации по безопасности</span><span class="sxs-lookup"><span data-stu-id="eade3-140">Security recommendations</span></span>](tvm-security-recommendation.md)
- [<span data-ttu-id="eade3-141">Инвентаризация программного обеспечения</span><span class="sxs-lookup"><span data-stu-id="eade3-141">Software inventory</span></span>](tvm-software-inventory.md)
