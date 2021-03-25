---
title: Настройка возможностей автоматического расследования и устранения последствий
description: Настройка возможностей автоматического расследования и исправлений в Microsoft Defender для конечной точки.
keywords: настройка, настройка, автоматизация, исследование, обнаружение, оповещения, исправление, ответ
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: deniseb
author: denisebmsft
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: how-to
ms.date: 01/27/2021
ms.reviewer: ramarom, evaldm, isco, mabraitm, chriggs
ms.openlocfilehash: 31a1c79440a8c1edc2bc8e2f2a163ded2a92fd64
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2021
ms.locfileid: "51165769"
---
# <a name="configure-automated-investigation-and-remediation-capabilities-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="23ccc-104">Настройка возможностей автоматического расследования и исправлений в Microsoft Defender для endpoint</span><span class="sxs-lookup"><span data-stu-id="23ccc-104">Configure automated investigation and remediation capabilities in Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="23ccc-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="23ccc-105">**Applies to:**</span></span>
- [<span data-ttu-id="23ccc-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="23ccc-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="23ccc-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="23ccc-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="23ccc-108">Хотите испытать Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="23ccc-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="23ccc-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="23ccc-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

<span data-ttu-id="23ccc-110">Если ваша организация использует [Microsoft Defender для конечной](https://docs.microsoft.com/windows/security/threat-protection/) точки (Defender для конечной точки), [](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/automated-investigations) возможности автоматического расследования и восстановления могут сэкономить время и усилия группы операций безопасности.</span><span class="sxs-lookup"><span data-stu-id="23ccc-110">If your organization is using [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/) (Defender for Endpoint), [automated investigation and remediation capabilities](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/automated-investigations) can save your security operations team time and effort.</span></span> <span data-ttu-id="23ccc-111">Как описано в [этом](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/enhance-your-soc-with-microsoft-defender-atp-automatic/ba-p/848946)блоге, эти возможности имитируют идеальные действия аналитика безопасности для расследования и устранения угроз.</span><span class="sxs-lookup"><span data-stu-id="23ccc-111">As outlined in [this blog post](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/enhance-your-soc-with-microsoft-defender-atp-automatic/ba-p/848946), these capabilities mimic the ideal steps that a security analyst takes to investigate and remediate threats.</span></span> <span data-ttu-id="23ccc-112">[Узнайте больше об автоматическом расследовании и исправлении.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/automated-investigations)</span><span class="sxs-lookup"><span data-stu-id="23ccc-112">[Learn more about automated investigation and remediation](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/automated-investigations).</span></span> 

<span data-ttu-id="23ccc-113">Чтобы настроить автоматическое расследование и исправление,</span><span class="sxs-lookup"><span data-stu-id="23ccc-113">To configure automated investigation and remediation,</span></span>
1. <span data-ttu-id="23ccc-114">[Включаем функции;](#turn-on-automated-investigation-and-remediation) и</span><span class="sxs-lookup"><span data-stu-id="23ccc-114">[Turn on the features](#turn-on-automated-investigation-and-remediation); and</span></span> 
2. <span data-ttu-id="23ccc-115">[Настройка групп устройств.](#set-up-device-groups)</span><span class="sxs-lookup"><span data-stu-id="23ccc-115">[Set up device groups](#set-up-device-groups).</span></span>

## <a name="turn-on-automated-investigation-and-remediation"></a><span data-ttu-id="23ccc-116">Включаем автоматическое расследование и исправление</span><span class="sxs-lookup"><span data-stu-id="23ccc-116">Turn on automated investigation and remediation</span></span>

1. <span data-ttu-id="23ccc-117">В качестве глобального администратора или администратора безопасности перейдите в Центр безопасности Защитника Майкрософт () и [https://securitycenter.windows.com](https://securitycenter.windows.com) войдите.</span><span class="sxs-lookup"><span data-stu-id="23ccc-117">As a global administrator or security administrator, go to the Microsoft Defender Security Center ([https://securitycenter.windows.com](https://securitycenter.windows.com)) and sign in.</span></span>
2. <span data-ttu-id="23ccc-118">В области навигации выберите **Параметры**.</span><span class="sxs-lookup"><span data-stu-id="23ccc-118">In the navigation pane, choose **Settings**.</span></span>
3. <span data-ttu-id="23ccc-119">В разделе **Общие** выберите **расширенные функции**.</span><span class="sxs-lookup"><span data-stu-id="23ccc-119">In the **General** section, select **Advanced features**.</span></span>
4. <span data-ttu-id="23ccc-120">Включаем **автоматическое расследование** **и автоматически разрешаем оповещения.**</span><span class="sxs-lookup"><span data-stu-id="23ccc-120">Turn on both **Automated Investigation** and **Automatically resolve alerts**.</span></span>

## <a name="set-up-device-groups"></a><span data-ttu-id="23ccc-121">Настройка групп устройств</span><span class="sxs-lookup"><span data-stu-id="23ccc-121">Set up device groups</span></span>

1. <span data-ttu-id="23ccc-122">В Центре безопасности Защитника Майкрософт (), на [https://securitycenter.windows.com](https://securitycenter.windows.com) странице **Параметры,** в **статье Permissions,** выберите **группы устройств.**</span><span class="sxs-lookup"><span data-stu-id="23ccc-122">In the Microsoft Defender Security Center ([https://securitycenter.windows.com](https://securitycenter.windows.com)), on the **Settings** page, under **Permissions**, select **Device groups**.</span></span>
2. <span data-ttu-id="23ccc-123">Выберите **+ Добавить группу устройств.**</span><span class="sxs-lookup"><span data-stu-id="23ccc-123">Select **+ Add device group**.</span></span>
3. <span data-ttu-id="23ccc-124">Создайте по крайней мере одну группу устройств следующим образом:</span><span class="sxs-lookup"><span data-stu-id="23ccc-124">Create at least one device group, as follows:</span></span>
   - <span data-ttu-id="23ccc-125">Укажите имя и описание группы устройств.</span><span class="sxs-lookup"><span data-stu-id="23ccc-125">Specify a name and description for the device group.</span></span>
   - <span data-ttu-id="23ccc-126">В **списке уровень автоматизации** выберите уровень, например Full — автоматически устраняйте **угрозы.**</span><span class="sxs-lookup"><span data-stu-id="23ccc-126">In the **Automation level list**, select a level, such as **Full – remediate threats automatically**.</span></span> <span data-ttu-id="23ccc-127">Уровень автоматизации определяет, принимаются ли действия по исправлению автоматически или только после утверждения.</span><span class="sxs-lookup"><span data-stu-id="23ccc-127">The automation level determines whether remediation actions are taken automatically, or only upon approval.</span></span> <span data-ttu-id="23ccc-128">Дополнительные статьи см. в [статьи Уровни автоматизации в автоматизированном расследовании и исправлении.](automation-levels.md)</span><span class="sxs-lookup"><span data-stu-id="23ccc-128">To learn more, see [Automation levels in automated investigation and remediation](automation-levels.md).</span></span>
   - <span data-ttu-id="23ccc-129">В разделе **Члены** используйте одно или несколько условий для идентификации и включаем устройства.</span><span class="sxs-lookup"><span data-stu-id="23ccc-129">In the **Members** section, use one or more conditions to identify and include devices.</span></span>
   - <span data-ttu-id="23ccc-130">На **вкладке Доступ** пользователя выберите группы [Azure Active Directory,](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-manage-groups?context=azure/active-directory/users-groups-roles/context/ugr-context) которые должны иметь доступ к создаемой группе устройств.</span><span class="sxs-lookup"><span data-stu-id="23ccc-130">On the **User access** tab, select the [Azure Active Directory groups](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-manage-groups?context=azure/active-directory/users-groups-roles/context/ugr-context) who should have access to the device group you're creating.</span></span>
4. <span data-ttu-id="23ccc-131">Выберите **Готово,** когда вы закончите настройку группы устройств.</span><span class="sxs-lookup"><span data-stu-id="23ccc-131">Select **Done** when you're finished setting up your device group.</span></span>

## <a name="next-steps"></a><span data-ttu-id="23ccc-132">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="23ccc-132">Next steps</span></span>

- [<span data-ttu-id="23ccc-133">Посетите Центр действий, чтобы просмотреть ожидающих и завершенных действий по исправлению</span><span class="sxs-lookup"><span data-stu-id="23ccc-133">Visit the Action Center to view pending and completed remediation actions</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/auto-investigation-action-center#the-action-center)
- [<span data-ttu-id="23ccc-134">Просмотр и утверждение ожидающих действий</span><span class="sxs-lookup"><span data-stu-id="23ccc-134">Review and approve pending actions</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/manage-auto-investigation)

## <a name="see-also"></a><span data-ttu-id="23ccc-135">См. также</span><span class="sxs-lookup"><span data-stu-id="23ccc-135">See also</span></span>

- [<span data-ttu-id="23ccc-136">Устранение ложных срабатыва-минусов в Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="23ccc-136">Address false positives/negatives in Microsoft Defender for Endpoint</span></span>](defender-endpoint-false-positives-negatives.md)
