---
title: Предварительные требования для Защиты от угроз (Майкрософт)
description: Сведения о лицензировании, требованиях к оборудованию и программному обеспечению, а также других параметрах конфигурации Защиты от угроз (Майкрософт)
keywords: требования, предварительные требования, оборудование, программное обеспечение, браузер, MTP, M365, лицензия
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
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
ms.openlocfilehash: 2175ca328678e271056ae75d1bcbb7dc70a2198d
ms.sourcegitcommit: 5b0a2e11c86c00e6e6b534f8b0a19962d1bb2805
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/27/2019
ms.locfileid: "40881970"
---
# <a name="microsoft-threat-protection-prerequisites"></a><span data-ttu-id="1f3f8-104">Предварительные требования для Защиты от угроз (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="1f3f8-104">Microsoft Threat Protection prerequisites</span></span>

<span data-ttu-id="1f3f8-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="1f3f8-105">**Applies to:**</span></span>
- <span data-ttu-id="1f3f8-106">Защита от угроз (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="1f3f8-106">Microsoft Threat Protection</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="1f3f8-107">Сведения о лицензировании, требованиях к оборудованию и программному обеспечению, а также других параметрах конфигурации для запуска и использования Безопасности Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="1f3f8-107">Learn about the licensing, hardware and software requirements, and other configuration settings to run and use the Microsoft 365 security.</span></span>

## <a name="licensing-requirements"></a><span data-ttu-id="1f3f8-108">Требования к лицензированию</span><span class="sxs-lookup"><span data-stu-id="1f3f8-108">Licensing requirements</span></span>
<span data-ttu-id="1f3f8-109">Для Безопасности Microsoft 365 требуется одна из следующих лицензий:</span><span class="sxs-lookup"><span data-stu-id="1f3f8-109">Microsoft 365 security requires one of the following licenses:</span></span>

- <span data-ttu-id="1f3f8-110">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="1f3f8-110">Microsoft 365 E5</span></span> 
- <span data-ttu-id="1f3f8-111">Office 365 E5, Enterprise Mobility + Security E5 и Windows E5</span><span class="sxs-lookup"><span data-stu-id="1f3f8-111">Office 365 E5, Enterprise Mobility + Security E5, and Windows E5</span></span>

<span data-ttu-id="1f3f8-112">Эти лицензии можно получить на странице [Microsoft 365 корпоративный](https://www.microsoft.com/en-us/microsoft-365/enterprise).</span><span class="sxs-lookup"><span data-stu-id="1f3f8-112">You can acquire these licenses from the [Microsoft 365 enterprise page](https://www.microsoft.com/en-us/microsoft-365/enterprise).</span></span>

### <a name="check-your-existing--licenses"></a><span data-ttu-id="1f3f8-113">Проверка существующих лицензий</span><span class="sxs-lookup"><span data-stu-id="1f3f8-113">Check your existing  licenses</span></span>
<span data-ttu-id="1f3f8-114">Перейдите в Центр администрирования Microsoft 365 по адресу [admin.microsoft.com](https://admin.microsoft.com/), чтобы просмотреть существующие лицензии.</span><span class="sxs-lookup"><span data-stu-id="1f3f8-114">Go to Microsoft 365 admin center at [admin.microsoft.com](https://admin.microsoft.com/) to view your existing licenses.</span></span> <span data-ttu-id="1f3f8-115">В Центре администрирования выберите **Выставление счетов** > **Лицензии**.</span><span class="sxs-lookup"><span data-stu-id="1f3f8-115">In the admin center, go to **Billing** > **Licenses**.</span></span>

<span data-ttu-id="1f3f8-116">Для просмотра сведений о лицензировании вам должна быть назначена роль **администратора выставления счетов** или **глобального читателя** [в Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles).</span><span class="sxs-lookup"><span data-stu-id="1f3f8-116">You need to be assigned either the **Billing admin** or **Global reader** [role in Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) to be able to see licensing information.</span></span> <span data-ttu-id="1f3f8-117">Если у вас возникли проблемы с доступом, обратитесь к глобальному администратору.</span><span class="sxs-lookup"><span data-stu-id="1f3f8-117">If you encounter access problems, contact a global admin.</span></span>  

## <a name="browser-requirements"></a><span data-ttu-id="1f3f8-118">Требования к браузеру</span><span class="sxs-lookup"><span data-stu-id="1f3f8-118">Browser requirements</span></span>
<span data-ttu-id="1f3f8-119">Доступ к Центру безопасности Microsoft 365 осуществляется через браузер.</span><span class="sxs-lookup"><span data-stu-id="1f3f8-119">Access to Microsoft 365 security center is done through a browser.</span></span> <span data-ttu-id="1f3f8-120">Поддерживаются Internet Explorer и Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="1f3f8-120">Internet Explorer and Microsoft Edge is supported.</span></span> <span data-ttu-id="1f3f8-121">Кроме того, поддерживаются все HTML5-совместимые браузеры.</span><span class="sxs-lookup"><span data-stu-id="1f3f8-121">Any HTML5 compliant browsers are also supported.</span></span>

## <a name="related-topics"></a><span data-ttu-id="1f3f8-122">См. также</span><span class="sxs-lookup"><span data-stu-id="1f3f8-122">Related topics</span></span>
- [<span data-ttu-id="1f3f8-123">Обзор Защиты от угроз (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="1f3f8-123">Microsoft Threat Protection overview</span></span>](microsoft-threat-protection.md)
- [<span data-ttu-id="1f3f8-124">Включение Защиты от угроз (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="1f3f8-124">Turn on Microsoft Threat Protection</span></span>](mtp-enable.md)