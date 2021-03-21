---
title: Предпосылки Microsoft 365 Defender
description: Узнайте о требованиях к лицензированию, оборудованию и программному обеспечению и других параметрах конфигурации для Microsoft 365 Defender
keywords: требования, необходимые условия, оборудование, программное обеспечение, браузер, MTP, M365, лицензия, E5, A5, EMS, покупка
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 0184b2c05121e1ea3bf365263df880548f1b9232
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50918874"
---
# <a name="microsoft-365-defender-prerequisites"></a><span data-ttu-id="9e35e-104">Предпосылки Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9e35e-104">Microsoft 365 Defender prerequisites</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="9e35e-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="9e35e-105">**Applies to:**</span></span>
- <span data-ttu-id="9e35e-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9e35e-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="9e35e-107">Узнайте о лицензировании и других требованиях к подготовкам и использованию [Microsoft 365 Defender.](microsoft-threat-protection.md)</span><span class="sxs-lookup"><span data-stu-id="9e35e-107">Learn about licensing and other requirements for provisioning and using [Microsoft 365 Defender](microsoft-threat-protection.md).</span></span>

## <a name="licensing-requirements"></a><span data-ttu-id="9e35e-108">Требования к лицензированию</span><span class="sxs-lookup"><span data-stu-id="9e35e-108">Licensing requirements</span></span>
<span data-ttu-id="9e35e-109">Любая из этих лицензий предоставляет доступ к функциям Microsoft 365 Defender в центре безопасности Microsoft 365 без дополнительных затрат:</span><span class="sxs-lookup"><span data-stu-id="9e35e-109">Any of these licenses gives you access to Microsoft 365 Defender features in Microsoft 365 security center without additional cost:</span></span>

- <span data-ttu-id="9e35e-110">Microsoft 365 E5 или A5</span><span class="sxs-lookup"><span data-stu-id="9e35e-110">Microsoft 365 E5 or A5</span></span>
- <span data-ttu-id="9e35e-111">Microsoft 365 E5 Security или A5 Security</span><span class="sxs-lookup"><span data-stu-id="9e35e-111">Microsoft 365 E5 Security or A5 Security</span></span>
- <span data-ttu-id="9e35e-112">Windows 10 Enterprise E5 или A5</span><span class="sxs-lookup"><span data-stu-id="9e35e-112">Windows 10 Enterprise E5 or A5</span></span>
- <span data-ttu-id="9e35e-113">Корпоративная мобильность + безопасность (EMS) E5 или A5</span><span class="sxs-lookup"><span data-stu-id="9e35e-113">Enterprise Mobility + Security (EMS) E5 or A5</span></span> 
- <span data-ttu-id="9e35e-114">Office 365 E5 или A5</span><span class="sxs-lookup"><span data-stu-id="9e35e-114">Office 365 E5 or A5</span></span>
- <span data-ttu-id="9e35e-115">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="9e35e-115">Microsoft Defender for Endpoint</span></span>
- <span data-ttu-id="9e35e-116">Microsoft Defender для удостоверений</span><span class="sxs-lookup"><span data-stu-id="9e35e-116">Microsoft Defender for Identity</span></span> 
- <span data-ttu-id="9e35e-117">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="9e35e-117">Microsoft Cloud App Security</span></span>
- <span data-ttu-id="9e35e-118">Defender for Office 365 (Plan 2)</span><span class="sxs-lookup"><span data-stu-id="9e35e-118">Defender for Office 365 (Plan 2)</span></span>

<span data-ttu-id="9e35e-119">Дополнительные сведения можно [получить в планах корпоративных служб Microsoft 365.](https://www.microsoft.com/licensing/product-licensing/microsoft-365-enterprise)</span><span class="sxs-lookup"><span data-stu-id="9e35e-119">For more information, [view the Microsoft 365 Enterprise service plans](https://www.microsoft.com/licensing/product-licensing/microsoft-365-enterprise).</span></span>

> <span data-ttu-id="9e35e-120">У вас еще нет лицензии?</span><span class="sxs-lookup"><span data-stu-id="9e35e-120">Don't have license yet?</span></span> [<span data-ttu-id="9e35e-121">Пробное использование или приобретение подписки на Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="9e35e-121">Try or buy a Microsoft 365 subscription</span></span>](../../commerce/try-or-buy-microsoft-365.md?view=o365-worldwide)

### <a name="check-your-existing--licenses"></a><span data-ttu-id="9e35e-122">Проверка существующих лицензий</span><span class="sxs-lookup"><span data-stu-id="9e35e-122">Check your existing  licenses</span></span>
<span data-ttu-id="9e35e-123">Перейдите в центр администрирования Microsoft 365[(admin.microsoft.com),](https://admin.microsoft.com/)чтобы просмотреть существующие лицензии.</span><span class="sxs-lookup"><span data-stu-id="9e35e-123">Go to Microsoft 365 admin center ([admin.microsoft.com](https://admin.microsoft.com/)) to view your existing licenses.</span></span> <span data-ttu-id="9e35e-124">В Центре администрирования выберите **Выставление счетов** > **Лицензии**.</span><span class="sxs-lookup"><span data-stu-id="9e35e-124">In the admin center, go to **Billing** > **Licenses**.</span></span>

>[!NOTE]
> <span data-ttu-id="9e35e-125">Для получения сведений о  лицензии  вам необходимо на должность администратора биллинга или глобального читателя в [Azure AD.](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles)</span><span class="sxs-lookup"><span data-stu-id="9e35e-125">You need to be assigned either the **Billing admin** or **Global reader** [role in Azure AD](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) to be able to see license information.</span></span> <span data-ttu-id="9e35e-126">Если у вас возникли проблемы с доступом, обратитесь к глобальному администратору.</span><span class="sxs-lookup"><span data-stu-id="9e35e-126">If you encounter access problems, contact a global admin.</span></span>

## <a name="required-permissions"></a><span data-ttu-id="9e35e-127">Обязательные разрешения</span><span class="sxs-lookup"><span data-stu-id="9e35e-127">Required permissions</span></span>
<span data-ttu-id="9e35e-128">Вы должны быть глобальным **администратором** или **администратором** безопасности в Azure Active Directory, чтобы включить Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="9e35e-128">You must be a **global administrator** or a **security administrator** in Azure Active Directory to turn on Microsoft 365 Defender.</span></span> <span data-ttu-id="9e35e-129">Список ролей, необходимых для использования защитника Microsoft 365, а также сведения о регулировании доступа к данным, читайте в материале Об управлении доступом к [Microsoft 365 Defender.](mtp-permissions.md)</span><span class="sxs-lookup"><span data-stu-id="9e35e-129">For the list of roles required to use Microsoft 365 Defender and information on how access to data is regulated, read about [managing access to Microsoft 365 Defender](mtp-permissions.md).</span></span>

## <a name="browser-requirements"></a><span data-ttu-id="9e35e-130">Требования к браузеру</span><span class="sxs-lookup"><span data-stu-id="9e35e-130">Browser requirements</span></span>
<span data-ttu-id="9e35e-131">Доступ к Microsoft 365 Defender в центре безопасности Microsoft 365 с помощью Microsoft Edge, Internet Explorer 11 или любого веб-браузера, совместимых с HTML 5.</span><span class="sxs-lookup"><span data-stu-id="9e35e-131">Access Microsoft 365 Defender in the Microsoft 365 security center using Microsoft Edge, Internet Explorer 11, or any HTML 5 compliant web browser.</span></span>

## <a name="availability-to-us-gcc-gcc-high-and-other-us-government-institutions"></a><span data-ttu-id="9e35e-132">Доступность для GCC, GCC High и других государственных учреждений США</span><span class="sxs-lookup"><span data-stu-id="9e35e-132">Availability to US GCC, GCC High, and other US government institutions</span></span>
<span data-ttu-id="9e35e-133">В настоящее время Защитник Microsoft 365 *не доступен* для:</span><span class="sxs-lookup"><span data-stu-id="9e35e-133">Currently, Microsoft 365 Defender is *not* available to:</span></span>
- <span data-ttu-id="9e35e-134">Облако сообщества правительства США (GCC)</span><span class="sxs-lookup"><span data-stu-id="9e35e-134">US Government Community Cloud (GCC)</span></span>
- <span data-ttu-id="9e35e-135">Облачное облако государственного сообщества США (GCC High)</span><span class="sxs-lookup"><span data-stu-id="9e35e-135">US Government Community Cloud High (GCC High)</span></span>
- <span data-ttu-id="9e35e-136">Министерство обороны США</span><span class="sxs-lookup"><span data-stu-id="9e35e-136">US Department of Defense</span></span>
- <span data-ttu-id="9e35e-137">Все государственные учреждения США с коммерческими лицензиями</span><span class="sxs-lookup"><span data-stu-id="9e35e-137">All US government institutions with commercial licenses</span></span>

## <a name="related-topics"></a><span data-ttu-id="9e35e-138">Родственные темы</span><span class="sxs-lookup"><span data-stu-id="9e35e-138">Related topics</span></span>
- [<span data-ttu-id="9e35e-139">Обзор Защитника Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="9e35e-139">Microsoft 365 Defender overview</span></span>](microsoft-threat-protection.md)
- [<span data-ttu-id="9e35e-140">Включив защитник Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="9e35e-140">Turn on Microsoft 365 Defender</span></span>](mtp-enable.md)
- [<span data-ttu-id="9e35e-141">Управление доступом и разрешениями</span><span class="sxs-lookup"><span data-stu-id="9e35e-141">Manage access and permissions</span></span>](mtp-permissions.md)