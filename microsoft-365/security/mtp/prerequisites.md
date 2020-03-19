---
title: Предварительные требования для Защиты от угроз (Майкрософт)
description: Сведения о лицензировании, требованиях к оборудованию и программному обеспечению, а также других параметрах конфигурации Защиты от угроз (Майкрософт)
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
ms.openlocfilehash: c482e46cf51cbf11960c02663221df0c136b067c
ms.sourcegitcommit: fe4beef350ef9f39b1098755cff46fa2b8e7dc4d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2020
ms.locfileid: "42857183"
---
# <a name="microsoft-threat-protection-prerequisites"></a><span data-ttu-id="1f51a-104">Предварительные требования для Защиты от угроз (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="1f51a-104">Microsoft Threat Protection prerequisites</span></span>

<span data-ttu-id="1f51a-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="1f51a-105">**Applies to:**</span></span>
- <span data-ttu-id="1f51a-106">Защита от угроз (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="1f51a-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="1f51a-107">Сведения о лицензировании, требованиях к оборудованию и программному обеспечению, а также другие параметры конфигурации для подготовки и использования защиты от угроз Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="1f51a-107">Learn about the licensing, hardware and software requirements, and other configuration settings to provision and use Microsoft Threat Protection.</span></span>

## <a name="licensing-requirements"></a><span data-ttu-id="1f51a-108">Требования к лицензированию</span><span class="sxs-lookup"><span data-stu-id="1f51a-108">Licensing requirements</span></span>
<span data-ttu-id="1f51a-109">Для использования защиты от угроз Майкрософт необходима одна или несколько лицензий.</span><span class="sxs-lookup"><span data-stu-id="1f51a-109">To use Microsoft Threat Protection, you need either a single license or a combination of licenses.</span></span>

### <a name="single-license"></a><span data-ttu-id="1f51a-110">Одна лицензия</span><span class="sxs-lookup"><span data-stu-id="1f51a-110">Single license</span></span>
<span data-ttu-id="1f51a-111">Вы можете использовать *одну* из следующих лицензий:</span><span class="sxs-lookup"><span data-stu-id="1f51a-111">You can use *one* of the following licenses:</span></span>

- <span data-ttu-id="1f51a-112">Microsoft 365 в ~ или A5</span><span class="sxs-lookup"><span data-stu-id="1f51a-112">Microsoft 365 E5 or A5</span></span>
- <span data-ttu-id="1f51a-113">Microsoft 365 и безопасность A5</span><span class="sxs-lookup"><span data-stu-id="1f51a-113">Microsoft 365 E5 Security or A5 Security</span></span>

### <a name="combination-of-licenses"></a><span data-ttu-id="1f51a-114">Комбинация лицензий</span><span class="sxs-lookup"><span data-stu-id="1f51a-114">Combination of licenses</span></span>
<span data-ttu-id="1f51a-115">Вы также можете использовать комбинацию лицензий для подписок "е" и "A5" до Office 365, *Enterprise Mobility + Security (EMS)* и Windows.</span><span class="sxs-lookup"><span data-stu-id="1f51a-115">You can also use a combination of licenses for E5 or A5 subscriptions to Office 365, *Enterprise Mobility + Security (EMS)*, and Windows.</span></span> <span data-ttu-id="1f51a-116">Эта комбинация лицензий должна включать *все* эти лицензии:</span><span class="sxs-lookup"><span data-stu-id="1f51a-116">The license combination must include *all* of these licenses:</span></span>

- <span data-ttu-id="1f51a-117">Office 365 в ~ или A5</span><span class="sxs-lookup"><span data-stu-id="1f51a-117">Office 365 E5 or A5</span></span>
- <span data-ttu-id="1f51a-118">*Enterprise Mobility + Security (EMS)* "Е" или "A5"</span><span class="sxs-lookup"><span data-stu-id="1f51a-118">*Enterprise Mobility + Security (EMS)* E5 or A5</span></span>
- <span data-ttu-id="1f51a-119">Windows, "~" и "A5"</span><span class="sxs-lookup"><span data-stu-id="1f51a-119">Windows E5 or A5</span></span>

<span data-ttu-id="1f51a-120">Дополнительные сведения см. [в планах корпоративных служб Microsoft 365](https://www.microsoft.com/licensing/product-licensing/microsoft-365-enterprise).</span><span class="sxs-lookup"><span data-stu-id="1f51a-120">For more information, [view the Microsoft 365 Enterprise service plans](https://www.microsoft.com/licensing/product-licensing/microsoft-365-enterprise).</span></span>

> <span data-ttu-id="1f51a-121">У вас еще нет лицензии?</span><span class="sxs-lookup"><span data-stu-id="1f51a-121">Don't have license yet?</span></span> [<span data-ttu-id="1f51a-122">Попробуйте или купите подписку на Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="1f51a-122">Try or buy a Microsoft 365 subscription</span></span>](https://docs.microsoft.com/microsoft-365/commerce/try-or-buy-microsoft-365?view=o365-worldwide)

### <a name="check-your-existing--licenses"></a><span data-ttu-id="1f51a-123">Проверка существующих лицензий</span><span class="sxs-lookup"><span data-stu-id="1f51a-123">Check your existing  licenses</span></span>
<span data-ttu-id="1f51a-124">Перейдите в центр администрирования Microsoft 365 ([Admin.Microsoft.com](https://admin.microsoft.com/)), чтобы просмотреть существующие лицензии.</span><span class="sxs-lookup"><span data-stu-id="1f51a-124">Go to Microsoft 365 admin center ([admin.microsoft.com](https://admin.microsoft.com/)) to view your existing licenses.</span></span> <span data-ttu-id="1f51a-125">В Центре администрирования выберите **Выставление счетов** > **Лицензии**.</span><span class="sxs-lookup"><span data-stu-id="1f51a-125">In the admin center, go to **Billing** > **Licenses**.</span></span>

>[!NOTE]
> <span data-ttu-id="1f51a-126">Для просмотра сведений о лицензии необходимо назначить роль **администратора выставления счетов** или роль **глобального читателя** [в Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) .</span><span class="sxs-lookup"><span data-stu-id="1f51a-126">You need to be assigned either the **Billing admin** or **Global reader** [role in Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) to be able to see license information.</span></span> <span data-ttu-id="1f51a-127">Если у вас возникли проблемы с доступом, обратитесь к глобальному администратору.</span><span class="sxs-lookup"><span data-stu-id="1f51a-127">If you encounter access problems, contact a global admin.</span></span>

## <a name="browser-requirements"></a><span data-ttu-id="1f51a-128">Требования к браузеру</span><span class="sxs-lookup"><span data-stu-id="1f51a-128">Browser requirements</span></span>
<span data-ttu-id="1f51a-129">Доступ к защите от угроз Майкрософт в центре безопасности Microsoft 365 с помощью Microsoft EDGE, Internet Explorer 11 или любого совместимого с HTML 5 веб-браузера.</span><span class="sxs-lookup"><span data-stu-id="1f51a-129">Access Microsoft Threat Protection in the Microsoft 365 security center using Microsoft Edge, Internet Explorer 11, or any HTML 5 compliant web browser.</span></span>

## <a name="microsoft-threat-protection-for-us-government-community-cloud-and-us-government-community-cloud-high-gcc-high-customers"></a><span data-ttu-id="1f51a-130">Защита от угроз Майкрософт для облачных сообществ США и облачных пользователей Office для государственных учреждений (GCC высокая)</span><span class="sxs-lookup"><span data-stu-id="1f51a-130">Microsoft Threat Protection for US Government Community Cloud and US Government Community Cloud High (GCC High) customers</span></span>
<span data-ttu-id="1f51a-131">В настоящее время защита от угроз Майкрософт недоступна для клиентов GCC и GCC High.</span><span class="sxs-lookup"><span data-stu-id="1f51a-131">Currently, Microsoft Threat Protection is not available to US GCC and GCC High customers.</span></span> 

## <a name="related-topics"></a><span data-ttu-id="1f51a-132">См. также</span><span class="sxs-lookup"><span data-stu-id="1f51a-132">Related topics</span></span>
- [<span data-ttu-id="1f51a-133">Обзор Защиты от угроз (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="1f51a-133">Microsoft Threat Protection overview</span></span>](microsoft-threat-protection.md)
- [<span data-ttu-id="1f51a-134">Включение Защиты от угроз (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="1f51a-134">Turn on Microsoft Threat Protection</span></span>](mtp-enable.md)
