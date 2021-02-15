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
description: Администраторы могут узнать, как использовать анализ возможных почтовых циклов fix на панели мониторинга потока обработки почты в Центре безопасности & соответствия требованиям для определения и исправления почтовых циклов в организации.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 3c9607f053fb5011b8c8af3c8bb2073a9d022909
ms.sourcegitcommit: e920e68c8d0eac8b152039b52cfc139d478a67b3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/09/2021
ms.locfileid: "50150235"
---
# <a name="fix-possible-mail-loop-insight-in-the-security--compliance-center"></a><span data-ttu-id="078ad-103">Исправление возможной информации о почтовом цикле в Центре & соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="078ad-103">Fix possible mail loop insight in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="078ad-104">**Область применения**</span><span class="sxs-lookup"><span data-stu-id="078ad-104">**Applies to**</span></span>
- [<span data-ttu-id="078ad-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="078ad-105">Exchange Online Protection</span></span>](https://go.microsoft.com/fwlink/?linkid=2148611)
- [<span data-ttu-id="078ad-106">Microsoft Defender для Office 365 (план 1 и план 2)</span><span class="sxs-lookup"><span data-stu-id="078ad-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](https://go.microsoft.com/fwlink/?linkid=2148715)
- [<span data-ttu-id="078ad-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="078ad-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="078ad-108">Почтовые циклы являются плохими, так как:</span><span class="sxs-lookup"><span data-stu-id="078ad-108">Mail loops are bad because:</span></span>

- <span data-ttu-id="078ad-109">Они тратить системные ресурсы.</span><span class="sxs-lookup"><span data-stu-id="078ad-109">They waste system resources.</span></span>
- <span data-ttu-id="078ad-110">Они потребляют квоту тома почты организации.</span><span class="sxs-lookup"><span data-stu-id="078ad-110">They consume your organization's mail volume quota.</span></span>
- <span data-ttu-id="078ad-111">Отправителю исходного сообщения отправляются запутанные отчеты о не доставке (также известные как отчеты о доставке или сообщения о возврате).</span><span class="sxs-lookup"><span data-stu-id="078ad-111">They send confusing non-delivery reports (also known as NDRs or bounce messages) to the original message senders.</span></span>

<span data-ttu-id="078ad-112">Анализ **возможных** почтовых циклов в области "Рекомендуемый для вас" панели мониторинга потока обработки почты в Центре безопасности и [соответствия](https://protection.office.com) требованиям & сообщает вам об обнаружении почтового цикла в организации.  [](mail-flow-insights-v2.md)</span><span class="sxs-lookup"><span data-stu-id="078ad-112">The **Fix possible mail loop** insight in the **Recommended for you** area of the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com) notifies you when a mail loop is detected in your organization.</span></span>

<span data-ttu-id="078ad-113">Эта информация отображается только после обнаружения условия (если у вас нет почтовых циклов, вы не увидите эти данные).</span><span class="sxs-lookup"><span data-stu-id="078ad-113">This insight appears only after the condition is detected (if you don't have any mail loops, you won't see the insight).</span></span>

![Исправление статистики о медленных правилах потока почты в области "Рекомендуемые для вас" панели мониторинга потока почты](../../media/mfi-fix-possible-mail-loop.png)

<span data-ttu-id="078ad-115">При **нажатии кнопки "Просмотреть сведения о** виджете" появится элемент с дополнительными сведениями:</span><span class="sxs-lookup"><span data-stu-id="078ad-115">When you click **View details** on the widget, a flyout appears with more information:</span></span>

- <span data-ttu-id="078ad-116">**Домен**</span><span class="sxs-lookup"><span data-stu-id="078ad-116">**Domain**</span></span>
- <span data-ttu-id="078ad-117">**Количество сообщений:** вы  можете щелкнуть "Просмотреть образцы сообщений", чтобы просмотреть результаты трассировки сообщений для примера сообщений, на которые повлиял цикл. [](message-trace-scc.md)</span><span class="sxs-lookup"><span data-stu-id="078ad-117">**Number of messages**: You can click **View sample messages** to see the [message trace](message-trace-scc.md) results for a sample of the messages that were affected by the loop.</span></span>
- <span data-ttu-id="078ad-118">**Тип домена**" Например, "До полномочного" или "Не до полномочного".</span><span class="sxs-lookup"><span data-stu-id="078ad-118">**Domain type**" For example, Authoritative or Non-authoritative.</span></span>
- <span data-ttu-id="078ad-119">**MX record**: The host (**Mail server**) and **Priority** values of the MX record for the domain.</span><span class="sxs-lookup"><span data-stu-id="078ad-119">**MX record**: The host (**Mail server**) and **Priority** values of the MX record for the domain.</span></span>
- <span data-ttu-id="078ad-120">**Причина цикла** **и исправление:** мы оденем наиболее распространенные сценарии почтового цикла и предоставляем рекомендуемые действия для его устранения.</span><span class="sxs-lookup"><span data-stu-id="078ad-120">**Loop reason** and **How to fix**: We'll identify the most common mail loop scenarios and provide recommended actions to fix the loop.</span></span>

![Flyout Details that appears after clicking View details on the Fix possible mail loop insight](../../media/mfi-fix-possible-mail-loop-details.png)

## <a name="see-also"></a><span data-ttu-id="078ad-122">См. также</span><span class="sxs-lookup"><span data-stu-id="078ad-122">See also</span></span>

<span data-ttu-id="078ad-123">Сведения о других сведениях на панели мониторинга потока обработки почты см. в анализе потока обработки почты в Центре безопасности [& соответствия требованиям.](mail-flow-insights-v2.md)</span><span class="sxs-lookup"><span data-stu-id="078ad-123">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
