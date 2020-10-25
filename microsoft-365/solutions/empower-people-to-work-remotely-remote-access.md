---
title: Этап 2. Обеспечение удаленного доступа к локальным приложениям и службам
f1.keywords:
- NOCSH
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- remotework
- m365solution-remotework
- m365solution-scenario
ms.custom: ''
description: Обеспечьте удаленным сотрудникам доступ к локальным ресурсам, одновременно оптимизируя доступ к облачным службам Microsoft 365.
ms.openlocfilehash: 1fbb1cb6ad9817f0e167ae95f9fc113ecdee4221
ms.sourcegitcommit: 554755bc9ce40228ce6e34bde6fc6e226869b6a1
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/22/2020
ms.locfileid: "48681424"
---
# <a name="step-2-provide-remote-access-to-on-premises-apps-and-services"></a><span data-ttu-id="9841c-104">Этап 2.</span><span class="sxs-lookup"><span data-stu-id="9841c-104">Step 2.</span></span> <span data-ttu-id="9841c-105">Обеспечение удаленного доступа к локальным приложениям и службам</span><span class="sxs-lookup"><span data-stu-id="9841c-105">Provide remote access to on-premises apps and services</span></span>

<span data-ttu-id="9841c-106">Если в вашей организации используется VPN-решение для удаленного доступа, как правило, с VPN-серверами на краю сети и VPN-клиентами, установленными на устройствах пользователей, пользователи могут использовать VPN-подключения удаленного доступа для доступа к локальным приложениям и серверам.</span><span class="sxs-lookup"><span data-stu-id="9841c-106">If your organization uses a remote access VPN solution, typically with VPN servers on the edge of your network and VPN clients installed on your users' devices, your users can use remote access VPN connections to access on-premises apps and servers.</span></span> <span data-ttu-id="9841c-107">Однако может потребоваться оптимизировать трафик в облачных службах Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="9841c-107">But you may need to optimize traffic to Microsoft 365 cloud-based services.</span></span>

<span data-ttu-id="9841c-108">Если пользователи не используют VPN-решение, вы можете предоставить доступ с помощью Azure Active Directory (Azure AD) Application Proxy или VPN-подключения типа "точка-сеть" (P2S) в Azure, в зависимости от того, все ли ваши приложения являются веб-приложениями.</span><span class="sxs-lookup"><span data-stu-id="9841c-108">If your users do not use a VPN solution, you can use Azure Active Directory (Azure AD) Application Proxy and Azure Point-to-Site (P2S) VPN to provide access, depending on whether all your apps are web-based.</span></span>

<span data-ttu-id="9841c-109">Ниже приведены основные конфигурации для удаленного доступа:</span><span class="sxs-lookup"><span data-stu-id="9841c-109">Here are the primary configurations for remote access:</span></span>

- <span data-ttu-id="9841c-110">Вы уже используете VPN-решение для удаленного доступа.</span><span class="sxs-lookup"><span data-stu-id="9841c-110">You are already using a remote access VPN solution.</span></span>
- <span data-ttu-id="9841c-111">Вы не используете VPN-решение для удаленного доступа и хотите, чтобы удаленные сотрудники использовали персональные компьютеры.</span><span class="sxs-lookup"><span data-stu-id="9841c-111">You are not using a remote access VPN solution and you want your remote workers to use their personal computers.</span></span>
- <span data-ttu-id="9841c-112">Вы не используете VPN-решение для удаленного доступа, у вас есть гибридное удостоверение, и вам необходим удаленный доступ только к локальным веб-приложениям.</span><span class="sxs-lookup"><span data-stu-id="9841c-112">You are not using a remote access VPN solution, you have hybrid identity, and you need remote access only to on-premises web-based apps.</span></span>
- <span data-ttu-id="9841c-113">Вы не используете VPN-решение для удаленного доступа, и вам необходим доступ к локальным приложениям, некоторые из которых не являются веб-приложениями.</span><span class="sxs-lookup"><span data-stu-id="9841c-113">You are not using a remote access VPN solution and you need access to on-premises apps, some of which are not web-based.</span></span>

<span data-ttu-id="9841c-114">На этой блок-схеме представлены параметры настройки удаленного доступа, рассматриваемые в этой статье.</span><span class="sxs-lookup"><span data-stu-id="9841c-114">See this flowchart for the remote access configuration options discussed in this article.</span></span>

![Блок-схема настройки удаленного доступа](../media/empower-people-to-work-remotely-remote-access/empower-people-to-work-remotely-remote-access-flowchart.png)

<span data-ttu-id="9841c-116">При наличии подключений удаленного доступа можно также использовать [удаленный рабочий стол](https://support.microsoft.com/help/4028379/windows-10-how-to-use-remote-desktop) для подключения пользователей к локальному ПК.</span><span class="sxs-lookup"><span data-stu-id="9841c-116">With remote access connections, you can also use [Remote Desktop](https://support.microsoft.com/help/4028379/windows-10-how-to-use-remote-desktop) to connect your users to an on-premises PC.</span></span> <span data-ttu-id="9841c-117">Например, удаленный сотрудник может использовать удаленный рабочий стол для подключения к ПК в офисе со своего устройства Windows, iOS или Android.</span><span class="sxs-lookup"><span data-stu-id="9841c-117">For example, a remote worker can use Remote Desktop to connect to the PC in their office from their Windows, iOS, or Android device.</span></span> <span data-ttu-id="9841c-118">Выполнив удаленное подключение, он может пользоваться компьютером, как если бы находился перед ним.</span><span class="sxs-lookup"><span data-stu-id="9841c-118">Once they are remotely connected, they can use it as if they were sitting in front of it.</span></span>

## <a name="optimize-performance-for-remote-access-vpn-clients-to-microsoft-365-cloud-services"></a><span data-ttu-id="9841c-119">Оптимизация производительности VPN-клиентов с удаленным доступом для облачных служб Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="9841c-119">Optimize performance for remote access VPN clients to Microsoft 365 cloud services</span></span>

<span data-ttu-id="9841c-120">Если удаленные сотрудники используют традиционный VPN-клиент для получения удаленного доступа к сети организации, убедитесь, что для VPN-клиента поддерживается раздельное туннелирование.</span><span class="sxs-lookup"><span data-stu-id="9841c-120">If your remote workers are using a traditional VPN client to obtain remote access to your organization network, verify that the VPN client has split tunneling support.</span></span>

<span data-ttu-id="9841c-121">Без раздельного туннелирования весь трафик для удаленной работы направляется через VPN-подключение, откуда перенаправляется на пограничные устройства организации, обрабатывается, а затем отправляется в Интернет.</span><span class="sxs-lookup"><span data-stu-id="9841c-121">Without split tunneling, all of your remote work traffic gets sent across the VPN connection, where it must be forwarded to your organization’s edge devices, get processed, and then sent on the Internet.</span></span>

![Сетевой трафик из VPN-клиентов без туннелирования](../media/empower-people-to-work-remotely-remote-access/empower-people-to-work-remotely-remote-access-before-tunneling.png)

<span data-ttu-id="9841c-123">Трафик Microsoft 365 в организации должен быть непрямым, для чего может использоваться перенаправление на точку входа в сеть Microsoft далеко от физического расположения VPN-клиента.</span><span class="sxs-lookup"><span data-stu-id="9841c-123">Microsoft 365 traffic must take an indirect route through your organization, which could be the forwarded to a Microsoft network entry point far away from the VPN client’s physical location.</span></span> <span data-ttu-id="9841c-124">Использование непрямого пути приводит к задержке сетевого трафика и снижению общей производительности.</span><span class="sxs-lookup"><span data-stu-id="9841c-124">This indirect path adds latency to the network traffic and decreases overall performance.</span></span> 

<span data-ttu-id="9841c-125">При использовании раздельного туннелирования в настройках VPN-клиента можно исключить передачу определенных типов трафика через VPN-подключение в сеть организации.</span><span class="sxs-lookup"><span data-stu-id="9841c-125">With split tunneling, you can configure your VPN client to exclude specific types of traffic from being sent over the VPN connection to the organization network.</span></span>

<span data-ttu-id="9841c-126">Чтобы оптимизировать доступ к облачным ресурсам Microsoft 365, в настройках VPN-клиентов с раздельным туннелированием исключите трафик через VPN-подключение к конечным точкам Microsoft 365 категории **оптимизации**.</span><span class="sxs-lookup"><span data-stu-id="9841c-126">To optimize access to Microsoft 365 cloud resources, configure your split tunneling VPN clients to exclude traffic to the **Optimize** category Microsoft 365 endpoints over the VPN connection.</span></span> <span data-ttu-id="9841c-127">Дополнительные сведения см. в статье [Категории конечных точек Office 365](https://docs.microsoft.com/microsoft-365/enterprise/microsoft-365-network-connectivity-principles#new-office-365-endpoint-categories).</span><span class="sxs-lookup"><span data-stu-id="9841c-127">For more information, see [Office 365 endpoint categories](https://docs.microsoft.com/microsoft-365/enterprise/microsoft-365-network-connectivity-principles#new-office-365-endpoint-categories).</span></span> <span data-ttu-id="9841c-128">См. [список](https://docs.microsoft.com/microsoft-365/enterprise/urls-and-ip-address-ranges) конечных точек категории оптимизации.</span><span class="sxs-lookup"><span data-stu-id="9841c-128">See [this list](https://docs.microsoft.com/microsoft-365/enterprise/urls-and-ip-address-ranges) of Optimize category endpoints.</span></span>

<span data-ttu-id="9841c-129">Ниже приведен полученный в результате поток трафика, в котором большая часть трафика к облачным приложениям Microsoft 365 обходит VPN-подключение.</span><span class="sxs-lookup"><span data-stu-id="9841c-129">Here is the resulting traffic flow, in which most of the traffic to Microsoft 365 cloud apps bypass the VPN connection.</span></span>

![Сетевой трафик из VPN-клиентов с использованием туннелирования](../media/empower-people-to-work-remotely-remote-access/empower-people-to-work-remotely-remote-access-after-tunneling.png)

<span data-ttu-id="9841c-131">Эта возможность позволяет VPN-клиенту отправлять и получать необходимый трафик облачных служб Microsoft 365 непосредственно через Интернет в ближайшей точке входа в сеть Microsoft.</span><span class="sxs-lookup"><span data-stu-id="9841c-131">This allows the VPN client to send and receive crucial Microsoft 365 cloud service traffic directly over the Internet and to the nearest entry point into the Microsoft network.</span></span>

<span data-ttu-id="9841c-132">Дополнительные сведения и инструкции см. в статье [Оптимизация подключения Office 365 для удаленных пользователей с помощью раздельного VPN-туннелирования](https://docs.microsoft.com/microsoft-365/enterprise/microsoft-365-vpn-split-tunnel??).</span><span class="sxs-lookup"><span data-stu-id="9841c-132">For more information and guidance, see [Optimize Office 365 connectivity for remote users using VPN split tunneling](https://docs.microsoft.com/microsoft-365/enterprise/microsoft-365-vpn-split-tunnel??).</span></span>

## <a name="deploy-remote-access-when-all-your-apps-are-web-apps-and-you-have-hybrid-identity"></a><span data-ttu-id="9841c-133">Развертывание удаленного доступа при наличии гибридного удостоверения, если все приложения являются веб-приложениями</span><span class="sxs-lookup"><span data-stu-id="9841c-133">Deploy remote access when all your apps are web apps and you have hybrid identity</span></span>

<span data-ttu-id="9841c-134">Если удаленные сотрудники не используют традиционный VPN-клиент, а локальные учетные записи и группы синхронизированы с Azure AD, можно использовать Azure AD Application Proxy, чтобы предоставить безопасный удаленный доступ к веб-приложениям, размещенным на локальных серверах.</span><span class="sxs-lookup"><span data-stu-id="9841c-134">If your remote workers are not using a traditional VPN client and your on-premises user accounts and groups are synchronized with Azure AD, you can use Azure AD Application Proxy to provide secure remote access for web-based applications hosted on on-premises servers.</span></span> <span data-ttu-id="9841c-135">Веб-приложения включают сайты SharePoint Server, серверы Outlook Web Access и другие бизнес-приложения.</span><span class="sxs-lookup"><span data-stu-id="9841c-135">Web-based applications include SharePoint Server sites, Outlook Web Access servers, or any other web-based line of business applications.</span></span> 

<span data-ttu-id="9841c-136">Ниже описаны компоненты Azure AD Application Proxy.</span><span class="sxs-lookup"><span data-stu-id="9841c-136">Here are the components of Azure AD Application Proxy.</span></span>

![Компоненты Azure AD Application Proxy](../media/empower-people-to-work-remotely-remote-access/empower-people-to-work-remotely-remote-access-application-proxy.png)

<span data-ttu-id="9841c-138">Дополнительные сведения см. в [обзоре Azure AD Application Proxy](https://docs.microsoft.com/azure/active-directory/manage-apps/application-proxy).</span><span class="sxs-lookup"><span data-stu-id="9841c-138">For more information, see this [overview of Azure AD Application Proxy](https://docs.microsoft.com/azure/active-directory/manage-apps/application-proxy).</span></span>

>[!Note]
><span data-ttu-id="9841c-139">Прокси приложения Azure AD не входит в подписку на Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="9841c-139">Azure AD Application Proxy is not included with a Microsoft 365 subscription.</span></span> <span data-ttu-id="9841c-140">Вам следует оплачивать использование с отдельной подпиской Azure.</span><span class="sxs-lookup"><span data-stu-id="9841c-140">You must pay for usage with a separate Azure subscription.</span></span>
>

## <a name="deploy-remote-access-when-not-all-your-apps-are-web-apps"></a><span data-ttu-id="9841c-141">Развертывание удаленного доступа, если не все приложения являются веб-приложениями</span><span class="sxs-lookup"><span data-stu-id="9841c-141">Deploy remote access when not all your apps are web apps</span></span>

<span data-ttu-id="9841c-142">Если удаленные сотрудники не используют традиционный VPN-клиент и у вас есть приложения, которые не являются веб-приложениями, можно использовать VPN-подключение типа "точка-сеть" (P2S) в Azure.</span><span class="sxs-lookup"><span data-stu-id="9841c-142">If your remote workers are not using a traditional VPN client and you have apps that are not web-based, you can use an Azure Point-to-Site (P2S) VPN.</span></span>

<span data-ttu-id="9841c-143">При использовании VPN-подключения P2S создается безопасное подключение с устройства удаленного сотрудника к сети организации через виртуальную сеть Azure.</span><span class="sxs-lookup"><span data-stu-id="9841c-143">A P2S VPN connection creates a secure connection from a remote worker’s device to your organization network through an Azure virtual network.</span></span> 

![Компоненты VPN-подключения P2S в Azure](../media/empower-people-to-work-remotely-remote-access/empower-people-to-work-remotely-remote-access-p2s-vpn.png)

<span data-ttu-id="9841c-145">Дополнительные сведения см. в [обзоре VPN-подключения P2S](https://docs.microsoft.com/azure/vpn-gateway/point-to-site-about).</span><span class="sxs-lookup"><span data-stu-id="9841c-145">For more information, see this [overview of P2S VPN](https://docs.microsoft.com/azure/vpn-gateway/point-to-site-about).</span></span>

>[!Note]
><span data-ttu-id="9841c-146">Azure P2S VPN не входит в подписку на Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="9841c-146">Azure P2S VPN is not included with a Microsoft 365 subscription.</span></span> <span data-ttu-id="9841c-147">Вам следует оплачивать использование с отдельной подпиской Azure.</span><span class="sxs-lookup"><span data-stu-id="9841c-147">You must pay for usage with a separate Azure subscription.</span></span>
>

## <a name="deploy-windows-virtual-desktop-to-provide-remote-access-for-remote-workers-using-personal-devices"></a><span data-ttu-id="9841c-148">Развертывание Виртуального рабочего стола Windows для предоставления удаленного доступа удаленным сотрудникам, использующим личные устройства</span><span class="sxs-lookup"><span data-stu-id="9841c-148">Deploy Windows Virtual Desktop to provide remote access for remote workers using personal devices</span></span> 

<span data-ttu-id="9841c-149">В целях поддержки удаленных сотрудников, использующих только личные и неуправляемые устройства, используйте Виртуальный рабочий стол Windows в Azure, чтобы создавать и назначать виртуальные рабочие столы пользователям для работы из дома.</span><span class="sxs-lookup"><span data-stu-id="9841c-149">To support remote workers who can only use their personal and unmanaged devices, use Windows Virtual Desktop in Azure to create and allocate virtual desktops for your users to use from home.</span></span> <span data-ttu-id="9841c-150">Виртуализированные ПК могут работать так же, как компьютеры, подключенные к сети организации.</span><span class="sxs-lookup"><span data-stu-id="9841c-150">Virtualized PCs can act just like PCs connected to your organization network.</span></span>

![Компоненты виртуального рабочего стола для Azure Windows](../media/empower-people-to-work-remotely-remote-access/empower-people-to-work-remotely-remote-access-windows-virtual-desktop.png)

<span data-ttu-id="9841c-152">Дополнительные сведения см. в [обзоре Виртуального рабочего стола Windows](https://docs.microsoft.com/azure/virtual-desktop/overview).</span><span class="sxs-lookup"><span data-stu-id="9841c-152">For more information, see this [overview of Windows Virtual Desktop](https://docs.microsoft.com/azure/virtual-desktop/overview).</span></span> 

>[!Note]
><span data-ttu-id="9841c-153">Виртуальный рабочий стол Windows не входит в подписку на Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="9841c-153">Windows Virtual Desktop is not included with a Microsoft 365 subscription.</span></span> <span data-ttu-id="9841c-154">Вам следует оплачивать использование с отдельной подпиской Azure.</span><span class="sxs-lookup"><span data-stu-id="9841c-154">You must pay for usage with a separate Azure subscription.</span></span>
>

## <a name="protect-your-remote-desktop-services-connections-with-the-remote-desktop-services-gateway"></a><span data-ttu-id="9841c-155">Защитите подключения к службам удаленных рабочих столов с помощью шлюза служб удаленных рабочих столов</span><span class="sxs-lookup"><span data-stu-id="9841c-155">Protect your Remote Desktop Services connections with the Remote Desktop Services Gateway</span></span>

<span data-ttu-id="9841c-156">Если вы используете службы удаленных рабочих столов (RDS), чтобы разрешить сотрудникам подключаться к компьютерам под управлением Windows в локальной сети, используйте шлюз служб удаленных рабочих столов (Майкрософт) в сети периметра.</span><span class="sxs-lookup"><span data-stu-id="9841c-156">If you are using Remote Desktop Services (RDS) to allow employees to connect into Windows-based computers on your on-premises network, you should use a Microsoft Remote Desktop Services gateway in your edge network.</span></span> <span data-ttu-id="9841c-157">Шлюз использует протокол SSL для шифрования сообщений и предотвращает непосредственное подключение локального компьютера, на котором размещены службы RDS, к Интернету.</span><span class="sxs-lookup"><span data-stu-id="9841c-157">The gateway uses Secure Sockets Layer (SSL) to encrypt communications and prevents the on-premises computer hosting RDS from being directly exposed to the Internet.</span></span>

![Подключения к службам удаленных рабочих столов с помощью шлюза служб удаленных рабочих столов](../media/empower-people-to-work-remotely-remote-access/empower-people-to-work-remotely-remote-access-remote-desktop.png)

<span data-ttu-id="9841c-159">Дополнительные сведения см. в [этой статье](https://www.microsoft.com/security/blog/2020/04/16/security-guidance-remote-desktop-adoption/).</span><span class="sxs-lookup"><span data-stu-id="9841c-159">See [this article](https://www.microsoft.com/security/blog/2020/04/16/security-guidance-remote-desktop-adoption/) for more information.</span></span>

## <a name="admin-technical-resources-for-remote-access"></a><span data-ttu-id="9841c-160">Технические ресурсы администраторов для предоставления удаленного доступа</span><span class="sxs-lookup"><span data-stu-id="9841c-160">Admin technical resources for remote access</span></span>

- <span data-ttu-id="9841c-161">[Быстрая оптимизация трафика Office 365 для удаленных сотрудников и снижение нагрузки на инфраструктуру](https://techcommunity.microsoft.com/t5/office-365-blog/how-to-quickly-optimize-office-365-traffic-for-remote-staff-amp/ba-p/1214571).</span><span class="sxs-lookup"><span data-stu-id="9841c-161">[How to quickly optimize Office 365 traffic for remote staff & reduce the load on your infrastructure](https://techcommunity.microsoft.com/t5/office-365-blog/how-to-quickly-optimize-office-365-traffic-for-remote-staff-amp/ba-p/1214571)</span></span>
- [<span data-ttu-id="9841c-162">Оптимизация подключения Office 365 для удаленных пользователей с использованием раздельного VPN-туннелирования</span><span class="sxs-lookup"><span data-stu-id="9841c-162">Optimize Office 365 connectivity for remote users using VPN split tunneling</span></span>](https://docs.microsoft.com/microsoft-365/enterprise/microsoft-365-vpn-split-tunnel?)

## <a name="results-of-step-2"></a><span data-ttu-id="9841c-163">Результаты этапа 2</span><span class="sxs-lookup"><span data-stu-id="9841c-163">Results of Step 2</span></span>

<span data-ttu-id="9841c-164">После развертывания решения для удаленного доступа для удаленных сотрудников:</span><span class="sxs-lookup"><span data-stu-id="9841c-164">After deployment of a remote access solution for your remote workers:</span></span>

| <span data-ttu-id="9841c-165">Конфигурация удаленного доступа</span><span class="sxs-lookup"><span data-stu-id="9841c-165">Remote access configuration</span></span> | <span data-ttu-id="9841c-166">Результаты</span><span class="sxs-lookup"><span data-stu-id="9841c-166">Results</span></span> |
|:-------|:-----|
| <span data-ttu-id="9841c-167">Используется VPN-решение для удаленного доступа</span><span class="sxs-lookup"><span data-stu-id="9841c-167">A remote access VPN solution is in place</span></span> | <span data-ttu-id="9841c-168">Для VPN-клиента с удаленным доступом настроено раздельное туннелирование и конечные точки Microsoft 365 категории оптимизации.</span><span class="sxs-lookup"><span data-stu-id="9841c-168">You have configured your remote access VPN client for split tunneling and for the Optimize category of Microsoft 365 endpoints.</span></span> |
| <span data-ttu-id="9841c-169">VPN-решение для удаленного доступа не используется, необходим только удаленный доступ к локальным веб-приложениям</span><span class="sxs-lookup"><span data-stu-id="9841c-169">No remote access VPN solution and you need remote access only to on-premises web-based apps</span></span> | <span data-ttu-id="9841c-170">Настроена функция Azure Application Proxy.</span><span class="sxs-lookup"><span data-stu-id="9841c-170">You have configured Azure Application Proxy.</span></span> |
| <span data-ttu-id="9841c-171">VPN-решение для удаленного доступа не используется, необходим доступ к локальным приложениям, некоторые из которых не являются веб-приложениями</span><span class="sxs-lookup"><span data-stu-id="9841c-171">No remote access VPN solution and you need access to on-premises apps, some of which are not web-based</span></span> | <span data-ttu-id="9841c-172">Настроено VPN-подключение P2S в Azure.</span><span class="sxs-lookup"><span data-stu-id="9841c-172">You have configured Azure P2S VPN.</span></span> |
| <span data-ttu-id="9841c-173">Удаленные сотрудники используют личные устройства из дома</span><span class="sxs-lookup"><span data-stu-id="9841c-173">Remote workers are using their personal devices from home</span></span> | <span data-ttu-id="9841c-174">Настроен Виртуальный рабочий стол Windows.</span><span class="sxs-lookup"><span data-stu-id="9841c-174">You have configured Windows Virtual Desktop.</span></span> |
| <span data-ttu-id="9841c-175">Удаленные работники используют подключения RDS к локальным системам.</span><span class="sxs-lookup"><span data-stu-id="9841c-175">Remote workers are using RDS connections to on-premises systems</span></span> | <span data-ttu-id="9841c-176">Вы развернули шлюз служб удаленных рабочих столов в сети периметра.</span><span class="sxs-lookup"><span data-stu-id="9841c-176">You have deployed a Remote Desktop Services gateway in your edge network.</span></span> |
|||

## <a name="next-step"></a><span data-ttu-id="9841c-177">Следующий этап</span><span class="sxs-lookup"><span data-stu-id="9841c-177">Next step</span></span>

<span data-ttu-id="9841c-178">[![Этап 3. Развертывание служб безопасности и соответствия требованиям Microsoft 365](../media/empower-people-to-work-remotely/remote-workers-step-grid-3.png)](empower-people-to-work-remotely-security-compliance.md)</span><span class="sxs-lookup"><span data-stu-id="9841c-178">[![Step 3: Deploy Microsoft 365 security and compliance services](../media/empower-people-to-work-remotely/remote-workers-step-grid-3.png)](empower-people-to-work-remotely-security-compliance.md)</span></span>

<span data-ttu-id="9841c-179">Перейдите к [Этапу 3](empower-people-to-work-remotely-security-compliance.md), чтобы развернуть службы безопасности и соответствия требованиям Microsoft 365 для защиты приложений, данных и устройств.</span><span class="sxs-lookup"><span data-stu-id="9841c-179">Continue with [Step 3](empower-people-to-work-remotely-security-compliance.md) to deploy Microsoft 365 security and compliance services to protect your apps, data, and devices.</span></span>

