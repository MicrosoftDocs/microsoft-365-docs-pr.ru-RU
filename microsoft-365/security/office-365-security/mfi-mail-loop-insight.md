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
description: Администраторы могут узнать, как использовать анализ возможных почтовых циклов fix на панели мониторинга потока обработки почты в Центре безопасности и соответствия требованиям & для определения и исправления почтовых циклов в организации.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: f08c27c761cdfe4acbbd8cf80e8ab6da8012b55f
ms.sourcegitcommit: 537e513a4a232a01e44ecbc76d86a8bcaf142482
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/27/2021
ms.locfileid: "50029898"
---
# <a name="fix-possible-mail-loop-insight-in-the-security--compliance-center"></a><span data-ttu-id="899fb-103">Исправление возможной информации о почтовом цикле в Центре & соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="899fb-103">Fix possible mail loop insight in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="899fb-104">Почтовые циклы являются плохими, так как:</span><span class="sxs-lookup"><span data-stu-id="899fb-104">Mail loops are bad because:</span></span>

- <span data-ttu-id="899fb-105">Они тратить системные ресурсы.</span><span class="sxs-lookup"><span data-stu-id="899fb-105">They waste system resources.</span></span>
- <span data-ttu-id="899fb-106">Они потребляют квоту тома почты организации.</span><span class="sxs-lookup"><span data-stu-id="899fb-106">They consume your organization's mail volume quota.</span></span>
- <span data-ttu-id="899fb-107">Отправителю исходного сообщения отправляются запутанные отчеты о не доставке (также известные как сообщения о возврате).</span><span class="sxs-lookup"><span data-stu-id="899fb-107">They send confusing non-delivery reports (also known as NDRs or bounce messages) to the original message senders.</span></span>

<span data-ttu-id="899fb-108">Анализ **возможных** почтовых циклов в области "Рекомендуемый для вас" панели мониторинга потока обработки почты в Центре безопасности и [соответствия](https://protection.office.com) требованиям & сообщает вам об обнаружении почтового цикла в организации.  [](mail-flow-insights-v2.md)</span><span class="sxs-lookup"><span data-stu-id="899fb-108">The **Fix possible mail loop** insight in the **Recommended for you** area of the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com) notifies you when a mail loop is detected in your organization.</span></span>

<span data-ttu-id="899fb-109">Эта информация отображается только после обнаружения условия (если у вас нет почтовых циклов, вы не увидите эти данные).</span><span class="sxs-lookup"><span data-stu-id="899fb-109">This insight appears only after the condition is detected (if you don't have any mail loops, you won't see the insight).</span></span>

![Исправление статистики о медленных правилах потока почты в области "Рекомендуемые для вас" панели мониторинга потока почты](../../media/mfi-fix-possible-mail-loop.png)

<span data-ttu-id="899fb-111">При **нажатии кнопки "Просмотреть сведения о** виджете" появится элемент с дополнительными сведениями:</span><span class="sxs-lookup"><span data-stu-id="899fb-111">When you click **View details** on the widget, a flyout appears with more information:</span></span>

- <span data-ttu-id="899fb-112">**Домен**</span><span class="sxs-lookup"><span data-stu-id="899fb-112">**Domain**</span></span>
- <span data-ttu-id="899fb-113">**Количество сообщений:** вы  можете щелкнуть "Просмотреть образцы сообщений", чтобы просмотреть результаты трассировки сообщений для примера сообщений, на которые повлиял цикл. [](message-trace-scc.md)</span><span class="sxs-lookup"><span data-stu-id="899fb-113">**Number of messages**: You can click **View sample messages** to see the [message trace](message-trace-scc.md) results for a sample of the messages that were affected by the loop.</span></span>
- <span data-ttu-id="899fb-114">**Тип домена**" Например, "До полномочного" или "Не до полномочного".</span><span class="sxs-lookup"><span data-stu-id="899fb-114">**Domain type**" For example, Authoritative or Non-authoritative.</span></span>
- <span data-ttu-id="899fb-115">**MX record**: The host (**Mail server**) and **Priority** values of the MX record for the domain.</span><span class="sxs-lookup"><span data-stu-id="899fb-115">**MX record**: The host (**Mail server**) and **Priority** values of the MX record for the domain.</span></span>
- <span data-ttu-id="899fb-116">**Причина цикла** **и решение:** мы оденем наиболее распространенные сценарии почтового цикла и предоставляем рекомендуемые действия для исправления цикла.</span><span class="sxs-lookup"><span data-stu-id="899fb-116">**Loop reason** and **How to fix**: We'll identify the most common mail loop scenarios and provide recommended actions to fix the loop.</span></span>

![Flyout Details that appears after clicking View details on the Fix possible mail loop insight](../../media/mfi-fix-possible-mail-loop-details.png)

## <a name="see-also"></a><span data-ttu-id="899fb-118">См. также</span><span class="sxs-lookup"><span data-stu-id="899fb-118">See also</span></span>

<span data-ttu-id="899fb-119">Сведения о других сведениях на панели мониторинга потока обработки почты см. в анализе потока обработки почты в Центре безопасности [& соответствия требованиям.](mail-flow-insights-v2.md)</span><span class="sxs-lookup"><span data-stu-id="899fb-119">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
