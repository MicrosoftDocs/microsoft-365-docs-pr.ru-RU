---
title: GDPR для серверов Office
description: Узнайте, как обеспечивать соблюдение требований GDPR на локальных серверах Office.
f1.keywords:
- NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
titleSuffix: Microsoft GDPR
ms.openlocfilehash: 5ef03851064104df6dcb00ac853bf7dff65cbfd3
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "41596436"
---
# <a name="gdpr-for-office-on-premises-servers"></a><span data-ttu-id="2edb3-103">GDPR для локальных серверов Office</span><span class="sxs-lookup"><span data-stu-id="2edb3-103">GDPR for Office on-premises Servers</span></span>

<span data-ttu-id="2edb3-p101">Общий регламент по защите данных (GDPR) устанавливает требования в отношении защиты персональных данных и надлежащего реагирования на запросы субъектов данных. В этой серии статей представлены рекомендуемые подходы для локальных рабочих нагрузок.</span><span class="sxs-lookup"><span data-stu-id="2edb3-p101">The General Data Protection Regulation (GDPR) introduces requirements for organizations to protect personal data and respond appropriately to data subject requests. This series of articles provides recommended approaches for on-premises workloads:</span></span>

-   [<span data-ttu-id="2edb3-106">SharePoint Server</span><span class="sxs-lookup"><span data-stu-id="2edb3-106">SharePoint Server</span></span>](gdpr-for-sharepoint-server.md)

-   [<span data-ttu-id="2edb3-107">Exchange Server</span><span class="sxs-lookup"><span data-stu-id="2edb3-107">Exchange Server</span></span>](gdpr-for-exchange-server.md)

-   [<span data-ttu-id="2edb3-108">Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="2edb3-108">Skype for Business Server</span></span>](gdpr-for-skype-for-business-server.md)

-   [<span data-ttu-id="2edb3-109">Project Server</span><span class="sxs-lookup"><span data-stu-id="2edb3-109">Project Server</span></span>](gdpr-for-project-server.md)

-   [<span data-ttu-id="2edb3-110">Сервер Office Web Apps и Office Online Server</span><span class="sxs-lookup"><span data-stu-id="2edb3-110">Office Web Apps Server and Office Online Server</span></span>](gdpr-for-office-online-server.md)

-   [<span data-ttu-id="2edb3-111">Локальные общие папки</span><span class="sxs-lookup"><span data-stu-id="2edb3-111">On-premises file shares</span></span>](gdpr-for-on-premises-file-shares.md)

<span data-ttu-id="2edb3-112">Дополнительные сведения о GDPR и поддержке, которую может оказать вам корпорация Майкрософт см. в [центре управления безопасностью (Майкрософт)](https://www.microsoft.com/TrustCenter/Privacy/gdpr/default.aspx).</span><span class="sxs-lookup"><span data-stu-id="2edb3-112">For more information about the GDPR and how Microsoft can help you, see the [Microsoft Trust Center](https://www.microsoft.com/TrustCenter/Privacy/gdpr/default.aspx).</span></span>

<span data-ttu-id="2edb3-p102">Прежде чем выполнять какие-либо действия с локальными данными, проконсультируйтесь с вашими юристами и группой по обеспечению соответствия требованиям, чтобы получить рекомендации и сведения о существующих схемах классификации и подходах к работе с персональными данными. Рекомендации по разработке и расширению схем классификации корпорации Майкрософт представлены в наборе средств для обнаружения данных GDPR по адресу [https://aka.ms/gdprpartners](<https://aka.ms/gdprpartners>). В этом наборе средств также описываются способы перемещения локальных данных в облако, где можно использовать более сложные функции для управления данными. В статьях из этого раздела представлены рекомендации по работе с данными, которые должны оставаться в локальной среде.</span><span class="sxs-lookup"><span data-stu-id="2edb3-p102">Before doing any work with on-premises data, consult with your legal and compliance teams to seek guidance and to learn about existing classification schemas and approaches to working with personal data. Microsoft provides recommendations for developing and extending classifications schemas in the Microsoft GDPR Data Discovery Toolkit at [https://aka.ms/gdprpartners](<https://aka.ms/gdprpartners>). This toolkit also describes approaches for moving on-premises data to the cloud where you can use more sophisticated data governance capabilities, if this is desired. The articles in this section provide recommendations for data that is intended to remain on premises.</span></span>

<span data-ttu-id="2edb3-p103">Ниже перечислены рекомендуемые функции для обнаружения, классификации, защиты и мониторинга персональные данных для каждой из этих рабочих нагрузок. Дополнительные сведения см. в статьях этого раздела.</span><span class="sxs-lookup"><span data-stu-id="2edb3-p103">The following illustration lists recommended capabilities to use across each of these workloads to discover, classify, protect, and monitor personal data. See the articles in this section for more information.</span></span>

![](media/gdpr-for-office-servers-image1.png)

## <a name="illustration-description"></a><span data-ttu-id="2edb3-119">Описание иллюстрации</span><span class="sxs-lookup"><span data-stu-id="2edb3-119">Illustration description</span></span>

<span data-ttu-id="2edb3-120">Для работы специальных возможностей примеры на рисунке также приведены в таблице ниже.</span><span class="sxs-lookup"><span data-stu-id="2edb3-120">For accessibility, the following table provides the same examples in the illustration.</span></span>

|             |<span data-ttu-id="2edb3-121">Общие папки Windows Server</span><span class="sxs-lookup"><span data-stu-id="2edb3-121">Windows Server file shares</span></span>|<span data-ttu-id="2edb3-122">SharePoint Server</span><span class="sxs-lookup"><span data-stu-id="2edb3-122">SharePoint Server</span></span>|<span data-ttu-id="2edb3-123">Exchange Server</span><span class="sxs-lookup"><span data-stu-id="2edb3-123">Exchange Server</span></span>|<span data-ttu-id="2edb3-124">Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="2edb3-124">Skype for Business</span></span>|<span data-ttu-id="2edb3-125">Project Server</span><span class="sxs-lookup"><span data-stu-id="2edb3-125">Project Server</span></span>|
|:------------|:-------------------------|:----------------|:--------------|:-----------------|:-------------|
|<span data-ttu-id="2edb3-126">Обнаружение</span><span class="sxs-lookup"><span data-stu-id="2edb3-126">Discover</span></span>|<span data-ttu-id="2edb3-127">Сканер Azure Information Protection\*</span><span class="sxs-lookup"><span data-stu-id="2edb3-127">Azure Information Protection scanner\*</span></span>|<span data-ttu-id="2edb3-128">Центр поиска или обнаружение электронных данных (после классификации данных); сканер Azure Information Protection\*</span><span class="sxs-lookup"><span data-stu-id="2edb3-128">Search Center or eDiscovery (after data is classified); Azure Information Protection scanner\*</span></span>|<span data-ttu-id="2edb3-129">Портал обнаружения электронных данных Exchange</span><span class="sxs-lookup"><span data-stu-id="2edb3-129">Exchange eDiscovery Portal</span></span>|<span data-ttu-id="2edb3-130">Портал обнаружения электронных данных Exchange</span><span class="sxs-lookup"><span data-stu-id="2edb3-130">Exchange eDiscovery portal</span></span>|<span data-ttu-id="2edb3-131">Скрипты SQL для обнаружения и экспорта</span><span class="sxs-lookup"><span data-stu-id="2edb3-131">SQL scripts for discovery and exporting</span></span>|
|<span data-ttu-id="2edb3-132">Классификация</span><span class="sxs-lookup"><span data-stu-id="2edb3-132">Classify</span></span>|<span data-ttu-id="2edb3-133">Сканер Azure Information Protection\*; типы конфиденциальной информации Office 365</span><span class="sxs-lookup"><span data-stu-id="2edb3-133">Azure Information Protection scanner\*; Office 365 sensitive information types</span></span>|<span data-ttu-id="2edb3-134">Сканер Azure Information Protection\*; типы конфиденциальной информации Office 365</span><span class="sxs-lookup"><span data-stu-id="2edb3-134">Azure Information Protection scanner\*; Office 365 sensitive information types</span></span>|<span data-ttu-id="2edb3-135">Теги и политики хранения Exchange</span><span class="sxs-lookup"><span data-stu-id="2edb3-135">Exchange retention tags and retention policies</span></span>|<span data-ttu-id="2edb3-136">Теги и политики хранения Exchange</span><span class="sxs-lookup"><span data-stu-id="2edb3-136">Exchange retention tags and retention policies</span></span>||
|<span data-ttu-id="2edb3-137">Защита</span><span class="sxs-lookup"><span data-stu-id="2edb3-137">Protect</span></span>||<span data-ttu-id="2edb3-138">Правила защиты от потери данных Exchange Server; разрешения, защита IRM для библиотек</span><span class="sxs-lookup"><span data-stu-id="2edb3-138">Exchange Server data loss prevention rules; Permissions, IRM-protection for libraries</span></span>|<span data-ttu-id="2edb3-139">Правила защиты от потери данных Exchange Server; интеграция IRM с Exchange Server</span><span class="sxs-lookup"><span data-stu-id="2edb3-139">Exchange Server data loss prevention rules; IRM integration with Exchange Server</span></span>|||
|<span data-ttu-id="2edb3-140">Мониторинг</span><span class="sxs-lookup"><span data-stu-id="2edb3-140">Monitor</span></span>|<span data-ttu-id="2edb3-141">Интеграция журналов с инструментами SIEM</span><span class="sxs-lookup"><span data-stu-id="2edb3-141">Integrate logs with SIEM tools</span></span>|<span data-ttu-id="2edb3-142">Интеграция журналов с инструментами SIEM</span><span class="sxs-lookup"><span data-stu-id="2edb3-142">Integrate logs with SIEM tools</span></span>|<span data-ttu-id="2edb3-143">Интеграция журналов с инструментами SIEM</span><span class="sxs-lookup"><span data-stu-id="2edb3-143">Integrate logs with SIEM tools</span></span>|<span data-ttu-id="2edb3-144">Интеграция журналов с инструментами SIEM</span><span class="sxs-lookup"><span data-stu-id="2edb3-144">Integrate logs with SIEM tools</span></span>|<span data-ttu-id="2edb3-145">Интеграция журналов с инструментами SIEM</span><span class="sxs-lookup"><span data-stu-id="2edb3-145">Integrate logs with SIEM tools</span></span>|

<span data-ttu-id="2edb3-p104">\* Обратите внимание, что система защиты шифрует файл. Соответственно, сервер SharePoint не может найти конфиденциальную информацию в защищенных файлах.</span><span class="sxs-lookup"><span data-stu-id="2edb3-p104">\*Note that protection encrypts the file. Consequently, SharePoint Server can’t find the sensitive information types in protected files.</span></span>
