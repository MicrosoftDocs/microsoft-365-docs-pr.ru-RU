---
title: Аналитика состояния потока обработки почты верхнего домена на панели мониторинга потока обработки почты
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
description: Администраторы могут научиться использовать аналитику состояния потока обработки почты верхнего домена на панели мониторинга потока обработки почты в Центре соответствия требованиям безопасности & для устранения проблем с потоком обработки почты, связанных с записями MX в их доменах электронной почты.
ms.openlocfilehash: 9640d5e37932efeb7c0c8f8c56d0a15bc7f07e5b
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/20/2020
ms.locfileid: "46827019"
---
# <a name="top-domain-mail-flow-status-insight-in-the-security--compliance-center"></a><span data-ttu-id="31965-103">Аналитика состояния для потока обработки почты верхнего домена в Центре безопасности & соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="31965-103">Top domain mail flow status insight in the Security & Compliance Center</span></span>

<span data-ttu-id="31965-104">Аналитика **состояния потока обработки почты верхнего** домена на панели [мониторинга](mail-flow-insights-v2.md) потока обработки почты в Центре соответствия требованиям безопасности & дает текущее состояние доменов организации в условиях потока обработки почты.</span><span class="sxs-lookup"><span data-stu-id="31965-104">The **Top domain mail flow status** insight in the [Mail flow dashboard](mail-flow-insights-v2.md) in the Security & Compliance Center gives you the current status for your organization's domains in terms of mail flow.</span></span> <span data-ttu-id="31965-105">Эти сведения помогают определить домены, которые могут возникать проблемы с потоком обработки почты (например, и не могут получать электронную почту), особенно истечение срока действия домена или домены с неправильными записями обмена почтой. ***mail flow impacting***</span><span class="sxs-lookup"><span data-stu-id="31965-105">This insight helps you identify and troubleshoot domains that are experiencing ***mail flow impacting*** issues (for example, unable to receive external email), especially domain expirations or domains with incorrect MX records.</span></span>

![Мини-приложение status flow верхнего домена на панели мониторинга потока обработки почты в Центре безопасности & соответствия требованиям](../../media/mfi-top-domain-mail-flow-status-widget.png)

<span data-ttu-id="31965-107">Если нажать **кнопку "Просмотреть сведения"** в мини-приложении появится всплывающий элемент "Состояние домена", в котором отображаются дополнительные сведения о состоянии каждого домена: **Domain status**</span><span class="sxs-lookup"><span data-stu-id="31965-107">When you click **View details** in the widget, a **Domain status** flyout appears that shows you more details for the status of each domain:</span></span>

- <span data-ttu-id="31965-108">**Домен**</span><span class="sxs-lookup"><span data-stu-id="31965-108">**Domain**</span></span>
- <span data-ttu-id="31965-109">**Предыдущая запись MX**</span><span class="sxs-lookup"><span data-stu-id="31965-109">**Previous MX record**</span></span>
- <span data-ttu-id="31965-110">**Текущая запись MX**</span><span class="sxs-lookup"><span data-stu-id="31965-110">**Current MX record**</span></span>
- <span data-ttu-id="31965-111">**Состояние приема электронной почты**</span><span class="sxs-lookup"><span data-stu-id="31965-111">**Email receiving status**</span></span>
- <span data-ttu-id="31965-112">**Состояние домена:** зеленый флажок означает, что текущая запись MX (щелкнувшая ее на суточноудии) совпадает со значением, заданным на мини-приложением, и что в течение последнего двух часов домен получил электронную почту.</span><span class="sxs-lookup"><span data-stu-id="31965-112">**Domain status**: A green check mark indicates the current MX record (at the time you clicked on the widget) matches the value we have on record, and that the domain has received email during the past two hours.</span></span>

  <span data-ttu-id="31965-113">Красный значок X указывает на то, что запись MX была изменена, а домен не получает электронную почту за последние 6 часов.</span><span class="sxs-lookup"><span data-stu-id="31965-113">A red X indicates the MX record has been changed, and that the domain has received no email during the past 6 hours.</span></span> <span data-ttu-id="31965-114">Скорее всего, это означает, что срок действия домена истек или что запись MX была неправильно обновлена.</span><span class="sxs-lookup"><span data-stu-id="31965-114">This likely indicates that your domain has expired, or that the MX record has been incorrectly updated.</span></span> <span data-ttu-id="31965-115">Обратитесь к регистратору доменных имен или в службу размещения DNS и выясните, истек ли срок действия домена или запись MX домена является неправильной.</span><span class="sxs-lookup"><span data-stu-id="31965-115">Check with your domain registrar or DNS hosting service to see if the domain has expired, or if the domain's MX record is incorrect.</span></span>

<span data-ttu-id="31965-116">Вы можете **щелкнуть кнопку "Подробнее",** чтобы просмотреть эти же сведения о других доменах.</span><span class="sxs-lookup"><span data-stu-id="31965-116">You can click **View more** to see the same information for more domains.</span></span>

![Всплывающем элементе "Сведения о состоянии потока обработки почты верхнего домена"](../../media/mfi-top-domain-mail-flow-status-view-details.png)

## <a name="related-topics"></a><span data-ttu-id="31965-118">Связанные статьи</span><span class="sxs-lookup"><span data-stu-id="31965-118">Related topics</span></span>

<span data-ttu-id="31965-119">Сведения о других аналитических данных на панели мониторинга потока обработки почты см. в статье "Аналитика потока [обработки почты" в Центре безопасности & соответствия требованиям.](mail-flow-insights-v2.md)</span><span class="sxs-lookup"><span data-stu-id="31965-119">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
