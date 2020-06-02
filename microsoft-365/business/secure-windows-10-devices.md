---
title: Защита устройств с Windows 10
f1.keywords:
- CSH
ms.author: sirkkuw
author: sirkkuw
manager: scotv
audience: Admin
ms.topic: conceptual
f1_keywords:
- O365E_BCSSetup4WindowsConfig
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 21e5551f-fa35-4f13-9418-f80d668b6a2b
description: Сведения о настройке параметров политики устройств по умолчанию, которое будет получать любое устройство Windows 10 после входа в рабочую или учебную учетную запись.
ms.openlocfilehash: 03ae86861ddb0cb83cd39b7834f19e01bf3e99e2
ms.sourcegitcommit: 2d664a95b9875f0775f0da44aca73b16a816e1c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/01/2020
ms.locfileid: "44470634"
---
# <a name="secure-windows-10-devices"></a><span data-ttu-id="a98f4-103">Защита устройств с Windows 10</span><span class="sxs-lookup"><span data-stu-id="a98f4-103">Secure Windows 10 devices</span></span>

<span data-ttu-id="a98f4-104">Эта статья относится к Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="a98f4-104">This article applies to Microsoft 365 Business Premium.</span></span>

<span data-ttu-id="a98f4-105">Описанные в этой статье параметры входят в стандартную политику для устройств с Windows 10.</span><span class="sxs-lookup"><span data-stu-id="a98f4-105">The settings that you configure here are part of the default device policy for Windows 10.</span></span> <span data-ttu-id="a98f4-106">Все пользователи, которые подключаются к устройству Windows 10, в том числе к мобильным устройствам и ПК, при входе с использованием своей рабочей учетной записи будут автоматически получать эти параметры.</span><span class="sxs-lookup"><span data-stu-id="a98f4-106">All users who connect a Windows 10 device, including mobile devices and PCs, by signing in with their work account will automatically receive these settings.</span></span> <span data-ttu-id="a98f4-107">Советуем во время настройки принять стандартную конфигурацию, а политики, предназначенные для определенных групп пользователей добавить позднее.</span><span class="sxs-lookup"><span data-stu-id="a98f4-107">We recommend that you accept the default policy during setup and add policies later that target specific groups of users.</span></span>
  
## <a name="settings-to-secure-windows-10-devices"></a><span data-ttu-id="a98f4-108">Параметры для защиты устройств с Windows 10</span><span class="sxs-lookup"><span data-stu-id="a98f4-108">Settings to secure Windows 10 devices</span></span>

<span data-ttu-id="a98f4-p102">Все параметры **включены** по умолчанию. Доступны следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="a98f4-p102">By default all settings are **On**. The following settings are available:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="a98f4-111">Параметр</span><span class="sxs-lookup"><span data-stu-id="a98f4-111">Setting</span></span>  <br/> |<span data-ttu-id="a98f4-112">Описание</span><span class="sxs-lookup"><span data-stu-id="a98f4-112">Description</span></span>  <br/> |
|<span data-ttu-id="a98f4-113">Использование антивирусной программы "Защитник Windows"</span><span class="sxs-lookup"><span data-stu-id="a98f4-113">Help protect PCs from viruses and other threats using Windows Defender Antivirus</span></span>  <br/> |<span data-ttu-id="a98f4-114">Требует включения антивирусной программы "Защитник Windows" для защиты компьютеров, подключенных к Интернету.</span><span class="sxs-lookup"><span data-stu-id="a98f4-114">Requires that Windows Defender Antivirus is turned on to protect PCs from the dangers of being connected to the internet.</span></span>  <br/> |
|<span data-ttu-id="a98f4-115">Защитите компьютеры от угроз из Интернета в Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="a98f4-115">Help protect PCs from web-based threats in Microsoft Edge</span></span>  <br/> |<span data-ttu-id="a98f4-116">Включает параметры в Microsoft Edge, которые помогают защитить пользователей от вредоносных сайтов и скачиваний.</span><span class="sxs-lookup"><span data-stu-id="a98f4-116">Turns on settings in Edge that help protect users from malicious sites and downloads.</span></span>  <br/> |
|<span data-ttu-id="a98f4-117">Выключать экран устройства, если оно неактивно в течение указанного периода времени</span><span class="sxs-lookup"><span data-stu-id="a98f4-117">Turn off device screen when idle for this amount of time</span></span>  <br/> |<span data-ttu-id="a98f4-p103">Обеспечивает защиту корпоративных данных, когда пользователь неактивен. Пользователь может работать в общественном месте, например кафе, и на короткое время отойти или отвлечься. При этом посторонние могут случайно увидеть сведения на экране. Этот параметр управляет временем, на протяжении которого пользователь может оставаться неактивным, прежде чем экран выключится.</span><span class="sxs-lookup"><span data-stu-id="a98f4-p103">Makes sure that company data is protected if a user is idle. A user may be working in a public location, like a coffee shop, and step away or be distracted for just a moment, leaving their device vulnerable to random glances. This setting lets you control how long the user can be idle before the screen shuts off.</span></span>  <br/> |
|<span data-ttu-id="a98f4-121">Разрешить пользователям скачивать приложения из Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="a98f4-121">Allow users to download apps from Microsoft Store</span></span>  <br/> |<span data-ttu-id="a98f4-p104">Позволяет пользователям скачивать и устанавливать приложения из Microsoft Store. Это касается любых приложений, от инструментов для повышения производительности до игр, поэтому этот параметр **включен**, но его можно отключить, чтобы обеспечить дополнительную защиту.  </span><span class="sxs-lookup"><span data-stu-id="a98f4-p104">Lets users download and install apps from the Microsoft Store. Apps include everything from games to productivity tools, so we leave this setting **On**, but you can turn it off for extra security.  </span></span><br/> |
|<span data-ttu-id="a98f4-124">Разрешить пользователям доступ к Кортане</span><span class="sxs-lookup"><span data-stu-id="a98f4-124">Allow users to access Cortana</span></span>  <br/> |<span data-ttu-id="a98f4-125">Кортана может быть очень полезной.</span><span class="sxs-lookup"><span data-stu-id="a98f4-125">Cortana can be very helpful!</span></span> <span data-ttu-id="a98f4-126">Кортана может включать или отключать параметры, давать указания и следить за временем встреч, поэтому по умолчанию этот параметр следует оставить **включенным** .</span><span class="sxs-lookup"><span data-stu-id="a98f4-126">Cortana can turn settings on or off for you, give directions, and make sure you're on time for appointments, so we keep this setting **On** by default.</span></span>  <br/> |
|<span data-ttu-id="a98f4-127">Разрешить пользователям получать советы и объявления для Windows от Майкрософт</span><span class="sxs-lookup"><span data-stu-id="a98f4-127">Allow users to receive Windows tips and advertisements from Microsoft</span></span>  <br/> |<span data-ttu-id="a98f4-128">Советы для Windows могут оказаться очень кстати. Они помогают пользователям сориентироваться, когда выпускаются новые возможности.</span><span class="sxs-lookup"><span data-stu-id="a98f4-128">Windows tips can be handy and help orient users when new features are released.</span></span>  <br/> |
|<span data-ttu-id="a98f4-129">Автоматически обновлять устройства с Windows 10</span><span class="sxs-lookup"><span data-stu-id="a98f4-129">Keep Windows 10 devices up to date automatically</span></span>  <br/> |<span data-ttu-id="a98f4-130">Обеспечивает автоматическую установку последних обновлений на устройствах с Windows 10.</span><span class="sxs-lookup"><span data-stu-id="a98f4-130">Makes sure that Windows 10 devices automatically receive the latest updates.</span></span>  <br/> |
   

