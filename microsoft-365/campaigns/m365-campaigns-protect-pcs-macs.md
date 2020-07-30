---
title: Защитите неуправляемые компьютеры с Windows 10 и Mac
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
description: Защита от фишинга и других атак с помощью Microsoft 365 для кампаний.
ms.openlocfilehash: 3e0c6a52209c56e75c6ff1210f26e6926e4d7d32
ms.sourcegitcommit: 6501e01a9ab131205a3eef910e6cea7f65b3f010
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/30/2020
ms.locfileid: "46527142"
---
# <a name="protect-unmanaged-windows-10-pcs-and-macs"></a><span data-ttu-id="7fa8d-103">Защитите неуправляемые компьютеры с Windows 10 и Mac</span><span class="sxs-lookup"><span data-stu-id="7fa8d-103">Protect unmanaged Windows 10 PCs and Macs</span></span>

<span data-ttu-id="7fa8d-104">Вы можете управлять компьютерами с Windows 10 и Макинтошми, заменяя их в Microsoft Intune, что позволяет убедиться, что они работоспособны и безопасны, прежде чем получать доступ к данным в вашей среде.</span><span class="sxs-lookup"><span data-stu-id="7fa8d-104">You can manage Windows 10 PCs and Macs by enrolling them in Microsoft Intune, which allows you to ensure they're healthy and secure before accessing data in your environment.</span></span> <span data-ttu-id="7fa8d-105">Однако многие кампании и малые предприятия включают сотрудников, которые приносят свои собственные устройства (BYOD), которые не будут управляться Организацией.</span><span class="sxs-lookup"><span data-stu-id="7fa8d-105">However, many campaigns and small businesses include staff who bring their own devices (byod), which will not be managed by the organization.</span></span> <span data-ttu-id="7fa8d-106">Для этих неуправляемых компьютеров и компьютеров Макинтош используйте эту статью, чтобы убедиться в том, что минимальные возможности безопасности настроены.</span><span class="sxs-lookup"><span data-stu-id="7fa8d-106">For these unmanaged PCs and Macs, use this article to ensure that minimum security capabilities are configured.</span></span> 

<!--A Windows 10 PC is considered managed after you have completed the following two steps:

1. You (or the admin) set up device and data protection policies in the [setup  wizard](../business/set-up.md).

2. You have [connected your computer to Azure Active Directory](../business/set-up-windows-devices.md) and use your Microsoft 365 username and password to sign in.
3. --> 

## <a name="protect-a-computer-running-windows-10-or-a-mac"></a><span data-ttu-id="7fa8d-107">Защита компьютера под управлением Windows 10 или Mac</span><span class="sxs-lookup"><span data-stu-id="7fa8d-107">Protect a computer running Windows 10 or a Mac</span></span>

<!--If you have a PC that is running Windows 10 that is not connected to Microsoft 365, or a Mac, the Microsoft 365 protections do not apply to it, but here are some things you can do to keep your data secure on these devices as well:
-->
<span data-ttu-id="7fa8d-108">Если ваш компьютер с Windows 10 или Mac не управляется вашей организацией, обязательно настройте эти функции безопасности.</span><span class="sxs-lookup"><span data-stu-id="7fa8d-108">If your Windows 10 PC or Mac is not managed by your organization, be sure to configure these security capabilities.</span></span>

## <a name="windows-10"></a>[<span data-ttu-id="7fa8d-109">Windows 10</span><span class="sxs-lookup"><span data-stu-id="7fa8d-109">Windows 10</span></span>](#tab/Windows10)
<span data-ttu-id="7fa8d-110">**Включение шифрования устройств**</span><span class="sxs-lookup"><span data-stu-id="7fa8d-110">**Turn on device encryption**</span></span><p>

<span data-ttu-id="7fa8d-111">Шифрование устройств доступно для широкого спектра устройств Windows и защищает данные путем их шифрования.</span><span class="sxs-lookup"><span data-stu-id="7fa8d-111">Device encryption is available on a wide range of Windows devices and helps protect your data by encrypting it.</span></span> <span data-ttu-id="7fa8d-112">Если включено шифрование устройства, только авторизованные пользователи смогут получать доступ к устройству и данным.</span><span class="sxs-lookup"><span data-stu-id="7fa8d-112">If you turn on device encryption, only authorized individuals will be able to access your device and data.</span></span> <span data-ttu-id="7fa8d-113">Инструкции по [включению шифрования устройств](https://support.microsoft.com/help/4028713/windows-10-turn-on-device-encryption) .</span><span class="sxs-lookup"><span data-stu-id="7fa8d-113">See [turn on device encryption](https://support.microsoft.com/help/4028713/windows-10-turn-on-device-encryption) for instructions.</span></span>

 <span data-ttu-id="7fa8d-114">Если шифрование устройства недоступно на вашем устройстве, вместо этого можно включить стандартное [Шифрование BitLocker](https://support.microsoft.com/help/4028713/windows-10-turn-on-device-encryption) .</span><span class="sxs-lookup"><span data-stu-id="7fa8d-114">If device encryption isn't available on your device, you can turn on standard [BitLocker encryption](https://support.microsoft.com/help/4028713/windows-10-turn-on-device-encryption) instead.</span></span> <span data-ttu-id="7fa8d-115">(BitLocker недоступен в Windows 10 Home Edition.)</span><span class="sxs-lookup"><span data-stu-id="7fa8d-115">(BitLocker isn't available on Windows 10 Home edition.)</span></span> 


<span data-ttu-id="7fa8d-116">**Защита устройства с помощью системы безопасности Windows**</span><span class="sxs-lookup"><span data-stu-id="7fa8d-116">**Protect your device with Windows Security**</span></span><p>
<span data-ttu-id="7fa8d-117">Если у вас есть Windows 10, вы получите последнюю антивирусную защиту с помощью системы безопасности Windows.</span><span class="sxs-lookup"><span data-stu-id="7fa8d-117">If you have Windows 10, you'll get the latest antivirus protection with Windows Security.</span></span> <span data-ttu-id="7fa8d-118">При первом запуске Windows 10 система безопасности Windows включена и активно помогает защитить компьютер, проверяя наличие вредоносных программ, вирусов и угроз безопасности.</span><span class="sxs-lookup"><span data-stu-id="7fa8d-118">When you start up Windows 10 for the first time, Windows Security is on and actively helping to protect your PC by scanning for malware (malicious software), viruses, and security threats.</span></span> <span data-ttu-id="7fa8d-119">Система безопасности Windows использует защиту в режиме реального времени для сканирования всех загружаемых или выполняемых на компьютере компонентов.</span><span class="sxs-lookup"><span data-stu-id="7fa8d-119">Windows Security uses real-time protection to scan everything you download or run on your PC.</span></span>

<span data-ttu-id="7fa8d-120">Центр обновления Windows автоматически загружает обновления для безопасности Windows, чтобы защитить компьютер и защитить его от угроз.</span><span class="sxs-lookup"><span data-stu-id="7fa8d-120">Windows Update downloads updates for Windows Security automatically to help keep your PC safe and protect it from threats.</span></span>

<span data-ttu-id="7fa8d-121">Если вы используете более раннюю версию Windows и используете Microsoft Security Essentials, рекомендуется переместиться в систему безопасности Windows.</span><span class="sxs-lookup"><span data-stu-id="7fa8d-121">If you have an earlier version of Windows and are using Microsoft Security Essentials, it's a good idea to move to Windows Security.</span></span> <span data-ttu-id="7fa8d-122">Дополнительные сведения можно найти в статье [Защита устройства с помощью безопасности Windows](https://support.microsoft.com/help/17464/windows-10-help-protect-my-device-with-windows-security).</span><span class="sxs-lookup"><span data-stu-id="7fa8d-122">For more information, see [help protect my device with Windows Security](https://support.microsoft.com/help/17464/windows-10-help-protect-my-device-with-windows-security).</span></span>

<span data-ttu-id="7fa8d-123">**Включение брандмауэра Windows**</span><span class="sxs-lookup"><span data-stu-id="7fa8d-123">**Turn on Windows Firewall**</span></span><p>
<span data-ttu-id="7fa8d-124">Следует всегда запускать брандмауэр Windows, даже если включен другой брандмауэр.</span><span class="sxs-lookup"><span data-stu-id="7fa8d-124">You should always run Windows Firewall even if you have another firewall turned on.</span></span> <span data-ttu-id="7fa8d-125">Отключение брандмауэра Windows может сделать устройство (и сеть, если она есть) более уязвимым для несанкционированного доступа.</span><span class="sxs-lookup"><span data-stu-id="7fa8d-125">Turning off Windows Firewall might make your device (and your network, if you have one) more vulnerable to unauthorized access.</span></span> <span data-ttu-id="7fa8d-126">Инструкции по [включению и отключению брандмауэра Windows](https://support.microsoft.com/help/4028544/windows-10-turn-windows-defender-firewall-on-or-off)</span><span class="sxs-lookup"><span data-stu-id="7fa8d-126">See [Turn Windows Firewall on or off](https://support.microsoft.com/help/4028544/windows-10-turn-windows-defender-firewall-on-or-off) for instructions</span></span>

## <a name="mac"></a>[<span data-ttu-id="7fa8d-127">Mac</span><span class="sxs-lookup"><span data-stu-id="7fa8d-127">Mac</span></span>](#tab/Mac)
<span data-ttu-id="7fa8d-128">**Использование Филеваулт для шифрования диска Mac**</span><span class="sxs-lookup"><span data-stu-id="7fa8d-128">**Use FileVault to encrypt your Mac disk**</span></span><p>
<span data-ttu-id="7fa8d-129">Шифрование диска защищает данные в случае потери или кражи устройств.</span><span class="sxs-lookup"><span data-stu-id="7fa8d-129">Disk encryption protects data when devices are lost or stolen.</span></span> <span data-ttu-id="7fa8d-130">Филеваулт полное шифрование диска предотвращает несанкционированный доступ к информации на загрузочном диске.</span><span class="sxs-lookup"><span data-stu-id="7fa8d-130">FileVault full-disk encryption helps prevent unauthorized access to the information on your startup disk.</span></span> <span data-ttu-id="7fa8d-131">[В разделе Использование филеваулт для шифрования загрузочного диска в Mac](https://support.apple.com/HT204837) .</span><span class="sxs-lookup"><span data-stu-id="7fa8d-131">See [use FileVault to encrypt the startup disk on your Mac](https://support.apple.com/HT204837) for instructions.</span></span>

<span data-ttu-id="7fa8d-132">**Защита Макинтош от вредоносных программ**</span><span class="sxs-lookup"><span data-stu-id="7fa8d-132">**Protect your mac from malware**</span></span><p>
<span data-ttu-id="7fa8d-133">Корпорация Майкрософт рекомендует установить и использовать надежное антивирусное программное обеспечение на компьютере Mac.</span><span class="sxs-lookup"><span data-stu-id="7fa8d-133">Microsoft recommends that you install and use reliable antivirus software on your Mac.</span></span> <span data-ttu-id="7fa8d-134">В следующей статье приведен список вариантов: лучшая версия для [Macintosh antivirus 2019 ](https://www.macworld.co.uk/feature/mac-software/mac-antivirus-3672182/).</span><span class="sxs-lookup"><span data-stu-id="7fa8d-134">See the following article for a list of choices: [Best Mac antivirus 2019 ](https://www.macworld.co.uk/feature/mac-software/mac-antivirus-3672182/).</span></span>

<span data-ttu-id="7fa8d-135">Кроме того, вы можете снизить риск заражения вредоносными программами, используя программное обеспечение только из надежных источников.</span><span class="sxs-lookup"><span data-stu-id="7fa8d-135">You can also reduce the risk of malware by using software only from reliable sources.</span></span> <span data-ttu-id="7fa8d-136">Параметры в параметрах безопасности & конфиденциальности позволяют указать источники программного обеспечения, установленные на компьютере Mac.</span><span class="sxs-lookup"><span data-stu-id="7fa8d-136">The settings in Security & Privacy preferences allow you to specify the sources of software installed on your Mac.</span></span> <span data-ttu-id="7fa8d-137">Дополнительные сведения можно найти [в статье Защита системы Макинтош от вредоносных программ](https://support.apple.com/kb/PH25087).</span><span class="sxs-lookup"><span data-stu-id="7fa8d-137">For more information, see [protect your Mac from malware](https://support.apple.com/kb/PH25087).</span></span>

<span data-ttu-id="7fa8d-138">**Включение защиты с брандмауэром**</span><span class="sxs-lookup"><span data-stu-id="7fa8d-138">**Turn on firewall protection**</span></span><p>
<span data-ttu-id="7fa8d-139">Используйте параметры брандмауэра для защиты компьютера Макинтош от нежелательного контакта, инициированного другими компьютерами при наличии подключения к Интернету или сети.</span><span class="sxs-lookup"><span data-stu-id="7fa8d-139">Use firewall settings to protect your Mac from unwanted contact initiated by other computers when you're connected to the Internet or a network.</span></span> <span data-ttu-id="7fa8d-140">Без этой защиты ваш Mac-адрес может быть более уязвим для несанкционированного доступа.</span><span class="sxs-lookup"><span data-stu-id="7fa8d-140">Without this protection, your Mac might be more vulnerable to unauthorized access.</span></span> <span data-ttu-id="7fa8d-141">Для получения инструкций обратитесь к разделу [о брандмауэре приложения](https://support.apple.com/HT201642) .</span><span class="sxs-lookup"><span data-stu-id="7fa8d-141">See [about the application firewall](https://support.apple.com/HT201642) for instructions.</span></span>
