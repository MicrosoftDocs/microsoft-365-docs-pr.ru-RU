---
title: Анализ исправления возможного почтового цикла
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
ms.assetid: cb801985-3c89-4979-9c18-17829a4cb563
ms.custom:
- seo-marvel-apr2020
description: Администраторы могут узнать, как использовать сведения о возможном выполнении циклов почты в панели мониторинга потока почты в Центре & безопасности для определения и исправления циклов почты в своей организации.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 8bb08eb2f9a5ea0eb72433f92b6d28175edc75b8
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51071301"
---
# <a name="fix-possible-mail-loop-insight-in-the-security--compliance-center"></a><span data-ttu-id="97e37-103">Исправление возможного анализа циклов почты в Центре & безопасности</span><span class="sxs-lookup"><span data-stu-id="97e37-103">Fix possible mail loop insight in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="97e37-104">**Область применения**</span><span class="sxs-lookup"><span data-stu-id="97e37-104">**Applies to**</span></span>
- [<span data-ttu-id="97e37-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="97e37-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="97e37-106">Microsoft Defender для Office 365 (план 1 и план 2)</span><span class="sxs-lookup"><span data-stu-id="97e37-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="97e37-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="97e37-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="97e37-108">Циклы почты являются плохими, так как:</span><span class="sxs-lookup"><span data-stu-id="97e37-108">Mail loops are bad because:</span></span>

- <span data-ttu-id="97e37-109">Они растратяют системные ресурсы.</span><span class="sxs-lookup"><span data-stu-id="97e37-109">They waste system resources.</span></span>
- <span data-ttu-id="97e37-110">Они потребляют квоту объема почты организации.</span><span class="sxs-lookup"><span data-stu-id="97e37-110">They consume your organization's mail volume quota.</span></span>
- <span data-ttu-id="97e37-111">Они отправляют запутанные отчеты о невывозе (также известных как NDRs или сообщения отказов) отправителям исходных сообщений.</span><span class="sxs-lookup"><span data-stu-id="97e37-111">They send confusing non-delivery reports (also known as NDRs or bounce messages) to the original message senders.</span></span>

<span data-ttu-id="97e37-112">Сведения о **возможном** выполнении циклов почты [](mail-flow-insights-v2.md) в рекомендуемой [](https://protection.office.com) для вас области панели мониторинга потока почты в Центре соответствия требованиям безопасности & о том, когда в организации обнаружен цикл почты. </span><span class="sxs-lookup"><span data-stu-id="97e37-112">The **Fix possible mail loop** insight in the **Recommended for you** area of the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com) notifies you when a mail loop is detected in your organization.</span></span>

<span data-ttu-id="97e37-113">Это представление появляется только после обнаружения условия (если у вас нет каких-либо циклов почты, вы не увидите представление).</span><span class="sxs-lookup"><span data-stu-id="97e37-113">This insight appears only after the condition is detected (if you don't have any mail loops, you won't see the insight).</span></span>

![Исправлено представление правил медленного потока почты в рекомендуемой для вас области панели мониторинга потока почты](../../media/mfi-fix-possible-mail-loop.png)

<span data-ttu-id="97e37-115">При **нажатии сведений о** просмотре на виджете появляется флажок с дополнительными сведениями:</span><span class="sxs-lookup"><span data-stu-id="97e37-115">When you click **View details** on the widget, a flyout appears with more information:</span></span>

- <span data-ttu-id="97e37-116">**Домен**</span><span class="sxs-lookup"><span data-stu-id="97e37-116">**Domain**</span></span>
- <span data-ttu-id="97e37-117">**Количество сообщений.** Вы можете щелкнуть **просмотреть** примеры сообщений, чтобы просмотреть результаты трассировки сообщений для примера сообщений, затронутых циклом. [](message-trace-scc.md)</span><span class="sxs-lookup"><span data-stu-id="97e37-117">**Number of messages**: You can click **View sample messages** to see the [message trace](message-trace-scc.md) results for a sample of the messages that were affected by the loop.</span></span>
- <span data-ttu-id="97e37-118">**Тип домена**" Например, авторитетный или неавтетный.</span><span class="sxs-lookup"><span data-stu-id="97e37-118">**Domain type**" For example, Authoritative or Non-authoritative.</span></span>
- <span data-ttu-id="97e37-119">**Запись MX:** хост **(почтовый сервер)** и значения приоритета записи MX для домена. </span><span class="sxs-lookup"><span data-stu-id="97e37-119">**MX record**: The host (**Mail server**) and **Priority** values of the MX record for the domain.</span></span>
- <span data-ttu-id="97e37-120">**Причина цикла** **и исправление.** Мы определяем наиболее распространенные сценарии циклов почты и предоставляем рекомендуемые действия для исправления цикла.</span><span class="sxs-lookup"><span data-stu-id="97e37-120">**Loop reason** and **How to fix**: We'll identify the most common mail loop scenarios and provide recommended actions to fix the loop.</span></span>

![Подробные сведения, которые появляются после нажатия просмотра сведений о возможной проницательности цикла исправлений](../../media/mfi-fix-possible-mail-loop-details.png)

## <a name="see-also"></a><span data-ttu-id="97e37-122">См. также</span><span class="sxs-lookup"><span data-stu-id="97e37-122">See also</span></span>

<span data-ttu-id="97e37-123">Сведения о других сведениях в панели мониторинга потока почты см. в странице Анализ потока почты в Центре [& соответствия](mail-flow-insights-v2.md)требованиям.</span><span class="sxs-lookup"><span data-stu-id="97e37-123">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
