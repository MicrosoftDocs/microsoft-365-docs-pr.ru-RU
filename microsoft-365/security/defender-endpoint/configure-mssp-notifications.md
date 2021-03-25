---
title: Настройка уведомлений оповещений, отправленных в MSSPs
description: Настройка уведомлений оповещений, отправленных в MSSPs
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
ms.openlocfilehash: 67f7081e72b5ecc8bdb077f0537cf0cf92df38b9
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166057"
---
# <a name="configure-alert-notifications-that-are-sent-to-mssps"></a><span data-ttu-id="a50d8-104">Настройка уведомлений оповещений, отправленных в MSSPs</span><span class="sxs-lookup"><span data-stu-id="a50d8-104">Configure alert notifications that are sent to MSSPs</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="a50d8-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="a50d8-105">**Applies to:**</span></span>
- [<span data-ttu-id="a50d8-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="a50d8-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="a50d8-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a50d8-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="a50d8-108">Хотите испытать Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="a50d8-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="a50d8-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="a50d8-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-mssp-support-abovefoldlink)


>[!NOTE]
><span data-ttu-id="a50d8-110">Этот шаг может быть сделан клиентом MSSP или MSSP.</span><span class="sxs-lookup"><span data-stu-id="a50d8-110">This step can be done by either the MSSP customer or MSSP.</span></span> <span data-ttu-id="a50d8-111">MsSPs должны быть предоставлены соответствующие разрешения для настройки этого от имени клиента MSSP.</span><span class="sxs-lookup"><span data-stu-id="a50d8-111">MSSPs must be granted the appropriate permissions to configure this on behalf of the MSSP customer.</span></span>

<span data-ttu-id="a50d8-112">После предоставления доступа к порталу можно создать правила оповещения, чтобы сообщения электронной почты отправлялись в MSSPs при создания оповещений, связанных с клиентом, и удовлетворены заданные условия.</span><span class="sxs-lookup"><span data-stu-id="a50d8-112">After access the portal is granted, alert notification rules can to be created so that emails are sent to MSSPs when alerts associated with the tenant are created and set conditions are met.</span></span>

 
<span data-ttu-id="a50d8-113">Дополнительные сведения см. в [сообщении Create rules for alert notifications.](configure-email-notifications.md#create-rules-for-alert-notifications)</span><span class="sxs-lookup"><span data-stu-id="a50d8-113">For more information, see [Create rules for alert notifications](configure-email-notifications.md#create-rules-for-alert-notifications).</span></span>
 

<span data-ttu-id="a50d8-114">Эти флажки должны быть проверены:</span><span class="sxs-lookup"><span data-stu-id="a50d8-114">These check boxes must be checked:</span></span>
- <span data-ttu-id="a50d8-115">**Включайте имя организации** . Имя клиента будет добавлено в уведомления электронной почты</span><span class="sxs-lookup"><span data-stu-id="a50d8-115">**Include organization name** - The customer name will be added to email notifications</span></span>
- <span data-ttu-id="a50d8-116">**Включайте** ссылку портала для клиента - URL-адрес ссылки оповещения будет иметь определенный параметр клиента (tid=target_tenant_id), который позволяет прямой доступ к целевому порталу клиента.</span><span class="sxs-lookup"><span data-stu-id="a50d8-116">**Include tenant-specific portal link** - Alert link URL will have tenant specific parameter (tid=target_tenant_id) that allows direct access to target tenant portal</span></span>


## <a name="related-topics"></a><span data-ttu-id="a50d8-117">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="a50d8-117">Related topics</span></span>
- [<span data-ttu-id="a50d8-118">Предоставление доступа MSSP к порталу</span><span class="sxs-lookup"><span data-stu-id="a50d8-118">Grant MSSP access to the portal</span></span>](grant-mssp-access.md)
- [<span data-ttu-id="a50d8-119">Доступ к порталу клиентов MSSP</span><span class="sxs-lookup"><span data-stu-id="a50d8-119">Access the MSSP customer portal</span></span>](access-mssp-portal.md)
- [<span data-ttu-id="a50d8-120">Извлечение оповещений от клиента-клиента</span><span class="sxs-lookup"><span data-stu-id="a50d8-120">Fetch alerts from customer tenant</span></span>](fetch-alerts-mssp.md)
