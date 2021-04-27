---
title: Ответ и поддержка coviD-19 contoso для удаленной и удаленной работы на месте
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Поймите, как корпорация Contoso отреагировала на пандемию COVID-19 и смонтировал их инфраструктуру установки и обновления программного обеспечения для удаленной и удаленной работы на месте.
ms.openlocfilehash: 0bded43f03dd529ffdf463818a93af70e10eed89
ms.sourcegitcommit: e02cf5702af178ddd2968877a808874ecb49ed2c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/26/2021
ms.locfileid: "52028984"
---
# <a name="contosos-covid-19-response-and-support-for-remote-and-onsite-work"></a><span data-ttu-id="aad03-103">Ответ и поддержка coviD-19 contoso для удаленной и удаленной работы на месте</span><span class="sxs-lookup"><span data-stu-id="aad03-103">Contoso's COVID-19 response and support for remote and onsite work</span></span>

<span data-ttu-id="aad03-104">Contoso всегда поддерживала удаленных сотрудников, которые получили доступ к локальному ресурсу через центральный VPN-сервер в парижской штаб-квартире.</span><span class="sxs-lookup"><span data-stu-id="aad03-104">Contoso had always supported its remote workers, who accessed on-premises resources through a central VPN server in the Paris headquarters.</span></span> <span data-ttu-id="aad03-105">Contoso выдал всем удаленным сотрудникам управляемый ноутбук.</span><span class="sxs-lookup"><span data-stu-id="aad03-105">Contoso had issued all remote workers a managed laptop.</span></span> <span data-ttu-id="aad03-106">У рабочих на месте была смесь настольных компьютеров и ноутбуков.</span><span class="sxs-lookup"><span data-stu-id="aad03-106">On-premises workers had a mixture of desktop computers and laptops.</span></span>

## <a name="contosos-response-to-covid-19"></a><span data-ttu-id="aad03-107">Ответ Contoso на COVID-19</span><span class="sxs-lookup"><span data-stu-id="aad03-107">Contoso’s response to COVID-19</span></span>

<span data-ttu-id="aad03-108">С началом пандемии COVID-19 внезапно все сотрудники, кроме основных, были удаленными работниками.</span><span class="sxs-lookup"><span data-stu-id="aad03-108">With the onset of the COVID-19 pandemic, suddenly all but essential workers were remote workers.</span></span> <span data-ttu-id="aad03-109">Contoso ответила тем, что переключила свои сотрудники на работу из дома и проводит свои основные действия с помощью удаленного доступа к локальному ресурсу и в Интернете с помощью облачных служб Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="aad03-109">Contoso responded by shifting its workforce to work from home and conduct its primary activities through remote access to on-premises resources and online using Microsoft 365 cloud services.</span></span>

<span data-ttu-id="aad03-110">У Contoso были VPN-серверы удаленного доступа в офисе парижской штаб-квартиры, чтобы поддерживать 25% уже удаленных сотрудников, но быстро перешли к масштабирования возможностей удаленного доступа для поддержки 90% рабочей силы.</span><span class="sxs-lookup"><span data-stu-id="aad03-110">Contoso had remote access VPN servers in the Paris headquarters office to support the 25% of its already remote workforce, but quickly moved to scale up it's remote access capacity to support 90% of its workforce.</span></span> <span data-ttu-id="aad03-111">Contoso развернула VPN-серверы удаленного доступа в каждом спутниковом офисе, чтобы удаленные сотрудники использовали региональную закрытую точку входа для доступа к интрасети Contoso.</span><span class="sxs-lookup"><span data-stu-id="aad03-111">Contoso deployed remote access VPN servers in each satellite office so that remote workers would use a regionally close entry point for access to the Contoso intranet.</span></span>

<span data-ttu-id="aad03-112">Contoso также обновила конфигурацию VPN-клиентов, установленных на ноутбуках, планшетах и смартфонах для раздельного туннелирования, чтобы трафик для конечных точек Office 365 обходил VPN-подключение и отправлялся непосредственно через Интернет.</span><span class="sxs-lookup"><span data-stu-id="aad03-112">Contoso also updated the configuration of VPN clients installed on laptops, tablets, and smart phones for split tunneling so that traffic for the Optimize set of Office 365 endpoints bypassed the VPN connection and was sent directly over the internet.</span></span> <span data-ttu-id="aad03-113">Дополнительные сведения см. в раздел [Оптимизация подключения Office 365](../enterprise/microsoft-365-vpn-split-tunnel.md)для удаленных пользователей с помощью раздельного vpn-туннеля.</span><span class="sxs-lookup"><span data-stu-id="aad03-113">For more information, see [Optimize Office 365 connectivity for remote users using VPN split tunneling](../enterprise/microsoft-365-vpn-split-tunnel.md).</span></span>

<span data-ttu-id="aad03-114">Вот итоговая конфигурация с VPN-устройствами, установленными в парижской штаб-квартире и каждом из спутниковых офисов.</span><span class="sxs-lookup"><span data-stu-id="aad03-114">Here is the resulting configuration with VPN devices installed in the Paris headquarters and each of the satellite offices.</span></span> 

![VPN-инфраструктура Contoso](../media/contoso-remote-onsite-work/contoso-vpn-infrastructure.png)

<span data-ttu-id="aad03-116">Удаленный сотрудник с установленным VPN-клиентом использует DNS для поиска ближайшего к региону офиса и подключается к установленной там VPN-устройстве.</span><span class="sxs-lookup"><span data-stu-id="aad03-116">A remote worker with the installed VPN client uses DNS to find the regionally closest office and connects to the VPN device installed there.</span></span> <span data-ttu-id="aad03-117">При разделенном туннеле, трафик в конечные точки Microsoft 365 Оптимизируйте отправляется непосредственно в ближайшее к региону расположение сети Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="aad03-117">With split tunneling, traffic to Microsoft 365 Optimize endpoints gets sent directly to the regionally closest Microsoft 365 network location.</span></span> <span data-ttu-id="aad03-118">Весь другой трафик отправляется через VPN-подключение к VPN-устройству.</span><span class="sxs-lookup"><span data-stu-id="aad03-118">All other traffic gets sent over the VPN connection to the VPN device.</span></span>

## <a name="contosos-support-for-remote-and-onsite-work"></a><span data-ttu-id="aad03-119">Поддержка contoso для удаленной и удаленной работы на месте</span><span class="sxs-lookup"><span data-stu-id="aad03-119">Contoso’s support for remote and onsite work</span></span>

<span data-ttu-id="aad03-120">После внесения первоначальных изменений для поддержки в основном удаленных сотрудников во время региональных блокировок contoso вносили изменения в инфраструктуру для поддержки удаленной и удаленной работы, в которой может быть сотрудник:</span><span class="sxs-lookup"><span data-stu-id="aad03-120">After the initial changes were made to support mostly remote workers during regional lockdowns, Contoso made infrastructure changes to support remote and onsite work in which a worker could be:</span></span>

- <span data-ttu-id="aad03-121">Всегда удаленный.</span><span class="sxs-lookup"><span data-stu-id="aad03-121">Always remote.</span></span>
- <span data-ttu-id="aad03-122">Всегда на месте.</span><span class="sxs-lookup"><span data-stu-id="aad03-122">Always onsite.</span></span>
- <span data-ttu-id="aad03-123">Сочетание удаленного и удаленного на месте.</span><span class="sxs-lookup"><span data-stu-id="aad03-123">A combination of onsite and remote.</span></span>

<span data-ttu-id="aad03-124">Функции удостоверений, безопасности и соответствия требованиям Microsoft 365 предназначены для zero Trust и работают независимо от расположения пользователя и устройства.</span><span class="sxs-lookup"><span data-stu-id="aad03-124">Microsoft 365 identity, security, and compliance features are designed for Zero Trust and to work regardless of the location of the user and their device.</span></span> <span data-ttu-id="aad03-125">Дополнительные сведения см. в [ок. Zero Trust](https://www.microsoft.com/security/business/zero-trust).</span><span class="sxs-lookup"><span data-stu-id="aad03-125">For more information, see [Zero Trust](https://www.microsoft.com/security/business/zero-trust).</span></span>

<span data-ttu-id="aad03-126">Однако управление новыми установками и обновлениями программного обеспечения зависит от расположения устройства, так как программное обеспечение для установки может приходить из локального или интернет-источника.</span><span class="sxs-lookup"><span data-stu-id="aad03-126">However, managing new installs and updates of software is dependent on the location of the device because the software to install could come from an on-premises or an internet source.</span></span> <span data-ttu-id="aad03-127">ИТ-архитекторы Contoso разработали новую инфраструктуру установок и обновлений в зависимости от расположения устройства, а не рабочего.</span><span class="sxs-lookup"><span data-stu-id="aad03-127">Contoso IT architects designed their new installs and updates infrastructure based on the location of the device, rather than the worker.</span></span>

<span data-ttu-id="aad03-128">Они обозначили два типа устройств: выделенные на месте и роуминг.</span><span class="sxs-lookup"><span data-stu-id="aad03-128">They designated two types of devices: dedicated on-premises and roaming.</span></span>

### <a name="dedicated-on-premises"></a><span data-ttu-id="aad03-129">Выделенные локально</span><span class="sxs-lookup"><span data-stu-id="aad03-129">Dedicated on-premises</span></span>

<span data-ttu-id="aad03-130">Специализированное локальное устройство — это настольный или серверный компьютер, который никогда не выходит из интрасети Contoso и не имеет установленного VPN-клиента.</span><span class="sxs-lookup"><span data-stu-id="aad03-130">A dedicated on-premises device is a desktop or server computer that never leaves the Contoso intranet and does not have a VPN client installed.</span></span> <span data-ttu-id="aad03-131">На этих локальном устройстве по-прежнему используется Microsoft Endpoint Configuration Manager и его точки распространения для установок и обновлений Windows 10, Microsoft 365 Apps для предприятия и браузера Edge.</span><span class="sxs-lookup"><span data-stu-id="aad03-131">These on-premises devices continue to use Microsoft Endpoint Configuration Manager and its distribution points for installs and updates of Windows 10, Microsoft 365 Apps for enterprise, and the Edge browser.</span></span>

### <a name="roaming"></a><span data-ttu-id="aad03-132">Роуминг</span><span class="sxs-lookup"><span data-stu-id="aad03-132">Roaming</span></span>

<span data-ttu-id="aad03-133">Устройство для роуминга может покинуть интрасеть Contoso и включает ноутбуки, выданные многим офисным работникам, а также всем удаленным сотрудникам и другим устройствам, таким как смартфоны и планшеты с установленным VPN-клиентом Contoso.</span><span class="sxs-lookup"><span data-stu-id="aad03-133">A roaming device can leave the Contoso intranet and includes laptops issued to many office workers and all remote workers and other organization-owned devices such as smart phones and tablets with the Contoso VPN client installed.</span></span> 

<span data-ttu-id="aad03-134">Поскольку эти устройства могут быть подключены к Интернету в любое время, они используют Intune или другие облачные службы для установки и обновления Windows 10, Microsoft 365 Apps для предприятия и Edge.</span><span class="sxs-lookup"><span data-stu-id="aad03-134">Because these devices can be connected to the Internet at any given time, they use Intune or other cloud-based services for installs and updates of Windows 10, Microsoft 365 Apps for enterprise, and Edge.</span></span> <span data-ttu-id="aad03-135">Они не используют существующие локально точки рассылки Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="aad03-135">They do not use the existing on-premises Configuration Manager distribution points.</span></span>

<span data-ttu-id="aad03-136">Это означает, что некоторые из установок и обновлений для устройства для роуминга будут сделаны через Интернет, пока они находятся на локальном устройстве и подключены к интрасети.</span><span class="sxs-lookup"><span data-stu-id="aad03-136">This means some of the installs and updates for roaming device will be done over the internet while they are on-premises and connected to the intranet.</span></span> <span data-ttu-id="aad03-137">Но ИТ-архитекторы Contoso решили, что простота конфигурации важнее оптимизации пропускной способности интрасети в Интернете, особенно если большинство удаленных сотрудников редко подключены к интрасети.</span><span class="sxs-lookup"><span data-stu-id="aad03-137">But Contoso IT architects decided that simplicity of configuration was more important than optimization of intranet bandwidth to the internet, especially when most remote workers are seldom connected to the intranet.</span></span>

<span data-ttu-id="aad03-138">Ниже приводится итоговая инфраструктура.</span><span class="sxs-lookup"><span data-stu-id="aad03-138">Here is the resulting infrastructure.</span></span>

![Инфраструктура установки и обновления Contoso](../media/contoso-remote-onsite-work/contoso-updates-infrastructure.png)

<span data-ttu-id="aad03-140">Поведение установки и обновления определяется путем принятия учетных записей компьютеров устройств членом одной из этих групп:</span><span class="sxs-lookup"><span data-stu-id="aad03-140">Install and update behavior is determined by making the computer accounts of devices a member of one of these groups:</span></span>

- <span data-ttu-id="aad03-141">OnPremDevices</span><span class="sxs-lookup"><span data-stu-id="aad03-141">OnPremDevices</span></span>

  <span data-ttu-id="aad03-142">Клиент Configuration Manager на устройстве использует точки распространения для установок и обновлений.</span><span class="sxs-lookup"><span data-stu-id="aad03-142">The Configuration Manager client on the device uses distribution points for installs and updates.</span></span>

- <span data-ttu-id="aad03-143">RoamingDevices</span><span class="sxs-lookup"><span data-stu-id="aad03-143">RoamingDevices</span></span>

  <span data-ttu-id="aad03-144">Intune и другие параметры на устройстве указывают использование сети Microsoft 365 для установок и обновлений.</span><span class="sxs-lookup"><span data-stu-id="aad03-144">Intune and other settings on the device specify the use of the Microsoft 365 network for installs and updates.</span></span>

## <a name="new-onboarding-process"></a><span data-ttu-id="aad03-145">Новый процесс onboarding</span><span class="sxs-lookup"><span data-stu-id="aad03-145">New onboarding process</span></span>

<span data-ttu-id="aad03-146">Для нового специального локального устройства, выданного новому сотруднику или новому серверу в центр обработки данных, когда сотрудник вошел, клиент Configuration Manager на основе членства устройства в группах OnPremDevices загружает и устанавливает последние обновления для Windows 10, Microsoft 365 Apps для предприятия и Edge из локальной точки рассылки Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="aad03-146">For a new dedicated on-premises device issued to a new worker or for a new server in a datacenter, when the worker signs in, the Configuration Manager client based on the device's membership in the OnPremDevices group downloads and installs the latest updates for Windows 10, Microsoft 365 Apps for enterprise, and Edge from on-premises Configuration Manager distribution points.</span></span> <span data-ttu-id="aad03-147">По завершению выделенное локальное устройство готово к использованию и использует эти точки распространения для текущих обновлений.</span><span class="sxs-lookup"><span data-stu-id="aad03-147">When complete, the dedicated on-premises device is ready for use and uses these distribution points for ongoing updates.</span></span>

<span data-ttu-id="aad03-148">Для нового удаленного устройства, выданного новому работнику, при его в записи устройство, основанное на его членстве в группе RoamingDevices, контактирует с облачной службой Intune и другими службами и загружает и устанавливает последние обновления для Windows 10, Microsoft 365 Apps для предприятия и Edge.</span><span class="sxs-lookup"><span data-stu-id="aad03-148">For a new remote device issued to a new worker, when the worker signs in, the device, based on its membership in the RoamingDevices group, contacts the Intune cloud service and other services and downloads and installs the latest updates for Windows 10, Microsoft 365 Apps for enterprise, and Edge.</span></span> <span data-ttu-id="aad03-149">После завершения работы удаленное устройство готово к использованию и использует установленный VPN-клиент для доступа к локальному ресурсу и сети Microsoft 365 для текущих обновлений.</span><span class="sxs-lookup"><span data-stu-id="aad03-149">When complete, the remote device is ready for use and uses the installed VPN client for access to on-premises resources and the Microsoft 365 network for ongoing updates.</span></span>

## <a name="next-step"></a><span data-ttu-id="aad03-150">Следующий шаг</span><span class="sxs-lookup"><span data-stu-id="aad03-150">Next step</span></span>

<span data-ttu-id="aad03-151">[Расширение прав и возможностей удаленных сотрудников](empower-people-to-work-remotely.md) в организации.</span><span class="sxs-lookup"><span data-stu-id="aad03-151">[Empower the remote workers](empower-people-to-work-remotely.md) in your organization.</span></span>
