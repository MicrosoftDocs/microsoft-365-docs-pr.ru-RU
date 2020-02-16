---
title: Анализ состояния для потока обработки почты верхнего домена
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
description: Администраторы могут узнать о состоянии верхнего уровня почтовых ящиков в почтовых процессах в панели мониторинга "Управление почтовыми сообщениями" в центре безопасности & соответствия требованиям.
ms.openlocfilehash: 42ce0545dad2804829d15572ce6e1f5a0ca6b49f
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42082854"
---
# <a name="top-domain-mail-flow-status-insight"></a><span data-ttu-id="c85f1-103">Анализ состояния для потока обработки почты верхнего домена</span><span class="sxs-lookup"><span data-stu-id="c85f1-103">Top domain mail flow status insight</span></span>

<span data-ttu-id="c85f1-104">Сведения **о состоянии почтовых процессов верхнего уровня** предоставляют сведения о текущем состоянии доменов организации в отношении почтового процесса.</span><span class="sxs-lookup"><span data-stu-id="c85f1-104">The **Top domain mail flow status** insight gives you the current status for your organization's domains in terms of mail flow.</span></span> <span data-ttu-id="c85f1-105">Эта информация поможет вам определить и устранить неполадки в доменах, в которых возникают проблемы с ***почтовыми сообщениями*** (например, невозможно получить внешние сообщения электронной почты), особенно истечения срока действия домена или доменов с неверными записями MX.</span><span class="sxs-lookup"><span data-stu-id="c85f1-105">This insight helps you identify and troubleshoot domains that are experiencing ***mail flow impacting*** issues (for example, unable to receive external email), especially domain expirations or domains with incorrect MX records.</span></span>

![Состояние поверх верхнего уровня домена в панели мониторинга "почтовый ящик" в центре безопасности & соответствия требованиям](../../media/domain-mail-flow-status-selected.png)

<span data-ttu-id="c85f1-107">При нажатии кнопки **Просмотреть сведения в представлении** отобразится раскрывающееся меню, в котором вы увидите дополнительные сведения о состоянии каждого домена.</span><span class="sxs-lookup"><span data-stu-id="c85f1-107">When you click **View details** in the insight, a flyout appears that shows you more details for the status of each domain.</span></span>

<span data-ttu-id="c85f1-108">Зеленая галочка для домена указывает, что текущая запись MX (при переходе на панель мониторинга "Сводка обработки почты") соответствует значению, указанному в записи, и что в течение последних двух часов домен получил электронную почту.</span><span class="sxs-lookup"><span data-stu-id="c85f1-108">A green check mark for a domain indicates the current MX record (when you browsed to the mail flow insights dashboard) matches the value we have on record, and that the domain has received email during the past two hours.</span></span>

<span data-ttu-id="c85f1-109">Красный крестик для домена указывает на то, что запись MX была изменена и что в течение предыдущих 6 часов домен не получил электронную почту.</span><span class="sxs-lookup"><span data-stu-id="c85f1-109">A red x for a domain indicates the MX record has been changed, and that the domain has received no email during the past 6 hours.</span></span> <span data-ttu-id="c85f1-110">Это может указывать на то, что срок действия домена истек или запись MX была неправильно обновлена.</span><span class="sxs-lookup"><span data-stu-id="c85f1-110">This likely indicates that your domain has expired, or that the MX record has been incorrectly updated.</span></span> <span data-ttu-id="c85f1-111">Обратитесь к регистратору доменных имен или в службе хостинга DNS, чтобы узнать, истек ли срок действия домена, или если запись MX домена неверна.</span><span class="sxs-lookup"><span data-stu-id="c85f1-111">Check with your domain registrar or DNS hosting service to see if the domain has expired, or if the domain's MX record is incorrect.</span></span>

![Всплывающее окно сведений в самом верхнем состоянии управления состоянием неактивных доменов](../../media/domain-mail-flow-status-flyout.png)

## <a name="see-also"></a><span data-ttu-id="c85f1-113">См. также</span><span class="sxs-lookup"><span data-stu-id="c85f1-113">See also</span></span>

<span data-ttu-id="c85f1-114">Для получения дополнительных сведений о других аналитиках почтовых ящиков в панели мониторинга обработки почты ознакомьтесь с разрешениями [почтовых ящиков в центре безопасности & соответствия требованиям](mail-flow-insights-v2.md).</span><span class="sxs-lookup"><span data-stu-id="c85f1-114">For more information about other mail flow insights in the mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
