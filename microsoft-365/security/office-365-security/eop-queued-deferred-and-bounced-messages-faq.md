---
title: Поставленные в очередь, отложенные и возвращенные сообщения EOP вопросы и ответы
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: troubleshooting
localization_priority: Normal
ms.assetid: 9d015a0d-52a0-484d-9a08-121d04f973d3
ms.custom:
- seo-marvel-apr2020
description: Ответы на наиболее распространенные вопросы о сообщениях, которые были в очереди, отложены или возвращены в процессе фильтрации Exchange Online Protection (EOP).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: e54a260a70a9c68a94412243308bffe60d989e99
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/18/2021
ms.locfileid: "50289703"
---
# <a name="eop-queued-deferred-and-bounced-messages-faq"></a><span data-ttu-id="c4cf8-103">Поставленные в очередь, отложенные и возвращенные сообщения EOP: вопросы и ответы</span><span class="sxs-lookup"><span data-stu-id="c4cf8-103">EOP queued, deferred, and bounced messages FAQ</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="c4cf8-104">**Область применения**</span><span class="sxs-lookup"><span data-stu-id="c4cf8-104">**Applies to**</span></span>
- [<span data-ttu-id="c4cf8-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="c4cf8-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="c4cf8-106">Microsoft Defender для Office 365 (план 1 и план 2)</span><span class="sxs-lookup"><span data-stu-id="c4cf8-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="c4cf8-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c4cf8-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="c4cf8-108">В этом разделе дан ответ на часто задающие вопросы о сообщениях, которые были в очереди, отложены или возвращены в процессе фильтрации Exchange Online Protection (EOP).</span><span class="sxs-lookup"><span data-stu-id="c4cf8-108">This topic provides answers to frequently asked questions about messages that have been queued, deferred, or bounced during the Exchange Online Protection (EOP) filtering process.</span></span>

## <a name="why-is-mail-queuing"></a><span data-ttu-id="c4cf8-109">Почему почтовые очереди?</span><span class="sxs-lookup"><span data-stu-id="c4cf8-109">Why is mail queuing?</span></span>

<span data-ttu-id="c4cf8-110">Сообщения добавляются в очередь или откладываются, если службе не удается установить соединение с сервером получателя для доставки.</span><span class="sxs-lookup"><span data-stu-id="c4cf8-110">Messages are queued or deferred if the service is unable to make a connection to the recipient server for delivery.</span></span> <span data-ttu-id="c4cf8-111">Сообщения не откладываются, если сеть получателя возвращает ошибку серии 500.</span><span class="sxs-lookup"><span data-stu-id="c4cf8-111">It will not defer messages if a 500-series error is returned from the recipient network.</span></span>

## <a name="how-does-a-message-become-deferred"></a><span data-ttu-id="c4cf8-112">Как сообщение становится отложенным?</span><span class="sxs-lookup"><span data-stu-id="c4cf8-112">How does a message become deferred?</span></span>

<span data-ttu-id="c4cf8-113">Сообщения будут удерживаться, когда не удается установить соединение с сервером получателя, или сервер возвращает временную ошибку, например истечение времени ожидания подключения, отказ в соединении или ошибку серии 400.</span><span class="sxs-lookup"><span data-stu-id="c4cf8-113">Messages will be held when a connection to the recipient server cannot be made and the recipient's server is returning a "temporary failure" such as a connection time-out, connection refused, or a 400-series error.</span></span> <span data-ttu-id="c4cf8-114">В случае постоянной ошибки, например ошибки серии 500, сообщение будет возвращено отправителю.</span><span class="sxs-lookup"><span data-stu-id="c4cf8-114">If there is a permanent failure, such as a 500-series error, then the message will be returned to the sender.</span></span>

## <a name="how-long-does-a-message-remain-in-deferral-and-what-is-the-retry-interval"></a><span data-ttu-id="c4cf8-115">Как долго сообщение остается в отсрочке и каков интервал между повторной попытку?</span><span class="sxs-lookup"><span data-stu-id="c4cf8-115">How long does a message remain in deferral and what is the retry interval?</span></span>

<span data-ttu-id="c4cf8-116">Отложенные сообщения будут оставаться в очередях в течение 1 дня.</span><span class="sxs-lookup"><span data-stu-id="c4cf8-116">Messages in deferral will remain in our queues for 1 day.</span></span> <span data-ttu-id="c4cf8-117">Попытки повторной отправки сообщений зависят от ошибки, полученной от почтовой системы получателя.</span><span class="sxs-lookup"><span data-stu-id="c4cf8-117">Message retry attempts are based on the error we get back from the recipient's mail system.</span></span> <span data-ttu-id="c4cf8-118">Первые несколько отложенных периодов — 15 минут или меньше, при этом последующие действия (в течение следующего полудюжины) увеличивают интервал между несколькими повторной задержкой до максимум 60 минут.</span><span class="sxs-lookup"><span data-stu-id="c4cf8-118">The first few deferrals are 15 minutes or less, with subsequent retries (over the next half dozen or so) increasing the interval over multiple retries to a max of 60 minutes.</span></span> <span data-ttu-id="c4cf8-119">Расширение длительности интервала является динамическим, учитывая несколько переменных, таких как размер очереди и приоритет внутренних сообщений.</span><span class="sxs-lookup"><span data-stu-id="c4cf8-119">The interval duration expansion is dynamic, taking into consideration multiple variables like queue sizes and internal message priority.</span></span> <span data-ttu-id="c4cf8-120">В базовом — 15 минут (или меньше) для начала, а затем расширение с этого времени в течение следующих нескольких часов до максимального максимума в 60 минут.</span><span class="sxs-lookup"><span data-stu-id="c4cf8-120">In basic, it's 15 minutes (or less) to start, then expanding from there over the next few hours to 60 mins max.</span></span>

## <a name="after-your-email-server-is-restored-how-are-queued-messages-distributed"></a><span data-ttu-id="c4cf8-121">Как сообщения в очереди распространяются после восстановления почтового сервера?</span><span class="sxs-lookup"><span data-stu-id="c4cf8-121">After your email server is restored, how are queued messages distributed?</span></span>

<span data-ttu-id="c4cf8-122">После восстановления почтового сервера все сообщения из очереди автоматически обрабатываются в то же порядке, в котором они были получены и добавлены в очередь, когда сервер стал недоступен.</span><span class="sxs-lookup"><span data-stu-id="c4cf8-122">After your email server is restored, all queued messages are automatically processed in the order in which they were received and queued when the server became unavailable.</span></span>
