---
title: Подложные уведомления о недоставленном сообщении и EOP
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 12/9/2016
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 6f64f2de-d626-48ed-8084-03cc72301aa4
ms.collection:
- M365-security-compliance
description: "Почтовые сообщения — это автоматизированные сообщения, которые отправляются почтовыми серверами, как правило, в результате входящих нежелательных сообщений. Список Backscatterer DNSBL \x97 это список IP-адресов, отправляющих подложные уведомления о недоставленном сообщении. Это не список злоумышленников, рассылающих нежелательную почту, и мы не пытаемся удалить наши серверы из него."
ms.openlocfilehash: e8a8f98045d111976078b09797a1078d0fbb6a6b
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/20/2019
ms.locfileid: "37090477"
---
# <a name="backscatter-messages-and-eop"></a><span data-ttu-id="6961a-105">Подложные уведомления о недоставленных сообщениях и EOP</span><span class="sxs-lookup"><span data-stu-id="6961a-105">Backscatter messages and EOP</span></span>

<span data-ttu-id="6961a-106">Почтовые сообщения — это автоматизированные сообщения, которые отправляются почтовыми серверами, как правило, в результате входящих нежелательных сообщений.</span><span class="sxs-lookup"><span data-stu-id="6961a-106">Backscatter messages are the automated bounce messages that are sent by mail servers, typically as a result of incoming spam.</span></span> <span data-ttu-id="6961a-107">Так как Exchange Online Protection (EOP)  это служба фильтрации нежелательной почты, сообщения электронной почты, отправленные несуществующим получателям и на другие подозрительные адреса, отклоняются нашей службой.</span><span class="sxs-lookup"><span data-stu-id="6961a-107">Because Exchange Online Protection (EOP) is a spam filtering service, email messages sent to nonexistent recipients and to other suspicious destinations are rejected by our service.</span></span> <span data-ttu-id="6961a-108">В этом случае EOP создает сообщение отчета о недоставке (NDR) и направляет его "отправителю".</span><span class="sxs-lookup"><span data-stu-id="6961a-108">When this happens, EOP generates a non-delivery report (NDR) message and delivers it back to the "sender."</span></span> <span data-ttu-id="6961a-109">Так как злоумышленники, рассылающие нежелательную почту, часто используют поддельный или недопустимый адрес отправителя в своих сообщениях, то после отправки отчета о недоставки может быть отправлено подложное уведомление о недоставленном сообщении.</span><span class="sxs-lookup"><span data-stu-id="6961a-109">Because spammers frequently use a forged or invalid "From" address in their messages, the sender address to which the NDR is sent may result in a backscatter message.</span></span> <span data-ttu-id="6961a-110">В этом случае серверы исходящей почты, связанные с сетью EOP, могут попасть в список блокировки DNS отправителей подложных сообщений Backscatterer (DNSBL).</span><span class="sxs-lookup"><span data-stu-id="6961a-110">When this happens, outgoing servers that are associated with the EOP network may be listed on the Backscatterer DNS Block List (DNSBL).</span></span> <span data-ttu-id="6961a-111">Список Backscatterer DNSBL  это список IP-адресов, отправляющих подложные уведомления о недоставленном сообщении.</span><span class="sxs-lookup"><span data-stu-id="6961a-111">The Backscatterer DNSBL is a list of IP addresses that send backscatter messages.</span></span> <span data-ttu-id="6961a-112">Это не список злоумышленников, рассылающих нежелательную почту, и мы не пытаемся удалить наши серверы из него.</span><span class="sxs-lookup"><span data-stu-id="6961a-112">It isn't a spammer list, and we don't try to remove our servers from the Backscatterer DNSBL.</span></span> 
  
> [!TIP]
> <span data-ttu-id="6961a-p103">Согласно инструкциям на веб-сайте Backscatterer использование режима отклонения для всех входящих сообщений не является рекомендуемой конфигурацией этой службы. Ее необходимо использовать в безопасном режиме. Дополнительные сведения о реализации правильной конфигурации Backscatterer см. на [веб-сайте Backscatterer.org](http://www.backscatterer.org/?target=usage).</span><span class="sxs-lookup"><span data-stu-id="6961a-p103">According to the instructions on the Backscatterer website, the use of reject mode for all incoming mail isn't a recommended configuration or use of that service. It should be used in safe mode instead. For more information about implementing the correct backscatter configuration, visit the [Backscatterer.org website](http://www.backscatterer.org/?target=usage).</span></span> 
  
## <a name="related-topics"></a><span data-ttu-id="6961a-116">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="6961a-116">Related topics</span></span>
  
[<span data-ttu-id="6961a-117">Параметры расширенной фильтрации нежелательной почты</span><span class="sxs-lookup"><span data-stu-id="6961a-117">Advanced spam filtering  options</span></span>](advanced-spam-filtering-asf-options.md)
  

