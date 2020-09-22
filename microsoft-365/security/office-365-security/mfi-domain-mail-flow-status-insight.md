---
title: Состояние почтовых процессов верхнего уровня в панели мониторинга почтового процесса
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: Администраторы могут узнать, как использовать высший статус почтовых ящиков в панели мониторинга обработки почты в центре управления безопасностью & соответствия требованиям, чтобы устранять проблемы, связанные с записями MX в их доменах электронной почты.
ms.openlocfilehash: 24922d6ae7d2ec50e3d9383631991cf46a818c05
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "48197529"
---
# <a name="top-domain-mail-flow-status-insight-in-the-security--compliance-center"></a><span data-ttu-id="b0788-103">Состояние почтовых процессов верхнего уровня в центре безопасности & соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="b0788-103">Top domain mail flow status insight in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="b0788-104">**Состояние почтовых ящиков верхнего уровня** в [панели мониторинга обработки почты](mail-flow-insights-v2.md) в [центре безопасности & соответствия требованиям](https://protection.office.com) позволяет получить сведения о текущем состоянии доменов организации в отношении почтового процесса.</span><span class="sxs-lookup"><span data-stu-id="b0788-104">The **Top domain mail flow status** insight in the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com) gives you the current status for your organization's domains in terms of mail flow.</span></span> <span data-ttu-id="b0788-105">Эта информация поможет вам определить и устранить неполадки в доменах, в которых возникают проблемы с ***почтовыми сообщениями*** (например, невозможно получить внешние сообщения электронной почты), особенно истечения срока действия домена или доменов с неверными записями MX.</span><span class="sxs-lookup"><span data-stu-id="b0788-105">This insight helps you identify and troubleshoot domains that are experiencing ***mail flow impacting*** issues (for example, unable to receive external email), especially domain expirations or domains with incorrect MX records.</span></span>

![Самый верхний мини-приложение состояния последовательности доменов на панели мониторинга "почтовый ящик" в центре безопасности & соответствия требованиям](../../media/mfi-top-domain-mail-flow-status-widget.png)

<span data-ttu-id="b0788-107">При нажатии кнопки **Просмотреть сведения** в мини-приложении отображается всплывающее окно **состояния домена** , в котором отображаются дополнительные сведения о состоянии каждого домена:</span><span class="sxs-lookup"><span data-stu-id="b0788-107">When you click **View details** in the widget, a **Domain status** flyout appears that shows you more details for the status of each domain:</span></span>

- <span data-ttu-id="b0788-108">**Домен**</span><span class="sxs-lookup"><span data-stu-id="b0788-108">**Domain**</span></span>
- <span data-ttu-id="b0788-109">**Предыдущая запись MX**</span><span class="sxs-lookup"><span data-stu-id="b0788-109">**Previous MX record**</span></span>
- <span data-ttu-id="b0788-110">**Текущая запись MX**</span><span class="sxs-lookup"><span data-stu-id="b0788-110">**Current MX record**</span></span>
- <span data-ttu-id="b0788-111">**Состояние получения электронной почты**</span><span class="sxs-lookup"><span data-stu-id="b0788-111">**Email receiving status**</span></span>
- <span data-ttu-id="b0788-112">**Состояние домена**: зеленая галочка указывает, что текущая запись MX (при нажатии на мини-приложение) соответствует значению, указанному для записи, и что в течение последних двух часов в домене получено сообщение электронной почты.</span><span class="sxs-lookup"><span data-stu-id="b0788-112">**Domain status**: A green check mark indicates the current MX record (at the time you clicked on the widget) matches the value we have on record, and that the domain has received email during the past two hours.</span></span>

  <span data-ttu-id="b0788-113">Красный крестик указывает на то, что запись MX была изменена и что в течение предыдущих 6 часов домен не получил электронную почту.</span><span class="sxs-lookup"><span data-stu-id="b0788-113">A red X indicates the MX record has been changed, and that the domain has received no email during the past 6 hours.</span></span> <span data-ttu-id="b0788-114">Это может указывать на то, что срок действия домена истек или запись MX была неправильно обновлена.</span><span class="sxs-lookup"><span data-stu-id="b0788-114">This likely indicates that your domain has expired, or that the MX record has been incorrectly updated.</span></span> <span data-ttu-id="b0788-115">Обратитесь к регистратору доменных имен или в службе хостинга DNS, чтобы узнать, истек ли срок действия домена, или если запись MX домена неверна.</span><span class="sxs-lookup"><span data-stu-id="b0788-115">Check with your domain registrar or DNS hosting service to see if the domain has expired, or if the domain's MX record is incorrect.</span></span>

<span data-ttu-id="b0788-116">Вы можете нажать кнопку **Показать больше** , чтобы отобразить те же сведения для других доменов.</span><span class="sxs-lookup"><span data-stu-id="b0788-116">You can click **View more** to see the same information for more domains.</span></span>

![Всплывающее окно со сведениями о состоянии почтовых процессов верхнего домена](../../media/mfi-top-domain-mail-flow-status-view-details.png)

## <a name="related-topics"></a><span data-ttu-id="b0788-118">Связанные статьи</span><span class="sxs-lookup"><span data-stu-id="b0788-118">Related topics</span></span>

<span data-ttu-id="b0788-119">Сведения о других аналитиках в панели мониторинга для почтового процесса приведены в статье сведения о [почтовых сообщениях в центре безопасности & соответствия требованиям](mail-flow-insights-v2.md).</span><span class="sxs-lookup"><span data-stu-id="b0788-119">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
