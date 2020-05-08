---
title: Этап 2. Обеспечение удаленного доступа к локальным приложениям и службам
f1.keywords:
- NOCSH
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 05/01/2020
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- remotework
- M365solutions
ms.custom: ''
description: Обеспечьте удаленным сотрудникам доступ к локальным ресурсам, одновременно оптимизируя доступ к облачным службам Microsoft 365.
ms.openlocfilehash: 363f2a5edb43d294be5a8ecfe0fd02964dd8b945
ms.sourcegitcommit: 9c828bc27cd73a1bb85e9fe38d818190025ebb3f
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2020
ms.locfileid: "44160754"
---
# <a name="step-2-provide-remote-access-to-on-premises-apps-and-services"></a><span data-ttu-id="e7560-104">Этап 2.</span><span class="sxs-lookup"><span data-stu-id="e7560-104">Step 2.</span></span> <span data-ttu-id="e7560-105">Обеспечение удаленного доступа к локальным приложениям и службам</span><span class="sxs-lookup"><span data-stu-id="e7560-105">Provide remote access to on-premises apps and services</span></span>

<span data-ttu-id="e7560-106">Если в вашей организации используется VPN-решение для удаленного доступа, как правило, с VPN-серверами на краю сети и VPN-клиентами, установленными на устройствах пользователей, пользователи могут использовать VPN-подключения удаленного доступа для доступа к локальным приложениям и серверам.</span><span class="sxs-lookup"><span data-stu-id="e7560-106">If your organization uses a remote access VPN solution, typically with VPN servers on the edge of your network and VPN clients installed on your users' devices, your users can use remote access VPN connections to access on-premises apps and servers.</span></span> <span data-ttu-id="e7560-107">Однако может потребоваться оптимизировать трафик в облачных службах Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e7560-107">But you may need to optimize traffic to Microsoft 365 cloud-based services.</span></span>

<span data-ttu-id="e7560-108">Если пользователи не используют VPN-решение, вы можете предоставить доступ с помощью Azure Active Directory (Azure AD) Application Proxy или VPN-подключения типа "точка-сеть" (P2S) в Azure, в зависимости от того, все ли ваши приложения являются веб-приложениями.</span><span class="sxs-lookup"><span data-stu-id="e7560-108">If your users do not use a VPN solution, you can use Azure Active Directory (Azure AD) Application Proxy and Azure Point-to-Site (P2S) VPN to provide access, depending on whether all your apps are web-based.</span></span>

<span data-ttu-id="e7560-109">Существует три основных конфигурации:</span><span class="sxs-lookup"><span data-stu-id="e7560-109">There are three primary configurations:</span></span>

1. <span data-ttu-id="e7560-110">Вы уже используете VPN-решение для удаленного доступа.</span><span class="sxs-lookup"><span data-stu-id="e7560-110">You are already using a remote access VPN solution.</span></span>
2. <span data-ttu-id="e7560-111">Вы не используете VPN-решение для удаленного доступа, у вас есть гибридное удостоверение, и вам необходим удаленный доступ только к локальным веб-приложениям.</span><span class="sxs-lookup"><span data-stu-id="e7560-111">You are not using a remote access VPN solution, you have hybrid identity, and you need remote access only to on-premises web-based apps.</span></span>
3. <span data-ttu-id="e7560-112">Вы не используете VPN-решение для удаленного доступа, и вам необходим доступ к локальным приложениям, некоторые из которых не являются веб-приложениями.</span><span class="sxs-lookup"><span data-stu-id="e7560-112">You are not using a remote access VPN solution and you need access to on-premises apps, some of which are not web-based.</span></span>

<span data-ttu-id="e7560-113">На этой блок-схеме представлены параметры настройки удаленного доступа, рассматриваемые в этой статье.</span><span class="sxs-lookup"><span data-stu-id="e7560-113">See this flowchart for the remote access configuration options discussed in this article.</span></span>

![Блок-схема настройки удаленного доступа](../media/empower-people-to-work-remotely-remote-access/empower-people-to-work-remotely-remote-access-flowchart.png)

<span data-ttu-id="e7560-115">При наличии подключений удаленного доступа можно также использовать [удаленный рабочий стол](https://support.microsoft.com/help/4028379/windows-10-how-to-use-remote-desktop) для подключения пользователей к локальному ПК.</span><span class="sxs-lookup"><span data-stu-id="e7560-115">With remote access connections, you can also use [Remote Desktop](https://support.microsoft.com/help/4028379/windows-10-how-to-use-remote-desktop) to connect your users to an on-premises PC.</span></span> <span data-ttu-id="e7560-116">Например, удаленный сотрудник может использовать удаленный рабочий стол для подключения к ПК в офисе с устройства Windows, iOS или Android.</span><span class="sxs-lookup"><span data-stu-id="e7560-116">For example, a remote worker can use Remote Desktop to connect to the PC in their office from their Windows, iOS or Android device.</span></span> <span data-ttu-id="e7560-117">Выполнив удаленное подключение, он может пользоваться компьютером, как если бы находился перед ним.</span><span class="sxs-lookup"><span data-stu-id="e7560-117">Once they are remotely connected, they can use it as if they were sitting in front of it.</span></span>

## <a name="optimize-performance-for-remote-access-vpn-clients-to-microsoft-365-cloud-services"></a><span data-ttu-id="e7560-118">Оптимизация производительности VPN-клиентов с удаленным доступом для облачных служб Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="e7560-118">Optimize performance for remote access VPN clients to Microsoft 365 cloud services</span></span>

<span data-ttu-id="e7560-119">Если удаленные сотрудники используют традиционный VPN-клиент для получения удаленного доступа к сети организации, убедитесь, что для VPN-клиента поддерживается раздельное туннелирование.</span><span class="sxs-lookup"><span data-stu-id="e7560-119">If your remote workers are using a traditional VPN client to obtain remote access to your organization network, verify that the VPN client has split tunneling support.</span></span>

<span data-ttu-id="e7560-120">Без раздельного туннелирования весь трафик для удаленной работы направляется через VPN-подключение, откуда перенаправляется на пограничные устройства организации, обрабатывается, а затем отправляется в Интернет.</span><span class="sxs-lookup"><span data-stu-id="e7560-120">Without split tunneling, all of your remote work traffic gets sent across the VPN connection, where it must be forwarded to your organization’s edge devices, get processed, and then sent on the Internet.</span></span>

![Сетевой трафик из VPN-клиентов без туннелирования](../media/empower-people-to-work-remotely-remote-access/empower-people-to-work-remotely-remote-access-before-tunneling.png)

<span data-ttu-id="e7560-122">Трафик Microsoft 365 в организации должен быть непрямым, для чего может использоваться перенаправление на точку входа в сеть Microsoft далеко от физического расположения VPN-клиента.</span><span class="sxs-lookup"><span data-stu-id="e7560-122">Microsoft 365 traffic must take an indirect route through your organization, which could be the forwarded to a Microsoft network entry point far away from the VPN client’s physical location.</span></span> <span data-ttu-id="e7560-123">Использование непрямого пути приводит к задержке сетевого трафика и снижению общей производительности.</span><span class="sxs-lookup"><span data-stu-id="e7560-123">This indirect path adds latency to the network traffic and decreases overall performance.</span></span> 

<span data-ttu-id="e7560-124">При использовании раздельного туннелирования в настройках VPN-клиента можно исключить передачу определенных типов трафика через VPN-подключение в сеть организации.</span><span class="sxs-lookup"><span data-stu-id="e7560-124">With split tunneling, you can configure your VPN client to exclude specific types of traffic from being sent over the VPN connection to the organization network.</span></span>

<span data-ttu-id="e7560-125">Чтобы оптимизировать доступ к облачным ресурсам Microsoft 365, в настройках VPN-клиентов с раздельным туннелированием исключите трафик через VPN-подключение к конечным точкам Microsoft 365 категории **оптимизации**.</span><span class="sxs-lookup"><span data-stu-id="e7560-125">To optimize access to Microsoft 365 cloud resources, configure your split tunneling VPN clients to exclude traffic to the **Optimize** category Microsoft 365 endpoints over the VPN connection.</span></span> <span data-ttu-id="e7560-126">Дополнительные сведения см. в статье [Категории конечных точек Office 365](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles#new-office-365-endpoint-categories).</span><span class="sxs-lookup"><span data-stu-id="e7560-126">For more information, see [Office 365 endpoint categories](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles#new-office-365-endpoint-categories).</span></span> <span data-ttu-id="e7560-127">См. список конечных точек категории оптимизации [здесь](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges).</span><span class="sxs-lookup"><span data-stu-id="e7560-127">See the list of Optimize category endpoints [here](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges).</span></span>

![Сетевой трафик из VPN-клиентов с использованием туннелирования](../media/empower-people-to-work-remotely-remote-access/empower-people-to-work-remotely-remote-access-after-tunneling.png)

<span data-ttu-id="e7560-129">Эта возможность позволяет VPN-клиенту отправлять и получать необходимый трафик облачных служб Microsoft 365 непосредственно через Интернет в ближайшей точке входа в сеть Microsoft.</span><span class="sxs-lookup"><span data-stu-id="e7560-129">This allows the VPN client to send and receive crucial Microsoft 365 cloud service traffic directly over the Internet and to the nearest entry point into the Microsoft network.</span></span>

<span data-ttu-id="e7560-130">Дополнительные сведения и инструкции см. в статье [Оптимизация подключения Office 365 для удаленных пользователей с помощью раздельного VPN-туннелирования](https://docs.microsoft.com/office365/enterprise/office-365-vpn-split-tunnel).</span><span class="sxs-lookup"><span data-stu-id="e7560-130">For more information and guidance, see [Optimize Office 365 connectivity for remote users using VPN split tunneling](https://docs.microsoft.com/office365/enterprise/office-365-vpn-split-tunnel).</span></span>

## <a name="deploy-remote-access-when-all-your-apps-are-web-apps-and-you-have-hybrid-identity"></a><span data-ttu-id="e7560-131">Развертывание удаленного доступа при наличии гибридного удостоверения, если все приложения являются веб-приложениями</span><span class="sxs-lookup"><span data-stu-id="e7560-131">Deploy remote access when all your apps are web apps and you have hybrid identity</span></span>

<span data-ttu-id="e7560-132">Если удаленные сотрудники не используют традиционный VPN-клиент, а локальные учетные записи и группы синхронизированы с Azure AD, можно использовать Azure AD Application Proxy, чтобы предоставить безопасный удаленный доступ к веб-приложениям, размещенным на серверах интрасети.</span><span class="sxs-lookup"><span data-stu-id="e7560-132">If your remote workers are not using a traditional VPN client and your on-premises user accounts and groups are synchronized with Azure AD, you can use Azure AD Application Proxy to provide secure remote access for web-based applications hosted on intranet servers.</span></span> <span data-ttu-id="e7560-133">Веб-приложения включают сайты SharePoint, серверы Outlook Web Access и любые другие бизнес-приложения.</span><span class="sxs-lookup"><span data-stu-id="e7560-133">Web-based applications include SharePoint sites, Outlook Web Access servers, or any other web-based line of business applications.</span></span> 

<span data-ttu-id="e7560-134">Ниже описаны компоненты Azure AD Application Proxy.</span><span class="sxs-lookup"><span data-stu-id="e7560-134">Here are the components of Azure AD Application Proxy.</span></span>

![Компоненты Azure AD Application Proxy](../media/empower-people-to-work-remotely-remote-access/empower-people-to-work-remotely-remote-access-application-proxy.png)

<span data-ttu-id="e7560-136">Дополнительные сведения см. в [обзоре Azure AD Application Proxy](https://docs.microsoft.com/azure/active-directory/manage-apps/application-proxy).</span><span class="sxs-lookup"><span data-stu-id="e7560-136">For more information, see this [overview of Azure AD Application Proxy](https://docs.microsoft.com/azure/active-directory/manage-apps/application-proxy).</span></span>

## <a name="deploy-remote-access-when-not-all-your-apps-are-web-apps"></a><span data-ttu-id="e7560-137">Развертывание удаленного доступа, если не все приложения являются веб-приложениями</span><span class="sxs-lookup"><span data-stu-id="e7560-137">Deploy remote access when not all your apps are web apps</span></span>

<span data-ttu-id="e7560-138">Если удаленные сотрудники не используют традиционный VPN-клиент и некоторые из ваших приложений не являются веб-приложениями, можно использовать VPN-подключение типа "точка-сеть" (P2S) в Azure.</span><span class="sxs-lookup"><span data-stu-id="e7560-138">If your remote workers are not using a traditional VPN client and any of your apps are not web-based, you can use an Azure Point-to-Site (P2S) VPN.</span></span>

<span data-ttu-id="e7560-139">При использовании VPN-подключения P2S создается безопасное подключение с устройства удаленного сотрудника к сети организации через виртуальную сеть Azure.</span><span class="sxs-lookup"><span data-stu-id="e7560-139">A P2S VPN connection creates a secure connection from a remote worker’s device to your organization network through an Azure virtual network.</span></span> 

![Компоненты VPN-подключения P2S в Azure](../media/empower-people-to-work-remotely-remote-access/empower-people-to-work-remotely-remote-access-p2s-vpn.png)

<span data-ttu-id="e7560-141">Дополнительные сведения см. в [обзоре VPN-подключения P2S](https://docs.microsoft.com/azure/vpn-gateway/point-to-site-about).</span><span class="sxs-lookup"><span data-stu-id="e7560-141">For more information, see this [overview of P2S VPN](https://docs.microsoft.com/azure/vpn-gateway/point-to-site-about).</span></span>

## <a name="deploy-windows-virtual-desktop-to-provide-remote-access-for-remote-workers-using-personal-devices"></a><span data-ttu-id="e7560-142">Развертывание Виртуального рабочего стола Windows для предоставления удаленного доступа удаленным сотрудникам, использующим личные устройства</span><span class="sxs-lookup"><span data-stu-id="e7560-142">Deploy Windows Virtual Desktop to provide remote access for remote workers using personal devices</span></span> 

<span data-ttu-id="e7560-143">В целях поддержки удаленных сотрудников, использующих только личные и неуправляемые устройства, используйте Виртуальный рабочий стол Windows в Azure, чтобы создавать и назначать виртуальные рабочие столы пользователям для работы из дома.</span><span class="sxs-lookup"><span data-stu-id="e7560-143">To support remote workers who can only use their personal and unmanaged devices, use Windows Virtual Desktop in Azure to create and allocate virtual desktops for your users to use from home.</span></span>

<span data-ttu-id="e7560-144">Виртуализированные ПК могут работать так же, как компьютеры, подключенные к сети организации.</span><span class="sxs-lookup"><span data-stu-id="e7560-144">Virtualized PCs can act just like PCs connected to your organization network.</span></span>

<span data-ttu-id="e7560-145">Дополнительные сведения см. в [обзоре Виртуального рабочего стола Windows](https://docs.microsoft.com/azure/virtual-desktop/overview).</span><span class="sxs-lookup"><span data-stu-id="e7560-145">For more information, see [this overview of Windows Virtual Desktop](https://docs.microsoft.com/azure/virtual-desktop/overview).</span></span>

## <a name="admin-technical-resources-for-remote-access"></a><span data-ttu-id="e7560-146">Технические ресурсы администраторов для предоставления удаленного доступа</span><span class="sxs-lookup"><span data-stu-id="e7560-146">Admin technical resources for remote access</span></span>

- <span data-ttu-id="e7560-147">[Быстрая оптимизация трафика Office 365 для удаленных сотрудников и снижение нагрузки на инфраструктуру](https://techcommunity.microsoft.com/t5/office-365-blog/how-to-quickly-optimize-office-365-traffic-for-remote-staff-amp/ba-p/1214571).</span><span class="sxs-lookup"><span data-stu-id="e7560-147">[How to quickly optimize Office 365 traffic for remote staff & reduce the load on your infrastructure](https://techcommunity.microsoft.com/t5/office-365-blog/how-to-quickly-optimize-office-365-traffic-for-remote-staff-amp/ba-p/1214571)</span></span>
- [<span data-ttu-id="e7560-148">Оптимизация подключения Office 365 для удаленных пользователей с использованием раздельного VPN-туннелирования</span><span class="sxs-lookup"><span data-stu-id="e7560-148">Optimize Office 365 connectivity for remote users using VPN split tunneling</span></span>](https://docs.microsoft.com/office365/enterprise/office-365-vpn-split-tunnel)

## <a name="results-of-step-2"></a><span data-ttu-id="e7560-149">Результаты этапа 2</span><span class="sxs-lookup"><span data-stu-id="e7560-149">Results of Step 2</span></span>

<span data-ttu-id="e7560-150">После развертывания решения для удаленного доступа для удаленных сотрудников:</span><span class="sxs-lookup"><span data-stu-id="e7560-150">After deployment of a remote access solution for your remote workers:</span></span>

| <span data-ttu-id="e7560-151">Конфигурация удаленного доступа</span><span class="sxs-lookup"><span data-stu-id="e7560-151">Remote access configuration</span></span> | <span data-ttu-id="e7560-152">Результаты</span><span class="sxs-lookup"><span data-stu-id="e7560-152">Results</span></span> |
|:-------|:-----|
| <span data-ttu-id="e7560-153">Используется VPN-решение для удаленного доступа</span><span class="sxs-lookup"><span data-stu-id="e7560-153">A remote access VPN solution is in place</span></span> | <span data-ttu-id="e7560-154">Для VPN-клиента с удаленным доступом настроено раздельное туннелирование и конечные точки Microsoft 365 категории оптимизации.</span><span class="sxs-lookup"><span data-stu-id="e7560-154">You have configured your remote access VPN client for split tunneling and for the Optimize category of Microsoft 365 endpoints.</span></span> |
| <span data-ttu-id="e7560-155">VPN-решение для удаленного доступа не используется, необходим только удаленный доступ к локальным веб-приложениям</span><span class="sxs-lookup"><span data-stu-id="e7560-155">No remote access VPN solution and you need remote access only to on-premises web-based apps</span></span> | <span data-ttu-id="e7560-156">Настроена функция Azure Application Proxy.</span><span class="sxs-lookup"><span data-stu-id="e7560-156">You have configured Azure Application Proxy.</span></span> |
| <span data-ttu-id="e7560-157">VPN-решение для удаленного доступа не используется, необходим доступ к локальным приложениям, некоторые из которых не являются веб-приложениями</span><span class="sxs-lookup"><span data-stu-id="e7560-157">No remote access VPN solution and you need access to on-premises apps, some of which are not web-based</span></span> | <span data-ttu-id="e7560-158">Настроено VPN-подключение P2S в Azure.</span><span class="sxs-lookup"><span data-stu-id="e7560-158">You have configured Azure P2S VPN.</span></span> |
| <span data-ttu-id="e7560-159">Удаленные сотрудники используют личные устройства из дома</span><span class="sxs-lookup"><span data-stu-id="e7560-159">Remote workers are using their personal devices from home</span></span> | <span data-ttu-id="e7560-160">Настроен Виртуальный рабочий стол Windows.</span><span class="sxs-lookup"><span data-stu-id="e7560-160">You have configured Windows Virtual Desktop.</span></span> |
|||

## <a name="next-step"></a><span data-ttu-id="e7560-161">Следующий этап</span><span class="sxs-lookup"><span data-stu-id="e7560-161">Next step</span></span>

<span data-ttu-id="e7560-162">Чтобы перейти к управлению устройствами, ПК и другими конечными точками, см. [этап 3](empower-people-to-work-remotely-manage-endpoints.md).</span><span class="sxs-lookup"><span data-stu-id="e7560-162">Continue with [Step 3](empower-people-to-work-remotely-manage-endpoints.md) to manage your devices, PCs, and other endpoints.</span></span>
