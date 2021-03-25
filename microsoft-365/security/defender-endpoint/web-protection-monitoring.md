---
title: Мониторинг безопасности просмотра веб-страниц в ATP Защитника Майкрософт
description: Использование веб-защиты в ATP Защитника Майкрософт для мониторинга безопасности просмотра веб-страниц
keywords: веб-защита, защита от веб-угроз, просмотр веб-сайтов, мониторинг, отчеты, карты, список доменов, безопасность, фишинг, вредоносные программы, эксплойт, веб-сайты, защита сети, Edge, Internet Explorer, Chrome, Firefox, веб-браузер
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: ellevin
author: levinec
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 326e508fbf5a0e968e890f5727a6ae542de437c2
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2021
ms.locfileid: "51186009"
---
# <a name="monitor-web-browsing-security"></a><span data-ttu-id="ba10c-104">Мониторинг безопасности просмотра веб-страниц</span><span class="sxs-lookup"><span data-stu-id="ba10c-104">Monitor web browsing security</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="ba10c-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="ba10c-105">**Applies to:**</span></span>
- [<span data-ttu-id="ba10c-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="ba10c-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="ba10c-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ba10c-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="ba10c-108">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="ba10c-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="ba10c-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="ba10c-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-main-abovefoldlink&rtc=1)

<span data-ttu-id="ba10c-110">Веб-защита позволяет отслеживать безопасность просмотра веб-страниц в  организации с помощью отчетов в > веб-защиты в Центре безопасности Защитника Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="ba10c-110">Web protection lets you monitor your organization’s web browsing security through reports under **Reports > Web protection** in the Microsoft Defender Security Center.</span></span> <span data-ttu-id="ba10c-111">Отчет содержит карточки, которые предоставляют статистику обнаружения веб-угроз.</span><span class="sxs-lookup"><span data-stu-id="ba10c-111">The report contains cards that provide web threat detection statistics.</span></span>

- <span data-ttu-id="ba10c-112">Обнаружение **веб-угроз** со временем — эта карта тренда отображает количество веб-угроз, обнаруженных по типу в течение выбранного периода времени (Последние 30 дней, Последние 3 месяца, Последние 6 месяцев)</span><span class="sxs-lookup"><span data-stu-id="ba10c-112">**Web threat protection detections over time** - this trending card displays the number of web threats detected by type during the selected time period (Last 30 days, Last 3 months, Last 6 months)</span></span>
 
    ![Изображение карты, показывающая обнаружение защиты от веб-угроз со временем](images/wtp-blocks-over-time.png)

- <span data-ttu-id="ba10c-114">**Сводка по** защите от веб-угроз — эта карта отображает общее количество обнаружений веб-угроз за последние 30 дней, демонстрируя распространение различных типов веб-угроз.</span><span class="sxs-lookup"><span data-stu-id="ba10c-114">**Web threat protection summary** - this card displays the total web threat detections in the past 30 days, showing distribution across the different types of web threats.</span></span> <span data-ttu-id="ba10c-115">Выбор фрагмента открывает список доменов, найденных на вредоносных или нежелательных веб-сайтах.</span><span class="sxs-lookup"><span data-stu-id="ba10c-115">Selecting a slice opens the list of the domains that were found with malicious or unwanted websites.</span></span>

    ![Изображение карты с сводкой защиты от веб-угроз](images/wtp-summary.png)

>[!Note]
><span data-ttu-id="ba10c-117">Это может занять до 12 часов, прежде чем блок будет отражен в картах или списке домена.</span><span class="sxs-lookup"><span data-stu-id="ba10c-117">It can take up to 12 hours before a block is reflected in the cards or the domain list.</span></span>

## <a name="types-of-web-threats"></a><span data-ttu-id="ba10c-118">Типы веб-угроз</span><span class="sxs-lookup"><span data-stu-id="ba10c-118">Types of web threats</span></span>

<span data-ttu-id="ba10c-119">Веб-защита классифицируют вредоносные и нежелательные веб-сайты как:</span><span class="sxs-lookup"><span data-stu-id="ba10c-119">Web protection categorizes malicious and unwanted websites as:</span></span>

- <span data-ttu-id="ba10c-120">**Фишинг —** веб-сайты, содержащие поддельные веб-формы и другие механизмы фишинга, предназначенные для обмана пользователей в разглашение учетных данных и других конфиденциальных сведений</span><span class="sxs-lookup"><span data-stu-id="ba10c-120">**Phishing** - websites that contain spoofed web forms and other phishing mechanisms designed to trick users into divulging credentials and other sensitive information</span></span>
- <span data-ttu-id="ba10c-121">**Вредоносные** — веб-сайты с вредоносными программами и кодом эксплойтов</span><span class="sxs-lookup"><span data-stu-id="ba10c-121">**Malicious** - websites that host malware and exploit code</span></span>
- <span data-ttu-id="ba10c-122">**Настраиваемый индикатор** — веб-сайты, URL-адреса или домены которых добавлены в [настраиваемый](manage-indicators.md) список индикаторов для блокировки</span><span class="sxs-lookup"><span data-stu-id="ba10c-122">**Custom indicator** - websites whose URLs or domains you've added to your [custom indicator list](manage-indicators.md) for blocking</span></span>

## <a name="view-the-domain-list"></a><span data-ttu-id="ba10c-123">Просмотр списка доменов</span><span class="sxs-lookup"><span data-stu-id="ba10c-123">View the domain list</span></span>

<span data-ttu-id="ba10c-124">Выберите определенную категорию веб-угроз в сводной карте **защиты** от веб-угроз, чтобы открыть страницу **Домены.**</span><span class="sxs-lookup"><span data-stu-id="ba10c-124">Select a specific web threat category in the **Web threat protection summary** card to open the **Domains** page.</span></span> <span data-ttu-id="ba10c-125">На этой странице отображается список доменов этой категории угроз.</span><span class="sxs-lookup"><span data-stu-id="ba10c-125">This page displays the list of the domains under that threat category.</span></span> <span data-ttu-id="ba10c-126">На странице приводится следующая информация для каждого домена:</span><span class="sxs-lookup"><span data-stu-id="ba10c-126">The page provides the following information for each domain:</span></span>

- <span data-ttu-id="ba10c-127">**Количество запросов** на URL-адреса в домене</span><span class="sxs-lookup"><span data-stu-id="ba10c-127">**Access count** - number of requests for URLs in the domain</span></span>
- <span data-ttu-id="ba10c-128">**Блоки** — количество запросов было заблокировано</span><span class="sxs-lookup"><span data-stu-id="ba10c-128">**Blocks** - number of times requests were blocked</span></span>
- <span data-ttu-id="ba10c-129">**Тенденция доступа** — изменение количества попыток доступа</span><span class="sxs-lookup"><span data-stu-id="ba10c-129">**Access trend** - change in number of access attempts</span></span>
- <span data-ttu-id="ba10c-130">**Категория угрозы** — тип веб-угрозы</span><span class="sxs-lookup"><span data-stu-id="ba10c-130">**Threat category** - type of web threat</span></span>
- <span data-ttu-id="ba10c-131">**Устройства** — число устройств с попытками доступа</span><span class="sxs-lookup"><span data-stu-id="ba10c-131">**Devices** - number of devices with access attempts</span></span>

<span data-ttu-id="ba10c-132">Выберите домен, чтобы просмотреть список устройств, которые пытались получить доступ к URL-адресам в этом домене, и список URL-адресов.</span><span class="sxs-lookup"><span data-stu-id="ba10c-132">Select a domain to view the list of devices that have attempted to access URLs in that domain and the list of URLs.</span></span>

## <a name="related-topics"></a><span data-ttu-id="ba10c-133">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="ba10c-133">Related topics</span></span>

- [<span data-ttu-id="ba10c-134">Обзор веб-защиты</span><span class="sxs-lookup"><span data-stu-id="ba10c-134">Web protection overview</span></span>](web-protection-overview.md)
- [<span data-ttu-id="ba10c-135">Фильтрация веб-контента</span><span class="sxs-lookup"><span data-stu-id="ba10c-135">Web content filtering</span></span>](web-content-filtering.md)
- [<span data-ttu-id="ba10c-136">Защита от веб-угроз</span><span class="sxs-lookup"><span data-stu-id="ba10c-136">Web threat protection</span></span>](web-threat-protection.md)
- [<span data-ttu-id="ba10c-137">Реагирование на веб-угрозы</span><span class="sxs-lookup"><span data-stu-id="ba10c-137">Respond to web threats</span></span>](web-protection-response.md)