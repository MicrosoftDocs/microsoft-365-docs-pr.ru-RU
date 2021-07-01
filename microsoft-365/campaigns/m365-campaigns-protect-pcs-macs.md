---
title: Защита неуправляемых компьютеров с Windows 10 и компьютеров Mac
f1.keywords:
- NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-identity-device-management
- M365-Campaigns
- m365solution-smb
ms.custom:
- Adm_O365
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
- MOE150
description: Защита неугодных или собственных устройств (BYOD) с помощью Microsoft 365.
ms.openlocfilehash: 40e94e2f961ab34827de4ce5e43e100af53a7340
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/30/2021
ms.locfileid: "53227503"
---
# <a name="protect-unmanaged-windows-10-pcs-and-macs"></a><span data-ttu-id="114d6-103">Защита неуправляемых компьютеров с Windows 10 и компьютеров Mac</span><span class="sxs-lookup"><span data-stu-id="114d6-103">Protect unmanaged Windows 10 PCs and Macs</span></span>

<span data-ttu-id="114d6-104">Вы можете управлять Windows 10 компьютерами и компьютерами Mac, зачислив их в Microsoft Intune, что позволяет убедиться, что они здоровы и безопасны перед доступом к данным в вашей среде.</span><span class="sxs-lookup"><span data-stu-id="114d6-104">You can manage Windows 10 PCs and Macs by enrolling them in Microsoft Intune, which allows you to ensure they're healthy and secure before accessing data in your environment.</span></span> <span data-ttu-id="114d6-105">Однако многие кампании и малые предприятия включают сотрудников, которые приносят свои собственные устройства (BYOD), которые не будут управляться организацией.</span><span class="sxs-lookup"><span data-stu-id="114d6-105">However, many campaigns and small businesses include staff who bring their own devices (BYOD), which will not be managed by the organization.</span></span> <span data-ttu-id="114d6-106">Для этих неугомонных компьютеров и компьютеров Mac используйте эту статью, чтобы обеспечить настройку минимальных возможностей безопасности.</span><span class="sxs-lookup"><span data-stu-id="114d6-106">For these unmanaged PCs and Macs, use this article to ensure that minimum security capabilities are configured.</span></span>

<!--A Windows 10 PC is considered managed after you have completed the following two steps:

1. You (or the admin) set up device and data protection policies in the [setup  wizard](../business/set-up.md).

2. You have [connected your computer to Azure Active Directory](../business/set-up-windows-devices.md) and use your Microsoft 365 username and password to sign in.
3. --> 

## <a name="protect-a-computer-running-windows-10-or-a-mac"></a><span data-ttu-id="114d6-107">Защита компьютера с Windows 10 mac</span><span class="sxs-lookup"><span data-stu-id="114d6-107">Protect a computer running Windows 10 or a Mac</span></span>

<!--If you have a PC that is running Windows 10 that is not connected to Microsoft 365, or a Mac, the Microsoft 365 protections do not apply to it, but here are some things you can do to keep your data secure on these devices as well:
-->
<span data-ttu-id="114d6-108">Если Windows 10 или Mac не управляется вашей организацией, не забудьте настроить эти возможности безопасности.</span><span class="sxs-lookup"><span data-stu-id="114d6-108">If your Windows 10 PC or Mac is not managed by your organization, be sure to configure these security capabilities.</span></span>

## <a name="windows-10"></a>[<span data-ttu-id="114d6-109">Windows 10</span><span class="sxs-lookup"><span data-stu-id="114d6-109">Windows 10</span></span>](#tab/Windows10)

<span data-ttu-id="114d6-110">**Включив шифрование устройств**</span><span class="sxs-lookup"><span data-stu-id="114d6-110">**Turn on device encryption**</span></span><p>

<span data-ttu-id="114d6-111">Шифрование устройств доступно на широком диапазоне устройств Windows и помогает защитить данные, шифруя их.</span><span class="sxs-lookup"><span data-stu-id="114d6-111">Device encryption is available on a wide range of Windows devices and helps protect your data by encrypting it.</span></span> <span data-ttu-id="114d6-112">Если включить шифрование устройств, доступ к вашему устройству и данным смогут получить только уполномоченные лица.</span><span class="sxs-lookup"><span data-stu-id="114d6-112">If you turn on device encryption, only authorized individuals will be able to access your device and data.</span></span> <span data-ttu-id="114d6-113">[Включаем шифрование](https://support.microsoft.com/help/4028713/windows-10-turn-on-device-encryption) устройств для инструкций.</span><span class="sxs-lookup"><span data-stu-id="114d6-113">See [turn on device encryption](https://support.microsoft.com/help/4028713/windows-10-turn-on-device-encryption) for instructions.</span></span>

 <span data-ttu-id="114d6-114">Если шифрование устройства не доступно на устройстве, вместо этого можно включить стандартное [шифрование BitLocker.](https://support.microsoft.com/help/4028713/windows-10-turn-on-device-encryption)</span><span class="sxs-lookup"><span data-stu-id="114d6-114">If device encryption isn't available on your device, you can turn on standard [BitLocker encryption](https://support.microsoft.com/help/4028713/windows-10-turn-on-device-encryption) instead.</span></span> <span data-ttu-id="114d6-115">(BitLocker не доступен в Windows 10 Домашняя выпуске.)</span><span class="sxs-lookup"><span data-stu-id="114d6-115">(BitLocker isn't available on Windows 10 Home edition.)</span></span> 

<span data-ttu-id="114d6-116">**Защитите устройство с помощью Безопасность Windows**</span><span class="sxs-lookup"><span data-stu-id="114d6-116">**Protect your device with Windows Security**</span></span><p>
<span data-ttu-id="114d6-117">Если у вас Windows 10, вы получите последнюю антивирусную защиту с помощью Безопасность Windows.</span><span class="sxs-lookup"><span data-stu-id="114d6-117">If you have Windows 10, you'll get the latest antivirus protection with Windows Security.</span></span> <span data-ttu-id="114d6-118">При первом запуске Windows 10, Безопасность Windows активно помогает защитить компьютер, сканируя вредоносные программы(вредоносные программы), вирусы и угрозы безопасности.</span><span class="sxs-lookup"><span data-stu-id="114d6-118">When you start up Windows 10 for the first time, Windows Security is on and actively helping to protect your PC by scanning for malware (malicious software), viruses, and security threats.</span></span> <span data-ttu-id="114d6-119">Безопасность Windows защиты в режиме реального времени для сканирования всего, что вы скачиваете или работаете на компьютере.</span><span class="sxs-lookup"><span data-stu-id="114d6-119">Windows Security uses real-time protection to scan everything you download or run on your PC.</span></span>

<span data-ttu-id="114d6-120">Центр обновления Windows автоматически скачивает обновления для приложения "Безопасность Windows", чтобы обеспечить безопасность вашего компьютера и защитить его от угроз.</span><span class="sxs-lookup"><span data-stu-id="114d6-120">Windows Update downloads updates for Windows Security automatically to help keep your PC safe and protect it from threats.</span></span>

<span data-ttu-id="114d6-121">Если у вас есть более раная версия Windows и используется Microsoft Security Essentials, лучше перейти к Безопасность Windows.</span><span class="sxs-lookup"><span data-stu-id="114d6-121">If you have an earlier version of Windows and are using Microsoft Security Essentials, it's a good idea to move to Windows Security.</span></span> <span data-ttu-id="114d6-122">Дополнительные сведения см. [в справке о защите устройства с помощью Безопасность Windows.](https://support.microsoft.com/help/17464/windows-10-help-protect-my-device-with-windows-security)</span><span class="sxs-lookup"><span data-stu-id="114d6-122">For more information, see [help protect my device with Windows Security](https://support.microsoft.com/help/17464/windows-10-help-protect-my-device-with-windows-security).</span></span>

<span data-ttu-id="114d6-123">**Включаем Windows брандмауэр**</span><span class="sxs-lookup"><span data-stu-id="114d6-123">**Turn on Windows Firewall**</span></span><p>
<span data-ttu-id="114d6-124">Вы всегда должны запускать Windows брандмауэра, даже если включен другой брандмауэр.</span><span class="sxs-lookup"><span data-stu-id="114d6-124">You should always run Windows Firewall even if you have another firewall turned on.</span></span> <span data-ttu-id="114d6-125">Отключение Windows брандмауэра может сделать ваше устройство (и сеть, если у вас есть) более уязвимым для несанкционированного доступа.</span><span class="sxs-lookup"><span data-stu-id="114d6-125">Turning off Windows Firewall might make your device (and your network, if you have one) more vulnerable to unauthorized access.</span></span> <span data-ttu-id="114d6-126">См. [Windows брандмауэра](https://support.microsoft.com/help/4028544/windows-10-turn-windows-defender-firewall-on-or-off) включить или отключить для инструкций.</span><span class="sxs-lookup"><span data-stu-id="114d6-126">See [Turn Windows Firewall on or off](https://support.microsoft.com/help/4028544/windows-10-turn-windows-defender-firewall-on-or-off) for instructions.</span></span>

## <a name="mac"></a>[<span data-ttu-id="114d6-127">Mac</span><span class="sxs-lookup"><span data-stu-id="114d6-127">Mac</span></span>](#tab/Mac)

<span data-ttu-id="114d6-128">**Используйте FileVault для шифрования диска Mac**</span><span class="sxs-lookup"><span data-stu-id="114d6-128">**Use FileVault to encrypt your Mac disk**</span></span><p>
<span data-ttu-id="114d6-129">Шифрование диска защищает данные в случае потери или кражи устройств.</span><span class="sxs-lookup"><span data-stu-id="114d6-129">Disk encryption protects data when devices are lost or stolen.</span></span> <span data-ttu-id="114d6-130">Шифрование полного диска FileVault помогает предотвратить несанкционированный доступ к данным на вашем диске запуска.</span><span class="sxs-lookup"><span data-stu-id="114d6-130">FileVault full-disk encryption helps prevent unauthorized access to the information on your startup disk.</span></span> <span data-ttu-id="114d6-131">См. [в инструкциях с помощью FileVault](https://support.apple.com/HT204837) для шифрования диска запуска на Mac.</span><span class="sxs-lookup"><span data-stu-id="114d6-131">See [use FileVault to encrypt the startup disk on your Mac](https://support.apple.com/HT204837) for instructions.</span></span>

<span data-ttu-id="114d6-132">**Защита mac от вредоносных программ**</span><span class="sxs-lookup"><span data-stu-id="114d6-132">**Protect your mac from malware**</span></span><p>
<span data-ttu-id="114d6-133">Корпорация Майкрософт рекомендует установить и использовать надежное антивирусное программное обеспечение на Компьютере Mac.</span><span class="sxs-lookup"><span data-stu-id="114d6-133">Microsoft recommends that you install and use reliable antivirus software on your Mac.</span></span> <span data-ttu-id="114d6-134">Список вариантов: Лучший антивирус [Mac 2019](https://www.macworld.co.uk/feature/mac-software/mac-antivirus-3672182/)см. в следующей статье.</span><span class="sxs-lookup"><span data-stu-id="114d6-134">See the following article for a list of choices: [Best Mac antivirus 2019](https://www.macworld.co.uk/feature/mac-software/mac-antivirus-3672182/).</span></span>

<span data-ttu-id="114d6-135">Вы также можете снизить риск вредоносных программ, используя программное обеспечение только из надежных источников.</span><span class="sxs-lookup"><span data-stu-id="114d6-135">You can also reduce the risk of malware by using software only from reliable sources.</span></span> <span data-ttu-id="114d6-136">Параметры в параметрах & конфиденциальности позволяют указать источники программного обеспечения, установленного на Mac.</span><span class="sxs-lookup"><span data-stu-id="114d6-136">The settings in Security & Privacy preferences allow you to specify the sources of software installed on your Mac.</span></span> <span data-ttu-id="114d6-137">Дополнительные сведения см. в [дополнительных сведениях о защите Mac от вредоносных программ.](https://support.apple.com/kb/PH25087)</span><span class="sxs-lookup"><span data-stu-id="114d6-137">For more information, see [protect your Mac from malware](https://support.apple.com/kb/PH25087).</span></span>

<span data-ttu-id="114d6-138">**Включить защиту брандмауэра**</span><span class="sxs-lookup"><span data-stu-id="114d6-138">**Turn on firewall protection**</span></span><p>
<span data-ttu-id="114d6-139">Используйте параметры брандмауэра, чтобы защитить Mac от нежелательного контакта, инициированного другими компьютерами, когда вы подключены к Интернету или сети.</span><span class="sxs-lookup"><span data-stu-id="114d6-139">Use firewall settings to protect your Mac from unwanted contact initiated by other computers when you're connected to the Internet or a network.</span></span> <span data-ttu-id="114d6-140">Без этой защиты mac может быть более уязвимым для несанкционированного доступа.</span><span class="sxs-lookup"><span data-stu-id="114d6-140">Without this protection, your Mac might be more vulnerable to unauthorized access.</span></span> <span data-ttu-id="114d6-141">Узнайте [о брандмауэре приложений](https://support.apple.com/HT201642) для инструкций.</span><span class="sxs-lookup"><span data-stu-id="114d6-141">See [about the application firewall](https://support.apple.com/HT201642) for instructions.</span></span>
