---
title: Требования к Microsoft 365 Lighthouse
f1.keywords: NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: article
ms.prod: microsoft-365-lighthouse
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- M365-Lighthouse
search.appverid: MET150
description: Для поставщиков управляемых служб (MSP) получите список требований к использованию Microsoft 365 Lighthouse.
ms.openlocfilehash: 9c87744053ffe3bace90534287cd2b81697f3554
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/12/2021
ms.locfileid: "53395353"
---
# <a name="requirements-for-microsoft-365-lighthouse"></a><span data-ttu-id="097ae-103">Требования к Microsoft 365 Lighthouse</span><span class="sxs-lookup"><span data-stu-id="097ae-103">Requirements for Microsoft 365 Lighthouse</span></span>

> [!NOTE]
> <span data-ttu-id="097ae-104">Функции, описанные в этой статье, подлежат изменениям и доступны только партнерам, которые соответствуют требованиям, указанным в этой статье.</span><span class="sxs-lookup"><span data-stu-id="097ae-104">The features described in this article are in Preview, are subject to change, and are only available to partners who meet the requirements listed in this article.</span></span> <span data-ttu-id="097ae-105">Если в организации нет Microsoft 365 Lighthouse, [см.](m365-lighthouse-sign-up.md)в Microsoft 365 Lighthouse.</span><span class="sxs-lookup"><span data-stu-id="097ae-105">If your organization does not have Microsoft 365 Lighthouse, see [Sign up for Microsoft 365 Lighthouse](m365-lighthouse-sign-up.md).</span></span>

<span data-ttu-id="097ae-106">Microsoft 365 Lighthouse является порталом администрирования, который помогает управляемым поставщикам услуг (MSP) обеспечивать безопасность устройств, данных и пользователей в масштабе для клиентов малого и среднего бизнеса (SMB).</span><span class="sxs-lookup"><span data-stu-id="097ae-106">Microsoft 365 Lighthouse is an admin portal that helps Managed Service Providers (MSPs) secure and manage devices, data, and users at scale for small- and medium-sized business (SMB) customers.</span></span>  

<span data-ttu-id="097ae-107">MsPs должны быть зарегистрированы в программе поставщик облачных решений (CSP) в качестве непрямого посредника или партнера Direct Bill для использования Microsoft 365 Lighthouse.</span><span class="sxs-lookup"><span data-stu-id="097ae-107">MSPs must be enrolled in the Cloud Solution Provider (CSP) program as an Indirect Reseller or Direct Bill partner to use Microsoft 365 Lighthouse.</span></span>  

<span data-ttu-id="097ae-108">Кроме того, каждый клиент MSP должен иметь право на Microsoft 365 Lighthouse, выполнев следующие требования:</span><span class="sxs-lookup"><span data-stu-id="097ae-108">In addition, each MSP customer tenant must qualify for Microsoft 365 Lighthouse by meeting the following requirements:</span></span> 
 
- <span data-ttu-id="097ae-109">Делегированная привилегия администратора (DAP) для MSP</span><span class="sxs-lookup"><span data-stu-id="097ae-109">Delegated Admin Privileges (DAP) for the MSP</span></span> 
- <span data-ttu-id="097ae-110">По крайней мере одна Microsoft 365 бизнес премиум лицензия</span><span class="sxs-lookup"><span data-stu-id="097ae-110">At least one Microsoft 365 Business Premium license</span></span> 
- <span data-ttu-id="097ae-111">Менее 500 лицензированных пользователей</span><span class="sxs-lookup"><span data-stu-id="097ae-111">Fewer than 500 licensed users</span></span>  

## <a name="requirements-for-enablingdevice-management"></a><span data-ttu-id="097ae-112">Требования для включения управления устройствами</span><span class="sxs-lookup"><span data-stu-id="097ae-112">Requirements for enabling device management</span></span>   

<span data-ttu-id="097ae-113">Чтобы просмотреть устройства клиента-клиента на страницах управления устройствами, MSP должен:</span><span class="sxs-lookup"><span data-stu-id="097ae-113">To view customer tenant devices on the device management pages, a MSP must:</span></span>    

- <span data-ttu-id="097ae-114">Регистрация всех устройств клиентов в Microsoft Endpoint Manager (MEM).</span><span class="sxs-lookup"><span data-stu-id="097ae-114">Enroll all customer devices in Microsoft Endpoint Manager (MEM).</span></span><span data-ttu-id="097ae-115">Дополнительные сведения см. в [Microsoft Intune.](/mem/intune/enrollment/)</span><span class="sxs-lookup"><span data-stu-id="097ae-115"> For more information, see [Enroll devices in Microsoft Intune](/mem/intune/enrollment/).</span></span>
- <span data-ttu-id="097ae-116">Назначение политик соответствия требованиям для всех устройств клиента.</span><span class="sxs-lookup"><span data-stu-id="097ae-116">Assign compliance policies to all customer devices.</span></span><span data-ttu-id="097ae-117">Дополнительные сведения см. в [дополнительных сведениях о создании](/mem/intune/protect/create-compliance-policy)политики соответствия требованиям в Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="097ae-117"> For more information, see [Create a compliance policy in Microsoft Intune](/mem/intune/protect/create-compliance-policy).</span></span> 

## <a name="requirements-for-enabling-usermanagement"></a><span data-ttu-id="097ae-118">Требования для включения управления пользователями</span><span class="sxs-lookup"><span data-stu-id="097ae-118">Requirements for enabling user management</span></span> 

<span data-ttu-id="097ae-119">Чтобы данные клиентов были в отчетах на страницах управления пользователями, включая рискованных пользователей, многофакторную проверку подлинности и сброс пароля, клиенты должны иметь лицензии на Azure Active Directory Premium P1 или более поздней основе.</span><span class="sxs-lookup"><span data-stu-id="097ae-119">For customer data to show up in reports on user management pages, including Risky users, Multifactor authentication, and Password reset, customer tenants must have licenses for Azure Active Directory Premium P1 or later.</span></span> <span data-ttu-id="097ae-120">Azure AD Premium P1 включен в Microsoft 365 бизнес премиум.</span><span class="sxs-lookup"><span data-stu-id="097ae-120">Azure AD Premium P1 is included with Microsoft 365 Business Premium.</span></span>   

## <a name="requirements-for-enablingthreat-management"></a><span data-ttu-id="097ae-121">Требования для включения управления угрозами</span><span class="sxs-lookup"><span data-stu-id="097ae-121">Requirements for enabling threat management</span></span> 

<span data-ttu-id="097ae-122">Чтобы просмотреть устройства клиента и угрозы на страницах управления угрозами, необходимо записать все устройства клиента в Microsoft Endpoint Manager (MEM) и защитить их, запуская антивирусная программа в Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="097ae-122">To view customer tenant devices and threats on the threat management pages, you must enroll all customer tenant devices in Microsoft Endpoint Manager (MEM) and protect them by running Microsoft Defender Antivirus.</span></span>  

<span data-ttu-id="097ae-123">Дополнительные сведения см. в [Microsoft Intune.](/mem/intune/enrollment/)</span><span class="sxs-lookup"><span data-stu-id="097ae-123">For more information, see [Enroll devices in Microsoft Intune](/mem/intune/enrollment/).</span></span>  

<span data-ttu-id="097ae-124">антивирусная программа в Microsoft Defender является частью Windows операционной системы и включена по умолчанию на устройствах с Windows 10.</span><span class="sxs-lookup"><span data-stu-id="097ae-124">Microsoft Defender Antivirus is part of the Windows operating system and is enabled by default on devices running Windows 10.</span></span>  

> [!NOTE] 
> <span data-ttu-id="097ae-125">Если вы используете антивирусное решение, не в microsoft, а не антивирусная программа в Microsoft Defender, антивирусная программа в Microsoft Defender автоматически отключается.</span><span class="sxs-lookup"><span data-stu-id="097ae-125">If you're using a non-Microsoft antivirus solution and not Microsoft Defender Antivirus, Microsoft Defender Antivirus is disabled automatically.</span></span> <span data-ttu-id="097ae-126">При отсечении антивирусного решения, антивирусная программа в Microsoft Defender автоматически активируется для защиты Windows устройств от угроз.</span><span class="sxs-lookup"><span data-stu-id="097ae-126">When you uninstall the non-Microsoft antivirus solution, Microsoft Defender Antivirus is activated automatically to protect your Windows devices from threats.</span></span>    

## <a name="related-content"></a><span data-ttu-id="097ae-127">См. также:</span><span class="sxs-lookup"><span data-stu-id="097ae-127">Related content</span></span>   

<span data-ttu-id="097ae-128">[Настройка Microsoft 365 Lighthouse безопасности портала](m365-lighthouse-configure-portal-security.md) (статья)</span><span class="sxs-lookup"><span data-stu-id="097ae-128">[Configure Microsoft 365 Lighthouse portal security](m365-lighthouse-configure-portal-security.md) (article)</span></span>\
<span data-ttu-id="097ae-129">[Microsoft 365 Lighthouse страницы соответствия требованиям устройства](m365-lighthouse-device-compliance-page-overview.md) (статья)</span><span class="sxs-lookup"><span data-stu-id="097ae-129">[Microsoft 365 Lighthouse Device compliance page overview](m365-lighthouse-device-compliance-page-overview.md) (article)</span></span>\
<span data-ttu-id="097ae-130">[Microsoft 365 Lighthouse страницы пользователей](m365-lighthouse-users-page-overview.md) (статья)</span><span class="sxs-lookup"><span data-stu-id="097ae-130">[Microsoft 365 Lighthouse Users page overview](m365-lighthouse-users-page-overview.md) (article)</span></span>\
<span data-ttu-id="097ae-131">[Microsoft 365 Lighthouse страницы управления угрозами](m365-lighthouse-threat-management-page-overview.md) (статья)</span><span class="sxs-lookup"><span data-stu-id="097ae-131">[Microsoft 365 Lighthouse Threat management page overview](m365-lighthouse-threat-management-page-overview.md) (article)</span></span>\
<span data-ttu-id="097ae-132">[Microsoft 365 Lighthouse faQ](m365-lighthouse-faq.yml)   (статья)</span><span class="sxs-lookup"><span data-stu-id="097ae-132">[Microsoft 365 Lighthouse FAQ](m365-lighthouse-faq.yml) (article)</span></span>

