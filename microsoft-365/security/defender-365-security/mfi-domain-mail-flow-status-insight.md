---
title: Верхнее представление о состоянии потока почты домена в панели мониторинга потока почты
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: Администраторы могут узнать, как использовать сведения о состоянии потока электронной почты верхнего домена в панели мониторинга потока почты в Центре соответствия требованиям & безопасности для устранения проблем с потоком почты, связанных с записями MX.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 850e72fa0ad7a3f41450a1d0a2c02dd3df4a0cb5
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51071310"
---
# <a name="top-domain-mail-flow-status-insight-in-the-security--compliance-center"></a><span data-ttu-id="9ff71-103">Верхнее представление о состоянии потока почты домена в Центре & безопасности</span><span class="sxs-lookup"><span data-stu-id="9ff71-103">Top domain mail flow status insight in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="9ff71-104">**Область применения**</span><span class="sxs-lookup"><span data-stu-id="9ff71-104">**Applies to**</span></span>
- [<span data-ttu-id="9ff71-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="9ff71-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="9ff71-106">Microsoft Defender для Office 365 (план 1 и план 2)</span><span class="sxs-lookup"><span data-stu-id="9ff71-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="9ff71-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9ff71-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="9ff71-108">Сведения **о состоянии потока** почтовой почты [](https://protection.office.com) верхнего домена в панели мониторинга потока почты в Центре & безопасности дают вам текущее состояние потока почты для организации. [](mail-flow-insights-v2.md)</span><span class="sxs-lookup"><span data-stu-id="9ff71-108">The **Top domain mail flow status** insight in the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com) gives you the current mail flow status for your organization.</span></span>

<span data-ttu-id="9ff71-109">Это понимание помогает определить и устранить проблемы доменов, которые испытывают проблемы ***с потоком*** почты.</span><span class="sxs-lookup"><span data-stu-id="9ff71-109">This insight helps you identify and troubleshoot domains that are experiencing ***mail flow*** issues.</span></span> <span data-ttu-id="9ff71-110">Например, домен не может получать внешнюю электронную почту из-за истечения срока действия домена или неправильной записи MX.</span><span class="sxs-lookup"><span data-stu-id="9ff71-110">For example, the domain is unable to receive external email because the domain has expired or the domain has an incorrect MX record.</span></span>

![Виджет состояния потока домена в панели мониторинга потока почты в Центре & безопасности](../../media/mfi-top-domain-mail-flow-status-widget.png)

<span data-ttu-id="9ff71-112">При  **нажатии** сведений о просмотре в виджете появляется флажок состояния домена, который показывает дополнительные сведения о состоянии каждого домена:</span><span class="sxs-lookup"><span data-stu-id="9ff71-112">When you click **View details** in the widget, a **Domain status** flyout appears that shows you more details for the status of each domain:</span></span>

- <span data-ttu-id="9ff71-113">**Домен**</span><span class="sxs-lookup"><span data-stu-id="9ff71-113">**Domain**</span></span>
- <span data-ttu-id="9ff71-114">**Предыдущая запись MX**</span><span class="sxs-lookup"><span data-stu-id="9ff71-114">**Previous MX record**</span></span>
- <span data-ttu-id="9ff71-115">**Текущая запись MX**</span><span class="sxs-lookup"><span data-stu-id="9ff71-115">**Current MX record**</span></span>
- <span data-ttu-id="9ff71-116">**Состояние получения электронной почты**</span><span class="sxs-lookup"><span data-stu-id="9ff71-116">**Email receiving status**</span></span>
- <span data-ttu-id="9ff71-117">**Состояние** домена. Зеленый знак проверки указывает, что текущая запись MX (на момент нажатия на виджет) соответствует значению, которое мы имеем в записи, и домен получил электронную почту в течение последних двух часов.</span><span class="sxs-lookup"><span data-stu-id="9ff71-117">**Domain status**: A green check mark indicates the current MX record (at the time you clicked on the widget) matches the value we have on record, and the domain has received email during the past two hours.</span></span>

  <span data-ttu-id="9ff71-118">Красный X указывает, что запись MX была изменена, а домен не получал электронной почты в течение последних 6 часов.</span><span class="sxs-lookup"><span data-stu-id="9ff71-118">A red X indicates the MX record has been changed, and the domain has received no email during the past 6 hours.</span></span> <span data-ttu-id="9ff71-119">Это, скорее всего, указывает на то, что срок действия домена истек или что запись MX была неправильно обновлена.</span><span class="sxs-lookup"><span data-stu-id="9ff71-119">This likely indicates that your domain has expired, or that the MX record has been incorrectly updated.</span></span> <span data-ttu-id="9ff71-120">Обратитесь к регистратору домена или службе размещения DNS, чтобы узнать, истек ли домен или неправильная запись MX домена.</span><span class="sxs-lookup"><span data-stu-id="9ff71-120">Check with your domain registrar or DNS hosting service to see if the domain has expired, or if the domain's MX record is incorrect.</span></span>

<span data-ttu-id="9ff71-121">Вы можете **щелкнуть Просмотреть больше,** чтобы просмотреть те же сведения для более доменов.</span><span class="sxs-lookup"><span data-stu-id="9ff71-121">You can click **View more** to see the same information for more domains.</span></span>

![Сведения о вылете в анализе состояния потока почты верхнего домена](../../media/mfi-top-domain-mail-flow-status-view-details.png)

## <a name="see-also"></a><span data-ttu-id="9ff71-123">См. также</span><span class="sxs-lookup"><span data-stu-id="9ff71-123">See also</span></span>

<span data-ttu-id="9ff71-124">Сведения о других сведениях в панели мониторинга потока почты см. в странице Анализ потока почты в Центре [& соответствия](mail-flow-insights-v2.md)требованиям.</span><span class="sxs-lookup"><span data-stu-id="9ff71-124">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
