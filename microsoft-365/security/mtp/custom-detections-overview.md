---
title: Обзор пользовательских обнаружений в Microsoft 365 Defender
description: Понять, как можно использовать расширенный поиск для создания пользовательских обнаружений и создания оповещений
keywords: advanced hunting, threat hunting, cyber threat hunting, microsoft threat protection, microsoft 365, mtp, m365, search, query, telemetry, custom detections, schema, kusto, microsoft 365, Microsoft Threat Protection
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: de9fb28f09b88cf1730f3bb3539234f6a03ec2e3
ms.sourcegitcommit: d354727303d9574991b5a0fd298d2c9414e19f6c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/02/2021
ms.locfileid: "50080717"
---
# <a name="custom-detections-overview"></a><span data-ttu-id="35121-104">Обзор настраиваемых обнаружений</span><span class="sxs-lookup"><span data-stu-id="35121-104">Custom detections overview</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="35121-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="35121-105">**Applies to:**</span></span>
- <span data-ttu-id="35121-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="35121-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="35121-107">С помощью настраиваемого обнаружения можно заблаговременно отслеживать различные события и состояния системы, включая подозрительные нарушения безопасности и неправильно настроенные конечные точки.</span><span class="sxs-lookup"><span data-stu-id="35121-107">With custom detections, you can proactively monitor for and respond to various events and system states, including suspected breach activity and misconfigured endpoints.</span></span> <span data-ttu-id="35121-108">Это можно сделать с помощью настраиваемых правил обнаружения, которые автоматически запускают оповещения, а также ответные действия.</span><span class="sxs-lookup"><span data-stu-id="35121-108">This is made possible by customizable detection rules that automatically trigger alerts as well as response actions.</span></span>

<span data-ttu-id="35121-109">Пользовательские обнаружения работают с [расширенным](advanced-hunting-overview.md)поиском, который предоставляет мощный гибкий язык запросов, который охватывает широкий набор событий и системных сведений из вашей сети.</span><span class="sxs-lookup"><span data-stu-id="35121-109">Custom detections work with [advanced hunting](advanced-hunting-overview.md), which provides a powerful, flexible query language that covers a broad set of event and system information from your network.</span></span> <span data-ttu-id="35121-110">Вы можете настроить их на регулярный запуск, создавая оповещения и принимая ответные действия при совпадениях.</span><span class="sxs-lookup"><span data-stu-id="35121-110">You can set them to run at regular intervals, generating alerts and taking response actions whenever there are matches.</span></span>

<span data-ttu-id="35121-111">Настраиваемые обнаружения обеспечивают:</span><span class="sxs-lookup"><span data-stu-id="35121-111">Custom detections provide:</span></span>
- <span data-ttu-id="35121-112">Оповещения об обнаружении на основе правил, основанные на расширенных запросах охоты</span><span class="sxs-lookup"><span data-stu-id="35121-112">Alerts for rule-based detections built from advanced hunting queries</span></span>
- <span data-ttu-id="35121-113">Действия автоматического ответа</span><span class="sxs-lookup"><span data-stu-id="35121-113">Automatic response actions</span></span>

## <a name="see-also"></a><span data-ttu-id="35121-114">См. также</span><span class="sxs-lookup"><span data-stu-id="35121-114">See also</span></span>
- [<span data-ttu-id="35121-115">Создание пользовательских правил обнаружения и управление ими</span><span class="sxs-lookup"><span data-stu-id="35121-115">Create and manage custom detection rules</span></span>](custom-detection-rules.md)
- [<span data-ttu-id="35121-116">Обзор расширенной охоты на угрозы</span><span class="sxs-lookup"><span data-stu-id="35121-116">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="35121-117">Перенос запросов на расширенный поиск из Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="35121-117">Migrate advanced hunting queries from Microsoft Defender for Endpoint</span></span>](advanced-hunting-migrate-from-mdatp.md)
