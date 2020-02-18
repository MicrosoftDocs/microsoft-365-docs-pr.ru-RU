---
title: Шаг 4. Настройка обхода трафика
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/23/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Настройте веб-браузеры и пограничные устройства для обхода трафика в доверенные места Office 365.
ms.openlocfilehash: 71f62c5e245962f3514c49477e3cdeda17cb6397
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42066694"
---
# <a name="step-4-configure-traffic-bypass"></a><span data-ttu-id="908c6-103">Шаг 4. Настройка обхода трафика</span><span class="sxs-lookup"><span data-stu-id="908c6-103">Step 4: Configure traffic bypass</span></span>

<span data-ttu-id="908c6-104">*Этот этап не является обязательным. Он применяется к планам E3 и E5 Microsoft 365 корпоративный.*</span><span class="sxs-lookup"><span data-stu-id="908c6-104">*This step is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![Этап 1. Сеть](../media/deploy-foundation-infrastructure/networking_icon-small.png)

<span data-ttu-id="908c6-106">Так как обычный интернет-трафик может быть опасным, в традиционных сетях организаций для обеспечения безопасности используются пограничные устройства, такие как прокси-серверы, устройства расшифровки и анализа SSL-трафика, устройства анализа пакетов и системы защиты от потери данных. </span><span class="sxs-lookup"><span data-stu-id="908c6-106">Because general Internet traffic can be risky, typical organization networks enforce security with edge devices such as proxy servers, SSL Break and Inspect, packet inspection devices, and data loss prevention systems.</span></span> <span data-ttu-id="908c6-107">Некоторые проблемы, связанные с устройствами сетевого перехвата, описаны в статье [Использование сторонних сетевых устройств или решений для трафика Office 365](https://support.microsoft.com/help/2690045/using-third-party-network-devices-or-solutions-with-office-365).</span><span class="sxs-lookup"><span data-stu-id="908c6-107">Read about some of the issues with network interception devices at [Using third-party network devices or solutions on Office 365 traffic](https://support.microsoft.com/help/2690045/using-third-party-network-devices-or-solutions-with-office-365).</span></span>

<span data-ttu-id="908c6-p102">Однако доменные имена DNS и IP-адреса, используемые облачными службами Microsoft 365, хорошо известны. Кроме того, сам трафик и службы надежно защищены. Поэтому вашим пограничным устройствам не нужно дублировать эту защиту. Промежуточные адреса и двойная обработка трафика Microsoft 365 могут значительно снизить производительность.</span><span class="sxs-lookup"><span data-stu-id="908c6-p102">However, the DNS domain names and IP addresses used by Microsoft 365 cloud-based services are well known. Additionally, the traffic and services themselves are protected with many security features. Because this security and protection is already in place, your edge devices don’t need to duplicate it. Intermediate destinations and duplicate security processing for Microsoft 365 traffic can dramatically decrease performance.</span></span>

<span data-ttu-id="908c6-p103">Первым шагом в устранении промежуточных адресов и двойной обработки является идентификация трафика Microsoft 365. Корпорация Майкрософт определила следующие типы доменных имен DNS и диапазонов IP-адресов (так называемые конечные точки):</span><span class="sxs-lookup"><span data-stu-id="908c6-p103">The first step in eliminating intermediate destinations and duplicate security processing is to identify Microsoft 365 traffic. Microsoft has defined the following types of DNS domain names and IP address ranges, known as endpoints:</span></span>

- <span data-ttu-id="908c6-114">**Оптимизация.** Требуются для подключения ко всем службам Office 365 и представляют более 75 % пропускной способности, подключений и данных Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="908c6-114">**Optimize** - Required for connectivity to every Office 365 service and represent over 75% of Microsoft 365 bandwidth, connections, and volume of data.</span></span> <span data-ttu-id="908c6-115">Эти конечные точки представляют сценарии Microsoft 365, которые наиболее чувствительны к производительности, задержке в сети и доступности.</span><span class="sxs-lookup"><span data-stu-id="908c6-115">These endpoints represent Microsoft 365 scenarios that are the most sensitive to network performance, latency, and availability.</span></span>
- <span data-ttu-id="908c6-116">**Разрешение.** Требуются для подключения к определенным службам и функциям Microsoft 365, но не так чувствительны к производительности и задержке в сети, как конечные точки категории "Оптимизация".</span><span class="sxs-lookup"><span data-stu-id="908c6-116">**Allow** - Required for connectivity to specific Microsoft 365 services and features but are not as sensitive to network performance and latency as those in the Optimize category.</span></span>
 - <span data-ttu-id="908c6-p105">**По умолчанию.** Представляют службы и зависимости Microsoft 365, не требующие оптимизации. Конечные точки категории "По умолчанию" можно рассматривать как обычный интернет-трафик.</span><span class="sxs-lookup"><span data-stu-id="908c6-p105">**Default** - Represent Microsoft 365 services and dependencies that do not require any optimization. You can treat Default category endpoints as normal Internet traffic.</span></span>

<span data-ttu-id="908c6-119">Доменные имена DNS и диапазоны IP-адресов можно найти на странице [https://aka.ms/o365endpoints](https://aka.ms/o365endpoints).</span><span class="sxs-lookup"><span data-stu-id="908c6-119">You can find the DNS domain names and IP address ranges at [https://aka.ms/o365endpoints](https://aka.ms/o365endpoints).</span></span>

<span data-ttu-id="908c6-120">Корпорация Майкрософт рекомендует:</span><span class="sxs-lookup"><span data-stu-id="908c6-120">Microsoft recommends that you:</span></span>

- <span data-ttu-id="908c6-121">использовать скрипты автоматической настройки прокси-сервера (PAC) в интернет-браузерах локальных компьютеров для обхода прокси-серверов для доменных имен DNS облачных служб Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="908c6-121">Use Proxy Automatic Configuration (PAC) scripts on the Internet browsers of your on-premises computers to bypass your proxy servers for the DNS domain names of Microsoft 365 cloud-based services.</span></span> <span data-ttu-id="908c6-122">См. последний скрипт PAC для Microsoft 365 в статье [Скрипт Get-Pacfile в PowerShell](https://docs.microsoft.com/office365/enterprise/managing-office-365-endpoints#use-a-pac-file-for-direct-routing-of-vital-office-365-traffic).</span><span class="sxs-lookup"><span data-stu-id="908c6-122">For the latest Microsoft 365 PAC script, see the [Get-Pacfile PowerShell script](https://docs.microsoft.com/office365/enterprise/managing-office-365-endpoints#use-a-pac-file-for-direct-routing-of-vital-office-365-traffic).</span></span>

- <span data-ttu-id="908c6-p107">проанализировать пограничные устройства, чтобы определить двойную обработку, а затем настроить пересылку трафика в конечные точки "Оптимизировать" и "Разрешить" без обработки. Это известно как обход трафика.</span><span class="sxs-lookup"><span data-stu-id="908c6-p107">Analyze your edge devices to determine the duplicate processing and then configure them to forward traffic to Optimize and Allow endpoints without processing. This is known as traffic bypass.</span></span> 

<span data-ttu-id="908c6-125">Ниже описаны рекомендации для вашей сетевой инфраструктуры.</span><span class="sxs-lookup"><span data-stu-id="908c6-125">Here are these recommendations in your network infrastructure.</span></span>

![Рекомендации по оптимизации локального трафика](../media/networking-configure-proxies-firewalls/bypassing-edge-devices.png)

<span data-ttu-id="908c6-127">К пограничным устройствам относятся брандмауэры, устройства расшифровки и анализа SSL-трафика, устройства анализа пакетов и системы защиты от потери данных.</span><span class="sxs-lookup"><span data-stu-id="908c6-127">Edge devices include firewalls, SSL Break and Inspect, packet inspection devices, and data loss prevention systems.</span></span> <span data-ttu-id="908c6-128">Чтобы настроить или обновить конфигурацию пограничных устройств, можно использовать сценарий или вызов метода REST для применения структурированного списка конечных точек в веб-службе конечных точек Office 365.</span><span class="sxs-lookup"><span data-stu-id="908c6-128">To configure and update the configurations of edge devices, you can use a script or a REST call to consume a structured list of endpoints from the Office 365 Endpoints web service.</span></span> <span data-ttu-id="908c6-129">Дополнительные сведения см. в статье [Веб-служба IP-адресов и URL-адресов в Office 365](https://docs.microsoft.com/office365/enterprise/office-365-ip-web-service).</span><span class="sxs-lookup"><span data-stu-id="908c6-129">For more information, see [Office 365 IP Address and URL Web service](https://docs.microsoft.com/office365/enterprise/office-365-ip-web-service).</span></span>

<span data-ttu-id="908c6-p109">Обратите внимание, что вы настраиваете обход только для трафика в конечные точки Microsoft 365 категорий "Оптимизировать" и "Разрешить". Остальной интернет-трафик будет передаваться через прокси и обрабатываться системами безопасности.</span><span class="sxs-lookup"><span data-stu-id="908c6-p109">Note that you are only bypassing normal proxy and network security processing for traffic to Microsoft 365 Optimize and Allow categories endpoints. All other general Internet traffic will be proxied and be subject to your existing network security processing.</span></span>


<span data-ttu-id="908c6-132">Прежде чем перейти к следующему шагу, проверьте [условия](networking-exit-criteria.md#crit-networking-step4), при выполнении которых можно считать данный шаг завершенным.</span><span class="sxs-lookup"><span data-stu-id="908c6-132">As an interim checkpoint, you can see the [exit criteria](networking-exit-criteria.md#crit-networking-step4) for this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="908c6-133">Следующий шаг</span><span class="sxs-lookup"><span data-stu-id="908c6-133">Next step</span></span>

|||
|:-------|:-----|
|![Шаг 5](../media/stepnumbers/Step5.png)|[<span data-ttu-id="908c6-135">Оптимизация производительности клиентов и служб Office 365</span><span class="sxs-lookup"><span data-stu-id="908c6-135">Optimize client and Office 365 service performance</span></span>](networking-optimize-tcp-performance.md) |



