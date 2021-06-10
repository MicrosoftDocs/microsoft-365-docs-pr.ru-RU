---
title: Доступ к Центр безопасности в Microsoft Defender клиентского портала MSSP
description: Доступ к Центр безопасности в Microsoft Defender клиентского портала MSSP
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
ms.openlocfilehash: 97122decede91e8b4f059b3b66999ac12b300172
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2021
ms.locfileid: "51164861"
---
# <a name="access-the-microsoft-defender-security-center-mssp-customer-portal"></a><span data-ttu-id="e8206-104">Доступ к Центр безопасности в Microsoft Defender клиентского портала MSSP</span><span class="sxs-lookup"><span data-stu-id="e8206-104">Access the Microsoft Defender Security Center MSSP customer portal</span></span>

<span data-ttu-id="e8206-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="e8206-105">**Applies to:**</span></span>
- [<span data-ttu-id="e8206-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="e8206-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="e8206-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e8206-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="e8206-108">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="e8206-108">**Applies to:**</span></span>

- [<span data-ttu-id="e8206-109">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="e8206-109">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)

><span data-ttu-id="e8206-110">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="e8206-110">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="e8206-111">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="e8206-111">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-mssp-support-abovefoldlink)




>[!NOTE] 
><span data-ttu-id="e8206-112">Этот набор действий направлен в направлении MSSP.</span><span class="sxs-lookup"><span data-stu-id="e8206-112">These set of steps are directed towards the MSSP.</span></span> 

<span data-ttu-id="e8206-113">По умолчанию клиенты MSSP имеют доступ к Центр безопасности в Microsoft Defender клиенту по следующему URL-адресу: `https://securitycenter.windows.com` .</span><span class="sxs-lookup"><span data-stu-id="e8206-113">By default, MSSP customers access their Microsoft Defender Security Center tenant through the following URL: `https://securitycenter.windows.com`.</span></span>
 

<span data-ttu-id="e8206-114">MsSPs, однако, необходимо использовать URL-адрес клиента в следующем формате: для доступа  `https://securitycenter.windows.com?tid=customer_tenant_id` к порталу клиентов MSSP.</span><span class="sxs-lookup"><span data-stu-id="e8206-114">MSSPs however, will need to use a tenant-specific URL in the following format:  `https://securitycenter.windows.com?tid=customer_tenant_id` to access the MSSP customer portal.</span></span> 

<span data-ttu-id="e8206-115">В общем, msSPs необходимо будет добавить в каждый клиент MSSP Azure AD, который они намерены управлять.</span><span class="sxs-lookup"><span data-stu-id="e8206-115">In general, MSSPs will need to be added to each of the MSSP customer's Azure AD that they intend to manage.</span></span>


<span data-ttu-id="e8206-116">Используйте следующие действия, чтобы получить ID клиента MSSP, а затем использовать ID для доступа к URL-адресу клиента:</span><span class="sxs-lookup"><span data-stu-id="e8206-116">Use the following steps to obtain the MSSP customer tenant ID and then use the ID to access the tenant-specific URL:</span></span>

1. <span data-ttu-id="e8206-117">В качестве msSP войдите в Azure AD с учетными данными.</span><span class="sxs-lookup"><span data-stu-id="e8206-117">As an MSSP, login to Azure AD with your credentials.</span></span> 

2. <span data-ttu-id="e8206-118">Переключение каталога на клиента MSSP.</span><span class="sxs-lookup"><span data-stu-id="e8206-118">Switch directory to the MSSP customer's tenant.</span></span>

3.  <span data-ttu-id="e8206-119">Выберите **Azure Active Directory > свойства**.</span><span class="sxs-lookup"><span data-stu-id="e8206-119">Select **Azure Active Directory > Properties**.</span></span> <span data-ttu-id="e8206-120">В поле Directory ID вы найдете ИД клиента.</span><span class="sxs-lookup"><span data-stu-id="e8206-120">You'll find the tenant ID in the Directory ID field.</span></span> 

4. <span data-ttu-id="e8206-121">Доступ на клиентский портал MSSP, заменив значение в `customer_tenant_id` следующем URL-адресе: `https://securitycenter.windows.com?tid=customer_tenant_id` .</span><span class="sxs-lookup"><span data-stu-id="e8206-121">Access the MSSP customer portal by replacing the `customer_tenant_id` value in the following URL: `https://securitycenter.windows.com?tid=customer_tenant_id`.</span></span>


## <a name="related-topics"></a><span data-ttu-id="e8206-122">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="e8206-122">Related topics</span></span>
- [<span data-ttu-id="e8206-123">Предоставление MSSP доступа к порталу</span><span class="sxs-lookup"><span data-stu-id="e8206-123">Grant MSSP access to the portal</span></span>](grant-mssp-access.md)
- [<span data-ttu-id="e8206-124">Настройка уведомлений оповещений</span><span class="sxs-lookup"><span data-stu-id="e8206-124">Configure alert notifications</span></span>](configure-mssp-notifications.md)
- [<span data-ttu-id="e8206-125">Получение оповещений от владельца клиента</span><span class="sxs-lookup"><span data-stu-id="e8206-125">Fetch alerts from customer tenant</span></span>](fetch-alerts-mssp.md)
