---
title: Управление политиками Skype для бизнеса Online с помощью PowerShell
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/17/2020
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- NOCSH
ms.custom: ''
ms.assetid: ff93a341-6f0f-4f06-9690-726052e1be64
description: Сводка. Использование PowerShell для управления свойствами учетной записи пользователя Skype для бизнеса Online с политиками.
ms.openlocfilehash: 20a75fa1c131f693fcf30d20477af5c9ee7aed35
ms.sourcegitcommit: 22755cebfbfa2c4dc3f8b4f54ccb23636a211ee5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2020
ms.locfileid: "48477045"
---
# <a name="manage-skype-for-business-online-policies-with-powershell"></a><span data-ttu-id="eee08-103">Управление политиками Skype для бизнеса Online с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="eee08-103">Manage Skype for Business Online policies with PowerShell</span></span>

<span data-ttu-id="eee08-104">*Эта статья относится к Microsoft 365 корпоративный и Office 365 корпоративный.*</span><span class="sxs-lookup"><span data-stu-id="eee08-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="eee08-105">Для управления многими свойствами учетной записи пользователя в Skype для бизнеса Online необходимо указать их в качестве свойств политик с помощью PowerShell для Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="eee08-105">To manage many properties of user account for Skype for Business Online, you must specify them as properties of policies with PowerShell for Microsoft 365.</span></span>
  
## <a name="before-you-begin"></a><span data-ttu-id="eee08-106">Перед началом работы</span><span class="sxs-lookup"><span data-stu-id="eee08-106">Before you begin</span></span>

<span data-ttu-id="eee08-107">Чтобы получить настройки для выполнения команд, воспользуйтесь приведенными ниже инструкциями (пропустите выполненные ранее шаги).</span><span class="sxs-lookup"><span data-stu-id="eee08-107">Use these instructions to get set up to run the commands (skip the steps you have already completed):</span></span>

  > [!Note]
  > <span data-ttu-id="eee08-108">В настоящее время Skype для бизнеса Online Connector входит в состав последней версии модуля PowerShell для Teams.</span><span class="sxs-lookup"><span data-stu-id="eee08-108">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span> <span data-ttu-id="eee08-109">Если вы используете последний общедоступный выпуск Teams PowerShell, вам не нужно устанавливать соединитель Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="eee08-109">If you're using the latest Teams PowerShell public release, you don't need to install the Skype for Business Online Connector.</span></span>

1. <span data-ttu-id="eee08-110">Установите [модуль Командная консоль PowerShell](https://docs.microsoft.com/microsoftteams/teams-powershell-install).</span><span class="sxs-lookup"><span data-stu-id="eee08-110">Install the [Teams PowerShell module](https://docs.microsoft.com/microsoftteams/teams-powershell-install).</span></span>
    
2. <span data-ttu-id="eee08-111">Откройте командную строку Windows PowerShell и выполните указанные команды:</span><span class="sxs-lookup"><span data-stu-id="eee08-111">Open a Windows PowerShell command prompt and run the following commands:</span></span> 

   ```powershell
   Import-Module MicrosoftTeams
   $userCredential = Get-Credential
   $sfbSession = New-CsOnlineSession -Credential $userCredential
   Import-PSSession $sfbSession
   ```

   <span data-ttu-id="eee08-112">При поступлении соответствующего запроса системы введите имя и пароль учетной записи администратора Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="eee08-112">When prompted, enter your Skype for Business Online administrator account name and password.</span></span>
    
## <a name="manage-user-account-policies"></a><span data-ttu-id="eee08-113">Управление политиками учетной записи пользователя</span><span class="sxs-lookup"><span data-stu-id="eee08-113">Manage user account policies</span></span>

<span data-ttu-id="eee08-p102">Многие свойства учетной записи пользователя Skype для бизнеса Online настраиваются с помощью политик. Политики  это просто коллекции параметров, которые можно применить к одному или нескольким пользователям. Чтобы рассмотреть настройки политики, можно воспользоваться приведенной ниже командой для политики FederationAndPICDefault в качестве примера:</span><span class="sxs-lookup"><span data-stu-id="eee08-p102">Many Skype for Business Online user account properties are configured by using policies. Policies are simply collections of settings that can be applied to one or more users. To take a look at how the a policy has been configured, you can run this example command for the FederationAndPICDefault policy:</span></span>
  
```powershell
Get-CsExternalAccessPolicy -Identity "FederationAndPICDefault"
```

<span data-ttu-id="eee08-117">В ответ вы должны получить что-то вроде этого:</span><span class="sxs-lookup"><span data-stu-id="eee08-117">In turn, you should get back something similar to this:</span></span>
  
```powershell
Identity                          : Tag:FederationAndPICDefault
Description                       :
EnableFederationAccess            : True
EnableXmppAccess                  : False
EnablePublicCloudAccess           : True
EnablePublicCloudAudioVideoAccess : True
EnableOutsideAccess               : True
```

<span data-ttu-id="eee08-118">В приведенном примере значения в этих политиках определяют, что именно может делать пользователь в отношении обмена данными с федеративными пользователями.</span><span class="sxs-lookup"><span data-stu-id="eee08-118">In this example, the values within this policy determine what a use can or cannot do when it comes to communicating with federated users.</span></span> <span data-ttu-id="eee08-119">Например, для свойства EnableOutsideAccess необходимо задать значение True, чтобы пользователь мог обмениваться данными с пользователями вне организации.</span><span class="sxs-lookup"><span data-stu-id="eee08-119">For example, the EnableOutsideAccess property must be set to True for a user to be able to communicate with people outside the organization.</span></span> <span data-ttu-id="eee08-120">Обратите внимание, что это свойство не отображается в центре администрирования Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="eee08-120">Note that this property does not appear in the Microsoft 365 admin center.</span></span> <span data-ttu-id="eee08-121">Вместо этого для него автоматически устанавливается значение True или False на основе значений, выбранных для других свойств.</span><span class="sxs-lookup"><span data-stu-id="eee08-121">Instead, the property is automatically set to True or False based on the other selections that you make.</span></span> <span data-ttu-id="eee08-122">Ниже описаны два других интересующих нас свойства:</span><span class="sxs-lookup"><span data-stu-id="eee08-122">The other two properties of interest are:</span></span>
  
- <span data-ttu-id="eee08-123">Свойство **EnableFederationAccess** указывает, может ли пользователь обмениваться данными с пользователями из федеративных доменов.</span><span class="sxs-lookup"><span data-stu-id="eee08-123">**EnableFederationAccess** indicates whether the user can communicate with people from federated domains.</span></span>
    
- <span data-ttu-id="eee08-124">Свойство **EnablePublicCloudAccess** указывает, может ли пользователь обмениваться данными с пользователями Windows Live.</span><span class="sxs-lookup"><span data-stu-id="eee08-124">**EnablePublicCloudAccess** indicates whether the user can communicate with Windows Live users.</span></span>
    
<span data-ttu-id="eee08-p104">Следовательно, вы не изменяете свойства учетной записи пользователя, связанные с федерацией (например, **Set-CsUser -EnableFederationAccess $True**). Вместо этого вы назначаете пользователю политику внешнего доступа с предварительно настроенными значениями необходимых свойств. Чтобы пользователь смог обмениваться данными с федеративными пользователями и пользователями Windows Live, ему нужно назначить политику, разрешающую такой обмен данными.</span><span class="sxs-lookup"><span data-stu-id="eee08-p104">Therefore, you don't directly change federation-related properties on user accounts (for example, **Set-CsUser -EnableFederationAccess $True**). Instead, you assign an account an external access policy that has the desired property values preconfigured. If we want a user to be able to communicate with federated users and with Windows Live users, that user account must be assigned a policy that allows those types of communication.</span></span>
  
<span data-ttu-id="eee08-128">Чтобы узнать, может ли пользователь обмениваться данными с пользователями вне организации, необходимо выполнить следующие действия:</span><span class="sxs-lookup"><span data-stu-id="eee08-128">If you want to know whether or not someone can communicate with users from outside the organization, you have to:</span></span>
  
- <span data-ttu-id="eee08-129">Определить, какая политика внешнего доступа назначена этому пользователю.</span><span class="sxs-lookup"><span data-stu-id="eee08-129">Determine which external access policy has been assigned to that user.</span></span>
    
- <span data-ttu-id="eee08-130">Определить, какие возможности разрешает или запрещает эта политика.</span><span class="sxs-lookup"><span data-stu-id="eee08-130">Determine which capabilities are or are not allowed by that policy.</span></span>
    
<span data-ttu-id="eee08-131">Для этого можно воспользоваться указанной командой.</span><span class="sxs-lookup"><span data-stu-id="eee08-131">For example, you can do that by using this command:</span></span>
  
```powershell
Get-CsOnlineUser -Identity "Alex Darrow" | ForEach {Get-CsExternalAccessPolicy -Identity $_.ExternalAccessPolicy}
```

<span data-ttu-id="eee08-132">Эта команда находит политику, назначенную пользователю, а затем находит возможности, которые включены или отключены в этой политике.</span><span class="sxs-lookup"><span data-stu-id="eee08-132">This command finds the policy assigned to the user, then finds the capabilities enabled or disabled within that policy.</span></span>
  
<span data-ttu-id="eee08-133">Для управления политиками Skype для бизнеса Online с помощью PowerShell обратитесь к командлетам для:</span><span class="sxs-lookup"><span data-stu-id="eee08-133">To manage Skype for Business Online policies with PowerShell, see the cmdlets for:</span></span>

- <span data-ttu-id="eee08-134">[Client policy](https://docs.microsoft.com/previous-versions//mt228132(v=technet.10)#client-policy-cmdlets) (Политика клиента).</span><span class="sxs-lookup"><span data-stu-id="eee08-134">[Client policy](https://docs.microsoft.com/previous-versions//mt228132(v=technet.10)#client-policy-cmdlets)</span></span>
- <span data-ttu-id="eee08-135">[Политика конференц-связи](https://docs.microsoft.com/previous-versions//mt228132(v=technet.10)#conferencing-policy-cmdlets),</span><span class="sxs-lookup"><span data-stu-id="eee08-135">[Conferencing policy](https://docs.microsoft.com/previous-versions//mt228132(v=technet.10)#conferencing-policy-cmdlets)</span></span>
- <span data-ttu-id="eee08-136">[Политика для мобильных устройств](https://docs.microsoft.com/previous-versions//mt228132(v=technet.10)#mobile-policy-cmdlets)</span><span class="sxs-lookup"><span data-stu-id="eee08-136">[Mobile policy](https://docs.microsoft.com/previous-versions//mt228132(v=technet.10)#mobile-policy-cmdlets)</span></span>
- <span data-ttu-id="eee08-137">[Политика сетевой голосовой почты](https://docs.microsoft.com/previous-versions//mt228132(v=technet.10)#online-voicemail-policy-cmdlets)</span><span class="sxs-lookup"><span data-stu-id="eee08-137">[Online Voicemail policy](https://docs.microsoft.com/previous-versions//mt228132(v=technet.10)#online-voicemail-policy-cmdlets)</span></span>
- <span data-ttu-id="eee08-138">[Политика маршрутизации голосовой связи](https://docs.microsoft.com/previous-versions//mt228132(v=technet.10)#voice-routing-policy-cmdlets)</span><span class="sxs-lookup"><span data-stu-id="eee08-138">[Voice Routing policy](https://docs.microsoft.com/previous-versions//mt228132(v=technet.10)#voice-routing-policy-cmdlets)</span></span>


> [!NOTE]
> <span data-ttu-id="eee08-p105">Абонентская группа Skype для бизнеса Online  это политика во всех отношениях, кроме имени. Название "абонентская группа" выбрано вместо других названий (скажем, "политика набора") для обеспечения обратной совместимости с Office Communications Server и Exchange.</span><span class="sxs-lookup"><span data-stu-id="eee08-p105">A Skype for Business Online dial plan is a policy in every respect except the name. The name "dial plan" was chosen instead of, say, "dialing policy" in order to provide backward compatibility with Office Communications Server and with Exchange.</span></span> 
  
<span data-ttu-id="eee08-141">Например, чтобы просмотреть все доступные политики голосовой связи, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="eee08-141">For example, to look at all the voice policies available for your use, run this command:</span></span>
  
```powershell
Get-CsVoicePolicy
```

> [!NOTE]
> <span data-ttu-id="eee08-p106">Будет возвращен список всех доступных политик голосовой связи. Однако имейте в виду, что пользователям нельзя назначить некоторые политики. Это связано с различными ограничениями в отношении [места лицензирования и использования](https://msdn.microsoft.com/library/azure/dn194136.aspx). Чтобы узнать, какие политики внешнего доступа и конференций можно назначить пользователю, выполните команды, похожие на следующие:</span><span class="sxs-lookup"><span data-stu-id="eee08-p106">That returns a list of all the voice policies available to you. Keep in mind, however, that not all policies can be assigned to all users. This is due to various restrictions involving licensing and geographic location. (The so-called "[usage location](https://msdn.microsoft.com/library/azure/dn194136.aspx).") If you want to know the external access policies and the conferencing policies that can be assigned to a particular user, use commands similar to these:</span></span> 

```powershell
Get-CsConferencingPolicy -ApplicableTo "Alex Darrow"
Get-CsExternalAccessPolicy -ApplicableTo "Alex Darrow"
```

<span data-ttu-id="eee08-p107">Параметр ApplicableTo ограничивает данные, возвращаемые политиками, которые можно назначить указанному пользователю (например, Семену Маслову). В зависимости от ограничений в отношении лицензирования и места использования он может представлять подмножество всех доступных политик.</span><span class="sxs-lookup"><span data-stu-id="eee08-p107">The ApplicableTo parameter limits the returned data to policies that can be assigned to the specified user (for example, Alex Darrow). Depending on licensing and usage location restrictions, that might represent a subset of all the available policies.</span></span> 
  
<span data-ttu-id="eee08-148">В некоторых случаях свойства политик не используются в Microsoft 365, а другие могут управляться только сотрудниками службы поддержки Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="eee08-148">In some cases, properties of policies are not used with Microsoft 365, while others can only be managed by Microsoft support personnel.</span></span> 
  
<span data-ttu-id="eee08-p108">С Skype для бизнеса Online для управления пользователями необходимо использовать какую-либо политику. Если допустимое свойство, связанное с политикой, является пустым, значит, для управления рассматриваемым пользователем используется глобальная политика, т. е. политика, которая автоматически применяется к пользователю, если ему не назначена специальная индивидуальная политика. Управление пользователями, которым не назначена политика клиента, осуществляется с помощью глобальной политики. Определить глобальную политику клиента поможет приведенная ниже команда.</span><span class="sxs-lookup"><span data-stu-id="eee08-p108">With Skype for Business Online, users must be managed by a policy of some kind. If a valid policy-related property is blank, that means that the user in question is being managed by a global policy, which is a policy that is automatically applied to a user unless he or she is specifically assigned a per-user policy. Because we don't see a client policy listed for a user account, it is managed by the global policy. You can determine the global client policy with this command:</span></span>
  
```powershell
Get-CsClientPolicy -Identity "Global"
```

## <a name="see-also"></a><span data-ttu-id="eee08-153">См. также</span><span class="sxs-lookup"><span data-stu-id="eee08-153">See also</span></span>

[<span data-ttu-id="eee08-154">Управление Skype для бизнеса Online с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="eee08-154">Manage Skype for Business Online with PowerShell</span></span>](manage-skype-for-business-online-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="eee08-155">Управление Microsoft 365 с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="eee08-155">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="eee08-156">Начало работы с PowerShell для Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="eee08-156">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)

