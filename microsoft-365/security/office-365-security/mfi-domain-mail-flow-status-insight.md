---
title: Анализ состояния потока почты верхнего домена на панели мониторинга потока почты
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
description: Администраторы могут узнать, как использовать анализ состояния потока обработки почты верхнего домена на панели мониторинга потока обработки почты в Центре безопасности и соответствия требованиям & для устранения неполадок потока обработки почты, связанных с их записями MX.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 457675e7f32cd513f5593ede53a64aaef9d54904
ms.sourcegitcommit: 537e513a4a232a01e44ecbc76d86a8bcaf142482
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/27/2021
ms.locfileid: "50029910"
---
# <a name="top-domain-mail-flow-status-insight-in-the-security--compliance-center"></a><span data-ttu-id="c2d27-103">Анализ состояния потока обработки почты верхнего домена в Центре & соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="c2d27-103">Top domain mail flow status insight in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="c2d27-104">The **Top domain mail flow status** insight in the Mail flow [dashboard](mail-flow-insights-v2.md) in the Security & [Compliance Center](https://protection.office.com) gives you the current mail flow status for your organization.</span><span class="sxs-lookup"><span data-stu-id="c2d27-104">The **Top domain mail flow status** insight in the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com) gives you the current mail flow status for your organization.</span></span>

<span data-ttu-id="c2d27-105">Эта информация помогает определить домены, в которые возникли *_проблемы_* с потоком почты\* и устранить неполадки.</span><span class="sxs-lookup"><span data-stu-id="c2d27-105">This insight helps you identify and troubleshoot domains that are experiencing \**_mail flow_* _ issues.</span></span> <span data-ttu-id="c2d27-106">Например, домен не может получать внешнюю электронную почту, так как домен истек или домен имеет неправильную запись MX.</span><span class="sxs-lookup"><span data-stu-id="c2d27-106">For example, the domain is unable to receive external email because the domain has expired or the domain has an incorrect MX record.</span></span>

![Мини-приложения состояния потока обработки почты на панели мониторинга потока обработки почты в Центре безопасности & соответствия требованиям](../../media/mfi-top-domain-mail-flow-status-widget.png)

<span data-ttu-id="c2d27-108">При нажатии кнопки *_Просмотреть* сведения \* в виджете появится элемент "Состояние домена", который отображает дополнительные сведения о состоянии каждого домена: </span><span class="sxs-lookup"><span data-stu-id="c2d27-108">When you click _ *View details*\* in the widget, a **Domain status** flyout appears that shows you more details for the status of each domain:</span></span>

- <span data-ttu-id="c2d27-109">**Домен**</span><span class="sxs-lookup"><span data-stu-id="c2d27-109">**Domain**</span></span>
- <span data-ttu-id="c2d27-110">**Предыдущая запись MX**</span><span class="sxs-lookup"><span data-stu-id="c2d27-110">**Previous MX record**</span></span>
- <span data-ttu-id="c2d27-111">**Текущая запись MX**</span><span class="sxs-lookup"><span data-stu-id="c2d27-111">**Current MX record**</span></span>
- <span data-ttu-id="c2d27-112">**Состояние получения электронной почты**</span><span class="sxs-lookup"><span data-stu-id="c2d27-112">**Email receiving status**</span></span>
- <span data-ttu-id="c2d27-113">Состояние домена: зеленая метка указывает, что текущая запись MX (на момент нажатия мини-приложения) совпадает со значением, которое у нас есть в записи, и домен получил электронную почту в течение последних двух часов.</span><span class="sxs-lookup"><span data-stu-id="c2d27-113">**Domain status**: A green check mark indicates the current MX record (at the time you clicked on the widget) matches the value we have on record, and the domain has received email during the past two hours.</span></span>

  <span data-ttu-id="c2d27-114">Красный X указывает, что запись MX была изменена, а домен не получал электронной почты за последние 6 часов.</span><span class="sxs-lookup"><span data-stu-id="c2d27-114">A red X indicates the MX record has been changed, and the domain has received no email during the past 6 hours.</span></span> <span data-ttu-id="c2d27-115">Скорее всего, это указывает на то, что срок действия домена истек или что запись MX была неправильно обновлена.</span><span class="sxs-lookup"><span data-stu-id="c2d27-115">This likely indicates that your domain has expired, or that the MX record has been incorrectly updated.</span></span> <span data-ttu-id="c2d27-116">Обратитесь к регистратору доменных имен или службе размещения DNS, чтобы узнать, истек ли срок действия домена или запись MX домена неправильная.</span><span class="sxs-lookup"><span data-stu-id="c2d27-116">Check with your domain registrar or DNS hosting service to see if the domain has expired, or if the domain's MX record is incorrect.</span></span>

<span data-ttu-id="c2d27-117">Чтобы **просмотреть те** же сведения о дополнительных доменах, нажмите кнопку "Просмотреть".</span><span class="sxs-lookup"><span data-stu-id="c2d27-117">You can click **View more** to see the same information for more domains.</span></span>

![Flyout Details in the Top domain mail flow status insight](../../media/mfi-top-domain-mail-flow-status-view-details.png)

## <a name="see-also"></a><span data-ttu-id="c2d27-119">См. также</span><span class="sxs-lookup"><span data-stu-id="c2d27-119">See also</span></span>

<span data-ttu-id="c2d27-120">Сведения о других сведениях на панели мониторинга потока обработки почты см. в анализе потока обработки почты в Центре безопасности [& соответствия требованиям.](mail-flow-insights-v2.md)</span><span class="sxs-lookup"><span data-stu-id="c2d27-120">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
