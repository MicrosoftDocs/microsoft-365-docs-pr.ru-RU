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
description: Найдите ответы на наиболее распространенные вопросы о сообщениях, которые были в очереди, отложены или отскочили во время процесса фильтрации Exchange Online Protection (EOP).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: c7b5ba595e9a6401efd1b733c9e5a11c8a966037
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/25/2021
ms.locfileid: "51206788"
---
# <a name="eop-queued-deferred-and-bounced-messages-faq"></a><span data-ttu-id="31d1d-103">Поставленные в очередь, отложенные и возвращенные сообщения EOP: вопросы и ответы</span><span class="sxs-lookup"><span data-stu-id="31d1d-103">EOP queued, deferred, and bounced messages FAQ</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="31d1d-104">**Область применения**</span><span class="sxs-lookup"><span data-stu-id="31d1d-104">**Applies to**</span></span>
- [<span data-ttu-id="31d1d-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="31d1d-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="31d1d-106">Microsoft Defender для Office 365 (план 1 и план 2)</span><span class="sxs-lookup"><span data-stu-id="31d1d-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="31d1d-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="31d1d-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="31d1d-108">В этом разделе можно найти ответы на часто задамые вопросы о сообщениях, которые были в очереди, отложены или отскочили во время процесса фильтрации Exchange Online Protection (EOP).</span><span class="sxs-lookup"><span data-stu-id="31d1d-108">This topic provides answers to frequently asked questions about messages that have been queued, deferred, or bounced during the Exchange Online Protection (EOP) filtering process.</span></span>

## <a name="why-is-mail-queuing"></a><span data-ttu-id="31d1d-109">Почему очередь на почту?</span><span class="sxs-lookup"><span data-stu-id="31d1d-109">Why is mail queuing?</span></span>

<span data-ttu-id="31d1d-110">Сообщения добавляются в очередь или откладываются, если службе не удается установить соединение с сервером получателя для доставки.</span><span class="sxs-lookup"><span data-stu-id="31d1d-110">Messages are queued or deferred if the service is unable to make a connection to the recipient server for delivery.</span></span> <span data-ttu-id="31d1d-111">Сообщения не откладываются, если сеть получателя возвращает ошибку серии 500.</span><span class="sxs-lookup"><span data-stu-id="31d1d-111">It will not defer messages if a 500-series error is returned from the recipient network.</span></span>

## <a name="how-does-a-message-become-deferred"></a><span data-ttu-id="31d1d-112">Как отложено сообщение?</span><span class="sxs-lookup"><span data-stu-id="31d1d-112">How does a message become deferred?</span></span>

<span data-ttu-id="31d1d-113">Сообщения будут удерживаться, когда не удается установить соединение с сервером получателя, или сервер возвращает временную ошибку, например истечение времени ожидания подключения, отказ в соединении или ошибку серии 400.</span><span class="sxs-lookup"><span data-stu-id="31d1d-113">Messages will be held when a connection to the recipient server cannot be made and the recipient's server is returning a "temporary failure" such as a connection time-out, connection refused, or a 400-series error.</span></span> <span data-ttu-id="31d1d-114">В случае постоянной ошибки, например ошибки серии 500, сообщение будет возвращено отправителю.</span><span class="sxs-lookup"><span data-stu-id="31d1d-114">If there is a permanent failure, such as a 500-series error, then the message will be returned to the sender.</span></span>

## <a name="how-long-does-a-message-remain-in-deferral-and-what-is-the-retry-interval"></a><span data-ttu-id="31d1d-115">Как долго сообщение остается в отсрочке и каков интервал повторной работы?</span><span class="sxs-lookup"><span data-stu-id="31d1d-115">How long does a message remain in deferral and what is the retry interval?</span></span>

<span data-ttu-id="31d1d-116">Сообщения в отсрочке останутся в очередях в течение 1 дня.</span><span class="sxs-lookup"><span data-stu-id="31d1d-116">Messages in deferral will remain in our queues for 1 day.</span></span> <span data-ttu-id="31d1d-117">Попытки повторной отправки сообщений зависят от ошибки, полученной от почтовой системы получателя.</span><span class="sxs-lookup"><span data-stu-id="31d1d-117">Message retry attempts are based on the error we get back from the recipient's mail system.</span></span> <span data-ttu-id="31d1d-118">Первые несколько отложений — 15 минут или меньше, а последующие ириски (в течение следующих полудюжины или около того) увеличивают интервал между несколькими ирисами до максимума 60 минут.</span><span class="sxs-lookup"><span data-stu-id="31d1d-118">The first few deferrals are 15 minutes or less, with subsequent retries (over the next half dozen or so) increasing the interval over multiple retries to a max of 60 minutes.</span></span> <span data-ttu-id="31d1d-119">Расширение длительности интервала динамическое с учетом нескольких переменных, таких как размеры очереди и приоритет внутренних сообщений.</span><span class="sxs-lookup"><span data-stu-id="31d1d-119">The interval duration expansion is dynamic, taking into consideration multiple variables like queue sizes and internal message priority.</span></span> <span data-ttu-id="31d1d-120">В основном, это 15 минут (или меньше) для запуска, а затем расширения оттуда в течение следующих нескольких часов до 60 минут максимума.</span><span class="sxs-lookup"><span data-stu-id="31d1d-120">In basic, it's 15 minutes (or less) to start, then expanding from there over the next few hours to 60 mins max.</span></span>

## <a name="after-your-email-server-is-restored-how-are-queued-messages-distributed"></a><span data-ttu-id="31d1d-121">Как распределяются сообщения в очереди после восстановления сервера электронной почты?</span><span class="sxs-lookup"><span data-stu-id="31d1d-121">After your email server is restored, how are queued messages distributed?</span></span>

<span data-ttu-id="31d1d-122">После восстановления почтового сервера все сообщения из очереди автоматически обрабатываются в то же порядке, в котором они были получены и добавлены в очередь, когда сервер стал недоступен.</span><span class="sxs-lookup"><span data-stu-id="31d1d-122">After your email server is restored, all queued messages are automatically processed in the order in which they were received and queued when the server became unavailable.</span></span>
