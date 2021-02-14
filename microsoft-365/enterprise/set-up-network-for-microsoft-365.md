---
title: Настройка сети для Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/19/2019
audience: ITPro
ms.topic: hub-page
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Ent_TLGs
- seo-marvel-apr2020
ms.assetid: ''
description: Ссылки на статьи со сведениями о том, как настроить сеть для Microsoft 365, включая обзор сетевых подключений и список конечных точек.
ms.openlocfilehash: f0e0499c70745d31399240372c190758285408aa
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/14/2020
ms.locfileid: "46693014"
---
# <a name="set-up-your-network-for-microsoft-365"></a><span data-ttu-id="7c882-103">Настройка сети для Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="7c882-103">Set up your network for Microsoft 365</span></span>

<span data-ttu-id="7c882-104">*Эта статья относится к Microsoft 365 корпоративный и Office 365 корпоративный.*</span><span class="sxs-lookup"><span data-stu-id="7c882-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="7c882-105">Важной частью подключения Microsoft 365 является настройка сети и подключений к Интернету для оптимизированного доступа.</span><span class="sxs-lookup"><span data-stu-id="7c882-105">An important part of your Microsoft 365 onboarding is to ensure that your network and Internet connections are set up for optimized access.</span></span> <span data-ttu-id="7c882-106">Настройка локальной сети для доступа к глобально распределенному облаку SaaS отличается от традиционной сети, оптимизированной для трафика к локальному центру обработки данных и центральному подключению к Интернету.</span><span class="sxs-lookup"><span data-stu-id="7c882-106">Configuring your on-premises network to access a globally distributed Software-as-a-Service (SaaS) cloud is different from a traditional network that is optimized for traffic to on-premises datacenters and a central Internet connection.</span></span> 

<span data-ttu-id="7c882-107">С помощью этих статей можно ознакомиться с основными различиями пограничных устройств, клиентских компьютеров и локальной сети, а также изменять их для обеспечения оптимальной производительности для локальных пользователей.</span><span class="sxs-lookup"><span data-stu-id="7c882-107">Use these articles to understand the key differences and to modify your edge devices, client computers, and on-premises network to get the best performance for your on-premises users.</span></span>

## <a name="how-microsoft-365-networking-works"></a><span data-ttu-id="7c882-108">Как работает сеть Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="7c882-108">How Microsoft 365 networking works</span></span>

<span data-ttu-id="7c882-109">Обзор подключения для Microsoft 365 см. в этих статьях:</span><span class="sxs-lookup"><span data-stu-id="7c882-109">See these articles for an overview of connectivity for Microsoft 365:</span></span>

- [<span data-ttu-id="7c882-110">Обзор возможности сетевого подключения к Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="7c882-110">Microsoft 365 networking connectivity overview</span></span>](microsoft-365-networking-overview.md)
- [<span data-ttu-id="7c882-111">Принципы сетевого подключения Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="7c882-111">Microsoft 365 network connectivity principles</span></span>](microsoft-365-network-connectivity-principles.md)
- [<span data-ttu-id="7c882-112">Оценка сетевого подключения Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="7c882-112">Assessing Microsoft 365 network connectivity</span></span>](assessing-network-connectivity.md)

<span data-ttu-id="7c882-113">Советы по повышению производительности см. в планировании сети и настройке [производительности для Microsoft 365.](network-planning-and-performance.md)</span><span class="sxs-lookup"><span data-stu-id="7c882-113">For advice on enhancing performance, see [Network planning and performance tuning for Microsoft 365](network-planning-and-performance.md).</span></span>

## <a name="support-microsoft-365-networking-as-a-network-equipment-vendor"></a><span data-ttu-id="7c882-114">Поддержка сети Microsoft 365 в качестве поставщика сетевого оборудования</span><span class="sxs-lookup"><span data-stu-id="7c882-114">Support Microsoft 365 networking as a network equipment vendor</span></span>

<span data-ttu-id="7c882-p102">Если вы являетесь поставщиком сетевого оборудования, присоединяйтесь к [партнерской программе Office 365 для поставщиков сетевых устройств и служб](microsoft-365-networking-partner-program.md). Зарегистрируйтесь в программе, чтобы встроить принципы сетевого подключения к Office 365 в свои продукты и решения.</span><span class="sxs-lookup"><span data-stu-id="7c882-p102">If you are a network equipment vendor, join the [Office 365 Networking Partner Program](microsoft-365-networking-partner-program.md). Enroll in the program to build Office 365 network connectivity principles into your products and solutions.</span></span> 

## <a name="office-365-endpoints"></a><span data-ttu-id="7c882-117">Конечные точки Office 365</span><span class="sxs-lookup"><span data-stu-id="7c882-117">Office 365 endpoints</span></span>

<span data-ttu-id="7c882-118">Конечные точки — это набор конечных IP-адресов, доменных имен DNS и URL-адресов для трафика Office 365 в Интернете.</span><span class="sxs-lookup"><span data-stu-id="7c882-118">Endpoints are the set of destination IP addresses, DNS domain names, and URLs for Office 365 traffic on the Internet.</span></span> 

<span data-ttu-id="7c882-p103">Чтобы повысить производительность облачных служб Office 365, некоторым конечным точкам требуется специальная обработка клиентскими браузерами и устройствами в сети периметра. К этим устройствам относятся брандмауэры, устройства расшифровки и анализа SSL-трафика, устройства анализа пакетов и системы защиты от потери данных.</span><span class="sxs-lookup"><span data-stu-id="7c882-p103">To optimize performance to Office 365 cloud-based services, some endpoints need special handling by your client browsers and the devices in your edge network. These devices include firewalls, SSL Break and Inspect and packet inspection devices, and data loss prevention systems.</span></span>

<span data-ttu-id="7c882-121">Подробные сведения см. в статье [Управление конечными точками Office 365](managing-office-365-endpoints.md).</span><span class="sxs-lookup"><span data-stu-id="7c882-121">See [Managing Office 365 endpoints](managing-office-365-endpoints.md) for the details.</span></span>

<span data-ttu-id="7c882-p104">В настоящее время существует пять разных облаков Office 365. Эта таблица позволяет перейти к списку конечных точек для каждого из них.</span><span class="sxs-lookup"><span data-stu-id="7c882-p104">There are currently five different Office 365 clouds. This table takes you to the list of endpoints for each one.</span></span>

| <span data-ttu-id="7c882-124">Конечные точки</span><span class="sxs-lookup"><span data-stu-id="7c882-124">Endpoints</span></span> | <span data-ttu-id="7c882-125">Description</span><span class="sxs-lookup"><span data-stu-id="7c882-125">Description</span></span> |
|:-------|:-----|
| [<span data-ttu-id="7c882-126">Глобальные конечные точки</span><span class="sxs-lookup"><span data-stu-id="7c882-126">Worldwide endpoints</span></span>](urls-and-ip-address-ranges.md) | <span data-ttu-id="7c882-127">Конечные точки для подписок на Office 365 во всем мире, которые включают облако сообщества государственных организаций США (GCC).</span><span class="sxs-lookup"><span data-stu-id="7c882-127">The endpoints for worldwide Office 365 subscriptions, which include the United States Government Community Cloud (GCC).</span></span> |
| [<span data-ttu-id="7c882-128">Конечные точки U.S. Government DoD</span><span class="sxs-lookup"><span data-stu-id="7c882-128">U.S. Government DoD endpoints</span></span>](microsoft-365-u-s-government-dod-endpoints.md) | <span data-ttu-id="7c882-129">Конечные точки для подписок Министерства обороны США (DoD).</span><span class="sxs-lookup"><span data-stu-id="7c882-129">The endpoints for United States Department of Defense (DoD) subscriptions.</span></span> |
| [<span data-ttu-id="7c882-130">Конечные точки U.S. Government GCC High</span><span class="sxs-lookup"><span data-stu-id="7c882-130">U.S. Government GCC High endpoints</span></span>](microsoft-365-u-s-government-gcc-high-endpoints.md) | <span data-ttu-id="7c882-131">Конечные точки для подписок GCC High государственных организаций США.</span><span class="sxs-lookup"><span data-stu-id="7c882-131">The endpoints for United States Government Community Cloud High (GCC High) subscriptions.</span></span> |
| [<span data-ttu-id="7c882-132">Конечные точки Office 365 под управлением 21Vianet</span><span class="sxs-lookup"><span data-stu-id="7c882-132">Office 365 operated by 21Vianet endpoints</span></span>](urls-and-ip-address-ranges-21vianet.md) | <span data-ttu-id="7c882-133">Конечные точки для Office 365 под управлением компании 21Vianet, соответствующие требованиям для Office 365 в Китае.</span><span class="sxs-lookup"><span data-stu-id="7c882-133">The endpoints for Office 365 operated by 21Vianet, which is designed to meet the needs for Office 365 in China.</span></span> |
| [<span data-ttu-id="7c882-134">Конечные точки Office 365 Germany</span><span class="sxs-lookup"><span data-stu-id="7c882-134">Office 365 Germany endpoints</span></span>](microsoft-365-germany-endpoints.md) | <span data-ttu-id="7c882-135">Конечные точки отдельного облака в Европе для наиболее регулируемых клиентов в Германии, Европейском Союзе (ЕС) и Европейской ассоциации свободной торговли (ЕАСТ).</span><span class="sxs-lookup"><span data-stu-id="7c882-135">The endpoints for a separate cloud in Europe for the most regulated customers in Germany, the European Union (EU), and the European Free Trade Association (EFTA).</span></span> |
|||

<span data-ttu-id="7c882-136">Чтобы автоматизировать получение актуального списка конечных точек для облачной службы Office 365, см. статью [Веб-служба IP-адресов и URL-адресов в Office 365](microsoft-365-ip-web-service.md).</span><span class="sxs-lookup"><span data-stu-id="7c882-136">To automate getting the latest list of endpoints for your Office 365 cloud, see the [Office 365 IP Address and URL Web service](microsoft-365-ip-web-service.md).</span></span>

<span data-ttu-id="7c882-137">Сведения о дополнительных конечных точках см. в этих статьях:</span><span class="sxs-lookup"><span data-stu-id="7c882-137">For additional endpoints, see these articles:</span></span>

- [<span data-ttu-id="7c882-138">Дополнительные конечные точки, отсутствующие в веб-службе</span><span class="sxs-lookup"><span data-stu-id="7c882-138">Additional endpoints not included in the Web service</span></span>](additional-office365-ip-addresses-and-urls.md)
- [<span data-ttu-id="7c882-139">Сетевые запросы в Office 2016 для Mac</span><span class="sxs-lookup"><span data-stu-id="7c882-139">Network requests in Office 2016 for Mac</span></span>](network-requests-in-office-2016-for-mac.md)


## <a name="additional-topics-for-microsoft-365-networking"></a><span data-ttu-id="7c882-140">Дополнительные разделы о сети Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="7c882-140">Additional topics for Microsoft 365 networking</span></span>

<span data-ttu-id="7c882-141">В этих статьях данная статья посвящена специальным темам в сети Microsoft 365:</span><span class="sxs-lookup"><span data-stu-id="7c882-141">See these articles for specialized topics in Microsoft 365 networking:</span></span>

- [<span data-ttu-id="7c882-142">Сети доставки содержимого</span><span class="sxs-lookup"><span data-stu-id="7c882-142">Content delivery networks</span></span>](content-delivery-networks.md)
- [<span data-ttu-id="7c882-143">Поддержка IPv6 в службах Office 365</span><span class="sxs-lookup"><span data-stu-id="7c882-143">IPv6 support in Office 365 services</span></span>](ipv6-support.md)
- [<span data-ttu-id="7c882-144">Поддержка NAT в Office 365</span><span class="sxs-lookup"><span data-stu-id="7c882-144">NAT support with Office 365</span></span>](nat-support-with-microsoft-365.md)

## <a name="expressroute-for-microsoft-365"></a><span data-ttu-id="7c882-145">ExpressRoute для Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="7c882-145">ExpressRoute for Microsoft 365</span></span>

<span data-ttu-id="7c882-146">Сведения об использовании ExpressRoute для трафика Office 365 см. в указанных ниже статьях.</span><span class="sxs-lookup"><span data-stu-id="7c882-146">See these articles for information on the use of ExpressRoute for Office 365 traffic:</span></span>

- [<span data-ttu-id="7c882-147">Azure ExpressRoute для Office 365</span><span class="sxs-lookup"><span data-stu-id="7c882-147">Azure ExpressRoute for Office 365</span></span>](azure-expressroute.md)
- [<span data-ttu-id="7c882-148">Реализация ExpressRoute для Office 365</span><span class="sxs-lookup"><span data-stu-id="7c882-148">Implementing ExpressRoute for Office 365</span></span>](implementing-expressroute.md)
- [<span data-ttu-id="7c882-149">Планирование сети при использовании ExpressRoute для Office 365</span><span class="sxs-lookup"><span data-stu-id="7c882-149">Network planning with ExpressRoute for Office 365</span></span>](network-planning-with-expressroute.md)
- [<span data-ttu-id="7c882-150">Маршрутизация с использованием ExpressRoute для Office 365</span><span class="sxs-lookup"><span data-stu-id="7c882-150">Routing with ExpressRoute for Office 365</span></span>](routing-with-expressroute.md)
