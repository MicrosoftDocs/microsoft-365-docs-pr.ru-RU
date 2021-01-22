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
ms.openlocfilehash: ae9617a55fd5efb40a3aba07202ebfb1494d4db6
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/22/2021
ms.locfileid: "49928812"
---
# <a name="custom-detections-overview"></a><span data-ttu-id="e3618-104">Обзор настраиваемых обнаружений</span><span class="sxs-lookup"><span data-stu-id="e3618-104">Custom detections overview</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="e3618-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="e3618-105">**Applies to:**</span></span>
- <span data-ttu-id="e3618-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e3618-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="e3618-107">С помощью настраиваемого обнаружения можно заблаговременно отслеживать различные события и состояния системы, включая подозрительные нарушения безопасности и неправильно настроенные конечные точки.</span><span class="sxs-lookup"><span data-stu-id="e3618-107">With custom detections, you can proactively monitor for and respond to various events and system states, including suspected breach activity and misconfigured endpoints.</span></span> <span data-ttu-id="e3618-108">Это можно сделать с помощью настраиваемых правил обнаружения, которые автоматически запускают оповещения, а также ответные действия.</span><span class="sxs-lookup"><span data-stu-id="e3618-108">This is made possible by customizable detection rules that automatically trigger alerts as well as response actions.</span></span>

<span data-ttu-id="e3618-109">Пользовательские обнаружения работают с [расширенным](advanced-hunting-overview.md)поиском, который предоставляет мощный гибкий язык запросов, который охватывает широкий набор событий и системных сведений из вашей сети.</span><span class="sxs-lookup"><span data-stu-id="e3618-109">Custom detections work with [advanced hunting](advanced-hunting-overview.md), which provides a powerful, flexible query language that covers a broad set of event and system information from your network.</span></span> <span data-ttu-id="e3618-110">Вы можете настроить их на регулярный запуск с регулярными интервалами, создавая оповещения и принимая ответные действия при совпадениях.</span><span class="sxs-lookup"><span data-stu-id="e3618-110">You can set them to run at regular intervals, generating alerts and taking response actions whenever there are matches.</span></span>

<span data-ttu-id="e3618-111">Настраиваемые обнаружения обеспечивают:</span><span class="sxs-lookup"><span data-stu-id="e3618-111">Custom detections provide:</span></span>
- <span data-ttu-id="e3618-112">Оповещения об обнаружении на основе правил, основанные на расширенных запросах охоты</span><span class="sxs-lookup"><span data-stu-id="e3618-112">Alerts for rule-based detections built from advanced hunting queries</span></span>
- <span data-ttu-id="e3618-113">Действия автоматического ответа</span><span class="sxs-lookup"><span data-stu-id="e3618-113">Automatic response actions</span></span>

## <a name="related-topic"></a><span data-ttu-id="e3618-114">Связанная тема</span><span class="sxs-lookup"><span data-stu-id="e3618-114">Related topic</span></span>
- [<span data-ttu-id="e3618-115">Создание пользовательских правил обнаружения и управление ими</span><span class="sxs-lookup"><span data-stu-id="e3618-115">Create and manage custom detection rules</span></span>](custom-detection-rules.md)
- [<span data-ttu-id="e3618-116">Обзор расширенной охоты на угрозы</span><span class="sxs-lookup"><span data-stu-id="e3618-116">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
