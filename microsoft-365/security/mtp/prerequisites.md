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
ms.openlocfilehash: 3e18759387525ec600c24f74c96d6cddf206fc82
ms.sourcegitcommit: cc3b64a91e16ccdaa9c338b9a9056dbe3963ba9e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/10/2020
ms.locfileid: "42569049"
---
# <a name="microsoft-threat-protection-prerequisites"></a><span data-ttu-id="c8ba6-104">Предварительные требования для Защиты от угроз (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="c8ba6-104">Microsoft Threat Protection prerequisites</span></span>

<span data-ttu-id="c8ba6-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="c8ba6-105">**Applies to:**</span></span>
- <span data-ttu-id="c8ba6-106">Защита от угроз (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="c8ba6-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="c8ba6-107">Сведения о лицензировании, требованиях к оборудованию и программному обеспечению, а также другие параметры конфигурации для подготовки и использования защиты от угроз Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="c8ba6-107">Learn about the licensing, hardware and software requirements, and other configuration settings to provision and use Microsoft Threat Protection.</span></span>

## <a name="licensing-requirements"></a><span data-ttu-id="c8ba6-108">Требования к лицензированию</span><span class="sxs-lookup"><span data-stu-id="c8ba6-108">Licensing requirements</span></span>
<span data-ttu-id="c8ba6-109">Для использования защиты от угроз Майкрософт необходима *одна* из следующих лицензий или комбинация лицензий:</span><span class="sxs-lookup"><span data-stu-id="c8ba6-109">To use Microsoft Threat Protection, you need *one* of the following licenses or combination of licenses:</span></span>

- <span data-ttu-id="c8ba6-110">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="c8ba6-110">Microsoft 365 E5</span></span>
- <span data-ttu-id="c8ba6-111">Безопасность Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="c8ba6-111">Microsoft 365 E5 Security</span></span>
- <span data-ttu-id="c8ba6-112">Office 365 в ~ и "Enterprise Mobility + Security/Security (EMS)" и Windows ~</span><span class="sxs-lookup"><span data-stu-id="c8ba6-112">Office 365 E5 and "Enterprise Mobility + Security E5 (EMS E5)" and Windows E5</span></span>
- <span data-ttu-id="c8ba6-113">Microsoft 365 A5</span><span class="sxs-lookup"><span data-stu-id="c8ba6-113">Microsoft 365 A5</span></span>

<span data-ttu-id="c8ba6-114">Дополнительные сведения см. [в планах корпоративных служб Microsoft 365](https://www.microsoft.com/licensing/product-licensing/microsoft-365-enterprise).</span><span class="sxs-lookup"><span data-stu-id="c8ba6-114">For more information, [view the Microsoft 365 Enterprise service plans](https://www.microsoft.com/licensing/product-licensing/microsoft-365-enterprise).</span></span>

> <span data-ttu-id="c8ba6-115">У вас еще нет лицензии?</span><span class="sxs-lookup"><span data-stu-id="c8ba6-115">Don't have license yet?</span></span> [<span data-ttu-id="c8ba6-116">Попробуйте или купите подписку на Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="c8ba6-116">Try or buy a Microsoft 365 subscription</span></span>](https://docs.microsoft.com/microsoft-365/commerce/try-or-buy-microsoft-365?view=o365-worldwide)

### <a name="check-your-existing--licenses"></a><span data-ttu-id="c8ba6-117">Проверка существующих лицензий</span><span class="sxs-lookup"><span data-stu-id="c8ba6-117">Check your existing  licenses</span></span>
<span data-ttu-id="c8ba6-118">Перейдите в центр администрирования Microsoft 365 ([Admin.Microsoft.com](https://admin.microsoft.com/)), чтобы просмотреть существующие лицензии.</span><span class="sxs-lookup"><span data-stu-id="c8ba6-118">Go to Microsoft 365 admin center ([admin.microsoft.com](https://admin.microsoft.com/)) to view your existing licenses.</span></span> <span data-ttu-id="c8ba6-119">В Центре администрирования выберите **Выставление счетов** > **Лицензии**.</span><span class="sxs-lookup"><span data-stu-id="c8ba6-119">In the admin center, go to **Billing** > **Licenses**.</span></span>

>[!NOTE]
> <span data-ttu-id="c8ba6-120">Для просмотра сведений о лицензии необходимо назначить роль **администратора выставления счетов** или роль **глобального читателя** [в Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) .</span><span class="sxs-lookup"><span data-stu-id="c8ba6-120">You need to be assigned either the **Billing admin** or **Global reader** [role in Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) to be able to see license information.</span></span> <span data-ttu-id="c8ba6-121">Если у вас возникли проблемы с доступом, обратитесь к глобальному администратору.</span><span class="sxs-lookup"><span data-stu-id="c8ba6-121">If you encounter access problems, contact a global admin.</span></span>

## <a name="browser-requirements"></a><span data-ttu-id="c8ba6-122">Требования к браузеру</span><span class="sxs-lookup"><span data-stu-id="c8ba6-122">Browser requirements</span></span>
<span data-ttu-id="c8ba6-123">Доступ к защите от угроз Майкрософт в центре безопасности Microsoft 365 с помощью Microsoft EDGE, Internet Explorer 11 или любого совместимого с HTML 5 веб-браузера.</span><span class="sxs-lookup"><span data-stu-id="c8ba6-123">Access Microsoft Threat Protection in the Microsoft 365 security center using Microsoft Edge, Internet Explorer 11, or any HTML 5 compliant web browser.</span></span>

## <a name="related-topics"></a><span data-ttu-id="c8ba6-124">См. также</span><span class="sxs-lookup"><span data-stu-id="c8ba6-124">Related topics</span></span>
- [<span data-ttu-id="c8ba6-125">Обзор Защиты от угроз (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="c8ba6-125">Microsoft Threat Protection overview</span></span>](microsoft-threat-protection.md)
- [<span data-ttu-id="c8ba6-126">Включение Защиты от угроз (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="c8ba6-126">Turn on Microsoft Threat Protection</span></span>](mtp-enable.md)
