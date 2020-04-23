---
title: Шаг 4. Настройка обхода трафика
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/20/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Настройте веб-браузеры и пограничные устройства для обхода трафика в доверенные места Microsoft 365.
ms.openlocfilehash: 3e0f9cec8d0d1385025289f1a07d2380be34f1a1
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/21/2020
ms.locfileid: "43631505"
---
# <a name="step-4-configure-traffic-bypass"></a><span data-ttu-id="7d990-103">Шаг 4. Настройка обхода трафика</span><span class="sxs-lookup"><span data-stu-id="7d990-103">Step 4: Configure traffic bypass</span></span>

<span data-ttu-id="7d990-104">*Этот этап не является обязательным. Он применяется к планам E3 и E5 Microsoft 365 корпоративный.*</span><span class="sxs-lookup"><span data-stu-id="7d990-104">*This step is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![Этап 1. Сеть](../media/deploy-foundation-infrastructure/networking_icon-small.png)

<span data-ttu-id="7d990-106">Так как обычный интернет-трафик может быть опасным, в традиционных сетях организаций для обеспечения безопасности используются пограничные устройства, такие как прокси-серверы, устройства расшифровки и анализа SSL-трафика, устройства анализа пакетов и системы защиты от потери данных. </span><span class="sxs-lookup"><span data-stu-id="7d990-106">Because general Internet traffic can be risky, typical organization networks enforce security with edge devices such as proxy servers, SSL Break and Inspect, packet inspection devices, and data loss prevention systems.</span></span> <span data-ttu-id="7d990-107">Некоторые проблемы, связанные с устройствами сетевого перехвата, описаны в статье [Использование сторонних сетевых устройств или решений для трафика Microsoft 365](https://support.microsoft.com/help/2690045/using-third-party-network-devices-or-solutions-with-office-365).</span><span class="sxs-lookup"><span data-stu-id="7d990-107">Read about some of the issues with network interception devices at [Using third-party network devices or solutions on Microsoft 365 traffic](https://support.microsoft.com/help/2690045/using-third-party-network-devices-or-solutions-with-office-365).</span></span>

<span data-ttu-id="7d990-p102">Однако доменные имена DNS и IP-адреса, используемые облачными службами Microsoft 365, хорошо известны. Кроме того, сам трафик и службы надежно защищены. Поэтому вашим пограничным устройствам не нужно дублировать эту защиту. Промежуточные адреса и двойная обработка трафика Microsoft 365 могут значительно снизить производительность.</span><span class="sxs-lookup"><span data-stu-id="7d990-p102">However, the DNS domain names and IP addresses used by Microsoft 365 cloud-based services are well known. Additionally, the traffic and services themselves are protected with many security features. Because this security and protection is already in place, your edge devices don’t need to duplicate it. Intermediate destinations and duplicate security processing for Microsoft 365 traffic can dramatically decrease performance.</span></span>

<span data-ttu-id="7d990-p103">Первым шагом в устранении промежуточных адресов и двойной обработки является идентификация трафика Microsoft 365. Корпорация Майкрософт определила следующие типы доменных имен DNS и диапазонов IP-адресов (так называемые конечные точки):</span><span class="sxs-lookup"><span data-stu-id="7d990-p103">The first step in eliminating intermediate destinations and duplicate security processing is to identify Microsoft 365 traffic. Microsoft has defined the following types of DNS domain names and IP address ranges, known as endpoints:</span></span>

- <span data-ttu-id="7d990-114">**Оптимизация.** Требуются для подключения ко всем службам Microsoft 365 и представляют более 75 % пропускной способности, подключений и данных Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="7d990-114">**Optimize** - Required for connectivity to every Microsoft 365 service and represent over 75% of Microsoft 365 bandwidth, connections, and volume of data.</span></span> <span data-ttu-id="7d990-115">Эти конечные точки представляют сценарии Microsoft 365, которые наиболее чувствительны к производительности, задержке в сети и доступности.</span><span class="sxs-lookup"><span data-stu-id="7d990-115">These endpoints represent Microsoft 365 scenarios that are the most sensitive to network performance, latency, and availability.</span></span>
- <span data-ttu-id="7d990-116">**Разрешение.** Требуются для подключения к определенным службам и функциям Microsoft 365, но не так чувствительны к производительности и задержке в сети, как конечные точки категории "Оптимизация".</span><span class="sxs-lookup"><span data-stu-id="7d990-116">**Allow** - Required for connectivity to specific Microsoft 365 services and features but are not as sensitive to network performance and latency as those in the Optimize category.</span></span>
 - <span data-ttu-id="7d990-p105">**По умолчанию.** Представляют службы и зависимости Microsoft 365, не требующие оптимизации. Конечные точки категории "По умолчанию" можно рассматривать как обычный интернет-трафик.</span><span class="sxs-lookup"><span data-stu-id="7d990-p105">**Default** - Represent Microsoft 365 services and dependencies that do not require any optimization. You can treat Default category endpoints as normal Internet traffic.</span></span>

<span data-ttu-id="7d990-119">Доменные имена DNS и диапазоны IP-адресов можно найти на странице [https://aka.ms/o365endpoints](https://aka.ms/o365endpoints).</span><span class="sxs-lookup"><span data-stu-id="7d990-119">You can find the DNS domain names and IP address ranges at [https://aka.ms/o365endpoints](https://aka.ms/o365endpoints).</span></span>

<span data-ttu-id="7d990-120">Корпорация Майкрософт рекомендует:</span><span class="sxs-lookup"><span data-stu-id="7d990-120">Microsoft recommends that you:</span></span>

- <span data-ttu-id="7d990-121">использовать скрипты автоматической настройки прокси-сервера (PAC) в интернет-браузерах локальных компьютеров для обхода прокси-серверов для доменных имен DNS облачных служб Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="7d990-121">Use Proxy Automatic Configuration (PAC) scripts on the Internet browsers of your on-premises computers to bypass your proxy servers for the DNS domain names of Microsoft 365 cloud-based services.</span></span> <span data-ttu-id="7d990-122">См. последний скрипт PAC для Microsoft 365 в статье [Скрипт Get-Pacfile в PowerShell](https://docs.microsoft.com/office365/enterprise/managing-office-365-endpoints#use-a-pac-file-for-direct-routing-of-vital-office-365-traffic).</span><span class="sxs-lookup"><span data-stu-id="7d990-122">For the latest Microsoft 365 PAC script, see the [Get-Pacfile PowerShell script](https://docs.microsoft.com/office365/enterprise/managing-office-365-endpoints#use-a-pac-file-for-direct-routing-of-vital-office-365-traffic).</span></span>

- <span data-ttu-id="7d990-p107">проанализировать пограничные устройства, чтобы определить двойную обработку, а затем настроить пересылку трафика в конечные точки "Оптимизировать" и "Разрешить" без обработки. Это известно как обход трафика.</span><span class="sxs-lookup"><span data-stu-id="7d990-p107">Analyze your edge devices to determine the duplicate processing and then configure them to forward traffic to Optimize and Allow endpoints without processing. This is known as traffic bypass.</span></span> 

<span data-ttu-id="7d990-125">Ниже описаны рекомендации для вашей сетевой инфраструктуры.</span><span class="sxs-lookup"><span data-stu-id="7d990-125">Here are these recommendations in your network infrastructure.</span></span>

![Рекомендации по оптимизации локального трафика](../media/networking-configure-proxies-firewalls/bypassing-edge-devices.png)

<span data-ttu-id="7d990-127">К пограничным устройствам относятся брандмауэры, устройства расшифровки и анализа SSL-трафика, устройства анализа пакетов и системы защиты от потери данных.</span><span class="sxs-lookup"><span data-stu-id="7d990-127">Edge devices include firewalls, SSL Break and Inspect, packet inspection devices, and data loss prevention systems.</span></span> <span data-ttu-id="7d990-128">Чтобы настроить или обновить конфигурацию пограничных устройств, можно использовать сценарий или вызов метода REST для применения структурированного списка конечных точек в веб-службе конечных точек Office 365.</span><span class="sxs-lookup"><span data-stu-id="7d990-128">To configure and update the configurations of edge devices, you can use a script or a REST call to consume a structured list of endpoints from the Office 365 Endpoints web service.</span></span> <span data-ttu-id="7d990-129">Дополнительные сведения см. в статье [Веб-служба IP-адресов и URL-адресов в Microsoft 365](https://docs.microsoft.com/office365/enterprise/office-365-ip-web-service).</span><span class="sxs-lookup"><span data-stu-id="7d990-129">For more information, see [Microsoft 365 IP Address and URL Web service](https://docs.microsoft.com/office365/enterprise/office-365-ip-web-service).</span></span>

<span data-ttu-id="7d990-p109">Обратите внимание, что вы настраиваете обход только для трафика в конечные точки Microsoft 365 категорий "Оптимизировать" и "Разрешить". Остальной интернет-трафик будет передаваться через прокси и обрабатываться системами безопасности.</span><span class="sxs-lookup"><span data-stu-id="7d990-p109">Note that you are only bypassing normal proxy and network security processing for traffic to Microsoft 365 Optimize and Allow categories endpoints. All other general Internet traffic will be proxied and be subject to your existing network security processing.</span></span>

## <a name="optimizing-traffic-for-remote-workers-that-use-vpn-connections"></a><span data-ttu-id="7d990-132">Оптимизация трафика для удаленных сотрудников, использующих VPN-подключения</span><span class="sxs-lookup"><span data-stu-id="7d990-132">Optimizing traffic for remote workers that use VPN connections</span></span>

<span data-ttu-id="7d990-133">Подключения виртуальной частной сети (VPN) обычно используются удаленными сотрудниками для доступа к ресурсам в интрасети организации.</span><span class="sxs-lookup"><span data-stu-id="7d990-133">Virtual private network (VPN) connections are commonly used by remote workers to access resources on an organization intranet.</span></span> <span data-ttu-id="7d990-134">Обычное VPN-подключение направляет ВЕСЬ трафик, включая интернет-трафик, в интрасеть организации.</span><span class="sxs-lookup"><span data-stu-id="7d990-134">A conventional VPN connection routes ALL traffic, including Internet traffic, to the organization intranet.</span></span> <span data-ttu-id="7d990-135">Интернет-трафик направляется на устройства периметра сети организации и устройства обработки пакетов.</span><span class="sxs-lookup"><span data-stu-id="7d990-135">The Internet traffic gets routed to the organization's edge network and packet processing devices.</span></span> <span data-ttu-id="7d990-136">На этот трафик влияют задержки пути и обработки, которые могут значительно снизить скорость работы и повлиять на производительность ваших удаленных сотрудников.</span><span class="sxs-lookup"><span data-stu-id="7d990-136">This traffic is subject to travel and processing delays that can dramatically decrease performance and impact the productivity of your remote workers.</span></span> 

<span data-ttu-id="7d990-137">Раздельное туннелирование — это возможность VPN-подключения для направления определенного трафика через Интернет вместо его отправки через VPN-подключение к интрасети.</span><span class="sxs-lookup"><span data-stu-id="7d990-137">Split tunneling is the capability of a VPN connection to route specified traffic over the Internet rather than sending it over the VPN connection to your intranet.</span></span> <span data-ttu-id="7d990-138">Для оптимизации производительности удаленных сотрудников при работе с основными службами Microsoft 365, такими как Teams, SharePoint Online и Exchange Online, настройте раздельное туннелирование VPN-подключений для отправки трафика с целью оптимизации категории конечных точек прямо через Интернет.</span><span class="sxs-lookup"><span data-stu-id="7d990-138">For the best performance for remote workers to critical Microsoft 365 services such as Teams, SharePoint Online, and Exchange Online, configure your split tunneling VPN connections to send traffic to Optimize category endpoints directly over the Internet.</span></span> 

<span data-ttu-id="7d990-139">Подробные сведения см. в статье [Оптимизация подключения для удаленных пользователей с помощью раздельного VPN-туннелирования](https://docs.microsoft.com/office365/enterprise/office-365-vpn-split-tunnel).</span><span class="sxs-lookup"><span data-stu-id="7d990-139">For detailed information, see [Optimize connectivity for remote users using VPN split tunnelling](https://docs.microsoft.com/office365/enterprise/office-365-vpn-split-tunnel).</span></span>

<span data-ttu-id="7d990-140">Чтобы протестировать, насколько близко вы находитесь к точке входа в глобальную сеть Майкрософт, а также к точке подключения сети организации к поставщику услуг интернета, воспользуйтесь [средством подключения сети Office 365](https://connectivity.office.com/).</span><span class="sxs-lookup"><span data-stu-id="7d990-140">To test how close you are to an entry point for Microsoft’s global network and how close you are to the point where your organization network connects to your ISP, use the [Office 365 Network Onboarding tool](https://connectivity.office.com/).</span></span>

<span data-ttu-id="7d990-141">Прежде чем перейти к следующему шагу, проверьте [условия](networking-exit-criteria.md#crit-networking-step4), при выполнении которых можно считать данный шаг завершенным.</span><span class="sxs-lookup"><span data-stu-id="7d990-141">As an interim checkpoint, you can see the [exit criteria](networking-exit-criteria.md#crit-networking-step4) for this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="7d990-142">Следующий шаг</span><span class="sxs-lookup"><span data-stu-id="7d990-142">Next step</span></span>

|||
|:-------|:-----|
|![Шаг 5](../media/stepnumbers/Step5.png)|[<span data-ttu-id="7d990-144">Оптимизация производительности клиентов и служб</span><span class="sxs-lookup"><span data-stu-id="7d990-144">Optimize client and service performance</span></span>](networking-optimize-tcp-performance.md) |



