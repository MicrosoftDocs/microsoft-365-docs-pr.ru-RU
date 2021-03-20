---
title: Проверка параметров защиты приложений на компьютерах с Windows 10
f1.keywords:
- NOCSH
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
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
ms.assetid: fae8819d-7235-495f-9f07-d016f545887f
description: Узнайте, как убедиться, что параметры microsoft 365 для защиты бизнес-приложений вступили в силу на устройствах Windows 10 пользователей.
ms.openlocfilehash: ff99b3a4fce49aebdb5c72f51e46678a7821e186
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50912421"
---
# <a name="validate-device-protection-settings-on-windows-10-pcs"></a><span data-ttu-id="37089-103">Проверка параметров защиты устройств на компьютерах с Windows 10</span><span class="sxs-lookup"><span data-stu-id="37089-103">Validate device protection settings on Windows 10 PCs</span></span>

## <a name="verify-that-windows-10-device-policies-are-set"></a><span data-ttu-id="37089-104">Проверка настройки политик для устройств Windows 10</span><span class="sxs-lookup"><span data-stu-id="37089-104">Verify that Windows 10 device policies are set</span></span>

<span data-ttu-id="37089-105">[Применение политик для устройств](protection-settings-for-windows-10-pcs.md) пользователей может занять до нескольких часов после их настройки.</span><span class="sxs-lookup"><span data-stu-id="37089-105">After you [set up devices policies](protection-settings-for-windows-10-pcs.md), it may take up to a few hours for the policy to take effect on users' devices.</span></span> <span data-ttu-id="37089-106">Чтобы убедиться в их применении, вы можете просмотреть несколько экранов параметров Windows на устройствах пользователей.</span><span class="sxs-lookup"><span data-stu-id="37089-106">You can confirm that the policies took effect by looking at various Windows Settings screens on the users' devices.</span></span> <span data-ttu-id="37089-107">Так как пользователи не смогут изменять параметры Обновления Windows и Защитник Windows антивирусов на своих устройствах с Windows 10, многие параметры будут отсеяно.</span><span class="sxs-lookup"><span data-stu-id="37089-107">Because the users won't be able to modify the Windows Update and Windows Defender Antivirus settings on their Windows 10 devices, many options will be grayed out.</span></span>
  
1. <span data-ttu-id="37089-108">**Перезапустите** параметры обновления безопасности Windows и подтвердите, что все \> **&amp;** \>  \>  параметры серые.</span><span class="sxs-lookup"><span data-stu-id="37089-108">Go to **Settings** \> **Update &amp; security** \> **Windows Update** \> **Restart options** and confirm that all settings are grayed out.</span></span> 
    
    ![Все параметры перезапуска серые.](../media/31308da9-18b0-47c5-bbf6-d5fa6747c376.png)
  
2. <span data-ttu-id="37089-110">Перейдите **к параметрам** Обновления \> **&amp; безопасности** Windows \> **Update** \> **Расширенные параметры** и подтвердив, что все параметры серые.</span><span class="sxs-lookup"><span data-stu-id="37089-110">Go to **Settings** \> **Update &amp; security** \> **Windows Update** \> **Advanced options** and confirm that all settings are grayed out.</span></span> 
    
    ![Параметры windows Advanced updates все серые.](../media/049cf281-d503-4be9-898b-c0a3286c7fc2.png)
  
3. <span data-ttu-id="37089-112">Go to **Settings** \> **Update &amp; security** \> **Windows Update** \> **Advanced options** \> **Choose how updates are delivered**.</span><span class="sxs-lookup"><span data-stu-id="37089-112">Go to **Settings** \> **Update &amp; security** \> **Windows Update** \> **Advanced options** \> **Choose how updates are delivered**.</span></span>
    
    <span data-ttu-id="37089-113">Подтвердите, что вы можете увидеть сообщение (красным цветом) о том, что некоторые параметры скрыты или управляются организацией, и все параметры серые.</span><span class="sxs-lookup"><span data-stu-id="37089-113">Confirm that you can see the message (in red) that some settings are hidden or managed by your organization, and all the options are grayed out.</span></span>
    
    ![Choose how updates are delivered page indicates settings are hidden or managed by your organization.](../media/6b3e37c5-da41-4afd-9983-b4f406216b59.png)
  
4. <span data-ttu-id="37089-115">To open the Windows Defender Security Center, go to **Settings** \> **Update &amp; security** \> **Windows Defender** \> click **Open Windows Defender Security Center** \> **Virus &amp; thread protection** \> **Virus &amp; threat protection settings**.</span><span class="sxs-lookup"><span data-stu-id="37089-115">To open the Windows Defender Security Center, go to **Settings** \> **Update &amp; security** \> **Windows Defender** \> click **Open Windows Defender Security Center** \> **Virus &amp; thread protection** \> **Virus &amp; threat protection settings**.</span></span> 
    
5. <span data-ttu-id="37089-116">Убедитесь, что все параметры серые.</span><span class="sxs-lookup"><span data-stu-id="37089-116">Verify that all options are grayed out.</span></span> 
    
    ![Параметры защиты от вирусов и угроз серые.](../media/9ca68d40-a5d9-49d7-92a4-c581688b5926.png)
  
## <a name="related-topics"></a><span data-ttu-id="37089-118">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="37089-118">Related Topics</span></span>

[<span data-ttu-id="37089-119">Microsoft 365 для бизнес-документации и ресурсов</span><span class="sxs-lookup"><span data-stu-id="37089-119">Microsoft 365 for business documentation and resources</span></span>](./index.yml)
  
[<span data-ttu-id="37089-120">Начало работы с Microsoft 365 для бизнеса</span><span class="sxs-lookup"><span data-stu-id="37089-120">Get started with Microsoft 365 for business</span></span>](microsoft-365-business-overview.md)
  
[<span data-ttu-id="37089-121">Управление Microsoft 365 для бизнеса</span><span class="sxs-lookup"><span data-stu-id="37089-121">Manage Microsoft 365 for business</span></span>](manage.md)
  
[<span data-ttu-id="37089-122">Настройка параметров защиты устройств для компьютеров с Windows 10</span><span class="sxs-lookup"><span data-stu-id="37089-122">Set device configurations for Windows 10 PCs</span></span>](protection-settings-for-windows-10-pcs.md)
