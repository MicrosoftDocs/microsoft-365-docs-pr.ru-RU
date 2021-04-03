---
title: Новые возможности в Microsoft Defender для Office 365
description: Узнайте о новых возможностях и функциях, доступных в последнем выпуске Microsoft Defender для Office 365.
keywords: что нового в Office 365 atp, ga, как правило, доступны, возможности, доступные, новые
search.appverid: met150
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.topic: conceptual
ms.date: 01/12/2021
ms.custom: seo-marvel-apr2020
ms.reviewer: vippand
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 7dd691b0d018db2b7afb3b88a2c1f9f7f8a39a33
ms.sourcegitcommit: 6e5c00f84b5201422aed094f2697016407df8fc2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/02/2021
ms.locfileid: "51569783"
---
# <a name="whats-new-in-microsoft-defender-for-office-365"></a><span data-ttu-id="2edf1-104">Новые возможности в Microsoft Defender для Office 365</span><span class="sxs-lookup"><span data-stu-id="2edf1-104">What's new in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="2edf1-105">**Область применения**</span><span class="sxs-lookup"><span data-stu-id="2edf1-105">**Applies to**</span></span>
- [<span data-ttu-id="2edf1-106">Microsoft Defender для Office 365 (план 1 и план 2)</span><span class="sxs-lookup"><span data-stu-id="2edf1-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="2edf1-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2edf1-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="2edf1-108">В этой статье перечислены новые возможности последнего выпуска Microsoft Defender для Office 365.</span><span class="sxs-lookup"><span data-stu-id="2edf1-108">This article lists new features in the latest release of Microsoft Defender for Office 365.</span></span> <span data-ttu-id="2edf1-109">Функции, которые в настоящее время находятся в предварительном просмотре, обозначаются **(предварительный просмотр).**</span><span class="sxs-lookup"><span data-stu-id="2edf1-109">Features that are currently in preview are denoted with **(preview)**.</span></span>

<span data-ttu-id="2edf1-110">Узнайте больше, просмотрев [это видео.](https://www.youtube.com/watch?v=Tdz6KfruDGo&list=PL3ZTgFEc7LystRja2GnDeUFqk44k7-KXf&index=3)</span><span class="sxs-lookup"><span data-stu-id="2edf1-110">Learn more by watching [this video](https://www.youtube.com/watch?v=Tdz6KfruDGo&list=PL3ZTgFEc7LystRja2GnDeUFqk44k7-KXf&index=3).</span></span>
> [!TIP]
> <span data-ttu-id="2edf1-111">Еще нет Microsoft Defender для Office 365?</span><span class="sxs-lookup"><span data-stu-id="2edf1-111">Don't have Microsoft Defender for Office 365 yet?</span></span> <span data-ttu-id="2edf1-112">[Свяжитесь с продажами, чтобы начать пробную работу.](https://info.microsoft.com/ww-landing-M365SMB-web-contact.html)</span><span class="sxs-lookup"><span data-stu-id="2edf1-112">[Contact sales to start a trial](https://info.microsoft.com/ww-landing-M365SMB-web-contact.html).</span></span>

## <a name="februarymarch-2021"></a><span data-ttu-id="2edf1-113">Февраль-март 2021 г.</span><span class="sxs-lookup"><span data-stu-id="2edf1-113">February/March 2021</span></span> 

- <span data-ttu-id="2edf1-114">Интеграция оповещений (поиск с помощью alert ID и Alert-Explorer навигации) в [опытом охоты](threat-explorer.md)</span><span class="sxs-lookup"><span data-stu-id="2edf1-114">Alert ID integration (search using Alert ID and Alert-Explorer navigation) in [hunting experiences](threat-explorer.md)</span></span>
- <span data-ttu-id="2edf1-115">Увеличение ограничений на экспорт записей с 9990 до 200 000 в [охотничьих опытах](threat-explorer.md)</span><span class="sxs-lookup"><span data-stu-id="2edf1-115">Increasing the limits for Export of records from 9990 to 200,000 in [hunting experiences](threat-explorer.md)</span></span>
- <span data-ttu-id="2edf1-116">Расширение ограничения хранения и поиска данных Explorer (и обнаружения в режиме реального времени) для пробных клиентов с 7 (предыдущего ограничения) до 30 дней в ходе [охоты](threat-explorer.md)</span><span class="sxs-lookup"><span data-stu-id="2edf1-116">Extending the Explorer (and Real-time detections) data retention and search limit for trial tenants from 7 (previous limit) to 30 days in [hunting experiences](threat-explorer.md)</span></span>
- <span data-ttu-id="2edf1-117">Новые поворотные точки охоты,  называемые импотенциозным доменом и обезличенным пользователем в explorer (и обнаружения в режиме реального времени) для поиска атак на защищенных пользователей или доменов. </span><span class="sxs-lookup"><span data-stu-id="2edf1-117">New hunting pivots called **Impersonated domain** and **Impersonated user** within the Explorer (and Real-time detections) to search for impersonation attacks against protected users or domains.</span></span> <span data-ttu-id="2edf1-118">Дополнительные сведения см. в [дополнительных сведениях.](threat-explorer.md#view-phishing-emails-sent-to-impersonated-users-and-domains)</span><span class="sxs-lookup"><span data-stu-id="2edf1-118">For more information, see [details](threat-explorer.md#view-phishing-emails-sent-to-impersonated-users-and-domains).</span></span> <span data-ttu-id="2edf1-119">(Microsoft Defender для Office 365 Plan 1 или Plan 2)</span><span class="sxs-lookup"><span data-stu-id="2edf1-119">(Microsoft Defender for Office 365 Plan 1 or Plan 2)</span></span>

## <a name="december-2020"></a><span data-ttu-id="2edf1-120">Декабрь 2020 г.</span><span class="sxs-lookup"><span data-stu-id="2edf1-120">December 2020</span></span>

- [<span data-ttu-id="2edf1-121">Безопасность по умолчанию в Office 365</span><span class="sxs-lookup"><span data-stu-id="2edf1-121">Secure by default in Office 365</span></span>](secure-by-default.md)
- <span data-ttu-id="2edf1-122">Автоматизированные улучшения в расследовании: общие оповещения для ручных расследований электронной почты, обработка изменений почтовых ящиков в качестве отдельной категории сущности, удаление избыточных действий блокировки URL-адресов и создание исходящие кластеры электронной почты для скомпрометизированных пользователями расследований.</span><span class="sxs-lookup"><span data-stu-id="2edf1-122">Automated investigation improvements to: general alerts for manually triggered email investigations, treat mailbox changes as a separate entity category, remove redundant URL block actions, and create outbound email clusters for user compromised investigations.</span></span>

## <a name="november-2020"></a><span data-ttu-id="2edf1-123">Ноябрь 2020 г.</span><span class="sxs-lookup"><span data-stu-id="2edf1-123">November 2020</span></span>

- <span data-ttu-id="2edf1-124">Обновленные ограничения экспорта в центре > действий > из журнала отправки почты и действий (Defender for Office 365 Plan 2)</span><span class="sxs-lookup"><span data-stu-id="2edf1-124">Updated export limits in Review > Action Center > Remediation from Mail Submission and Action Log (Defender for Office 365 Plan 2)</span></span>

## <a name="septemberoctober-2020"></a><span data-ttu-id="2edf1-125">Сентябрь-октябрь 2020 г.</span><span class="sxs-lookup"><span data-stu-id="2edf1-125">September/October 2020</span></span>

- [<span data-ttu-id="2edf1-126">Проверка политик с помощью анализатора конфигурации</span><span class="sxs-lookup"><span data-stu-id="2edf1-126">Check your policies using Configuration Analyzer</span></span>](configuration-analyzer-for-security-policies.md)
- <span data-ttu-id="2edf1-127">Расширенные возможности в [Обозревателе](threat-explorer.md#new-features-in-threat-explorer-and-real-time-detections) угроз, включая топ-пользователей, правила транспорта и соединители (сведения Defender for Office 365 в Обозревателе угроз [(электронная](threat-explorer.md) почта была разрешена/заблокирована политикой клиента/пользователя) (Defender for Office 365 Plan 2)</span><span class="sxs-lookup"><span data-stu-id="2edf1-127">[Extended capabilities in Threat Explorer including top targeted users, transport rules, and connectors](threat-explorer.md#new-features-in-threat-explorer-and-real-time-detections) (Defender for Office 365 information in [Threat Explorer](threat-explorer.md) (email was allowed/blocked by tenant/user policy) (Defender for Office 365 Plan 2)</span></span>
- <span data-ttu-id="2edf1-128">Угрозы URL-адресов в [Обозревателе](threat-explorer.md#threats-in-urls) угроз (вредоносные программы, фишинг, спам или нет) (Defender for Office 365 Plan 2)</span><span class="sxs-lookup"><span data-stu-id="2edf1-128">Surfacing URL threats in [Threat Explorer](threat-explorer.md#threats-in-urls) (malware, phish, spam, or none) (Defender for Office 365 Plan 2)</span></span>
- <span data-ttu-id="2edf1-129">[Улучшения обозревателя](threat-explorer.md#improvements-to-the-threat-hunting-experience-upcoming) угроз для охоты с обновлениями вокруг угроз, дополнительных действий, расположения доставки и обновленного представления временной шкалы (Defender for Office 365 Plan 2)</span><span class="sxs-lookup"><span data-stu-id="2edf1-129">[Improvements to Hunting Experience Threat Explorer](threat-explorer.md#improvements-to-the-threat-hunting-experience-upcoming) with updates around Threats, Additional Actions, Delivery locations and Updated timeline view (Defender for Office 365 Plan 2)</span></span>

## <a name="julyaugust-2020"></a><span data-ttu-id="2edf1-130">Июль-август 2020 г.</span><span class="sxs-lookup"><span data-stu-id="2edf1-130">July/August 2020</span></span>

- <span data-ttu-id="2edf1-131">[Улучшение охоты](threat-explorer.md#improvements-to-threat-hunting-experience) (Microsoft Defender для Office 365 Plan 1 или Plan 2)</span><span class="sxs-lookup"><span data-stu-id="2edf1-131">[Experience improvements to the hunting experience](threat-explorer.md#improvements-to-threat-hunting-experience) (Microsoft Defender for Office 365 Plan 1 or Plan 2)</span></span>
- [<span data-ttu-id="2edf1-132">Легко применить рекомендуемые параметры с помощью заранее задав политики безопасности</span><span class="sxs-lookup"><span data-stu-id="2edf1-132">Easily apply recommended settings using preset security policies</span></span>](preset-security-policies.md)

## <a name="marchapril-2020"></a><span data-ttu-id="2edf1-133">Март-апрель 2020 г.</span><span class="sxs-lookup"><span data-stu-id="2edf1-133">March/April 2020</span></span>

- <span data-ttu-id="2edf1-134">Теперь в [общем доступе](address-compromised-users-quickly.md) доступна возможность устранения скомпрометизированных учетных записей пользователей с помощью автоматического расследования и ответа.</span><span class="sxs-lookup"><span data-stu-id="2edf1-134">The ability to [address compromised user accounts with automated investigation and response](address-compromised-users-quickly.md) is now generally available.</span></span> <span data-ttu-id="2edf1-135">(Microsoft Defender для Office 365 Plan 2)</span><span class="sxs-lookup"><span data-stu-id="2edf1-135">(Microsoft Defender for Office 365 Plan 2)</span></span>

## <a name="januaryfebruary-2020"></a><span data-ttu-id="2edf1-136">Январь-февраль 2020 г.</span><span class="sxs-lookup"><span data-stu-id="2edf1-136">January/February 2020</span></span>

- <span data-ttu-id="2edf1-137">[Общая доступность представлений кампании в Microsoft Defender для Office 365](campaigns.md) (Microsoft Defender для Office 365 Plan 2)</span><span class="sxs-lookup"><span data-stu-id="2edf1-137">[General availability of Campaign Views in Microsoft Defender for Office 365](campaigns.md) (Microsoft Defender for Office 365 Plan 2)</span></span>
- <span data-ttu-id="2edf1-138">Усовершенствования в [Обозревателе](threat-explorer.md) угроз, позволяющие группам операций безопасности искать и фильтровать на нескольких полях при расследовании электронной [почты:](investigate-malicious-email-that-was-delivered.md)(Microsoft Defender для Office 365 Plan 2)</span><span class="sxs-lookup"><span data-stu-id="2edf1-138">Enhancements to [Threat Explorer](threat-explorer.md) to enable security operations teams to search and filter on multiple fields while [investigating email](investigate-malicious-email-that-was-delivered.md): (Microsoft Defender for Office 365 Plan 2)</span></span>
  - <span data-ttu-id="2edf1-139">Расположение доставки и специальные действия</span><span class="sxs-lookup"><span data-stu-id="2edf1-139">Delivery location and special actions</span></span>
  - <span data-ttu-id="2edf1-140">Directionality (входящий, исходящие или внутри-org)</span><span class="sxs-lookup"><span data-stu-id="2edf1-140">Directionality (inbound, outbound, or intra-org)</span></span>
  - <span data-ttu-id="2edf1-141">Расширенные нефильтры (это расширенные параметры фильтрации, которые не содержат, не включают и т.д.)</span><span class="sxs-lookup"><span data-stu-id="2edf1-141">Advanced NOT filters (these are advanced filtering options that include does not contain, does not include, etc.)</span></span>
  - <span data-ttu-id="2edf1-142">Зернистые фильтры времени (день, час, полчаса)</span><span class="sxs-lookup"><span data-stu-id="2edf1-142">Granular time filters (day, hour, half-hour)</span></span>

- <span data-ttu-id="2edf1-143">Виджет **Incidents** теперь является **виджетом Центра действий.**</span><span class="sxs-lookup"><span data-stu-id="2edf1-143">The **Incidents** widget is now the **Action Center** widget.</span></span> <span data-ttu-id="2edf1-144">(Чтобы просмотреть виджеты безопасности в Центре & безопасности, перейдите к **управлению угрозами** \> **Обзор**.) (Microsoft Defender для Office 365 Plan 2)</span><span class="sxs-lookup"><span data-stu-id="2edf1-144">(To view your security widgets, in the Security & Compliance Center, go to **Threat management** \> **Review**.) (Microsoft Defender for Office 365 Plan 2)</span></span>

- <span data-ttu-id="2edf1-145">[Безопасные документы в Microsoft 365](safe-docs.md) **(предварительный просмотр)**</span><span class="sxs-lookup"><span data-stu-id="2edf1-145">[Safe Documents in Microsoft 365](safe-docs.md) **(preview)**</span></span>

## <a name="december-2019"></a><span data-ttu-id="2edf1-146">Декабрь 2019 г.</span><span class="sxs-lookup"><span data-stu-id="2edf1-146">December 2019</span></span>

- <span data-ttu-id="2edf1-147">[Экспорт URL-адреса щелкните](threat-explorer.md#new-features-in-threat-explorer-and-real-time-detections) данные для автономного анализа (Microsoft Defender для Office 365 Plan 1 или Plan 2)</span><span class="sxs-lookup"><span data-stu-id="2edf1-147">[Export URL click data for offline analysis](threat-explorer.md#new-features-in-threat-explorer-and-real-time-detections) (Microsoft Defender for Office 365 Plan 1 or Plan 2)</span></span>

- <span data-ttu-id="2edf1-148">[Использование представлений кампании в Microsoft Defender для Office 365 **(предварительный** просмотр)](campaigns.md) (Microsoft Defender для Office 365 Plan 2)</span><span class="sxs-lookup"><span data-stu-id="2edf1-148">[Use Campaign Views in Microsoft Defender for Office 365 (**preview**)](campaigns.md) (Microsoft Defender for Office 365 Plan 2)</span></span>

## <a name="november-2019"></a><span data-ttu-id="2edf1-149">Ноябрь 2019 г.</span><span class="sxs-lookup"><span data-stu-id="2edf1-149">November 2019</span></span>

- <span data-ttu-id="2edf1-150">[Ознакомьтесь с новыми возможностями](address-compromised-users-quickly.md) обнаруженияи реагирования пользователей (предварительный просмотр) (Microsoft Defender для Office 365 Plan 2)</span><span class="sxs-lookup"><span data-stu-id="2edf1-150">[Check out new compromised user detection and response capabilities](address-compromised-users-quickly.md) (**preview**) (Microsoft Defender for Office 365 Plan 2)</span></span>

## <a name="september-2019"></a><span data-ttu-id="2edf1-151">Сентябрь 2019 г.</span><span class="sxs-lookup"><span data-stu-id="2edf1-151">September 2019</span></span>

- <span data-ttu-id="2edf1-152">[Использование возможностей автоматического](automated-investigation-response-office.md) расследования и реагирования (Microsoft Defender для Office 365 Plan 2)</span><span class="sxs-lookup"><span data-stu-id="2edf1-152">[Employ automated investigation and response capabilities](automated-investigation-response-office.md) (Microsoft Defender for Office 365 Plan 2)</span></span>

- <span data-ttu-id="2edf1-153">Интеграция с Microsoft Defender для автоматизированных событий расследования и реагирования Office 365 с помощью API управления [Office 365](/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema) (Defender for Office 365 Plan 2)</span><span class="sxs-lookup"><span data-stu-id="2edf1-153">[Integrate with Microsoft Defender for Office 365 automated investigation and response events using the Office 365 Management Activity API](/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema) (Defender for Office 365 Plan 2)</span></span>

- <span data-ttu-id="2edf1-154">[Просмотр заголовок электронной почты](investigate-malicious-email-that-was-delivered.md) и скачивание тела электронной почты (Microsoft Defender для Office 365 Plan 1 или Plan 2)</span><span class="sxs-lookup"><span data-stu-id="2edf1-154">[View the email headers and download the email body](investigate-malicious-email-that-was-delivered.md) (Microsoft Defender for Office 365 Plan 1 or Plan 2)</span></span>

## <a name="august-2019"></a><span data-ttu-id="2edf1-155">Август 2019 г.</span><span class="sxs-lookup"><span data-stu-id="2edf1-155">August 2019</span></span>

- <span data-ttu-id="2edf1-156">[Просмотр временной шкалы электронной](investigate-malicious-email-that-was-delivered.md#view-the-timeline-of-your-email) почты (Microsoft Defender для Office 365 Plan 1 или Plan 2)</span><span class="sxs-lookup"><span data-stu-id="2edf1-156">[View the timeline of email](investigate-malicious-email-that-was-delivered.md#view-the-timeline-of-your-email) (Microsoft Defender for Office 365 Plan 1 or Plan 2)</span></span>

## <a name="july-2019"></a><span data-ttu-id="2edf1-157">Июль 2019 г.</span><span class="sxs-lookup"><span data-stu-id="2edf1-157">July 2019</span></span>

- <span data-ttu-id="2edf1-158">[Проверьте действие доставки и расположение сообщений](investigate-malicious-email-that-was-delivered.md#check-the-delivery-action-and-location) электронной почты (Microsoft Defender для Office 365 Plan 1 или 2)</span><span class="sxs-lookup"><span data-stu-id="2edf1-158">[Check the delivery action and location of email messages](investigate-malicious-email-that-was-delivered.md#check-the-delivery-action-and-location) (Microsoft Defender for Office 365 Plan 1 or 2)</span></span>

## <a name="june-2019"></a><span data-ttu-id="2edf1-159">Июнь 2019 г.</span><span class="sxs-lookup"><span data-stu-id="2edf1-159">June 2019</span></span>

- <span data-ttu-id="2edf1-160">[Просмотр URL-адресов фишинга](threat-explorer.md#view-phishing-url-and-click-verdict-data) и щелкните данные вердикта (Microsoft Defender для Office 365 Plan 1 или Plan 2)</span><span class="sxs-lookup"><span data-stu-id="2edf1-160">[View phishing URLs and click verdict data](threat-explorer.md#view-phishing-url-and-click-verdict-data) (Microsoft Defender for Office 365 Plan 1 or Plan 2)</span></span>

## <a name="microsoft-defender-for-office-365-plan-1-and-plan-2"></a><span data-ttu-id="2edf1-161">Microsoft Defender для Office 365 (план 1 и план 2)</span><span class="sxs-lookup"><span data-stu-id="2edf1-161">Microsoft Defender for Office 365 Plan 1 and Plan 2</span></span>

<span data-ttu-id="2edf1-162">Знаете ли вы, что Microsoft Defender для Office 365 доступен в двух планах?</span><span class="sxs-lookup"><span data-stu-id="2edf1-162">Did you know that Microsoft Defender for Office 365 is available in two plans?</span></span> <span data-ttu-id="2edf1-163">[Узнайте больше о том, что включает в себя каждый план.](defender-for-office-365.md#microsoft-defender-for-office-365-plan-1-and-plan-2)</span><span class="sxs-lookup"><span data-stu-id="2edf1-163">[Learn more about what each plan includes](defender-for-office-365.md#microsoft-defender-for-office-365-plan-1-and-plan-2).</span></span>

## <a name="see-also"></a><span data-ttu-id="2edf1-164">См. также</span><span class="sxs-lookup"><span data-stu-id="2edf1-164">See also</span></span>

[<span data-ttu-id="2edf1-165">Дорожная карта Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="2edf1-165">Microsoft 365 roadmap</span></span>](https://www.microsoft.com/microsoft-365/roadmap)

[<span data-ttu-id="2edf1-166">Описание службы Microsoft Defender для Office 365</span><span class="sxs-lookup"><span data-stu-id="2edf1-166">Microsoft Defender for Office 365 Service Description</span></span>](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)
