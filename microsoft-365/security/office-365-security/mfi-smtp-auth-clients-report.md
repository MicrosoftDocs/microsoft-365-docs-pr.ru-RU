---
title: Отчет по клиентам проверки подлинности SMTP
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
description: Администраторы могут узнать отчет о клиентах проверки подлинности SMTP в панели мониторинга "Управление почтовыми сообщениями" в центре безопасности & соответствия требованиям.
ms.openlocfilehash: 7d3977293b0456b9ab3d383c1a41be9858a66028
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/20/2019
ms.locfileid: "37091253"
---
# <a name="smtp-auth-clients-report"></a><span data-ttu-id="62357-103">Отчет по клиентам проверки подлинности SMTP</span><span class="sxs-lookup"><span data-stu-id="62357-103">SMTP Auth clients report</span></span>

<span data-ttu-id="62357-104">В отчете о клиентах **проверки подлинности SMTP** выделено использование протокола отправки SMTP-протокола проверки подлинности SMTP пользователями или системными учетными записями в Организации.</span><span class="sxs-lookup"><span data-stu-id="62357-104">The **SMTP Auth clients** report highlights the use of the SMTP Auth client submission protocol by users or system accounts in your organization.</span></span> <span data-ttu-id="62357-105">Этот устаревший протокол (использующий конечную точку smtp.office365.com) обеспечивает только обычную проверку подлинности и может использоваться скомпрометированными учетными записями для отправки электронной почты.</span><span class="sxs-lookup"><span data-stu-id="62357-105">This legacy protocol (which uses the endpoint smtp.office365.com) only offers Basic authentication, and is susceptible to being used by compromised accounts to send email.</span></span>  <span data-ttu-id="62357-106">Этот отчет позволяет проверить необычные действия.</span><span class="sxs-lookup"><span data-stu-id="62357-106">This report allows you to check for unusual activity.</span></span> <span data-ttu-id="62357-107">В нем также отображаются данные об использовании TLS для клиентов или устройств с использованием проверки подлинности SMTP.</span><span class="sxs-lookup"><span data-stu-id="62357-107">It also shows the TLS usage data for clients or devices using SMTP Auth.</span></span>

<span data-ttu-id="62357-108">Мини-приложение, показанное на панели мониторинга "почтовый ящик", указывает количество пользователей или учетных записей служб, которые использовали протокол проверки подлинности SMTP за последние 7 дней.</span><span class="sxs-lookup"><span data-stu-id="62357-108">The widget that's shown in the Mail Flow dashboard indicates the number of users or service accounts that have used the SMTP Auth protocol in the last 7 days.</span></span>

![Отчет по клиентам проверки подлинности SMTP в панели мониторинга "почтовые потоки" в центре безопасности & соответствия требованиям](../media/smtp-auth-clients-report-selected.png)

<span data-ttu-id="62357-110">Если щелкнуть мини-приложение, откроется всплывающее окно, в котором представлено сводное представление об использовании и томах TLS за последнюю неделю.</span><span class="sxs-lookup"><span data-stu-id="62357-110">Clicking on the widget opens a flyout that provides an aggregated view of the TLS usage and volumes for the last week.</span></span>

![Всплывающее меню в отчете о клиентах проверки подлинности SMTP](../media/smtp-auth-clients-flyout.png)

<span data-ttu-id="62357-112">Если щелкнуть ссылку отчет по **клиентам проверки подлинности SMTP** , вы увидите две основные сводки данных и два представления данных.</span><span class="sxs-lookup"><span data-stu-id="62357-112">When you click on the **SMTP Auth Clients Report** link, you'll see two main data pivots and two data views.</span></span> <span data-ttu-id="62357-113">Сводка данных — это **объем отправляемых** данных и **Использование TLS**.</span><span class="sxs-lookup"><span data-stu-id="62357-113">The data pivots are the **Sending Volume** and **TLS Usage**.</span></span> <span data-ttu-id="62357-114">Представления данных представляют собой диаграмму и таблицу Details.</span><span class="sxs-lookup"><span data-stu-id="62357-114">The data views are the chart and the details table.</span></span>

<span data-ttu-id="62357-115">В представлении " **Отправка тома** " показано количество сообщений, отправленных с помощью проверки подлинности SMTP, в указанный диапазон времени.</span><span class="sxs-lookup"><span data-stu-id="62357-115">The **Sending Volume** view shows the number of messages that were sent using SMTP Auth for the specified time range.</span></span> <span data-ttu-id="62357-116">Чтобы изменить диапазон, щелкните **фильтры**.</span><span class="sxs-lookup"><span data-stu-id="62357-116">You can adjust the range by clicking **Filters**.</span></span> <span data-ttu-id="62357-117">Диаграмма организована по домену отправителя.</span><span class="sxs-lookup"><span data-stu-id="62357-117">The chart is organized by sender domain.</span></span> <span data-ttu-id="62357-118">Чтобы просмотреть отдельные данные для каждого домена, выберите домен в раскрывающемся списке **Показать данные** .</span><span class="sxs-lookup"><span data-stu-id="62357-118">You can see separate data for each domain by selecting the domain in the **Show data for** drop down.</span></span>

![Отправка тома в отчете о клиентах проверки подлинности SMTP](../media/smtp-auth-clients-report-sending-volume.png)

<span data-ttu-id="62357-120">Чтобы просмотреть подробные сведения об отправителях и их счетчиках, щелкните **Просмотреть таблицу сведений**.</span><span class="sxs-lookup"><span data-stu-id="62357-120">You can view detailed information about the senders and their message counts by clicking **View details table**.</span></span> <span data-ttu-id="62357-121">Чтобы вернуться к диаграмме, нажмите кнопку **Просмотреть отчет**.</span><span class="sxs-lookup"><span data-stu-id="62357-121">To return to the chart, click **View report**.</span></span>

![Таблица Details для отправки тома в отчете о клиентах проверки подлинности SMTP](../media/smtp-auth-clients-report-details-sending-volume.png)

<span data-ttu-id="62357-123">Сводный **Анализ использования TLS** важен из-за предстоящей устаревшей работы протоколов TLS 1.0 и TLS 1.1 в Office 365.</span><span class="sxs-lookup"><span data-stu-id="62357-123">The **TLS Usage** pivot is important due to the upcoming deprecation of TLS1.0 and TLS1.1 in Office 365.</span></span> <span data-ttu-id="62357-124">Многие устаревшие устройства и приложения не смогут отправлять сообщения электронной почты, если они могут использовать протокол TLS 1.0 с проверкой подлинности SMTP. Эта сводная таблица позволяет определять и выполнять действия с пользователями и системными учетными записями, которые все еще используют старые версии протокола TLS.</span><span class="sxs-lookup"><span data-stu-id="62357-124">Many legacy devices and applications will be unable to send email if they are only capable of using TLS1.0 with SMTP Auth. This pivot allows you to identify and take action on users and system accounts that are still using older versions of TLS.</span></span>

![Использование TLS в отчете о клиентах проверки подлинности SMTP](../media/smtp-auth-clients-report-tls-usage.png)

<span data-ttu-id="62357-126">Вы можете просмотреть подробные сведения о отправителях, версиях TLS, которые они используют с проверкой подлинности SMTP, и количеством сообщений, щелкнув **Таблица Просмотр сведений**.</span><span class="sxs-lookup"><span data-stu-id="62357-126">You can view detailed information about the senders, the versions of TLS they are using with SMTP Auth, and their message counts by clicking **View details table**.</span></span> <span data-ttu-id="62357-127">Чтобы вернуться к диаграмме, нажмите кнопку **Просмотреть отчет**.</span><span class="sxs-lookup"><span data-stu-id="62357-127">To return to the chart, click **View report**.</span></span>

<span data-ttu-id="62357-128">Вы также можете скачать более подробную версию отчета, щелкнув запрос отчет.</span><span class="sxs-lookup"><span data-stu-id="62357-128">You can also download a more detailed version of the report by clicking Request report.</span></span>

![Таблица сведений об использовании TLS в отчете о клиентах проверки подлинности SMTP](../media/smtp-auth-clients-report-details-tls-usage.png)

## <a name="see-also"></a><span data-ttu-id="62357-130">См. также</span><span class="sxs-lookup"><span data-stu-id="62357-130">See also</span></span>

<span data-ttu-id="62357-131">Для получения дополнительных сведений о других аналитиках почтовых ящиков в панели мониторинга обработки почты ознакомьтесь с разрешениями [почтовых ящиков в центре безопасности & соответствия требованиям](mail-flow-insights-v2.md).</span><span class="sxs-lookup"><span data-stu-id="62357-131">For more information about other mail flow insights in the mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
