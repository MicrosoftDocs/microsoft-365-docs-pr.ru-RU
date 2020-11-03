---
title: Предварительные требования для защитника Microsoft 365
description: Сведения о лицензировании, требованиях к оборудованию и программному обеспечению, а также другие параметры конфигурации для защитника Microsoft 365
keywords: требования, предварительные требования, оборудование, программное обеспечение, браузер, MTP, M365, лицензия,, A5, A5, EMS, покупка
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: 415cdb79a6aa9371ee2f07de579cfb2f873f1acb
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/03/2020
ms.locfileid: "48844780"
---
# <a name="microsoft-365-defender-prerequisites"></a><span data-ttu-id="63e69-104">Предварительные требования для защитника Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="63e69-104">Microsoft 365 Defender prerequisites</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="63e69-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="63e69-105">**Applies to:**</span></span>
- <span data-ttu-id="63e69-106">Защитник Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="63e69-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="63e69-107">Сведения о лицензировании и других требованиях для подготовки и использования [защитника Microsoft 365](microsoft-threat-protection.md).</span><span class="sxs-lookup"><span data-stu-id="63e69-107">Learn about licensing and other requirements for provisioning and using [Microsoft 365 Defender](microsoft-threat-protection.md).</span></span>

## <a name="licensing-requirements"></a><span data-ttu-id="63e69-108">Требования к лицензированию</span><span class="sxs-lookup"><span data-stu-id="63e69-108">Licensing requirements</span></span>
<span data-ttu-id="63e69-109">Любая из этих лицензий предоставляет доступ к функциям защитника Microsoft 365 в центре безопасности Майкрософт 365 без дополнительных затрат:</span><span class="sxs-lookup"><span data-stu-id="63e69-109">Any of these licenses gives you access to Microsoft 365 Defender features in Microsoft 365 security center without additional cost:</span></span>

- <span data-ttu-id="63e69-110">Microsoft 365 в ~ или A5</span><span class="sxs-lookup"><span data-stu-id="63e69-110">Microsoft 365 E5 or A5</span></span>
- <span data-ttu-id="63e69-111">Microsoft 365 и безопасность A5</span><span class="sxs-lookup"><span data-stu-id="63e69-111">Microsoft 365 E5 Security or A5 Security</span></span>
- <span data-ttu-id="63e69-112">Windows 10 Корпоративная ячейка = или A5</span><span class="sxs-lookup"><span data-stu-id="63e69-112">Windows 10 Enterprise E5 or A5</span></span>
- <span data-ttu-id="63e69-113">Enterprise Mobility + Security (EMS), а также A5</span><span class="sxs-lookup"><span data-stu-id="63e69-113">Enterprise Mobility + Security (EMS) E5 or A5</span></span> 
- <span data-ttu-id="63e69-114">Office 365 в ~ или A5</span><span class="sxs-lookup"><span data-stu-id="63e69-114">Office 365 E5 or A5</span></span>
- <span data-ttu-id="63e69-115">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="63e69-115">Microsoft Defender for Endpoint</span></span>
- <span data-ttu-id="63e69-116">Microsoft Defender для удостоверений</span><span class="sxs-lookup"><span data-stu-id="63e69-116">Microsoft Defender for Identity</span></span> 
- <span data-ttu-id="63e69-117">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="63e69-117">Microsoft Cloud App Security</span></span>
- <span data-ttu-id="63e69-118">Защитник для Office 365 (план 2)</span><span class="sxs-lookup"><span data-stu-id="63e69-118">Defender for Office 365 (Plan 2)</span></span>

> [!NOTE]
> <span data-ttu-id="63e69-119">Пробные лицензии для Office 365 в настоящее время не предоставляют доступ к защитнику Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="63e69-119">Trial licenses for Office 365 currently do not provide access to Microsoft 365 Defender.</span></span>

<span data-ttu-id="63e69-120">Дополнительные сведения см. [в планах корпоративных служб Microsoft 365](https://www.microsoft.com/licensing/product-licensing/microsoft-365-enterprise).</span><span class="sxs-lookup"><span data-stu-id="63e69-120">For more information, [view the Microsoft 365 Enterprise service plans](https://www.microsoft.com/licensing/product-licensing/microsoft-365-enterprise).</span></span>

> <span data-ttu-id="63e69-121">У вас еще нет лицензии?</span><span class="sxs-lookup"><span data-stu-id="63e69-121">Don't have license yet?</span></span> [<span data-ttu-id="63e69-122">Пробное использование или приобретение подписки на Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="63e69-122">Try or buy a Microsoft 365 subscription</span></span>](https://docs.microsoft.com/microsoft-365/commerce/try-or-buy-microsoft-365?view=o365-worldwide)

### <a name="check-your-existing--licenses"></a><span data-ttu-id="63e69-123">Проверка существующих лицензий</span><span class="sxs-lookup"><span data-stu-id="63e69-123">Check your existing  licenses</span></span>
<span data-ttu-id="63e69-124">Перейдите в центр администрирования Microsoft 365 ([Admin.Microsoft.com](https://admin.microsoft.com/)), чтобы просмотреть существующие лицензии.</span><span class="sxs-lookup"><span data-stu-id="63e69-124">Go to Microsoft 365 admin center ([admin.microsoft.com](https://admin.microsoft.com/)) to view your existing licenses.</span></span> <span data-ttu-id="63e69-125">В Центре администрирования выберите **Выставление счетов** > **Лицензии**.</span><span class="sxs-lookup"><span data-stu-id="63e69-125">In the admin center, go to **Billing** > **Licenses**.</span></span>

>[!NOTE]
> <span data-ttu-id="63e69-126">Для просмотра сведений о лицензии необходимо назначить роль **администратора выставления счетов** или роль **глобального читателя** [в Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) .</span><span class="sxs-lookup"><span data-stu-id="63e69-126">You need to be assigned either the **Billing admin** or **Global reader** [role in Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) to be able to see license information.</span></span> <span data-ttu-id="63e69-127">Если у вас возникли проблемы с доступом, обратитесь к глобальному администратору.</span><span class="sxs-lookup"><span data-stu-id="63e69-127">If you encounter access problems, contact a global admin.</span></span>

## <a name="required-permissions"></a><span data-ttu-id="63e69-128">Обязательные разрешения</span><span class="sxs-lookup"><span data-stu-id="63e69-128">Required permissions</span></span>
<span data-ttu-id="63e69-129">Чтобы включить защитник Microsoft 365, необходимо быть **глобальным администратором** или **администратором безопасности** в Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="63e69-129">You must be a **global administrator** or a **security administrator** in Azure Active Directory to turn on Microsoft 365 Defender.</span></span> <span data-ttu-id="63e69-130">Список ролей, необходимых для использования защитника Microsoft 365, и сведения о контролируемом доступе к данным, читайте в статье [Управление доступом к защитнику microsoft 365](mtp-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="63e69-130">For the list of roles required to use Microsoft 365 Defender and information on how access to data is regulated, read about [managing access to Microsoft 365 Defender](mtp-permissions.md).</span></span>

## <a name="browser-requirements"></a><span data-ttu-id="63e69-131">Требования к браузеру</span><span class="sxs-lookup"><span data-stu-id="63e69-131">Browser requirements</span></span>
<span data-ttu-id="63e69-132">Доступ к защитнику Microsoft 365 в центре безопасности Майкрософт 365 с помощью Microsoft EDGE, Internet Explorer 11 или любого совместимого с HTML 5 веб-браузера.</span><span class="sxs-lookup"><span data-stu-id="63e69-132">Access Microsoft 365 Defender in the Microsoft 365 security center using Microsoft Edge, Internet Explorer 11, or any HTML 5 compliant web browser.</span></span>

## <a name="availability-to-us-gcc-gcc-high-and-other-us-government-institutions"></a><span data-ttu-id="63e69-133">Доступность для государственных учреждений США, а также других учреждений и других учреждений США</span><span class="sxs-lookup"><span data-stu-id="63e69-133">Availability to US GCC, GCC High, and other US government institutions</span></span>
<span data-ttu-id="63e69-134">В настоящее время защитник Microsoft 365 *недоступен* для следующих компонентов:</span><span class="sxs-lookup"><span data-stu-id="63e69-134">Currently, Microsoft 365 Defender is *not* available to:</span></span>
- <span data-ttu-id="63e69-135">Облако сообщества для государственных организаций США (GCC)</span><span class="sxs-lookup"><span data-stu-id="63e69-135">US Government Community Cloud (GCC)</span></span>
- <span data-ttu-id="63e69-136">Высококачественное облако сообщества США (GCC High)</span><span class="sxs-lookup"><span data-stu-id="63e69-136">US Government Community Cloud High (GCC High)</span></span>
- <span data-ttu-id="63e69-137">Отдел обороны США</span><span class="sxs-lookup"><span data-stu-id="63e69-137">US Department of Defense</span></span>
- <span data-ttu-id="63e69-138">Все правительственные учреждения США с коммерческими лицензиями</span><span class="sxs-lookup"><span data-stu-id="63e69-138">All US government institutions with commercial licenses</span></span>

## <a name="related-topics"></a><span data-ttu-id="63e69-139">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="63e69-139">Related topics</span></span>
- [<span data-ttu-id="63e69-140">Обзор защитника Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="63e69-140">Microsoft 365 Defender overview</span></span>](microsoft-threat-protection.md)
- [<span data-ttu-id="63e69-141">Включение защитника Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="63e69-141">Turn on Microsoft 365 Defender</span></span>](mtp-enable.md)
- [<span data-ttu-id="63e69-142">Управление доступом и разрешениями</span><span class="sxs-lookup"><span data-stu-id="63e69-142">Manage access and permissions</span></span>](mtp-permissions.md)
