---
title: Отчет о карте потока обработки почты
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
description: Администраторы могут узнать о отчете карты почтовых ящиков в панели мониторинга "Управление почтовыми сообщениями" в центре безопасности & соответствия требованиям.
ms.openlocfilehash: 11d605047b66751636ffce69ffff5c198f039fc7
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42088543"
---
# <a name="mail-flow-map-report"></a><span data-ttu-id="2bacb-103">Отчет о карте потока обработки почты</span><span class="sxs-lookup"><span data-stu-id="2bacb-103">Mail flow map report</span></span>

<span data-ttu-id="2bacb-104">Этот отчет предоставляет подробные сведения о том, как почтовые сообщения проходят через организацию Office 365.</span><span class="sxs-lookup"><span data-stu-id="2bacb-104">This report gives insights as to how mail flows through your Office 365 organization.</span></span> <span data-ttu-id="2bacb-105">Вы можете использовать эти сведения для изучения шаблонов, выявления аномалий и устранения проблем по мере их возникновения.</span><span class="sxs-lookup"><span data-stu-id="2bacb-105">You can use this information to learn patterns, identify anomalies, and fix issues as they arise.</span></span>

![Отчет карты почтовых ящиков в панели мониторинга "Управление почтовыми сообщениями" в центре безопасности & соответствия требованиям](../../media/mail-flow-map-selected.png)

## <a name="mail-flow-map-widget"></a><span data-ttu-id="2bacb-107">Мини-приложение карты почтовых ящиков</span><span class="sxs-lookup"><span data-stu-id="2bacb-107">Mail flow map widget</span></span>

<span data-ttu-id="2bacb-108">По умолчанию в карте почтовых ящиков показан шаблон почтовых ящиков высокого уровня с предыдущего дня.</span><span class="sxs-lookup"><span data-stu-id="2bacb-108">By default, the mail flow map shows the high level mail flow pattern from the previous day.</span></span> <span data-ttu-id="2bacb-109">Для разных дней можно использовать стрелки влево и вправо.</span><span class="sxs-lookup"><span data-stu-id="2bacb-109">You can use the left and right arrows for different days.</span></span> <span data-ttu-id="2bacb-110">При наведении курсора мыши на каждую область в отчете будет показан объем почты в организации Office 365, как показано на следующей схеме:</span><span class="sxs-lookup"><span data-stu-id="2bacb-110">Hovering your mouse cursor over each area in the report will show the volume of mail to and from your Office 365 organization as shown in the following diagram:</span></span>

![Стрелки влево и вправо в мини-приложении "карта процесса почты"](../../media/mail-flow-map-widget.png)

## <a name="overview"></a><span data-ttu-id="2bacb-112">Обзор</span><span class="sxs-lookup"><span data-stu-id="2bacb-112">Overview</span></span>

<span data-ttu-id="2bacb-113">Щелкнув мини-приложение **карты почтовых ящиков** , вы перейдете к отчету **карты процесса обработки почты** .</span><span class="sxs-lookup"><span data-stu-id="2bacb-113">Clicking on the **Mail flow map** widget will take you to the **Mail flow map** report.</span></span> <span data-ttu-id="2bacb-114">Вы можете увидеть более детализированный уровень отчетов, щелкнув таблица Просмотр сведений для просмотра подробных данных.</span><span class="sxs-lookup"><span data-stu-id="2bacb-114">Here you can see more granular level of report, you can click View details table to see detailed data.</span></span> <span data-ttu-id="2bacb-115">Вы также можете скачать подробный отчет, щелкнув запрос отчет.</span><span class="sxs-lookup"><span data-stu-id="2bacb-115">You can also download the detailed report by clicking Request report.</span></span>

![Представление "Обзор" в отчете карты почтовых ящиков](../../media/mail-flow-map-overview.png)

## <a name="details"></a><span data-ttu-id="2bacb-117">Сведения</span><span class="sxs-lookup"><span data-stu-id="2bacb-117">Details</span></span>

<span data-ttu-id="2bacb-118">По умолчанию для параметра **Показать данные** задано значение **Обзор**.</span><span class="sxs-lookup"><span data-stu-id="2bacb-118">By default, **Show data for** is set to the value **Overview**.</span></span> <span data-ttu-id="2bacb-119">Если щелкнуть раскрывающийся список и выбрать **сведения**, представление будет переключаться на сведения о уровне домена.</span><span class="sxs-lookup"><span data-stu-id="2bacb-119">When you click on the drop down and select **Detail**, the view switches to the domain level detail.</span></span>

![Выбор параметра "сведения в представлении" Показать данные для в обзоре в отчете карты почтовых ящиков "](../../media/mail-flow-map-select-detail.png)

<span data-ttu-id="2bacb-121">Отображаются домены верхнего отправителя и получателя, и остальные домены будут помещены в **другие** , как показано на следующих схемах:</span><span class="sxs-lookup"><span data-stu-id="2bacb-121">The top sender and recipient domains are listed, and the rest will be put in **Others** as shown in the following diagrams:</span></span>

![Представление "сведения" в отчете о схеме почтового процесса](../../media/mail-flow-map-detail.png)

## <a name="related-insights"></a><span data-ttu-id="2bacb-123">Связанная аналитика</span><span class="sxs-lookup"><span data-stu-id="2bacb-123">Related insights</span></span>

<span data-ttu-id="2bacb-124">Связанные сведения отображаются под схемой почтовых процессов, если они доступны (например, для получения сведений о домене отправителя или в цикле обработки почты).</span><span class="sxs-lookup"><span data-stu-id="2bacb-124">Related insights are shown beneath the Mail flow map if they're available (for example, the Sender domain insight or the Mail loop insight).</span></span>

## <a name="see-also"></a><span data-ttu-id="2bacb-125">См. также</span><span class="sxs-lookup"><span data-stu-id="2bacb-125">See also</span></span>

<span data-ttu-id="2bacb-126">Для получения дополнительных сведений о других аналитиках почтовых ящиков в панели мониторинга обработки почты ознакомьтесь с разрешениями [почтовых ящиков в центре безопасности & соответствия требованиям](mail-flow-insights-v2.md).</span><span class="sxs-lookup"><span data-stu-id="2bacb-126">For more information about other mail flow insights in the mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
