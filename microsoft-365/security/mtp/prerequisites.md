---
title: Предварительные требования для Защиты от угроз (Майкрософт)
description: Сведения о лицензировании, требованиях к оборудованию и программному обеспечению, а также других параметрах конфигурации Защиты от угроз (Майкрософт)
keywords: требования, предварительные требования, оборудование, программное обеспечение, браузер, MTP, M365, лицензия
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
ms.openlocfilehash: 7498f7a15578979a24a1524e94f307067eeeb893
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42083608"
---
# <a name="microsoft-threat-protection-prerequisites"></a><span data-ttu-id="b83d3-104">Предварительные требования для Защиты от угроз (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="b83d3-104">Microsoft Threat Protection prerequisites</span></span>

<span data-ttu-id="b83d3-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="b83d3-105">**Applies to:**</span></span>
- <span data-ttu-id="b83d3-106">Защита от угроз (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="b83d3-106">Microsoft Threat Protection</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="b83d3-107">Сведения о лицензировании, требованиях к оборудованию и программному обеспечению, а также другие параметры конфигурации для подготовки и использования защиты от угроз Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="b83d3-107">Learn about the licensing, hardware and software requirements, and other configuration settings to provision and use Microsoft Threat Protection.</span></span>

## <a name="licensing-requirements"></a><span data-ttu-id="b83d3-108">Требования к лицензированию</span><span class="sxs-lookup"><span data-stu-id="b83d3-108">Licensing requirements</span></span>
<span data-ttu-id="b83d3-109">Для использования защиты от угроз Майкрософт необходима одна из следующих лицензий или комбинация лицензий:</span><span class="sxs-lookup"><span data-stu-id="b83d3-109">To use Microsoft Threat Protection, you need one of the following licenses or combination of licenses:</span></span>

- <span data-ttu-id="b83d3-110">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="b83d3-110">Microsoft 365 E5</span></span>
- <span data-ttu-id="b83d3-111">Безопасность Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="b83d3-111">Microsoft 365 E5 Security</span></span>
- <span data-ttu-id="b83d3-112">Office 365 E5, Enterprise Mobility + Security E5 и Windows E5</span><span class="sxs-lookup"><span data-stu-id="b83d3-112">Office 365 E5, Enterprise Mobility + Security E5, and Windows E5</span></span>

[<span data-ttu-id="b83d3-113">Просмотр планов корпоративных служб Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="b83d3-113">View Microsoft 365 Enterprise service plans</span></span>](https://www.microsoft.com/en-us/licensing/product-licensing/microsoft-365-enterprise)

### <a name="check-your-existing--licenses"></a><span data-ttu-id="b83d3-114">Проверка существующих лицензий</span><span class="sxs-lookup"><span data-stu-id="b83d3-114">Check your existing  licenses</span></span>
<span data-ttu-id="b83d3-115">Перейдите в центр администрирования Microsoft 365 ([Admin.Microsoft.com](https://admin.microsoft.com/)), чтобы просмотреть существующие лицензии.</span><span class="sxs-lookup"><span data-stu-id="b83d3-115">Go to Microsoft 365 admin center ([admin.microsoft.com](https://admin.microsoft.com/)) to view your existing licenses.</span></span> <span data-ttu-id="b83d3-116">В Центре администрирования выберите **Выставление счетов** > **Лицензии**.</span><span class="sxs-lookup"><span data-stu-id="b83d3-116">In the admin center, go to **Billing** > **Licenses**.</span></span>

>[!NOTE]
> <span data-ttu-id="b83d3-117">Для просмотра сведений о лицензии необходимо назначить роль **администратора выставления счетов** или роль **глобального читателя** [в Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) .</span><span class="sxs-lookup"><span data-stu-id="b83d3-117">You need to be assigned either the **Billing admin** or **Global reader** [role in Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) to be able to see license information.</span></span> <span data-ttu-id="b83d3-118">Если у вас возникли проблемы с доступом, обратитесь к глобальному администратору.</span><span class="sxs-lookup"><span data-stu-id="b83d3-118">If you encounter access problems, contact a global admin.</span></span>

## <a name="browser-requirements"></a><span data-ttu-id="b83d3-119">Требования к браузеру</span><span class="sxs-lookup"><span data-stu-id="b83d3-119">Browser requirements</span></span>
<span data-ttu-id="b83d3-120">Доступ к защите от угроз Майкрософт в центре безопасности Microsoft 365 с помощью Microsoft EDGE, Internet Explorer 11 или любого совместимого с HTML 5 веб-браузера.</span><span class="sxs-lookup"><span data-stu-id="b83d3-120">Access Microsoft Threat Protection in the Microsoft 365 security center using Microsoft Edge, Internet Explorer 11, or any HTML 5 compliant web browser.</span></span>

## <a name="related-topics"></a><span data-ttu-id="b83d3-121">См. также</span><span class="sxs-lookup"><span data-stu-id="b83d3-121">Related topics</span></span>
- [<span data-ttu-id="b83d3-122">Обзор Защиты от угроз (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="b83d3-122">Microsoft Threat Protection overview</span></span>](microsoft-threat-protection.md)
- [<span data-ttu-id="b83d3-123">Включение Защиты от угроз (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="b83d3-123">Turn on Microsoft Threat Protection</span></span>](mtp-enable.md)
