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
ms.openlocfilehash: 85448507835b6310ca4136849be6a40caf6bb919
ms.sourcegitcommit: abf63669daf12993ad3353e4b578f41c8910b20f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/27/2020
ms.locfileid: "47289084"
---
# <a name="secure-windows-10-devices"></a><span data-ttu-id="ed719-103">Защита устройств с Windows 10</span><span class="sxs-lookup"><span data-stu-id="ed719-103">Secure Windows 10 devices</span></span>

<span data-ttu-id="ed719-104">Эта статья относится к Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="ed719-104">This article applies to Microsoft 365 Business Premium.</span></span>

<span data-ttu-id="ed719-105">Описанные в этой статье параметры входят в стандартную политику для устройств с Windows 10.</span><span class="sxs-lookup"><span data-stu-id="ed719-105">The settings that you configure here are part of the default device policy for Windows 10.</span></span> <span data-ttu-id="ed719-106">Все пользователи, которые подключаются к устройству Windows 10, в том числе к мобильным устройствам и ПК, при входе с использованием своей рабочей учетной записи будут автоматически получать эти параметры.</span><span class="sxs-lookup"><span data-stu-id="ed719-106">All users who connect a Windows 10 device, including mobile devices and PCs, by signing in with their work account will automatically receive these settings.</span></span> <span data-ttu-id="ed719-107">Советуем во время настройки принять стандартную конфигурацию, а политики, предназначенные для определенных групп пользователей добавить позднее.</span><span class="sxs-lookup"><span data-stu-id="ed719-107">We recommend that you accept the default policy during setup and add policies later that target specific groups of users.</span></span>
  
## <a name="settings-to-secure-windows-10-devices"></a><span data-ttu-id="ed719-108">Параметры для защиты устройств с Windows 10</span><span class="sxs-lookup"><span data-stu-id="ed719-108">Settings to secure Windows 10 devices</span></span>

<span data-ttu-id="ed719-p102">Все параметры **включены** по умолчанию. Доступны следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="ed719-p102">By default all settings are **On**. The following settings are available:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="ed719-111">Setting</span><span class="sxs-lookup"><span data-stu-id="ed719-111">Setting</span></span>  <br/> |<span data-ttu-id="ed719-112">Описание</span><span class="sxs-lookup"><span data-stu-id="ed719-112">Description</span></span>  <br/> |
|<span data-ttu-id="ed719-113">Использование антивирусной программы "Защитник Windows"</span><span class="sxs-lookup"><span data-stu-id="ed719-113">Help protect PCs from viruses and other threats using Windows Defender Antivirus</span></span>  <br/> |<span data-ttu-id="ed719-114">Требует включения антивирусной программы "Защитник Windows" для защиты компьютеров, подключенных к Интернету.</span><span class="sxs-lookup"><span data-stu-id="ed719-114">Requires that Windows Defender Antivirus is turned on to protect PCs from the dangers of being connected to the internet.</span></span>  <br/> |
|<span data-ttu-id="ed719-115">Защитите компьютеры от угроз из Интернета в Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="ed719-115">Help protect PCs from web-based threats in Microsoft Edge</span></span>  <br/> |<span data-ttu-id="ed719-116">Включает параметры в Microsoft Edge, которые помогают защитить пользователей от вредоносных сайтов и скачиваний.</span><span class="sxs-lookup"><span data-stu-id="ed719-116">Turns on settings in Edge that help protect users from malicious sites and downloads.</span></span>  <br/> |
|<span data-ttu-id="ed719-117">Защитить файлы и папки на компьютерах от несанкционированного доступа с помощью BitLocker</span><span class="sxs-lookup"><span data-stu-id="ed719-117">Help protect files and folders on PCs from unauthorized access with BitLocker</span></span>  <br/> |<span data-ttu-id="ed719-118">BitLocker защищает данные путем шифрования жестких дисков компьютера и защиты от риска потери данных в случае потери или кражи компьютера.</span><span class="sxs-lookup"><span data-stu-id="ed719-118">Bitlocker protects data by encrypting the computer hard drives and protect against data exposure if a computer is lost or stolen.</span></span> <span data-ttu-id="ed719-119">Дополнительные сведения можно найти в статье [вопросы и ответы по BitLocker](https://go.microsoft.com/fwlink/?linkid=871000).</span><span class="sxs-lookup"><span data-stu-id="ed719-119">For more information, see [Bitlocker FAQ](https://go.microsoft.com/fwlink/?linkid=871000).</span></span>  <br/> |
|<span data-ttu-id="ed719-120">Выключать экран устройства, если оно неактивно в течение указанного периода времени</span><span class="sxs-lookup"><span data-stu-id="ed719-120">Turn off device screen when idle for this amount of time</span></span>  <br/> |<span data-ttu-id="ed719-p104">Обеспечивает защиту корпоративных данных, когда пользователь неактивен. Пользователь может работать в общественном месте, например кафе, и на короткое время отойти или отвлечься. При этом посторонние могут случайно увидеть сведения на экране. Этот параметр управляет временем, на протяжении которого пользователь может оставаться неактивным, прежде чем экран выключится.</span><span class="sxs-lookup"><span data-stu-id="ed719-p104">Makes sure that company data is protected if a user is idle. A user may be working in a public location, like a coffee shop, and step away or be distracted for just a moment, leaving their device vulnerable to random glances. This setting lets you control how long the user can be idle before the screen shuts off.</span></span>  <br/> |
|