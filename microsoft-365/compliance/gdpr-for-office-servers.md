---
title: GDPR для серверов Office
description: Узнайте, как обеспечить соблюдение требований Общего регламента по защите данных (GDPR) на локальных серверах Office.
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
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 5ee42a12f65ad5eff0a33ef2b61d328ebdc7af3e
ms.sourcegitcommit: 27daadad9ca0f02a833ff3cff8a574551b9581da
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2020
ms.locfileid: "47547335"
---
# <a name="gdpr-for-office-on-premises-servers"></a><span data-ttu-id="50144-103">GDPR для локальных серверов Office</span><span class="sxs-lookup"><span data-stu-id="50144-103">GDPR for Office on-premises Servers</span></span>

<span data-ttu-id="50144-p101">Общий регламент по защите данных (GDPR) устанавливает требования в отношении защиты персональных данных и надлежащего реагирования на запросы субъектов данных. В этой серии статей представлены рекомендуемые подходы для локальных рабочих нагрузок.</span><span class="sxs-lookup"><span data-stu-id="50144-p101">The General Data Protection Regulation (GDPR) introduces requirements for organizations to protect personal data and respond appropriately to data subject requests. This series of articles provides recommended approaches for on-premises workloads:</span></span>

- [<span data-ttu-id="50144-106">SharePoint Server</span><span class="sxs-lookup"><span data-stu-id="50144-106">SharePoint Server</span></span>](gdpr-for-sharepoint-server.md)

- [<span data-ttu-id="50144-107">Exchange Server</span><span class="sxs-lookup"><span data-stu-id="50144-107">Exchange Server</span></span>](gdpr-for-exchange-server.md)

- [<span data-ttu-id="50144-108">Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="50144-108">Skype for Business Server</span></span>](gdpr-for-skype-for-business-server.md)

- [<span data-ttu-id="50144-109">Project Server</span><span class="sxs-lookup"><span data-stu-id="50144-109">Project Server</span></span>](gdpr-for-project-server.md)

- [<span data-ttu-id="50144-110">Сервер Office Web Apps и Office Online Server</span><span class="sxs-lookup"><span data-stu-id="50144-110">Office Web Apps Server and Office Online Server</span></span>](gdpr-for-office-online-server.md)

- [<span data-ttu-id="50144-111">Локальные общие папки</span><span class="sxs-lookup"><span data-stu-id="50144-111">On-premises file shares</span></span>](gdpr-for-on-premises-file-shares.md)

<span data-ttu-id="50144-112">Дополнительные сведения о GDPR и поддержке, которую может оказать вам корпорация Майкрософт см. в [центре управления безопасностью (Майкрософт)](https://www.microsoft.com/trust-center/privacy/gdpr-overview
).</span><span class="sxs-lookup"><span data-stu-id="50144-112">For more information about the GDPR and how Microsoft can help you, see the [Microsoft Trust Center](https://www.microsoft.com/trust-center/privacy/gdpr-overview
).</span></span>

<span data-ttu-id="50144-p102">Прежде чем выполнять какие-либо действия с локальными данными, проконсультируйтесь с вашими юристами и группой по обеспечению соответствия требованиям, чтобы получить рекомендации и сведения о существующих схемах классификации и подходах к работе с персональными данными. Рекомендации по разработке и расширению схем классификации корпорации Майкрософт представлены в наборе средств для обнаружения данных GDPR по адресу [https://aka.ms/gdprpartners](<https://aka.ms/gdprpartners>). В этом наборе средств также описываются способы перемещения локальных данных в облако, где можно использовать более сложные функции для управления данными. В статьях из этого раздела представлены рекомендации по работе с данными, которые должны оставаться в локальной среде.</span><span class="sxs-lookup"><span data-stu-id="50144-p102">Before doing any work with on-premises data, consult with your legal and compliance teams to seek guidance and to learn about existing classification schemas and approaches to working with personal data. Microsoft provides recommendations for developing and extending classifications schemas in the Microsoft GDPR Data Discovery Toolkit at [https://aka.ms/gdprpartners](<https://aka.ms/gdprpartners>). This toolkit also describes approaches for moving on-premises data to the cloud where you can use more sophisticated data governance capabilities, if this is desired. The articles in this section provide recommendations for data that is intended to remain on premises.</span></span>

<span data-ttu-id="50144-p103">Ниже перечислены рекомендуемые функции для обнаружения, классификации, защиты и мониторинга персональные данных для каждой из этих рабочих нагрузок. Дополнительные сведения см. в статьях этого раздела.</span><span class="sxs-lookup"><span data-stu-id="50144-p103">The following illustration lists recommended capabilities to use across each of these workloads to discover, classify, protect, and monitor personal data. See the articles in this section for more information.</span></span>

![Схема с описанием возможностей обнаружения, классификации, защиты и отслеживания персональных данных для рабочих нагрузок](../media/gdpr-for-office-servers-image1.png)

## <a name="illustration-description"></a><span data-ttu-id="50144-120">Описание иллюстрации</span><span class="sxs-lookup"><span data-stu-id="50144-120">Illustration description</span></span>

<span data-ttu-id="50144-121">Для работы специальных возможностей примеры на рисунке также приведены в таблице ниже.</span><span class="sxs-lookup"><span data-stu-id="50144-121">For accessibility, the following table provides the same examples in the illustration.</span></span>

****

|<span data-ttu-id="50144-122">Действие</span><span class="sxs-lookup"><span data-stu-id="50144-122">Action</span></span>|<span data-ttu-id="50144-123">Общие папки Windows Server</span><span class="sxs-lookup"><span data-stu-id="50144-123">Windows Server file shares</span></span>|<span data-ttu-id="50144-124">SharePoint Server</span><span class="sxs-lookup"><span data-stu-id="50144-124">SharePoint Server</span></span>|<span data-ttu-id="50144-125">Exchange Server</span><span class="sxs-lookup"><span data-stu-id="50144-125">Exchange Server</span></span>|<span data-ttu-id="50144-126">Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="50144-126">Skype for Business</span></span>|<span data-ttu-id="50144-127">Project Server</span><span class="sxs-lookup"><span data-stu-id="50144-127">Project Server</span></span>|
|---|---|---|---|---|---|
|<span data-ttu-id="50144-128">Поиск</span><span class="sxs-lookup"><span data-stu-id="50144-128">Discover</span></span>|<span data-ttu-id="50144-129">Сканер Azure Information Protection<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="50144-129">Azure Information Protection scanner<sup>\*</sup></span></span>|<span data-ttu-id="50144-130">Центр поиска или обнаружение электронных данных (после классификации данных)</span><span class="sxs-lookup"><span data-stu-id="50144-130">Search Center or eDiscovery (after data is classified)</span></span> <br/><br/> <span data-ttu-id="50144-131">Сканер Azure Information Protection<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="50144-131">Azure Information Protection scanner<sup>\*</sup></span></span>|<span data-ttu-id="50144-132">Портал обнаружения электронных данных Exchange</span><span class="sxs-lookup"><span data-stu-id="50144-132">Exchange eDiscovery Portal</span></span>|<span data-ttu-id="50144-133">Портал обнаружения электронных данных Exchange</span><span class="sxs-lookup"><span data-stu-id="50144-133">Exchange eDiscovery portal</span></span>|<span data-ttu-id="50144-134">Скрипты SQL для обнаружения и экспорта</span><span class="sxs-lookup"><span data-stu-id="50144-134">SQL scripts for discovery and exporting</span></span>|
|<span data-ttu-id="50144-135">Классификация</span><span class="sxs-lookup"><span data-stu-id="50144-135">Classify</span></span>|<span data-ttu-id="50144-136">Сканер Azure Information Protection<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="50144-136">Azure Information Protection scanner<sup>\*</sup></span></span> <br/><br/> <span data-ttu-id="50144-137">Типы конфиденциальной информации Office 365</span><span class="sxs-lookup"><span data-stu-id="50144-137">Office 365 sensitive information types</span></span>|<span data-ttu-id="50144-138">Сканер Azure Information Protection<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="50144-138">Azure Information Protection scanner<sup>\*</sup></span></span> <br/><br/> <span data-ttu-id="50144-139">Типы конфиденциальной информации Office 365</span><span class="sxs-lookup"><span data-stu-id="50144-139">Office 365 sensitive information types</span></span>|<span data-ttu-id="50144-140">Теги и политики хранения Exchange</span><span class="sxs-lookup"><span data-stu-id="50144-140">Exchange retention tags and retention policies</span></span>|<span data-ttu-id="50144-141">Теги и политики хранения Exchange</span><span class="sxs-lookup"><span data-stu-id="50144-141">Exchange retention tags and retention policies</span></span>||
|<span data-ttu-id="50144-142">Защитить</span><span class="sxs-lookup"><span data-stu-id="50144-142">Protect</span></span>||<span data-ttu-id="50144-143">Правила защиты от потери данных Exchange Server</span><span class="sxs-lookup"><span data-stu-id="50144-143">Exchange Server data loss prevention rules</span></span> <br/><br/> <span data-ttu-id="50144-144">Разрешения, защита IRM для библиотек</span><span class="sxs-lookup"><span data-stu-id="50144-144">Permissions, IRM-protection for libraries</span></span>|<span data-ttu-id="50144-145">Правила защиты от потери данных Exchange Server</span><span class="sxs-lookup"><span data-stu-id="50144-145">Exchange Server data loss prevention rules</span></span> <br/><br/> <span data-ttu-id="50144-146">Интеграция IRM с Exchange Server</span><span class="sxs-lookup"><span data-stu-id="50144-146">IRM integration with Exchange Server</span></span>|||
|<span data-ttu-id="50144-147">Отслеживать</span><span class="sxs-lookup"><span data-stu-id="50144-147">Monitor</span></span>|<span data-ttu-id="50144-148">Интеграция журналов с инструментами SIEM</span><span class="sxs-lookup"><span data-stu-id="50144-148">Integrate logs with SIEM tools</span></span>|<span data-ttu-id="50144-149">Интеграция журналов с инструментами SIEM</span><span class="sxs-lookup"><span data-stu-id="50144-149">Integrate logs with SIEM tools</span></span>|<span data-ttu-id="50144-150">Интеграция журналов с инструментами SIEM</span><span class="sxs-lookup"><span data-stu-id="50144-150">Integrate logs with SIEM tools</span></span>|<span data-ttu-id="50144-151">Интеграция журналов с инструментами SIEM</span><span class="sxs-lookup"><span data-stu-id="50144-151">Integrate logs with SIEM tools</span></span>|<span data-ttu-id="50144-152">Интеграция журналов с инструментами SIEM</span><span class="sxs-lookup"><span data-stu-id="50144-152">Integrate logs with SIEM tools</span></span>|
|

<span data-ttu-id="50144-153"><sup>\*</sup> Обратите внимание, что система защиты шифрует файл.</span><span class="sxs-lookup"><span data-stu-id="50144-153"><sup>\*</sup> Note that protection encrypts the file.</span></span> <span data-ttu-id="50144-154">Соответственно, SharePoint Server не может найти типы конфиденциальной информации в защищенных файлах.</span><span class="sxs-lookup"><span data-stu-id="50144-154">Consequently, SharePoint Server can't find the sensitive information types in protected files.</span></span>
