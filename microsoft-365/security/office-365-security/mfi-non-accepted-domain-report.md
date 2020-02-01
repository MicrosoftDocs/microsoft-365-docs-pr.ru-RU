---
title: Отчет о необслуживаемом домене
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
description: Администраторы могут ознакомиться с отчетом о непринятом домене в панели мониторинга "Управление почтовыми сообщениями" в центре безопасности & соответствия требованиям.
ms.openlocfilehash: 7872f454f10c8f8b7bb2f79fd62671e200463f7b
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "41599216"
---
# <a name="non-accepted-domain-report"></a><span data-ttu-id="25b8c-103">Отчет о необслуживаемом домене</span><span class="sxs-lookup"><span data-stu-id="25b8c-103">Non-accepted domain report</span></span>

<span data-ttu-id="25b8c-104">Как и при работе с **доменом отправителя** , **неодобренный доменное** представление определяет сообщения из локальной организации электронной почты, но домен отправителя не настраивается как обслуживаемый домен в организации Office 365.</span><span class="sxs-lookup"><span data-stu-id="25b8c-104">Similar to the **Sender domain** insight, the **Non-accepted domain** insight identifies messages from your on-premises email organization, but the sender's domain isn't configured as an accepted domain in your Office 365 organization.</span></span>

<span data-ttu-id="25b8c-105">Office 365 может регулировать эти сообщения, если у нас есть данные для подтверждения того, что назначение этих сообщений является вредоносным.</span><span class="sxs-lookup"><span data-stu-id="25b8c-105">Office 365 might throttle these messages if we have data to prove that the intent of these messages is malicious.</span></span> <span data-ttu-id="25b8c-106">Поэтому важно понимать, что происходит и как устранить проблему.</span><span class="sxs-lookup"><span data-stu-id="25b8c-106">Therefore, it's important for you to understand what's happening and to fix the issue.</span></span>

![Отчет о непринятом домене в панели мониторинга "почтовый ящик" в центре безопасности & соответствия требованиям](../media/non-accepted-domain-report-selected.png)

<span data-ttu-id="25b8c-108">Если щелкнуть мини-приложение, вы перейдете к полному отчету.</span><span class="sxs-lookup"><span data-stu-id="25b8c-108">When you click on the widget, you're taken to the full report.</span></span> <span data-ttu-id="25b8c-109">В полном отчете, где можно щелкнуть **Просмотреть сведения** , чтобы просмотреть сведения в таблице, как показано на следующей схеме:</span><span class="sxs-lookup"><span data-stu-id="25b8c-109">In the full report, where you can click **View details** to view the information in a table as shown in the following diagram:</span></span>

![Таблица "Просмотр сведений" в отчете о непринятом домене](../media/non-accepted-domain-report-view-details.png)

<span data-ttu-id="25b8c-111">Когда вы выбираете строку в таблице, в всплывающем меню появятся дополнительные сведения.</span><span class="sxs-lookup"><span data-stu-id="25b8c-111">When you select a row in the table, a flyout will show you more details.</span></span> <span data-ttu-id="25b8c-112">Вы можете щелкнуть **Просмотреть примеры сообщений** , чтобы увидеть некоторые из идентифицированных сообщений.</span><span class="sxs-lookup"><span data-stu-id="25b8c-112">You can click **view sample messages** to see some of the identified messages.</span></span>

![Выбор строки в таблице сведений в отчете о непринятом домене](../media/non-accepted-domain-report-select-row-in-table.png)

## <a name="see-also"></a><span data-ttu-id="25b8c-114">См. также</span><span class="sxs-lookup"><span data-stu-id="25b8c-114">See also</span></span>

<span data-ttu-id="25b8c-115">Для получения дополнительных сведений о других аналитиках почтовых ящиков в панели мониторинга обработки почты ознакомьтесь с разрешениями [почтовых ящиков в центре безопасности & соответствия требованиям](mail-flow-insights-v2.md).</span><span class="sxs-lookup"><span data-stu-id="25b8c-115">For more information about other mail flow insights in the mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
