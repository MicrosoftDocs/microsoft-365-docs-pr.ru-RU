---
title: Обзор пользовательских обнаружений в ATP Защитника Майкрософт
ms.reviewer: ''
description: Понять, как можно использовать расширенный поиск для создания настраиваемой диагностики и создания оповещений
keywords: настраиваемые обнаружения, оповещения, правила обнаружения, расширенные охоты, охота, запрос, действия отклика, интервал, mdatp, microsoft defender atp
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: c5de642d2fd22301b5cef1cf3674e60529455d5e
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2021
ms.locfileid: "51186921"
---
# <a name="custom-detections-overview"></a><span data-ttu-id="0069a-104">Обзор настраиваемых обнаружений</span><span class="sxs-lookup"><span data-stu-id="0069a-104">Custom detections overview</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="0069a-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="0069a-105">**Applies to:**</span></span>
- [<span data-ttu-id="0069a-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="0069a-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="0069a-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0069a-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="0069a-108">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="0069a-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="0069a-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="0069a-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


<span data-ttu-id="0069a-110">С помощью настраиваемого обнаружения можно активно отслеживать различные события и состояния системы и реагировать на них, в том числе заподозрить нарушения и неправильно настроенные устройства.</span><span class="sxs-lookup"><span data-stu-id="0069a-110">With custom detections, you can proactively monitor for and respond to various events and system states, including suspected breach activity and misconfigured devices.</span></span> <span data-ttu-id="0069a-111">Это можно сделать с помощью настраиваемых правил обнаружения, автоматически запускаемых оповещений и ответных действий.</span><span class="sxs-lookup"><span data-stu-id="0069a-111">You can do this with customizable detection rules that automatically trigger alerts and response actions.</span></span>

<span data-ttu-id="0069a-112">Настраиваемые обнаружения [](advanced-hunting-overview.md)работают с расширенными средствами охоты, которые предоставляют мощный гибкий язык запросов, который охватывает широкий набор событий и системных сведений из сети.</span><span class="sxs-lookup"><span data-stu-id="0069a-112">Custom detections work with [advanced hunting](advanced-hunting-overview.md), which provides a powerful, flexible query language that covers a broad set of event and system information from your network.</span></span> <span data-ttu-id="0069a-113">Вы можете настроить их для запуска с регулярными интервалами, создавая оповещения и принимая ответные действия при совпадениях.</span><span class="sxs-lookup"><span data-stu-id="0069a-113">You can set them to run at regular intervals, generating alerts and taking response actions whenever there are matches.</span></span>

<span data-ttu-id="0069a-114">Настраиваемые обнаружения обеспечивают:</span><span class="sxs-lookup"><span data-stu-id="0069a-114">Custom detections provide:</span></span>
- <span data-ttu-id="0069a-115">Оповещений об обнаружении на основе правил, построенных из расширенных запросов на охоту</span><span class="sxs-lookup"><span data-stu-id="0069a-115">Alerts for rule-based detections built from advanced hunting queries</span></span>
- <span data-ttu-id="0069a-116">Действия автоматического ответа, применимые к файлам и устройствам</span><span class="sxs-lookup"><span data-stu-id="0069a-116">Automatic response actions that apply to files and devices</span></span>

## <a name="related-topics"></a><span data-ttu-id="0069a-117">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="0069a-117">Related topics</span></span>
- [<span data-ttu-id="0069a-118">Создание правил обнаружения</span><span class="sxs-lookup"><span data-stu-id="0069a-118">Create detection rules</span></span>](custom-detection-rules.md)
- [<span data-ttu-id="0069a-119">Просмотр и управление правилами обнаружения</span><span class="sxs-lookup"><span data-stu-id="0069a-119">View and manage detection rules</span></span>](custom-detections-manage.md)
- [<span data-ttu-id="0069a-120">Обзор расширенной охоты на угрозы</span><span class="sxs-lookup"><span data-stu-id="0069a-120">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
