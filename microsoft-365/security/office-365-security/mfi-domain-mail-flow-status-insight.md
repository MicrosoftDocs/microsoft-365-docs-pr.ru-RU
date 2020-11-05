---
title: Состояние почтовых процессов верхнего уровня в панели мониторинга почтового процесса
f1.keywords:
- NOCSH
ms.author: siosulli
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: Администраторы могут узнать, как использовать высший статус почтовых ящиков в панели мониторинга обработки почты в центре управления безопасностью & соответствия требованиям, чтобы устранить проблемы с процессом обработки почты, связанные с записями MX.
ms.openlocfilehash: 0d750ab4dbe5875796118086fae1d9119dc486f0
ms.sourcegitcommit: d7975c391e03eeb96e29c1d02e77d2a1433ea67c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/05/2020
ms.locfileid: "48920588"
---
# <a name="top-domain-mail-flow-status-insight-in-the-security--compliance-center"></a><span data-ttu-id="03f43-103">Состояние почтовых процессов верхнего уровня в центре безопасности & соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="03f43-103">Top domain mail flow status insight in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="03f43-104">**Состояние почтовых ящиков верхнего уровня** в [панели мониторинга обработки почты](mail-flow-insights-v2.md) в [центре безопасности & соответствия требованиям](https://protection.office.com) обеспечивает текущее состояние процесса обработки почты для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="03f43-104">The **Top domain mail flow status** insight in the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com) gives you the current mail flow status for your organization.</span></span>

<span data-ttu-id="03f43-105">Это поможет вам определить и устранить проблемы с доменами, в которых возникают проблемы с *_почтовыми ящиками \* Mail Flow_*.</span><span class="sxs-lookup"><span data-stu-id="03f43-105">This insight helps you identify and troubleshoot domains that are experiencing \* *_mail flow_* _ issues.</span></span> <span data-ttu-id="03f43-106">Например, домен не может получить внешнюю почту из-за истечения срока действия домена или неправильной записи MX в домене.</span><span class="sxs-lookup"><span data-stu-id="03f43-106">For example, the domain is unable to receive external email because the domain has expired or the domain has an incorrect MX record.</span></span>

![Самый верхний мини-приложение состояния последовательности доменов на панели мониторинга "почтовый ящик" в центре безопасности & соответствия требованиям](../../media/mfi-top-domain-mail-flow-status-widget.png)

<span data-ttu-id="03f43-108">При нажатии кнопки _ *Просмотр сведений* \* мини-приложения отображается всплывающее окно **состояния домена** , в котором можно получить дополнительные сведения о состоянии каждого домена:</span><span class="sxs-lookup"><span data-stu-id="03f43-108">When you click _ *View details* \* in the widget, a **Domain status** flyout appears that shows you more details for the status of each domain:</span></span>

- <span data-ttu-id="03f43-109">**Домен**</span><span class="sxs-lookup"><span data-stu-id="03f43-109">**Domain**</span></span>
- <span data-ttu-id="03f43-110">**Предыдущая запись MX**</span><span class="sxs-lookup"><span data-stu-id="03f43-110">**Previous MX record**</span></span>
- <span data-ttu-id="03f43-111">**Текущая запись MX**</span><span class="sxs-lookup"><span data-stu-id="03f43-111">**Current MX record**</span></span>
- <span data-ttu-id="03f43-112">**Состояние получения электронной почты**</span><span class="sxs-lookup"><span data-stu-id="03f43-112">**Email receiving status**</span></span>
- <span data-ttu-id="03f43-113">**Состояние домена** : зеленая галочка указывает, что текущая запись MX (при нажатии на мини-приложение) соответствует значению, указанному для записи, а в течение последних двух часов в домене получено сообщение электронной почты.</span><span class="sxs-lookup"><span data-stu-id="03f43-113">**Domain status** : A green check mark indicates the current MX record (at the time you clicked on the widget) matches the value we have on record, and the domain has received email during the past two hours.</span></span>

  <span data-ttu-id="03f43-114">Красный крестик указывает на то, что запись MX изменена, а домен не получал сообщения в течение предыдущих 6 часов.</span><span class="sxs-lookup"><span data-stu-id="03f43-114">A red X indicates the MX record has been changed, and the domain has received no email during the past 6 hours.</span></span> <span data-ttu-id="03f43-115">Это может указывать на то, что срок действия домена истек или запись MX была неправильно обновлена.</span><span class="sxs-lookup"><span data-stu-id="03f43-115">This likely indicates that your domain has expired, or that the MX record has been incorrectly updated.</span></span> <span data-ttu-id="03f43-116">Обратитесь к регистратору доменных имен или в службе хостинга DNS, чтобы узнать, истек ли срок действия домена, или если запись MX домена неверна.</span><span class="sxs-lookup"><span data-stu-id="03f43-116">Check with your domain registrar or DNS hosting service to see if the domain has expired, or if the domain's MX record is incorrect.</span></span>

<span data-ttu-id="03f43-117">Вы можете нажать кнопку **Показать больше** , чтобы отобразить те же сведения для других доменов.</span><span class="sxs-lookup"><span data-stu-id="03f43-117">You can click **View more** to see the same information for more domains.</span></span>

![Всплывающее окно со сведениями о состоянии почтовых процессов верхнего домена](../../media/mfi-top-domain-mail-flow-status-view-details.png)

## <a name="see-also"></a><span data-ttu-id="03f43-119">См. также</span><span class="sxs-lookup"><span data-stu-id="03f43-119">See also</span></span>

<span data-ttu-id="03f43-120">Сведения о других аналитиках в панели мониторинга для почтового процесса приведены в статье сведения о [почтовых сообщениях в центре безопасности & соответствия требованиям](mail-flow-insights-v2.md).</span><span class="sxs-lookup"><span data-stu-id="03f43-120">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
