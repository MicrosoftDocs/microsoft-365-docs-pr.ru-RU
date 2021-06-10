---
title: Обзор настраиваемого обнаружения в Microsoft 365 Defender
description: Понять, как можно использовать расширенный поиск для создания настраиваемой диагностики и создания оповещений
keywords: передовая охота, охота на угрозы, охота на киберугрозы, Microsoft 365 Defender, Microsoft 365, m365, поиск, запрос, телеметрия, настраиваемые обнаружения, схема, кусто
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 748b3534ef1f6ca5736667fc3910bb9fa96d23ff
ms.sourcegitcommit: 7cc2be0244fcc30049351e35c25369cacaaf4ca9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2021
ms.locfileid: "51952540"
---
# <a name="custom-detections-overview"></a><span data-ttu-id="5a53a-104">Обзор настраиваемых обнаружений</span><span class="sxs-lookup"><span data-stu-id="5a53a-104">Custom detections overview</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="5a53a-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="5a53a-105">**Applies to:**</span></span>
- <span data-ttu-id="5a53a-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5a53a-106">Microsoft 365 Defender</span></span>
- <span data-ttu-id="5a53a-107">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="5a53a-107">Microsoft Defender for Endpoint</span></span>

<span data-ttu-id="5a53a-108">С помощью настраиваемого обнаружения можно активно отслеживать различные события и состояния системы и реагировать на них, в том числе заподозрить нарушения и неправильные конечные точки.</span><span class="sxs-lookup"><span data-stu-id="5a53a-108">With custom detections, you can proactively monitor for and respond to various events and system states, including suspected breach activity and misconfigured endpoints.</span></span> <span data-ttu-id="5a53a-109">Это делается возможным благодаря настраиваемым правилам обнаружения, которые автоматически запускают оповещения, а также действия реагирования.</span><span class="sxs-lookup"><span data-stu-id="5a53a-109">This is made possible by customizable detection rules that automatically trigger alerts as well as response actions.</span></span>

<span data-ttu-id="5a53a-110">Настраиваемые обнаружения [](advanced-hunting-overview.md)работают с расширенными средствами охоты, которые предоставляют мощный гибкий язык запросов, который охватывает широкий набор событий и системных сведений из сети.</span><span class="sxs-lookup"><span data-stu-id="5a53a-110">Custom detections work with [advanced hunting](advanced-hunting-overview.md), which provides a powerful, flexible query language that covers a broad set of event and system information from your network.</span></span> <span data-ttu-id="5a53a-111">Вы можете настроить их для запуска с регулярными интервалами, создавая оповещения и принимая ответные действия при совпадениях.</span><span class="sxs-lookup"><span data-stu-id="5a53a-111">You can set them to run at regular intervals, generating alerts and taking response actions whenever there are matches.</span></span>

<span data-ttu-id="5a53a-112">Настраиваемые обнаружения обеспечивают:</span><span class="sxs-lookup"><span data-stu-id="5a53a-112">Custom detections provide:</span></span>
- <span data-ttu-id="5a53a-113">Оповещений об обнаружении на основе правил, построенных из расширенных запросов на охоту</span><span class="sxs-lookup"><span data-stu-id="5a53a-113">Alerts for rule-based detections built from advanced hunting queries</span></span>
- <span data-ttu-id="5a53a-114">Действия автоматического ответа</span><span class="sxs-lookup"><span data-stu-id="5a53a-114">Automatic response actions</span></span>

## <a name="see-also"></a><span data-ttu-id="5a53a-115">См. также</span><span class="sxs-lookup"><span data-stu-id="5a53a-115">See also</span></span>
- [<span data-ttu-id="5a53a-116">Создание и управление пользовательскими правилами обнаружения</span><span class="sxs-lookup"><span data-stu-id="5a53a-116">Create and manage custom detection rules</span></span>](custom-detection-rules.md)
- [<span data-ttu-id="5a53a-117">Обзор расширенной охоты</span><span class="sxs-lookup"><span data-stu-id="5a53a-117">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="5a53a-118">Перенос расширенных запросов на охоту из Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="5a53a-118">Migrate advanced hunting queries from Microsoft Defender for Endpoint</span></span>](advanced-hunting-migrate-from-mde.md)
