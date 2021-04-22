---
title: Обзор настраиваемого обнаружения в Microsoft 365 Defender
description: Понять, как можно использовать расширенный поиск для создания настраиваемой диагностики и создания оповещений
keywords: advanced hunting, threat hunting, cyber threat hunting, Microsoft 365 Defender, Microsoft 365, m365, search, query, telemetry, custom detections, schema, kusto
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
ms.openlocfilehash: bf635ed03cb0d99d54fc94b622bf244447b32a80
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935705"
---
# <a name="custom-detections-overview"></a><span data-ttu-id="ba744-104">Обзор настраиваемых обнаружений</span><span class="sxs-lookup"><span data-stu-id="ba744-104">Custom detections overview</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="ba744-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="ba744-105">**Applies to:**</span></span>
- <span data-ttu-id="ba744-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ba744-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="ba744-107">С помощью настраиваемого обнаружения можно активно отслеживать различные события и состояния системы и реагировать на них, в том числе заподозрить нарушения и неправильные конечные точки.</span><span class="sxs-lookup"><span data-stu-id="ba744-107">With custom detections, you can proactively monitor for and respond to various events and system states, including suspected breach activity and misconfigured endpoints.</span></span> <span data-ttu-id="ba744-108">Это делается возможным благодаря настраиваемым правилам обнаружения, которые автоматически запускают оповещения, а также действия реагирования.</span><span class="sxs-lookup"><span data-stu-id="ba744-108">This is made possible by customizable detection rules that automatically trigger alerts as well as response actions.</span></span>

<span data-ttu-id="ba744-109">Настраиваемые обнаружения [](advanced-hunting-overview.md)работают с расширенными средствами охоты, которые предоставляют мощный гибкий язык запросов, который охватывает широкий набор событий и системных сведений из сети.</span><span class="sxs-lookup"><span data-stu-id="ba744-109">Custom detections work with [advanced hunting](advanced-hunting-overview.md), which provides a powerful, flexible query language that covers a broad set of event and system information from your network.</span></span> <span data-ttu-id="ba744-110">Вы можете настроить их для запуска с регулярными интервалами, создавая оповещения и принимая ответные действия при совпадениях.</span><span class="sxs-lookup"><span data-stu-id="ba744-110">You can set them to run at regular intervals, generating alerts and taking response actions whenever there are matches.</span></span>

<span data-ttu-id="ba744-111">Настраиваемые обнаружения обеспечивают:</span><span class="sxs-lookup"><span data-stu-id="ba744-111">Custom detections provide:</span></span>
- <span data-ttu-id="ba744-112">Оповещений об обнаружении на основе правил, построенных из расширенных запросов на охоту</span><span class="sxs-lookup"><span data-stu-id="ba744-112">Alerts for rule-based detections built from advanced hunting queries</span></span>
- <span data-ttu-id="ba744-113">Действия автоматического ответа</span><span class="sxs-lookup"><span data-stu-id="ba744-113">Automatic response actions</span></span>

## <a name="see-also"></a><span data-ttu-id="ba744-114">См. также</span><span class="sxs-lookup"><span data-stu-id="ba744-114">See also</span></span>
- [<span data-ttu-id="ba744-115">Создание и управление пользовательскими правилами обнаружения</span><span class="sxs-lookup"><span data-stu-id="ba744-115">Create and manage custom detection rules</span></span>](custom-detection-rules.md)
- [<span data-ttu-id="ba744-116">Обзор расширенной охоты</span><span class="sxs-lookup"><span data-stu-id="ba744-116">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="ba744-117">Перенос расширенных запросов на охоту из Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="ba744-117">Migrate advanced hunting queries from Microsoft Defender for Endpoint</span></span>](advanced-hunting-migrate-from-mde.md)
