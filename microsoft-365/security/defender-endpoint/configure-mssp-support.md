---
title: Настройка поддержки поставщика управляемых служб безопасности
description: Примите необходимые меры для настройки интеграции MSSP с Microsoft Defender для конечной точки
keywords: поставщик управляемых служб безопасности, mssp, настройка, интеграция
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: d82bffd6eea54256f2c6773f843030a19e27275d
ms.sourcegitcommit: 0d1b065c94125b495e9886200f7918de3bda40b3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/08/2021
ms.locfileid: "53339362"
---
# <a name="configure-managed-security-service-provider-integration"></a><span data-ttu-id="e1731-104">Настройка интеграции управляемого поставщика службы безопасности</span><span class="sxs-lookup"><span data-stu-id="e1731-104">Configure managed security service provider integration</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="e1731-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="e1731-105">**Applies to:**</span></span>
- [<span data-ttu-id="e1731-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="e1731-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="e1731-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e1731-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="e1731-108">Хотите испытать Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="e1731-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="e1731-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="e1731-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-mssp-support-abovefoldlink)
 
[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="e1731-110">Чтобы включить интеграцию поставщика управляемых служб безопасности (MSSP), необходимо предпринять следующие действия по настройке.</span><span class="sxs-lookup"><span data-stu-id="e1731-110">You'll need to take the following configuration steps to enable the managed security service provider (MSSP) integration.</span></span>

>[!NOTE]
><span data-ttu-id="e1731-111">В этой статье используются следующие термины для различия между поставщиком услуг и потребителем услуг:</span><span class="sxs-lookup"><span data-stu-id="e1731-111">The following terms are used in this article to distinguish between the service provider and service consumer:</span></span>
> - <span data-ttu-id="e1731-112">MSSPs. Организации безопасности, которые предлагают отслеживать и управлять устройствами безопасности для организации.</span><span class="sxs-lookup"><span data-stu-id="e1731-112">MSSPs: Security organizations that offer to monitor and manage security devices for an organization.</span></span>
> - <span data-ttu-id="e1731-113">Клиенты MSSP. Организации, которые занимаются службами MSSPs.</span><span class="sxs-lookup"><span data-stu-id="e1731-113">MSSP customers: Organizations that engage the services of MSSPs.</span></span>

<span data-ttu-id="e1731-114">Интеграция позволит MSSP принять следующие действия:</span><span class="sxs-lookup"><span data-stu-id="e1731-114">The integration will allow MSSPs to take the following actions:</span></span>

- <span data-ttu-id="e1731-115">Получить доступ к порталу Microsoft 365 Defender msSP</span><span class="sxs-lookup"><span data-stu-id="e1731-115">Get access to MSSP customer's Microsoft 365 Defender portal</span></span>
- <span data-ttu-id="e1731-116">Получать уведомления электронной почты и</span><span class="sxs-lookup"><span data-stu-id="e1731-116">Get email notifications, and</span></span> 
- <span data-ttu-id="e1731-117">Извлечение оповещений с помощью средств управления безопасностью и событий (SIEM)</span><span class="sxs-lookup"><span data-stu-id="e1731-117">Fetch alerts through security information and event management (SIEM) tools</span></span>

<span data-ttu-id="e1731-118">Прежде чем msSPs смогут принять эти действия, клиент MSSP должен предоставить доступ к своему клиенту Defender для конечной точки, чтобы MSSP получил доступ к порталу.</span><span class="sxs-lookup"><span data-stu-id="e1731-118">Before MSSPs can take these actions, the MSSP customer will need to grant access to their Defender for Endpoint tenant so that the MSSP can access the portal.</span></span> 
 

<span data-ttu-id="e1731-119">Как правило, клиенты MSSP принимают начальные шаги по настройке, чтобы предоставить msSPs доступ к Защитник Windows центральному Защитник Windows безопасности.</span><span class="sxs-lookup"><span data-stu-id="e1731-119">Typically, MSSP customers take the initial configuration steps to grant MSSPs access to their Windows Defender Security Central tenant.</span></span> <span data-ttu-id="e1731-120">После предоставления доступа клиент MSSP или MSSP могут предпринять другие действия по настройке.</span><span class="sxs-lookup"><span data-stu-id="e1731-120">After access is granted, other configuration steps can be done by either the MSSP customer or the MSSP.</span></span>


<span data-ttu-id="e1731-121">В общем, необходимо предпринять следующие действия по настройке:</span><span class="sxs-lookup"><span data-stu-id="e1731-121">In general, the following configuration steps need to be taken:</span></span>


- <span data-ttu-id="e1731-122">**Предоставление доступа msSP к Microsoft 365 Defender**</span><span class="sxs-lookup"><span data-stu-id="e1731-122">**Grant the MSSP access to Microsoft 365 Defender**</span></span> <br>
<span data-ttu-id="e1731-123">Это действие должно быть сделано клиентом MSSP.</span><span class="sxs-lookup"><span data-stu-id="e1731-123">This action needs to be done by the MSSP customer.</span></span> <span data-ttu-id="e1731-124">Предоставляет доступ msSP к клиенту клиента MSSP Defender для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="e1731-124">It grants the MSSP access to the MSSP customer's Defender for Endpoint tenant.</span></span>
 

- <span data-ttu-id="e1731-125">**Настройка уведомлений оповещений, отправленных в MSSP**</span><span class="sxs-lookup"><span data-stu-id="e1731-125">**Configure alert notifications sent to MSSPs**</span></span> <br>
<span data-ttu-id="e1731-126">Это действие может быть принято либо клиентом MSSP, либо MSSP.</span><span class="sxs-lookup"><span data-stu-id="e1731-126">This action can be taken by either the MSSP customer or MSSP.</span></span> <span data-ttu-id="e1731-127">Это позволяет msSPs знать, какие оповещения необходимо адресовать для клиента MSSP.</span><span class="sxs-lookup"><span data-stu-id="e1731-127">This lets the MSSPs know what alerts they need to address for the MSSP customer.</span></span>

- <span data-ttu-id="e1731-128">**Извлечение оповещений клиента MSSP в систему SIEM**</span><span class="sxs-lookup"><span data-stu-id="e1731-128">**Fetch alerts from MSSP customer's tenant into SIEM system**</span></span> <br> <span data-ttu-id="e1731-129">Это действие будет принимать msSP.</span><span class="sxs-lookup"><span data-stu-id="e1731-129">This action is taken by the MSSP.</span></span> <span data-ttu-id="e1731-130">Она позволяет MSSP получать оповещения в средствах SIEM.</span><span class="sxs-lookup"><span data-stu-id="e1731-130">It allows MSSPs to fetch alerts in SIEM tools.</span></span>

- <span data-ttu-id="e1731-131">**Извлечение оповещений клиента MSSP с помощью API**</span><span class="sxs-lookup"><span data-stu-id="e1731-131">**Fetch alerts from MSSP customer's tenant using APIs**</span></span> <br>
<span data-ttu-id="e1731-132">Это действие будет принимать msSP.</span><span class="sxs-lookup"><span data-stu-id="e1731-132">This action is taken by the MSSP.</span></span> <span data-ttu-id="e1731-133">Она позволяет MSSP получать оповещения с помощью API.</span><span class="sxs-lookup"><span data-stu-id="e1731-133">It allows MSSPs to fetch alerts using APIs.</span></span>

## <a name="multi-tenant-access-for-mssps"></a><span data-ttu-id="e1731-134">Multi-tenant access for MSSPs</span><span class="sxs-lookup"><span data-stu-id="e1731-134">Multi-tenant access for MSSPs</span></span>
<span data-ttu-id="e1731-135">Сведения о реализации делегированного доступа с несколькими клиентами см. в нескольких клиентах для поставщиков управляемых [служб безопасности.](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/multi-tenant-access-for-managed-security-service-providers/ba-p/1533440)</span><span class="sxs-lookup"><span data-stu-id="e1731-135">For information on how to implement a multi-tenant delegated access, see [Multi-tenant access for Managed Security Service Providers](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/multi-tenant-access-for-managed-security-service-providers/ba-p/1533440).</span></span>



## <a name="related-topics"></a><span data-ttu-id="e1731-136">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="e1731-136">Related topics</span></span>
- [<span data-ttu-id="e1731-137">Предоставление MSSP доступа к порталу</span><span class="sxs-lookup"><span data-stu-id="e1731-137">Grant MSSP access to the portal</span></span>](grant-mssp-access.md)
- [<span data-ttu-id="e1731-138">Получение доступа к порталу клиентов MSSP</span><span class="sxs-lookup"><span data-stu-id="e1731-138">Access the MSSP customer portal</span></span>](access-mssp-portal.md)
- [<span data-ttu-id="e1731-139">Настройка уведомлений оповещений</span><span class="sxs-lookup"><span data-stu-id="e1731-139">Configure alert notifications</span></span>](configure-mssp-notifications.md)
- [<span data-ttu-id="e1731-140">Получение оповещений от владельца клиента</span><span class="sxs-lookup"><span data-stu-id="e1731-140">Fetch alerts from customer tenant</span></span>](fetch-alerts-mssp.md)

