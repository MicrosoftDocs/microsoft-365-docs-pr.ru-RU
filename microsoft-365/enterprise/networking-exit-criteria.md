---
title: Шаг 1. Условия, при выполнении которых можно считать сетевую инфраструктуру настроенной
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
description: Убедитесь, что используемая вами конфигурация соответствует критериям Microsoft 365 корпоративный для сетевой инфраструктуры.
ms.openlocfilehash: ad54284fdbd00fef486a13a957af6f06cb6a7450
ms.sourcegitcommit: 8bcd76e5c8749a5670fbc3356957a089454c03d1
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/02/2019
ms.locfileid: "37370156"
---
# <a name="phase-1-networking-infrastructure-exit-criteria"></a><span data-ttu-id="f63d0-103">Шаг 1. Условия, при выполнении которых можно считать сетевую инфраструктуру настроенной</span><span class="sxs-lookup"><span data-stu-id="f63d0-103">Phase 1: Networking infrastructure exit criteria</span></span>

![Этап 1. Сеть](./media/deploy-foundation-infrastructure/networking_icon-small.png)

<span data-ttu-id="f63d0-105">Убедитесь, что сетевая инфраструктура соответствует указанным ниже обязательным условиям и что рассмотрены необязательные условия.</span><span class="sxs-lookup"><span data-stu-id="f63d0-105">Make sure your networking infrastructure meets the following required criteria and that you've considered those that are optional.</span></span>

<a name="crit-networking-step1"></a>
## <a name="required-your-network-is-ready-for-microsoft-365-enterprise"></a><span data-ttu-id="f63d0-106">Обязательное: ваша сеть готова к Microsoft 365 корпоративный</span><span class="sxs-lookup"><span data-stu-id="f63d0-106">Required: Your network is ready for Microsoft 365 Enterprise</span></span>

- <span data-ttu-id="f63d0-107">Пропускная способность интернет-канала в ваших офисах является достаточной для трафика Microsoft 365, в том числе установки и обновлений Office 365, Microsoft Intune и Windows 10 Корпоративная.</span><span class="sxs-lookup"><span data-stu-id="f63d0-107">Your offices have adequate Internet bandwidth for Microsoft 365 traffic, including Office 365, Microsoft Intune, and Windows 10 Enterprise installation and updates</span></span>
- <span data-ttu-id="f63d0-108">В целом ваша сеть соответствует [эталонной архитектуре Office 365](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles#BKMK_P2).</span><span class="sxs-lookup"><span data-stu-id="f63d0-108">Your overall network maps to an Office 365 reference architecture</span></span>
- <span data-ttu-id="f63d0-109">Выполнено пилотное развертывание и тестирование изменений в вашей сети, и они соответствуют вашим требованиям к задержке трафика.</span><span class="sxs-lookup"><span data-stu-id="f63d0-109">Your network changes have been piloted and tested and meet with your traffic latency requirements</span></span>

<span data-ttu-id="f63d0-110">Чтобы выполнить это требование, см. [шаг 1](networking-provide-bandwidth-cloud-services.md).</span><span class="sxs-lookup"><span data-stu-id="f63d0-110">If needed, [Step 1](networking-provide-bandwidth-cloud-services.md) can help you with this requirement.</span></span>

<a name="crit-networking-step2"></a>
## <a name="required-your-local-offices-have-local-internet-connections-and-name-resolution"></a><span data-ttu-id="f63d0-111">Обязательное: локальные офисы имеют локальные подключения к Интернету и разрешение имен</span><span class="sxs-lookup"><span data-stu-id="f63d0-111">Required: Your local offices have local Internet connections and name resolution</span></span>

<span data-ttu-id="f63d0-112">Для каждого локального офиса вы настроили доступ к Интернету через локального поставщика услуг Интернета, чьи DNS-серверы используют локальный общедоступный IP-адрес, который определяет их местоположение в Интернете. </span><span class="sxs-lookup"><span data-stu-id="f63d0-112">You configured each local office with Internet access with a local ISP whose DNS servers use a local public IP address that identifies their location on the Internet. This ensures the best possible performance for users who access Office 365 and Intune.</span></span> <span data-ttu-id="f63d0-113">Это обеспечивает максимальную производительность для пользователей, работающих с облачными службами Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f63d0-113">This ensures the best possible performance for users who access Microsoft 365 cloud services.</span></span>

<span data-ttu-id="f63d0-114">Если вы не используете локального поставщика услуг Интернета для каждого филиала, это может снизить производительность, так как в этом случае сетевой трафик проходит через основной канал организации либо запросы к данным обрабатываются удаленными серверами переднего плана.</span><span class="sxs-lookup"><span data-stu-id="f63d0-114">If you don’t use a local ISP for each branch office, performance can suffer because network traffic must traverse an organization’s backbone or data requests are serviced by remote front-end servers.</span></span>

### <a name="how-to-test"></a><span data-ttu-id="f63d0-115">Проверка</span><span class="sxs-lookup"><span data-stu-id="f63d0-115">How to test</span></span>
<span data-ttu-id="f63d0-p102">С помощью соответствующего средства или веб-сайта на устройстве в этом офисе определите IP-адрес, используемый прокси-сервером. Например, можно использовать веб-страницу [для определения своего IP-адреса](https://www.whatismypublicip.com/). Этот общедоступный IP-адрес, назначенный вашим поставщиком услуг Интернета, должен быть локальным в географическом смысле. Его не должно быть в диапазоне общедоступных IP-адресов центрального офиса или облачного поставщика безопасности сети.</span><span class="sxs-lookup"><span data-stu-id="f63d0-p102">Use a tool or web site from a device in that office to determine the public IP address that the proxy server is using. For example, use the [What Is My IP Address](https://www.whatismypublicip.com/) web page. This public IP address assigned by your ISP should be geographically local. It should not be from a public IP address range for a central office or from a cloud-based network security vendor.</span></span>

<span data-ttu-id="f63d0-120">Чтобы выполнить это требование, см. [этап 2](networking-dns-resolution-same-location.md).</span><span class="sxs-lookup"><span data-stu-id="f63d0-120">If needed, [Step 2](networking-dns-resolution-same-location.md) can help you with this requirement.</span></span>

<a name="crit-networking-step3"></a>
## <a name="optional-unneccessary-network-hairpins-are-removed"></a><span data-ttu-id="f63d0-121">Необязательное: вы удалили ненужные развороты пакетов</span><span class="sxs-lookup"><span data-stu-id="f63d0-121">Optional: Unneeded network hairpins are removed</span></span>

<span data-ttu-id="f63d0-p103">Вы изучили развороты пакетов и определили их влияние на производительность во всех своих офисах. Вы удалили ненужные развороты пакетов или вместе со сторонним поставщиком реализовали оптимальный обмен трафиком Microsoft 365 для их сети.</span><span class="sxs-lookup"><span data-stu-id="f63d0-p103">You examined your network hairpins and determined their impact on performance for all of your offices. You removed network hairpins where possible or worked with your third-party network or security provider to implement optimal Microsoft 365 peering for their network.</span></span>

<span data-ttu-id="f63d0-124">Чтобы выполнить это требование, см. [шаг 3](networking-avoid-network-hairpins.md) (при необходимости).</span><span class="sxs-lookup"><span data-stu-id="f63d0-124">If needed, [Step 3](networking-avoid-network-hairpins.md) can help you with this option.</span></span>


<a name="crit-networking-step4"></a>
## <a name="optional-you-have-configured-traffic-bypass-on-your-internet-browsers-and-edge-devices"></a><span data-ttu-id="f63d0-125">Необязательное: вы настроили обход трафика в интернет-браузерах и на пограничных устройствах</span><span class="sxs-lookup"><span data-stu-id="f63d0-125">Optional: You have configured traffic bypass on your Internet browsers and edge devices</span></span>

<span data-ttu-id="f63d0-126">Вы развернули последние файлы PAC в своих локальных интернет-браузерах, чтобы трафик на доменные имена DNS Microsoft 365 обходил прокси-серверы.</span><span class="sxs-lookup"><span data-stu-id="f63d0-126">You deployed the latest PAC files to your on-premises Internet browsers so that traffic to Microsoft 365 DNS domain names bypass proxy servers.</span></span>

<span data-ttu-id="f63d0-127">Вы настроили обход трафика или минимальную обработку трафика в конечные точки Microsoft 365 категорий "Оптимизировать" и "Разрешить" в брандмауэрах, а также на устройствах расшифровки и анализа SSL-трафика и устройствах анализа пакетов.</span><span class="sxs-lookup"><span data-stu-id="f63d0-127">You configured your network perimeter devices—such as firewalls, and SSL Break and Inspect, and packet inspection devices— to use traffic bypass or to minimally process traffic to the Optimize and Allow categories of Microsoft 365 endpoints.</span></span>


### <a name="how-to-test"></a><span data-ttu-id="f63d0-128">Проверка</span><span class="sxs-lookup"><span data-stu-id="f63d0-128">How to test</span></span>

<span data-ttu-id="f63d0-129">С помощью средств ведения журналов на пограничных устройствах убедитесь, что трафик, направляемый в назначения Microsoft 365, не проверяется, не шифруется и не задерживается каким-либо другим способом.</span><span class="sxs-lookup"><span data-stu-id="f63d0-129">Use the logging tools on your network perimeter devices to ensure that traffic to Microsoft 365 destinations isn’t being inspected, decrypted, or otherwise hindered.</span></span>

<span data-ttu-id="f63d0-130">Чтобы выполнить это требование, см. [шаг 4](networking-configure-proxies-firewalls.md) (при необходимости).</span><span class="sxs-lookup"><span data-stu-id="f63d0-130">If needed, [Step 4](networking-configure-proxies-firewalls.md) can help you with this option.</span></span>


<a name="crit-networking-step5"></a>
## <a name="optional-your-clients-and-office-365-applications-are-configured-for-optimal-performance"></a><span data-ttu-id="f63d0-131">Необязательное требование: ваши клиенты и приложения Office 365 настроены для оптимальной производительности</span><span class="sxs-lookup"><span data-stu-id="f63d0-131">Optional: Your clients and Office 365 applications are configured for optimal performance</span></span>

<span data-ttu-id="f63d0-132">Вы оптимизировали параметры протокола TCP на своих клиентских устройствах, а также для служб Exchange Online, Skype для бизнеса Online, SharePoint Online и Project Online.</span><span class="sxs-lookup"><span data-stu-id="f63d0-132">You have optimized the Transmssion Control Protocol (TCP) settings on your client devices and for Exchange Online, Skype for Business Online, SharePoint Online, and Project Online services.</span></span>

<span data-ttu-id="f63d0-133">Чтобы выполнить это требование, см. [шаг 5](networking-optimize-tcp-performance.md) (при необходимости).</span><span class="sxs-lookup"><span data-stu-id="f63d0-133">If needed, [Step 5](networking-optimize-tcp-performance.md) can help you with this option.</span></span>

## <a name="results-and-next-steps"></a><span data-ttu-id="f63d0-134">Результаты и дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="f63d0-134">Results and next steps</span></span>

<span data-ttu-id="f63d0-135">Пользователи интрасети теперь готовы использовать облачные службы Microsoft 365 с помощью эффективного сетевого пути в Интернет.</span><span class="sxs-lookup"><span data-stu-id="f63d0-135">Your intranet users are now ready to consume Microsoft 365 cloud services over an efficient networking path to and across the Internet.</span></span>

|||
|:-------|:-----|
|![Этап 2. Удостоверения](./media/deploy-foundation-infrastructure/identity_icon-small.png)| <span data-ttu-id="f63d0-137">Если вы выполняете этапы полного развертывания Microsoft 365 корпоративный, следующий этап —[удостоверения](identity-infrastructure.md).</span><span class="sxs-lookup"><span data-stu-id="f63d0-137">If you're following the phases for the end-to-end deployment of Microsoft 365 Enterprise, your next phase is [identity](identity-infrastructure.md).</span></span> |
