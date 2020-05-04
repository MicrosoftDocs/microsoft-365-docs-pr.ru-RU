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
ms.openlocfilehash: dfc2136f04ed128fc655386c6eef7b91c5e5ef3a
ms.sourcegitcommit: bd8d55f82ca008af1b93a9bb4d1545f68e8188ad
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2020
ms.locfileid: "44011281"
---
# <a name="microsoft-threat-protection-prerequisites"></a><span data-ttu-id="1c0a0-104">Предварительные требования для Защиты от угроз (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="1c0a0-104">Microsoft Threat Protection prerequisites</span></span>

<span data-ttu-id="1c0a0-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="1c0a0-105">**Applies to:**</span></span>
- <span data-ttu-id="1c0a0-106">Защита от угроз (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="1c0a0-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="1c0a0-107">Сведения о лицензировании, требованиях к оборудованию и программному обеспечению, а также другие параметры конфигурации для подготовки и использования защиты от угроз Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="1c0a0-107">Learn about the licensing, hardware and software requirements, and other configuration settings to provision and use Microsoft Threat Protection.</span></span>

## <a name="licensing-requirements"></a><span data-ttu-id="1c0a0-108">Требования к лицензированию</span><span class="sxs-lookup"><span data-stu-id="1c0a0-108">Licensing requirements</span></span>

>[!IMPORTANT]
><span data-ttu-id="1c0a0-109">Начиная с 3 мая 2020 г. Корпорация Майкрософт постепенно выполнит развертывание новых, оптимизированных возможностей лицензирования и [включения защиты от угроз Майкрософт](mtp-enable.md).</span><span class="sxs-lookup"><span data-stu-id="1c0a0-109">Starting May 3, 2020, Microsoft will gradually roll out new, optimized experiences around licensing requirements and [turning on Microsoft Threat Protection](mtp-enable.md).</span></span> <span data-ttu-id="1c0a0-110">В течение нескольких недель в течение этого периода некоторые клиенты начнут видеть изменения в интерфейсах портала.</span><span class="sxs-lookup"><span data-stu-id="1c0a0-110">For several weeks during this period, some customers will start to see changes to their portal experiences.</span></span> <span data-ttu-id="1c0a0-111">Сведения о новых возможностях помечаются **новым интерфейсом** в этой статье.</span><span class="sxs-lookup"><span data-stu-id="1c0a0-111">Information about the new experiences are marked **New experience** in this article.</span></span>

<span data-ttu-id="1c0a0-112">Для использования защиты от угроз Майкрософт необходима одна или несколько лицензий.</span><span class="sxs-lookup"><span data-stu-id="1c0a0-112">To use Microsoft Threat Protection, you need either a single license or a combination of licenses.</span></span> <span data-ttu-id="1c0a0-113">Эти лицензии или сочетания лицензий предоставляют доступ к функциям защиты от угроз Майкрософт без дополнительных затрат.</span><span class="sxs-lookup"><span data-stu-id="1c0a0-113">These licenses or license combinations give you access to Microsoft Threat Protection features without additional cost.</span></span>

### <a name="single-license"></a><span data-ttu-id="1c0a0-114">Одна лицензия</span><span class="sxs-lookup"><span data-stu-id="1c0a0-114">Single license</span></span>
<span data-ttu-id="1c0a0-115">Вы можете использовать *одну* из следующих лицензий:</span><span class="sxs-lookup"><span data-stu-id="1c0a0-115">You can use *one* of the following licenses:</span></span>

- <span data-ttu-id="1c0a0-116">Microsoft 365 в ~ или A5</span><span class="sxs-lookup"><span data-stu-id="1c0a0-116">Microsoft 365 E5 or A5</span></span>
- <span data-ttu-id="1c0a0-117">Microsoft 365 и безопасность A5</span><span class="sxs-lookup"><span data-stu-id="1c0a0-117">Microsoft 365 E5 Security or A5 Security</span></span>

### <a name="combination-of-licenses"></a><span data-ttu-id="1c0a0-118">Комбинация лицензий</span><span class="sxs-lookup"><span data-stu-id="1c0a0-118">Combination of licenses</span></span>
<span data-ttu-id="1c0a0-119">Вы также можете использовать комбинацию лицензий для подписок "е" и "A5" до Office 365, *Enterprise Mobility + Security (EMS)* и Windows.</span><span class="sxs-lookup"><span data-stu-id="1c0a0-119">You can also use a combination of licenses for E5 or A5 subscriptions to Office 365, *Enterprise Mobility + Security (EMS)*, and Windows.</span></span> <span data-ttu-id="1c0a0-120">Эта комбинация лицензий должна включать *все* эти лицензии:</span><span class="sxs-lookup"><span data-stu-id="1c0a0-120">The license combination must include *all* of these licenses:</span></span>

- <span data-ttu-id="1c0a0-121">Office 365 в ~ или A5</span><span class="sxs-lookup"><span data-stu-id="1c0a0-121">Office 365 E5 or A5</span></span>
- <span data-ttu-id="1c0a0-122">*Enterprise Mobility + Security (EMS)* "Е" или "A5"</span><span class="sxs-lookup"><span data-stu-id="1c0a0-122">*Enterprise Mobility + Security (EMS)* E5 or A5</span></span>
- <span data-ttu-id="1c0a0-123">Windows 10 Корпоративная ячейка = или A5</span><span class="sxs-lookup"><span data-stu-id="1c0a0-123">Windows 10 Enterprise E5 or A5</span></span>

<span data-ttu-id="1c0a0-124">Дополнительные сведения см. [в планах корпоративных служб Microsoft 365](https://www.microsoft.com/licensing/product-licensing/microsoft-365-enterprise).</span><span class="sxs-lookup"><span data-stu-id="1c0a0-124">For more information, [view the Microsoft 365 Enterprise service plans](https://www.microsoft.com/licensing/product-licensing/microsoft-365-enterprise).</span></span>

> <span data-ttu-id="1c0a0-125">У вас еще нет лицензии?</span><span class="sxs-lookup"><span data-stu-id="1c0a0-125">Don't have license yet?</span></span> [<span data-ttu-id="1c0a0-126">Пробное использование или приобретение подписки на Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="1c0a0-126">Try or buy a Microsoft 365 subscription</span></span>](https://docs.microsoft.com/microsoft-365/commerce/try-or-buy-microsoft-365?view=o365-worldwide)


<span data-ttu-id="1c0a0-127">**Новые возможности:** Начиная с 3 мая 2020 клиенты постепенно перестанут получать изменения этого интерфейса.</span><span class="sxs-lookup"><span data-stu-id="1c0a0-127">**New experience:** Starting May 3, 2020, customers will gradually receive changes to this experience.</span></span> <span data-ttu-id="1c0a0-128">При использовании нового интерфейса возможность включения защиты от угроз Майкрософт будет доступна *всем* клиентам с любой из следующих лицензий:</span><span class="sxs-lookup"><span data-stu-id="1c0a0-128">For those with the new experience, the option to turn on Microsoft Threat Protection will be available to *all* customers with any of the following licenses:</span></span>

- <span data-ttu-id="1c0a0-129">Microsoft 365 в ~ или A5</span><span class="sxs-lookup"><span data-stu-id="1c0a0-129">Microsoft 365 E5 or A5</span></span>
- <span data-ttu-id="1c0a0-130">Microsoft 365 и безопасность A5</span><span class="sxs-lookup"><span data-stu-id="1c0a0-130">Microsoft 365 E5 Security or A5 Security</span></span>
- <span data-ttu-id="1c0a0-131">Windows 10 Корпоративная ячейка = или A5</span><span class="sxs-lookup"><span data-stu-id="1c0a0-131">Windows 10 Enterprise E5 or A5</span></span>
- <span data-ttu-id="1c0a0-132">Enterprise Mobility + Security (EMS), а также A5</span><span class="sxs-lookup"><span data-stu-id="1c0a0-132">Enterprise Mobility + Security (EMS) E5 or A5</span></span> 
- <span data-ttu-id="1c0a0-133">Office 365 в ~ или A5</span><span class="sxs-lookup"><span data-stu-id="1c0a0-133">Office 365 E5 or A5</span></span>
- <span data-ttu-id="1c0a0-134">Advanced Threat Protection в Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="1c0a0-134">Microsoft Defender Advanced Threat Protection</span></span> 
- <span data-ttu-id="1c0a0-135">Расширенная защита от угроз Azure</span><span class="sxs-lookup"><span data-stu-id="1c0a0-135">Azure Advanced Threat Protection</span></span> 
- <span data-ttu-id="1c0a0-136">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="1c0a0-136">Microsoft Cloud App Security</span></span> 
- <span data-ttu-id="1c0a0-137">Расширенная защита от угроз Office 365 (план 2)</span><span class="sxs-lookup"><span data-stu-id="1c0a0-137">Office 365 Advanced Threat Protection (Plan 2)</span></span> 

### <a name="check-your-existing--licenses"></a><span data-ttu-id="1c0a0-138">Проверка существующих лицензий</span><span class="sxs-lookup"><span data-stu-id="1c0a0-138">Check your existing  licenses</span></span>
<span data-ttu-id="1c0a0-139">Перейдите в центр администрирования Microsoft 365 ([Admin.Microsoft.com](https://admin.microsoft.com/)), чтобы просмотреть существующие лицензии.</span><span class="sxs-lookup"><span data-stu-id="1c0a0-139">Go to Microsoft 365 admin center ([admin.microsoft.com](https://admin.microsoft.com/)) to view your existing licenses.</span></span> <span data-ttu-id="1c0a0-140">В Центре администрирования выберите **Выставление счетов** > **Лицензии**.</span><span class="sxs-lookup"><span data-stu-id="1c0a0-140">In the admin center, go to **Billing** > **Licenses**.</span></span>

>[!NOTE]
> <span data-ttu-id="1c0a0-141">Для просмотра сведений о лицензии необходимо назначить роль **администратора выставления счетов** или роль **глобального читателя** [в Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) .</span><span class="sxs-lookup"><span data-stu-id="1c0a0-141">You need to be assigned either the **Billing admin** or **Global reader** [role in Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) to be able to see license information.</span></span> <span data-ttu-id="1c0a0-142">Если у вас возникли проблемы с доступом, обратитесь к глобальному администратору.</span><span class="sxs-lookup"><span data-stu-id="1c0a0-142">If you encounter access problems, contact a global admin.</span></span>

## <a name="browser-requirements"></a><span data-ttu-id="1c0a0-143">Требования к браузеру</span><span class="sxs-lookup"><span data-stu-id="1c0a0-143">Browser requirements</span></span>
<span data-ttu-id="1c0a0-144">Доступ к защите от угроз Майкрософт в центре безопасности Microsoft 365 с помощью Microsoft EDGE, Internet Explorer 11 или любого совместимого с HTML 5 веб-браузера.</span><span class="sxs-lookup"><span data-stu-id="1c0a0-144">Access Microsoft Threat Protection in the Microsoft 365 security center using Microsoft Edge, Internet Explorer 11, or any HTML 5 compliant web browser.</span></span>

## <a name="microsoft-threat-protection-for-us-government-community-cloud-and-us-government-community-cloud-high-gcc-high-customers"></a><span data-ttu-id="1c0a0-145">Защита от угроз Майкрософт для облачных сообществ США и облачных пользователей Office для государственных учреждений (GCC высокая)</span><span class="sxs-lookup"><span data-stu-id="1c0a0-145">Microsoft Threat Protection for US Government Community Cloud and US Government Community Cloud High (GCC High) customers</span></span>
<span data-ttu-id="1c0a0-146">В настоящее время защита от угроз Майкрософт недоступна для клиентов GCC и GCC High.</span><span class="sxs-lookup"><span data-stu-id="1c0a0-146">Currently, Microsoft Threat Protection is not available to US GCC and GCC High customers.</span></span> 

## <a name="related-topics"></a><span data-ttu-id="1c0a0-147">См. также</span><span class="sxs-lookup"><span data-stu-id="1c0a0-147">Related topics</span></span>
- [<span data-ttu-id="1c0a0-148">Обзор Защиты от угроз (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="1c0a0-148">Microsoft Threat Protection overview</span></span>](microsoft-threat-protection.md)
- [<span data-ttu-id="1c0a0-149">Включение Защиты от угроз (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="1c0a0-149">Turn on Microsoft Threat Protection</span></span>](mtp-enable.md)
