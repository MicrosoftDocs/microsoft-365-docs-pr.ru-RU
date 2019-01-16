---
title: Защита устройств с Windows 10
ms.author: sirkkuw
author: sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: overview
f1_keywords:
- O365E_BCSSetup4WindowsConfig
ms.service: o365-administration
localization_priority: Normal
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 21e5551f-fa35-4f13-9418-f80d668b6a2b
description: 'Описание по умолчанию и других параметров для обеспечения безопасности устройств Windows 10. '
ms.openlocfilehash: 0bdf6a56d880cb84f4a4f50550539d97c006ba49
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/16/2019
ms.locfileid: "26870997"
---
# <a name="secure-windows-10-devices"></a><span data-ttu-id="1ea48-103">Защита устройств с Windows 10</span><span class="sxs-lookup"><span data-stu-id="1ea48-103">Secure Windows 10 devices</span></span>

<span data-ttu-id="1ea48-p101">Описанные в этой статье параметры входят в стандартную политику для устройств с Windows 10. Эти настройки автоматически получают все пользователи, которые входят в систему с помощью своей рабочей учетной записи на устройстве с Windows 10 (мобильном устройстве или компьютере) и таким образом подключают его к организации. Советуем во время настройки принять стандартную конфигурацию, а политики, предназначенные для определенных групп пользователей добавить позднее.</span><span class="sxs-lookup"><span data-stu-id="1ea48-p101">The settings that you configure here are part of the default device policy for Windows 10. All users that connect a Windows 10 device, including mobile devices and PCs, by signing in with their work account, will automatically receive these settings. We recommend that you accept the default policy during setup and add policies later that target specific groups of users.</span></span>
  
## <a name="settings-to-secure-windows-10-devices"></a><span data-ttu-id="1ea48-107">Параметры для защиты устройств с Windows 10</span><span class="sxs-lookup"><span data-stu-id="1ea48-107">Settings to secure Windows 10 devices</span></span>

<span data-ttu-id="1ea48-p102">Все параметры **включены** по умолчанию. Доступны следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="1ea48-p102">By default all settings are **On**. The following settings are available:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="1ea48-110">Параметр</span><span class="sxs-lookup"><span data-stu-id="1ea48-110">Setting</span></span>  <br/> |<span data-ttu-id="1ea48-111">Описание</span><span class="sxs-lookup"><span data-stu-id="1ea48-111">Description</span></span>  <br/> |
|<span data-ttu-id="1ea48-112">Использование антивирусной программы "Защитник Windows"</span><span class="sxs-lookup"><span data-stu-id="1ea48-112">Help protect PCs from viruses and other threats using Windows Defender Antivirus</span></span>  <br/> |<span data-ttu-id="1ea48-113">Требует включения антивирусной программы "Защитник Windows" для защиты компьютеров, подключенных к Интернету.</span><span class="sxs-lookup"><span data-stu-id="1ea48-113">Requires that Windows Defender Antivirus is turned on to protect PCs from the dangers of being connected to the internet.</span></span>  <br/> |
|<span data-ttu-id="1ea48-114">Защитите компьютеры от угроз из Интернета в Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="1ea48-114">Help protect PCs from web-based threats in Microsoft Edge</span></span>  <br/> |<span data-ttu-id="1ea48-115">Включает параметры в Microsoft Edge, которые помогают защитить пользователей от вредоносных сайтов и скачиваний.</span><span class="sxs-lookup"><span data-stu-id="1ea48-115">Turns on settings in Edge that help protect users from malicious sites and downloads.</span></span>  <br/> |
|<span data-ttu-id="1ea48-116">Выключать экран устройства, если оно неактивно в течение указанного периода времени</span><span class="sxs-lookup"><span data-stu-id="1ea48-116">Turn off device screen when idle for this amount of time</span></span>  <br/> |<span data-ttu-id="1ea48-p103">Обеспечивает защиту корпоративных данных, когда пользователь неактивен. Пользователь может работать в общественном месте, например кафе, и на короткое время отойти или отвлечься. При этом посторонние могут случайно увидеть сведения на экране. Этот параметр управляет временем, на протяжении которого пользователь может оставаться неактивным, прежде чем экран выключится.</span><span class="sxs-lookup"><span data-stu-id="1ea48-p103">Makes sure that company data is protected if a user is idle. A user may be working in a public location, like a coffee shop, and step away or be distracted for just a moment, leaving their device vulnerable to random glances. This setting lets you control how long the user can be idle before the screen shuts off.</span></span>  <br/> |
|<span data-ttu-id="1ea48-120">Разрешить пользователям скачивать приложения из Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="1ea48-120">Allow users to download apps from Microsoft Store</span></span>  <br/> |<span data-ttu-id="1ea48-p104">Позволяет пользователям скачивать и устанавливать приложения из Microsoft Store. Это касается любых приложений, от инструментов для повышения производительности до игр, поэтому этот параметр **включен**, но его можно отключить, чтобы обеспечить дополнительную защиту.  </span><span class="sxs-lookup"><span data-stu-id="1ea48-p104">Lets users download and install apps from the Microsoft Store. Apps include everything from games to productivity tools, so we leave this setting **On**, but you can turn it off for extra security.  </span></span><br/> |
|<span data-ttu-id="1ea48-123">Разрешить пользователям доступ к Кортане</span><span class="sxs-lookup"><span data-stu-id="1ea48-123">Allow users to access Cortana</span></span>  <br/> |<span data-ttu-id="1ea48-p105">Кортана может быть очень полезной. Она умеет включать и отключать для вас параметры, давать рекомендации или следить, чтобы вы не пропустили назначенные встречи, поэтому этот параметр **включен** по умолчанию.  </span><span class="sxs-lookup"><span data-stu-id="1ea48-p105">Cortana can be very helpful! She can turn settings on or off for you, give directions, and make sure you're on time for appointments, so we keep this **On** by default.  </span></span><br/> |
|<span data-ttu-id="1ea48-126">Разрешить пользователям получать советы и объявления для Windows от Майкрософт</span><span class="sxs-lookup"><span data-stu-id="1ea48-126">Allow users to receive Windows tips and advertisements from Microsoft</span></span>  <br/> |<span data-ttu-id="1ea48-127">Советы для Windows могут оказаться очень кстати. Они помогают пользователям сориентироваться, когда выпускаются новые возможности.</span><span class="sxs-lookup"><span data-stu-id="1ea48-127">Windows tips can be handy and help orient users when new features are released.</span></span>  <br/> |
|<span data-ttu-id="1ea48-128">Автоматически обновлять устройства с Windows 10</span><span class="sxs-lookup"><span data-stu-id="1ea48-128">Keep Windows 10 devices up to date automatically</span></span>  <br/> |<span data-ttu-id="1ea48-129">Обеспечивает автоматическую установку последних обновлений на устройствах с Windows 10.</span><span class="sxs-lookup"><span data-stu-id="1ea48-129">Makes sure that Windows 10 devices automatically receive the latest updates.</span></span>  <br/> |
   

