---
title: Поставленные в очередь, отложенные и возвращенные сообщения EOP вопросы и ответы
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 9d015a0d-52a0-484d-9a08-121d04f973d3
ms.custom:
- seo-marvel-apr2020
description: Здесь вы найдете ответы на наиболее распространенные вопросы о сообщениях, помещенных в очередь, отложенных или возвращенных в ходе процесса фильтрации Exchange Online Protection (EOP).
ms.openlocfilehash: 38e72a04e855862c621bd2b170c11407e0d22af3
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/12/2020
ms.locfileid: "44206596"
---
# <a name="eop-queued-deferred-and-bounced-messages-faq"></a><span data-ttu-id="a2554-103">Поставленные в очередь, отложенные и возвращенные сообщения EOP: вопросы и ответы</span><span class="sxs-lookup"><span data-stu-id="a2554-103">EOP queued, deferred, and bounced messages FAQ</span></span>

<span data-ttu-id="a2554-104">В этом разделе приведены ответы на часто задаваемые вопросы о сообщениях, помещенных в очередь, отложенных или возвращенных в ходе процесса фильтрации Exchange Online Protection (EOP).</span><span class="sxs-lookup"><span data-stu-id="a2554-104">This topic provides answers to frequently asked questions about messages that have been queued, deferred, or bounced during the Exchange Online Protection (EOP) filtering process.</span></span>

## <a name="why-is-mail-queuing"></a><span data-ttu-id="a2554-105">Почему почтовые очереди?</span><span class="sxs-lookup"><span data-stu-id="a2554-105">Why is mail queuing?</span></span>

<span data-ttu-id="a2554-106">Сообщения добавляются в очередь или откладываются, если службе не удается установить соединение с сервером получателя для доставки.</span><span class="sxs-lookup"><span data-stu-id="a2554-106">Messages are queued or deferred if the service is unable to make a connection to the recipient server for delivery.</span></span> <span data-ttu-id="a2554-107">Сообщения не откладываются, если сеть получателя возвращает ошибку серии 500.</span><span class="sxs-lookup"><span data-stu-id="a2554-107">It will not defer messages if a 500-series error is returned from the recipient network.</span></span>

## <a name="how-does-a-message-become-deferred"></a><span data-ttu-id="a2554-108">Как сообщение откладывается?</span><span class="sxs-lookup"><span data-stu-id="a2554-108">How does a message become deferred?</span></span>

<span data-ttu-id="a2554-109">Сообщения будут удерживаться, когда не удается установить соединение с сервером получателя, или сервер возвращает временную ошибку, например истечение времени ожидания подключения, отказ в соединении или ошибку серии 400.</span><span class="sxs-lookup"><span data-stu-id="a2554-109">Messages will be held when a connection to the recipient server cannot be made and the recipient's server is returning a "temporary failure" such as a connection time-out, connection refused, or a 400-series error.</span></span> <span data-ttu-id="a2554-110">В случае постоянной ошибки, например ошибки серии 500, сообщение будет возвращено отправителю.</span><span class="sxs-lookup"><span data-stu-id="a2554-110">If there is a permanent failure, such as a 500-series error, then the message will be returned to the sender.</span></span>

## <a name="how-long-does-a-message-remain-in-deferral-and-what-is-the-retry-interval"></a><span data-ttu-id="a2554-111">Как долго сообщение будет находиться в РБП и каков интервал повтора?</span><span class="sxs-lookup"><span data-stu-id="a2554-111">How long does a message remain in deferral and what is the retry interval?</span></span>

<span data-ttu-id="a2554-112">Сообщения в РБП останутся в очередях в течение 1 дня.</span><span class="sxs-lookup"><span data-stu-id="a2554-112">Messages in deferral will remain in our queues for 1 day.</span></span> <span data-ttu-id="a2554-113">Попытки повторной отправки сообщений зависят от ошибки, полученной от почтовой системы получателя.</span><span class="sxs-lookup"><span data-stu-id="a2554-113">Message retry attempts are based on the error we get back from the recipient's mail system.</span></span> <span data-ttu-id="a2554-114">Первые несколько РБП выводятся 15 минут или меньше, при последующих повторах (на ближайшие половины десятков) увеличивается интервал до нескольких повторов в течение 60 минут.</span><span class="sxs-lookup"><span data-stu-id="a2554-114">The first few deferrals are 15 minutes or less, with subsequent retries (over the next half dozen or so) increasing the interval over multiple retries to a max of 60 minutes.</span></span> <span data-ttu-id="a2554-115">Расширение длительности интервала является динамическим, учитывая несколько переменных, таких как размер очереди и внутренний приоритет сообщений.</span><span class="sxs-lookup"><span data-stu-id="a2554-115">The interval duration expansion is dynamic, taking into consideration multiple variables like queue sizes and internal message priority.</span></span> <span data-ttu-id="a2554-116">В основном это 15 минут (или меньше) для запуска, а затем развертывание в течение следующих нескольких часов до 60 мин.</span><span class="sxs-lookup"><span data-stu-id="a2554-116">In basic, it's 15 minutes (or less) to start, then expanding from there over the next few hours to 60 mins max.</span></span>

## <a name="after-your-email-server-is-restored-how-are-queued-messages-distributed"></a><span data-ttu-id="a2554-117">Когда ваш сервер электронной почты будет восстановлен, как будут распространяться сообщения из очереди?</span><span class="sxs-lookup"><span data-stu-id="a2554-117">After your email server is restored, how are queued messages distributed?</span></span>

<span data-ttu-id="a2554-118">После восстановления почтового сервера все сообщения из очереди автоматически обрабатываются в то же порядке, в котором они были получены и добавлены в очередь, когда сервер стал недоступен.</span><span class="sxs-lookup"><span data-stu-id="a2554-118">After your email server is restored, all queued messages are automatically processed in the order in which they were received and queued when the server became unavailable.</span></span>
