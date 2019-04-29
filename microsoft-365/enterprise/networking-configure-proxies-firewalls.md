---
title: Шаг 4. Настройка обхода трафика
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 10/31/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Настройте веб-браузеры и пограничные устройства для обхода трафика в доверенные места Office 365.
ms.openlocfilehash: 8486b5c0da9e44ed0b9ee42feb7acbfd21445010
ms.sourcegitcommit: 3b2d3e2b38c4860db977e73dda119a465c669fa4
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2019
ms.locfileid: "33400103"
---
# <a name="step-4-configure-traffic-bypass"></a><span data-ttu-id="d62b1-103">Шаг 4. Настройка обхода трафика</span><span class="sxs-lookup"><span data-stu-id="d62b1-103">Step 4: Configure traffic bypass</span></span>

<span data-ttu-id="d62b1-104">*Этот шаг — необязательный; он применяется к планам E3 и E5 Microsoft 365 корпоративный.*</span><span class="sxs-lookup"><span data-stu-id="d62b1-104">*This step is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/networking_icon-small.png)

<span data-ttu-id="d62b1-p101">Так как обычный интернет-трафик может быть опасным, в традиционных сетях организаций для обеспечения безопасности используются пограничные устройства, такие как прокси-серверы, устройства расшифровки и анализа SSL-трафика, устройства анализа пакетов и системы защиты от потери данных. Проблемы, связанные с устройствами сетевого перехвата, описаны в статье "Использование сторонних сетевых устройств или решений для трафика Office 365".</span><span class="sxs-lookup"><span data-stu-id="d62b1-p101">Because general Internet traffic can be risky, typical organization networks enforce security with edge devices such as proxy servers, SSL Break and Inspect, and packet inspection devices, and data loss prevention systems. Read about some of the issues with network interception devices at Using third-party network devices or solutions on Office 365 traffic.</span></span>

<span data-ttu-id="d62b1-p102">Однако доменные имена DNS и IP-адреса, используемые облачными службами Microsoft 365, хорошо известны. Кроме того, сам трафик и службы надежно защищены. Поэтому вашим пограничным устройствам не нужно дублировать эту защиту. Промежуточные адреса и двойная обработка трафика Microsoft 365 могут значительно снизить производительность.</span><span class="sxs-lookup"><span data-stu-id="d62b1-p102">However, the DNS domain names and IP addresses used by Microsoft 365 cloud-based services are well known. Additionally, the traffic and services themselves are protected with many security features. Because this security and protection is already in place, your edge devices don’t need to duplicate it. Intermediate destinations and duplicate security processing for Microsoft 365 traffic can dramatically decrease performance.</span></span>

<span data-ttu-id="d62b1-p103">Первым шагом в устранении промежуточных адресов и двойной обработки является идентификация трафика Microsoft 365. Корпорация Майкрософт определила следующие типы доменных имен DNS и диапазонов IP-адресов (так называемые конечные точки):</span><span class="sxs-lookup"><span data-stu-id="d62b1-p103">The first step in eliminating intermediate destinations and duplicate security processing is to identify Microsoft 365 traffic. Microsoft has defined the following types of DNS domain names and IP address ranges, known as endpoints:</span></span>

- <span data-ttu-id="d62b1-p104">**Оптимизация.** Требуются для подключения ко всем службам Office 365 и представляют более 75 % пропускной способности, подключений и объема данных Microsoft 365. Эти конечные точки представляют сценарии Microsoft 365, наиболее чувствительные к производительности, задержке и доступности сети.</span><span class="sxs-lookup"><span data-stu-id="d62b1-p104">**Optimize** - Required for connectivity to every Office 365 service and represent over 75% of Microsoft 365 bandwidth, connections, and volume of data. These endpoints represent Microsoft 365 scenarios that are the most sensitive to network performance, latency and availability.</span></span>
- <span data-ttu-id="d62b1-115">**Разрешение.** Требуются для подключения к определенным службам и функциям Microsoft 365, но не так чувствительны к производительности и задержке в сети, как конечные точки категории "Оптимизация".</span><span class="sxs-lookup"><span data-stu-id="d62b1-115">**Allow** - Required for connectivity to specific Microsoft 365 services and features but are not as sensitive to network performance and latency as those in the Optimize category.</span></span>
 - <span data-ttu-id="d62b1-p105">**По умолчанию.** Представляют службы и зависимости Microsoft 365, не требующие оптимизации. Конечные точки категории "По умолчанию" можно рассматривать как обычный интернет-трафик.</span><span class="sxs-lookup"><span data-stu-id="d62b1-p105">**Default** - Represent Microsoft 365 services and dependencies that do not require any optimization. You can treat Default category endpoints as normal Internet traffic.</span></span>

<span data-ttu-id="d62b1-118">Доменные имена DNS и диапазоны IP-адресов можно найти на странице [https://aka.ms/o365endpoints](https://aka.ms/o365endpoints).</span><span class="sxs-lookup"><span data-stu-id="d62b1-118">You can find the DNS domain names and IP address ranges at [https://aka.ms/o365endpoints](https://aka.ms/o365endpoints).</span></span>

<span data-ttu-id="d62b1-119">Корпорация Майкрософт рекомендует:</span><span class="sxs-lookup"><span data-stu-id="d62b1-119">Microsoft recommends that you:</span></span>

- <span data-ttu-id="d62b1-p106">использовать скрипты PAC в интернет-браузерах локальных компьютеров для обхода прокси-серверов для доменных имен DNS облачных служб Microsoft 365. Последний скрипт PAC для Microsoft 365 — Get-Pacfile;</span><span class="sxs-lookup"><span data-stu-id="d62b1-p106">Use Proxy Automatic Configuration (PAC) scripts on the Internet browsers of your on-premises computers to bypass your proxy servers for the DNS domain names of Microsoft 365 cloud-based services. For the latest Microsoft 365 PAC script, see the Get-Pacfile PowerShell script.</span></span>
- <span data-ttu-id="d62b1-p107">проанализировать пограничные устройства, чтобы определить двойную обработку, а затем настроить пересылку трафика в конечные точки "Оптимизировать" и "Разрешить" без обработки. Это известно как обход трафика.</span><span class="sxs-lookup"><span data-stu-id="d62b1-p107">Analyze your edge devices to determine the duplicate processing and then configure them to forward traffic to Optimize and Allow endpoints without processing. This is known as traffic bypass.</span></span> 

<span data-ttu-id="d62b1-p108">К пограничным устройствам относятся брандмауэры, устройства расшифровки и анализа SSL-трафика, устройства анализа пакетов и системы защиты от потери данных. Чтобы настроить и обновить конфигурации пограничных устройств, используйте скрипт или вызов REST для получения структурированного списка конечных точек из веб-службы Office 365 Endpoints. Дополнительную информацию см. в статье [Веб-служба IP-адресов и URL-адресов в Office 365](https://docs.microsoft.com/office365/enterprise/office-365-ip-web-service).</span><span class="sxs-lookup"><span data-stu-id="d62b1-p108">Edge devices include firewalls, SSL Break and Inspect, and packet inspection devices, and data loss prevention systems. To configure and update the configurations of edge devices, you can use a script or a REST call to consume a structured list of endpoints from the Office 365 Endpoints web service. For more information, see [Office 365 IP Address and URL Web service](https://docs.microsoft.com/office365/enterprise/office-365-ip-web-service).</span></span>

<span data-ttu-id="d62b1-p109">Обратите внимание, что вы настраиваете обход только для трафика в конечные точки Microsoft 365 категорий "Оптимизировать" и "Разрешить". Остальной интернет-трафик будет передаваться через прокси и обрабатываться системами безопасности.</span><span class="sxs-lookup"><span data-stu-id="d62b1-p109">Note that you are only bypassing normal proxy and network security processing for traffic to Microsoft 365 Optimize and Allow categories endpoints. All other general Internet traffic will be proxied and be subject to your existing network security processing.</span></span>


<span data-ttu-id="d62b1-129">Прежде чем перейти к следующему шагу, проверьте [условия](networking-exit-criteria.md#crit-networking-step4), при выполнении которых можно считать данный шаг завершенным.</span><span class="sxs-lookup"><span data-stu-id="d62b1-129">As an interim checkpoint, you can see the [exit criteria](networking-exit-criteria.md#crit-networking-step4) for this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="d62b1-130">Следующий шаг</span><span class="sxs-lookup"><span data-stu-id="d62b1-130">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step5.png)|[<span data-ttu-id="d62b1-131">Оптимизация производительности клиентов и служб Office 365</span><span class="sxs-lookup"><span data-stu-id="d62b1-131">Optimize client and Office 365 service performance</span></span>](networking-optimize-tcp-performance.md) |



