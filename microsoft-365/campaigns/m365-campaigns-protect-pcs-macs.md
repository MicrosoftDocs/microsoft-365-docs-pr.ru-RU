---
title: Защита неугодных компьютеров с Windows 10 и Mac
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: sirkkuw
manager: scotv
ms.audience: Admin
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
ms.openlocfilehash: 5c27b29b5bb4fb445655e671d8c654ad8e9abc6b
ms.sourcegitcommit: 1b30ac6e05906c8a014b1fed33fc71e1821f6ad2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2021
ms.locfileid: "50044388"
---
# <a name="protect-unmanaged-windows-10-pcs-and-macs"></a><span data-ttu-id="37492-103">Защита неугодных компьютеров с Windows 10 и Mac</span><span class="sxs-lookup"><span data-stu-id="37492-103">Protect unmanaged Windows 10 PCs and Macs</span></span>

<span data-ttu-id="37492-104">Вы можете управлять компьютерами с Windows 10 и Компьютерами Mac, зарегистрировав их в Microsoft Intune, что позволяет убедиться, что они безопасны и безопасны перед доступом к данным в вашей среде.</span><span class="sxs-lookup"><span data-stu-id="37492-104">You can manage Windows 10 PCs and Macs by enrolling them in Microsoft Intune, which allows you to ensure they're healthy and secure before accessing data in your environment.</span></span> <span data-ttu-id="37492-105">Однако многие кампании и малые предприятия включают сотрудников, которые работают с собственными устройствами (BYOD), которые не будут управляться организацией.</span><span class="sxs-lookup"><span data-stu-id="37492-105">However, many campaigns and small businesses include staff who bring their own devices (BYOD), which will not be managed by the organization.</span></span> <span data-ttu-id="37492-106">Для таких неугодных компьютеров и компьютеров Mac воспользуйтесь этой статьей, чтобы убедиться, что настроены минимальные возможности безопасности.</span><span class="sxs-lookup"><span data-stu-id="37492-106">For these unmanaged PCs and Macs, use this article to ensure that minimum security capabilities are configured.</span></span>

<!--A Windows 10 PC is considered managed after you have completed the following two steps:

1. You (or the admin) set up device and data protection policies in the [setup  wizard](../business/set-up.md).

2. You have [connected your computer to Azure Active Directory](../business/set-up-windows-devices.md) and use your Microsoft 365 username and password to sign in.
3. --> 

## <a name="protect-a-computer-running-windows-10-or-a-mac"></a><span data-ttu-id="37492-107">Защита компьютера под управлением Windows 10 или Mac</span><span class="sxs-lookup"><span data-stu-id="37492-107">Protect a computer running Windows 10 or a Mac</span></span>

<!--If you have a PC that is running Windows 10 that is not connected to Microsoft 365, or a Mac, the Microsoft 365 protections do not apply to it, but here are some things you can do to keep your data secure on these devices as well:
-->
<span data-ttu-id="37492-108">Если компьютер с Windows 10 или Mac не управляется вашей организацией, настройте эти возможности безопасности.</span><span class="sxs-lookup"><span data-stu-id="37492-108">If your Windows 10 PC or Mac is not managed by your organization, be sure to configure these security capabilities.</span></span>

## <a name="windows-10"></a>[<span data-ttu-id="37492-109">Windows 10</span><span class="sxs-lookup"><span data-stu-id="37492-109">Windows 10</span></span>](#tab/Windows10)

<span data-ttu-id="37492-110">**Включить шифрование устройства**</span><span class="sxs-lookup"><span data-stu-id="37492-110">**Turn on device encryption**</span></span><p>

<span data-ttu-id="37492-111">Шифрование устройств доступно на широком спектре устройств с Windows и помогает защитить ваши данные путем их шифрования.</span><span class="sxs-lookup"><span data-stu-id="37492-111">Device encryption is available on a wide range of Windows devices and helps protect your data by encrypting it.</span></span> <span data-ttu-id="37492-112">Если включить шифрование устройства, только авторизованные лица смогут получить доступ к вашему устройству и данным.</span><span class="sxs-lookup"><span data-stu-id="37492-112">If you turn on device encryption, only authorized individuals will be able to access your device and data.</span></span> <span data-ttu-id="37492-113">Инструкции [см.](https://support.microsoft.com/help/4028713/windows-10-turn-on-device-encryption) в инструкциях по включению шифрования устройства.</span><span class="sxs-lookup"><span data-stu-id="37492-113">See [turn on device encryption](https://support.microsoft.com/help/4028713/windows-10-turn-on-device-encryption) for instructions.</span></span>

 <span data-ttu-id="37492-114">Если шифрование устройства не доступно на вашем устройстве, вы можете включить стандартное шифрование [BitLocker.](https://support.microsoft.com/help/4028713/windows-10-turn-on-device-encryption)</span><span class="sxs-lookup"><span data-stu-id="37492-114">If device encryption isn't available on your device, you can turn on standard [BitLocker encryption](https://support.microsoft.com/help/4028713/windows-10-turn-on-device-encryption) instead.</span></span> <span data-ttu-id="37492-115">(BitLocker не доступен в Windows 10 Домашняя.)</span><span class="sxs-lookup"><span data-stu-id="37492-115">(BitLocker isn't available on Windows 10 Home edition.)</span></span> 

<span data-ttu-id="37492-116">**Защита устройства с помощью системы безопасности Windows**</span><span class="sxs-lookup"><span data-stu-id="37492-116">**Protect your device with Windows Security**</span></span><p>
<span data-ttu-id="37492-117">Если у вас есть Windows 10, вы получите последнюю антивирусную защиту с помощью Windows Security.</span><span class="sxs-lookup"><span data-stu-id="37492-117">If you have Windows 10, you'll get the latest antivirus protection with Windows Security.</span></span> <span data-ttu-id="37492-118">При первом запуске Windows 10 система безопасности Windows активна и активно помогает защитить компьютер, сканируя вредоносные программы (вредоносные программы), вирусы и угрозы безопасности.</span><span class="sxs-lookup"><span data-stu-id="37492-118">When you start up Windows 10 for the first time, Windows Security is on and actively helping to protect your PC by scanning for malware (malicious software), viruses, and security threats.</span></span> <span data-ttu-id="37492-119">Система безопасности Windows использует защиту в режиме реального времени для сканирования всех загружаемых или запускаемых данных на компьютере.</span><span class="sxs-lookup"><span data-stu-id="37492-119">Windows Security uses real-time protection to scan everything you download or run on your PC.</span></span>

<span data-ttu-id="37492-120">Центр обновления Windows автоматически скачивает обновления для приложения "Безопасность Windows", чтобы обеспечить безопасность вашего компьютера и защитить его от угроз.</span><span class="sxs-lookup"><span data-stu-id="37492-120">Windows Update downloads updates for Windows Security automatically to help keep your PC safe and protect it from threats.</span></span>

<span data-ttu-id="37492-121">Если у вас есть более ранная версия Windows и вы используете Microsoft Security Essentials, то лучше перейти на windows Security.</span><span class="sxs-lookup"><span data-stu-id="37492-121">If you have an earlier version of Windows and are using Microsoft Security Essentials, it's a good idea to move to Windows Security.</span></span> <span data-ttu-id="37492-122">Дополнительные сведения см. в [справке по защите устройства с помощью Windows Security.](https://support.microsoft.com/help/17464/windows-10-help-protect-my-device-with-windows-security)</span><span class="sxs-lookup"><span data-stu-id="37492-122">For more information, see [help protect my device with Windows Security](https://support.microsoft.com/help/17464/windows-10-help-protect-my-device-with-windows-security).</span></span>

<span data-ttu-id="37492-123">**Включить брандмауэр Windows**</span><span class="sxs-lookup"><span data-stu-id="37492-123">**Turn on Windows Firewall**</span></span><p>
<span data-ttu-id="37492-124">Следует всегда запускать брандмауэр Windows, даже если включен другой брандмауэр.</span><span class="sxs-lookup"><span data-stu-id="37492-124">You should always run Windows Firewall even if you have another firewall turned on.</span></span> <span data-ttu-id="37492-125">Отключение брандмауэра Windows может сделать устройство (и сеть, если он у вас есть) более уязвимыми для несанкционированного доступа.</span><span class="sxs-lookup"><span data-stu-id="37492-125">Turning off Windows Firewall might make your device (and your network, if you have one) more vulnerable to unauthorized access.</span></span> <span data-ttu-id="37492-126">Инструкции [см.](https://support.microsoft.com/help/4028544/windows-10-turn-windows-defender-firewall-on-or-off) в инструкциях по включению и отключению брандмауэра Windows</span><span class="sxs-lookup"><span data-stu-id="37492-126">See [Turn Windows Firewall on or off](https://support.microsoft.com/help/4028544/windows-10-turn-windows-defender-firewall-on-or-off) for instructions</span></span>

## <a name="mac"></a>[<span data-ttu-id="37492-127">Mac</span><span class="sxs-lookup"><span data-stu-id="37492-127">Mac</span></span>](#tab/Mac)

<span data-ttu-id="37492-128">**Шифрование диска Mac с помощью FileVault**</span><span class="sxs-lookup"><span data-stu-id="37492-128">**Use FileVault to encrypt your Mac disk**</span></span><p>
<span data-ttu-id="37492-129">Шифрование диска защищает данные при утере или краже устройств.</span><span class="sxs-lookup"><span data-stu-id="37492-129">Disk encryption protects data when devices are lost or stolen.</span></span> <span data-ttu-id="37492-130">Шифрование на полном диске FileVault помогает предотвратить несанкционированный доступ к информации на диске запуска.</span><span class="sxs-lookup"><span data-stu-id="37492-130">FileVault full-disk encryption helps prevent unauthorized access to the information on your startup disk.</span></span> <span data-ttu-id="37492-131">Инструкции см. в инструкциях по шифрованию диска запуска на компьютере Mac с помощью [FileVault.](https://support.apple.com/HT204837)</span><span class="sxs-lookup"><span data-stu-id="37492-131">See [use FileVault to encrypt the startup disk on your Mac](https://support.apple.com/HT204837) for instructions.</span></span>

<span data-ttu-id="37492-132">**Защита mac от вредоносных программ**</span><span class="sxs-lookup"><span data-stu-id="37492-132">**Protect your mac from malware**</span></span><p>
<span data-ttu-id="37492-133">Корпорация Майкрософт рекомендует установить и использовать надежное антивирусное ПО на компьютере Mac.</span><span class="sxs-lookup"><span data-stu-id="37492-133">Microsoft recommends that you install and use reliable antivirus software on your Mac.</span></span> <span data-ttu-id="37492-134">Список вариантов: лучшая антивирусная программа [для Mac 2019: ](https://www.macworld.co.uk/feature/mac-software/mac-antivirus-3672182/)см. в следующей статье.</span><span class="sxs-lookup"><span data-stu-id="37492-134">See the following article for a list of choices: [Best Mac antivirus 2019 ](https://www.macworld.co.uk/feature/mac-software/mac-antivirus-3672182/).</span></span>

<span data-ttu-id="37492-135">Вы также можете снизить риск вредоносного ПО, используя программное обеспечение только из надежных источников.</span><span class="sxs-lookup"><span data-stu-id="37492-135">You can also reduce the risk of malware by using software only from reliable sources.</span></span> <span data-ttu-id="37492-136">Параметры в параметрах & конфиденциальности позволяют указать источники программного обеспечения, установленного на компьютере Mac.</span><span class="sxs-lookup"><span data-stu-id="37492-136">The settings in Security & Privacy preferences allow you to specify the sources of software installed on your Mac.</span></span> <span data-ttu-id="37492-137">Дополнительные сведения см. в [этой теме, чтобы защитить компьютер Mac от вредоносных программ.](https://support.apple.com/kb/PH25087)</span><span class="sxs-lookup"><span data-stu-id="37492-137">For more information, see [protect your Mac from malware](https://support.apple.com/kb/PH25087).</span></span>

<span data-ttu-id="37492-138">**Включить защиту брандмауэра**</span><span class="sxs-lookup"><span data-stu-id="37492-138">**Turn on firewall protection**</span></span><p>
<span data-ttu-id="37492-139">Используйте параметры брандмауэра, чтобы защитить компьютер Mac от нежелательных контактов, инициированных другими компьютерами при подсети или к Интернету.</span><span class="sxs-lookup"><span data-stu-id="37492-139">Use firewall settings to protect your Mac from unwanted contact initiated by other computers when you're connected to the Internet or a network.</span></span> <span data-ttu-id="37492-140">Без этой защиты компьютер Mac может быть более уязвимым к несанкционированному доступу.</span><span class="sxs-lookup"><span data-stu-id="37492-140">Without this protection, your Mac might be more vulnerable to unauthorized access.</span></span> <span data-ttu-id="37492-141">Инструкции [см. в брандмауэре](https://support.apple.com/HT201642) приложений.</span><span class="sxs-lookup"><span data-stu-id="37492-141">See [about the application firewall](https://support.apple.com/HT201642) for instructions.</span></span>
