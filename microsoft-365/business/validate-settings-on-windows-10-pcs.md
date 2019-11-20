---
title: Проверка параметров защиты приложений на компьютерах с Windows 10
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
search.appverid:
- BCS160
- MET150
ms.assetid: fae8819d-7235-495f-9f07-d016f545887f
description: Узнайте, как проверить параметры защиты Microsoft 365 бизнес-приложений на устройствах с Windows 10.
ms.openlocfilehash: b8793ab7f77bbc7f608f237e2455f6fd12c3bb26
ms.sourcegitcommit: 6a413a65b8c2e10cea08f0a15635b28a1362a582
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/19/2019
ms.locfileid: "38721807"
---
# <a name="validate-device-protection-settings-on-windows-10-pcs"></a><span data-ttu-id="7f853-103">Проверка параметров защиты устройств на компьютерах с Windows 10</span><span class="sxs-lookup"><span data-stu-id="7f853-103">Validate device protection settings on Windows 10 PCs</span></span>

## <a name="verify-that-windows-10-device-policies-are-set"></a><span data-ttu-id="7f853-104">Проверка настройки политик для устройств Windows 10</span><span class="sxs-lookup"><span data-stu-id="7f853-104">Verify that Windows 10 device policies are set</span></span>

<span data-ttu-id="7f853-105">[Применение политик для устройств](protection-settings-for-windows-10-pcs.md) пользователей может занять до нескольких часов после их настройки.</span><span class="sxs-lookup"><span data-stu-id="7f853-105">After you [set up devices policies](protection-settings-for-windows-10-pcs.md), it may take up to a few hours for the policy to take effect on users' devices.</span></span> <span data-ttu-id="7f853-106">Чтобы убедиться в их применении, вы можете просмотреть несколько экранов параметров Windows на устройствах пользователей.</span><span class="sxs-lookup"><span data-stu-id="7f853-106">You can confirm that the policies took effect by looking at various Windows Settings screens on the users' devices.</span></span> <span data-ttu-id="7f853-107">Так как пользователи не смогут изменять параметры Windows Update и антивирусной программы "Защитник Windows" на своих устройствах с Windows 10, многие параметры будут недоступны.</span><span class="sxs-lookup"><span data-stu-id="7f853-107">Because the users won't be able to modify the Windows Update and Windows Defender Antivirus settings on their Windows 10 devices, many options will be grayed out.</span></span>
  
1. <span data-ttu-id="7f853-108">Перейдите к разделу **Параметры** \> **обновления &amp; для системы безопасности** \> **центра обновления** \> Windows **и убедитесь** , что все параметры неактивны.</span><span class="sxs-lookup"><span data-stu-id="7f853-108">Go to **Settings** \> **Update &amp; security** \> **Windows Update** \> **Restart options** and confirm that all settings are grayed out.</span></span> 
    
    ![Все варианты перезапуска выделены серым цветом.](media/31308da9-18b0-47c5-bbf6-d5fa6747c376.png)
  
2. <span data-ttu-id="7f853-110">Перейдите к разделу **Параметры** \> **Обновление &amp; безопасности** \> **Windows Update** \> **Advanced Options** и убедитесь, что все параметры отключены.</span><span class="sxs-lookup"><span data-stu-id="7f853-110">Go to **Settings** \> **Update &amp; security** \> **Windows Update** \> **Advanced options** and confirm that all settings are grayed out.</span></span> 
    
    ![Параметры дополнительных обновлений Windows выделены серым цветом.](media/049cf281-d503-4be9-898b-c0a3286c7fc2.png)
  
3. <span data-ttu-id="7f853-112">Go to **Settings** \> **Update &amp; security** \> **Windows Update** \> **Advanced options** \> **Choose how updates are delivered**.</span><span class="sxs-lookup"><span data-stu-id="7f853-112">Go to **Settings** \> **Update &amp; security** \> **Windows Update** \> **Advanced options** \> **Choose how updates are delivered**.</span></span>
    
    <span data-ttu-id="7f853-113">Подтвердите, что вы видите сообщение (в красном) о том, что некоторые параметры скрыты или управляются вашей организацией, а все параметры выделены серым цветом.</span><span class="sxs-lookup"><span data-stu-id="7f853-113">Confirm that you can see the message (in red) that some settings are hidden or managed by your organization, and all the options are grayed out.</span></span>
    
    ![Choose how updates are delivered page indicates settings are hidden or managed by your organization.](media/6b3e37c5-da41-4afd-9983-b4f406216b59.png)
  
4. <span data-ttu-id="7f853-115">To open the Windows Defender Security Center, go to **Settings** \> **Update &amp; security** \> **Windows Defender** \> click **Open Windows Defender Security Center** \> **Virus &amp; thread protection** \> **Virus &amp; threat protection settings**.</span><span class="sxs-lookup"><span data-stu-id="7f853-115">To open the Windows Defender Security Center, go to **Settings** \> **Update &amp; security** \> **Windows Defender** \> click **Open Windows Defender Security Center** \> **Virus &amp; thread protection** \> **Virus &amp; threat protection settings**.</span></span> 
    
5. <span data-ttu-id="7f853-116">Убедитесь, что все параметры неактивны.</span><span class="sxs-lookup"><span data-stu-id="7f853-116">Verify that all options are grayed out.</span></span> 
    
    ![Параметры защиты от вирусов и угроз выделены серым цветом.](media/9ca68d40-a5d9-49d7-92a4-c581688b5926.png)
  
## <a name="related-topics"></a><span data-ttu-id="7f853-118">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="7f853-118">Related Topics</span></span>

[<span data-ttu-id="7f853-119">Документы и ресурсы по Microsoft 365 Business</span><span class="sxs-lookup"><span data-stu-id="7f853-119">Microsoft 365 Business documentation and resources</span></span>](https://go.microsoft.com/fwlink/p/?linkid=853701)
  
[<span data-ttu-id="7f853-120">Начало работы с Microsoft 365 Business</span><span class="sxs-lookup"><span data-stu-id="7f853-120">Get started with Microsoft 365 Business</span></span>](microsoft-365-business-overview.md)
  
[<span data-ttu-id="7f853-121">Управление Microsoft 365 бизнес</span><span class="sxs-lookup"><span data-stu-id="7f853-121">Manage Microsoft 365 Business</span></span>](manage.md)
  
[<span data-ttu-id="7f853-122">Настройка параметров защиты устройств для компьютеров с Windows 10</span><span class="sxs-lookup"><span data-stu-id="7f853-122">Set device configurations for Windows 10 PCs</span></span>](protection-settings-for-windows-10-pcs.md)
  

