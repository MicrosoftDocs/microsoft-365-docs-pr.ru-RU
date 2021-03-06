---
title: Назначение политик Skype для бизнеса в Интернете с помощью PowerShell для Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/16/2020
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
ms.assetid: 36743c86-46c2-46be-b9ed-ad9d4e85d186
description: Сводка. Используйте PowerShell для Microsoft 365 для назначения параметров связи для каждого пользователя с помощью политик Skype для бизнеса Online.
ms.openlocfilehash: 6ee237e5d2ee0c9f472f372a6aa66c9612336265
ms.sourcegitcommit: babbba2b5bf69fd3facde2905ec024b753dcd1b3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2021
ms.locfileid: "50514984"
---
# <a name="assign-per-user-skype-for-business-online-policies-with-powershell-for-microsoft-365"></a><span data-ttu-id="2b8bc-103">Назначение политик Skype для бизнеса в Интернете с помощью PowerShell для Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="2b8bc-103">Assign per-user Skype for Business Online policies with PowerShell for Microsoft 365</span></span>

<span data-ttu-id="2b8bc-104">*Эта статья относится к Microsoft 365 корпоративный и Office 365 корпоративный.*</span><span class="sxs-lookup"><span data-stu-id="2b8bc-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="2b8bc-105">Использование PowerShell для Microsoft 365 — это эффективный способ назначения параметров связи для каждого пользователя с помощью политик Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="2b8bc-105">Using PowerShell for Microsoft 365 is an efficient way to assign per-user communication settings with Skype for Business Online policies.</span></span>
  
## <a name="prepare-to-run-the-powershell-commands"></a><span data-ttu-id="2b8bc-106">Подготовка к запуску команд PowerShell</span><span class="sxs-lookup"><span data-stu-id="2b8bc-106">Prepare to run the PowerShell commands</span></span>

<span data-ttu-id="2b8bc-107">Чтобы получить настройки для выполнения команд, воспользуйтесь приведенными ниже инструкциями (пропустите выполненные ранее шаги).</span><span class="sxs-lookup"><span data-stu-id="2b8bc-107">Use these instructions to get set up to run the commands (skip the steps you have already completed):</span></span>
  
  > [!Note]
   > <span data-ttu-id="2b8bc-108">Соединитель Skype для бизнеса Online в настоящее время является частью последнего модуля Teams PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2b8bc-108">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span> <span data-ttu-id="2b8bc-109">Если вы используете последний общедоступный выпуск Teams PowerShell, вам не нужно устанавливать соединитель Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="2b8bc-109">If you're using the latest Teams PowerShell public release, you don't need to install the Skype for Business Online Connector.</span></span>

1. <span data-ttu-id="2b8bc-110">Установите модуль [Teams PowerShell.](https://docs.microsoft.com/microsoftteams/teams-powershell-install)</span><span class="sxs-lookup"><span data-stu-id="2b8bc-110">Install the [Teams PowerShell module](https://docs.microsoft.com/microsoftteams/teams-powershell-install).</span></span>
    
2. <span data-ttu-id="2b8bc-111">Откройте командную строку Windows PowerShell и выполните указанные команды:</span><span class="sxs-lookup"><span data-stu-id="2b8bc-111">Open a Windows PowerShell command prompt and run the following commands:</span></span> 
    
   ```powershell
   Import-Module MicrosoftTeams
   Connect-MicrosoftTeams
   ```

   <span data-ttu-id="2b8bc-112">При поступлении соответствующего запроса системы введите имя и пароль учетной записи администратора Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="2b8bc-112">When prompted, enter your Skype for Business Online administrator account name and password.</span></span>
    
## <a name="updating-external-communication-settings-for-a-user-account"></a><span data-ttu-id="2b8bc-113">Обновление параметров внешней связи для учетной записи пользователя</span><span class="sxs-lookup"><span data-stu-id="2b8bc-113">Updating external communication settings for a user account</span></span>

<span data-ttu-id="2b8bc-p102">Предположим, вы решили изменить параметры внешней связи для учетной записи пользователя. Например, необходимо разрешить Семену связываться с федеративными пользователями (задав для свойства EnableFederationAccess значение True) и запретить обмениваться данными с пользователями Windows Live (установив для политики EnablePublicCloudAccess значение False). Для этого необходимо выполнить два действия:</span><span class="sxs-lookup"><span data-stu-id="2b8bc-p102">Suppose you want to change external communication settings on a user account. For example, you want to allow Alex to communicate with federated users (EnableFederationAccess is equal to True) but not with Windows Live users (EnablePublicCloudAccess equals False). To do that, you need to do two things:</span></span>
  
1. <span data-ttu-id="2b8bc-117">найти политику внешнего доступа, которая отвечает нашим критериям;</span><span class="sxs-lookup"><span data-stu-id="2b8bc-117">Find an external access policy that meets our criteria.</span></span>
    
2. <span data-ttu-id="2b8bc-118">назначить эту политику внешнего доступа пользователю Семену.</span><span class="sxs-lookup"><span data-stu-id="2b8bc-118">Assign that external access policy to Alex.</span></span>
    
<span data-ttu-id="2b8bc-119">Как определить, какую политику внешнего доступа назначить Алекс?</span><span class="sxs-lookup"><span data-stu-id="2b8bc-119">How do you determine which external access policy to assign Alex?</span></span> <span data-ttu-id="2b8bc-120">Приведенная ниже команда возвращает все политики внешнего доступа, в которых для свойства EnableFederationAccess и политики EnablePublicCloudAccess заданы значения "True" и "False" соответственно.</span><span class="sxs-lookup"><span data-stu-id="2b8bc-120">The following command returns all the external access policies where EnableFederationAccess is set to True and EnablePublicCloudAccess is set to False:</span></span>
  
```powershell
Get-CsExternalAccessPolicy -Include All| Where-Object {$_.EnableFederationAccess -eq $True -and $_.EnablePublicCloudAccess -eq $False}
```

<span data-ttu-id="2b8bc-121">Если вы не создали настраиваемые экземпляры ExternalAccessPolicy, эта команда возвращает одну политику, которая соответствует нашим критериям (FederationOnly).</span><span class="sxs-lookup"><span data-stu-id="2b8bc-121">Unless you have created any custom instances of ExternalAccessPolicy, that command returns one policy that meets our criteria (FederationOnly).</span></span> <span data-ttu-id="2b8bc-122">Вот пример:</span><span class="sxs-lookup"><span data-stu-id="2b8bc-122">Here is an example:</span></span>
  
```powershell
Identity                          : Tag:FederationOnly
Description                       :
EnableFederationAccess            : True
EnableXmppAccess                  : False
EnablePublicCloudAccess           : False
EnablePublicCloudAudioVideoAccess : False
EnableOutsideAccess               : True
```

<span data-ttu-id="2b8bc-p105">Теперь мы знаем, какую политику назначить пользователю Семену, и сделаем это с помощью командлета [Grant-CsExternalAccessPolicy](https://go.microsoft.com/fwlink/?LinkId=523974). Ниже приведен пример.</span><span class="sxs-lookup"><span data-stu-id="2b8bc-p105">Now that you know which policy to assign to Alex, we can assign that policy by using the [Grant-CsExternalAccessPolicy](https://go.microsoft.com/fwlink/?LinkId=523974) cmdlet. Here is an example:</span></span>
  
```powershell
Grant-CsExternalAccessPolicy -Identity "Alex Darrow" -PolicyName "FederationOnly"
```

<span data-ttu-id="2b8bc-125">Назначить политику очень просто: нужно всего лишь указать идентификатор пользователя и имя назначаемой политики.</span><span class="sxs-lookup"><span data-stu-id="2b8bc-125">Assigning a policy is pretty simple: you simply specify the Identity of the user and the name of the policy to be assigned.</span></span> 
  
<span data-ttu-id="2b8bc-p106">Что касается политик и их назначений, можно одновременно работать с несколькими учетными записями пользователей. Например, предположим, что вам нужен список всех пользователей, которым разрешено обмениваться данными с федеративными партнерами и пользователями Windows Live. Мы уже знаем, что этим пользователям назначена политика доступа к внешним пользователям FederationAndPICDefault. Благодаря этому мы можем вернуть список всех этих пользователей, выполнив одну простую команду, которая приведена ниже.</span><span class="sxs-lookup"><span data-stu-id="2b8bc-p106">And when it comes to policies and policy assignments, you're not limited to working with user accounts one a time. For example, suppose you need a list of all the users who are allowed to communicate with federated partners and with Windows Live users. We already know that those users have been assigned the external user access policy FederationAndPICDefault. Because we know that, you can display a list of all those users by running one simple command. Here is the command:</span></span>
  
```powershell
Get-CsOnlineUser -Filter {ExternalAccessPolicy -eq "FederationAndPICDefault"} | Select-Object DisplayName
```

<span data-ttu-id="2b8bc-p107">Другими словами, отобразятся все пользователи, для свойства ExternalAccessPolicy которых задано значение FederationAndPICDefault. (Чтобы ограничить объем сведений, которые появляются на экране, используйте командлет Select-Object для показа только отображаемого имени каждого пользователя.)</span><span class="sxs-lookup"><span data-stu-id="2b8bc-p107">In other words, show us all the users where the ExternalAccessPolicy property is set to FederationAndPICDefault. (And, in order to limit the amount of information that appears onscreen, use the Select-Object cmdlet to display show us only each user's display name.)</span></span> 
  
<span data-ttu-id="2b8bc-133">Для настройки всех учетных записей пользователей на применение одной политики воспользуйтесь следующей командой:</span><span class="sxs-lookup"><span data-stu-id="2b8bc-133">To configure all our user accounts to use that same policy, use this command:</span></span>
  
```powershell
Get-CsOnlineUser | Grant-CsExternalAccessPolicy "FederationAndPICDefault"
```

<span data-ttu-id="2b8bc-134">С помощью командлета Get-CsOnlineUser эта команда возвращает коллекцию всех пользователей с включенной поддержкой Lync, затем передает эти сведения командлету Grant-CsExternalAccessPolicy, который назначает политику FederationAndPICDefault каждому пользователю в коллекции.</span><span class="sxs-lookup"><span data-stu-id="2b8bc-134">This command uses Get-CsOnlineUser to return a collection of all the users who have been enabled for Lync, then sends all that information to Grant-CsExternalAccessPolicy, which assigns the FederationAndPICDefault policy to each and every user in the collection.</span></span>
  
<span data-ttu-id="2b8bc-135">В качестве дополнительного примера предположим, что вы ранее назначили пользователю Семену политику FederationAndPICDefault, но передумали и хотите управлять им с помощью глобальной политики внешнего доступа.</span><span class="sxs-lookup"><span data-stu-id="2b8bc-135">As an additional example, suppose you've previously assigned Alex the FederationAndPICDefault policy and now you've changed your mind and would like him to be managed by the global external access policy.</span></span> <span data-ttu-id="2b8bc-136">Глобальную политику нельзя явно назначить какому-либо пользователю.</span><span class="sxs-lookup"><span data-stu-id="2b8bc-136">You can't explicitly assign the global policy to anyone.</span></span> <span data-ttu-id="2b8bc-137">Вместо этого глобальная политика используется для данного пользователя, если ему не назначена политика для каждого пользователя.</span><span class="sxs-lookup"><span data-stu-id="2b8bc-137">Instead, the global policy is used for a given user if no per-user policy is assigned to that user.</span></span> <span data-ttu-id="2b8bc-138">Таким образом, чтобы пользователем Семеном управляла глобальная политика, необходимо  *отменить*  все ранее назначенные ему индивидуальные политики.</span><span class="sxs-lookup"><span data-stu-id="2b8bc-138">Therefore, if we want Alex to be managed by the global policy, you need to  *unassign*  any per-user policy previously assigned to him.</span></span> <span data-ttu-id="2b8bc-139">Ниже приведен пример соответствующей команды.</span><span class="sxs-lookup"><span data-stu-id="2b8bc-139">Here is an example command:</span></span>
  
```powershell
Grant-CsExternalAccessPolicy -Identity "Alex Darrow" -PolicyName $Null
```

<span data-ttu-id="2b8bc-p109">Эта команда задает значение Null ($Null) для имени политики внешнего доступа, назначенной Семену. Значение Null означает "ничего". Другими словами, Семену не назначена ни одна политика внешнего доступа. Если пользователю не назначена ни одна политика внешнего доступа, для управления им используется глобальная политика.</span><span class="sxs-lookup"><span data-stu-id="2b8bc-p109">This command sets the name of the external access policy assigned to Alex to a null value ($Null). Null means "nothing". In other words, no external access policy is assigned to Alex. When no external access policy is assigned to a user, that user then gets managed by the global policy.</span></span>
  

## <a name="managing-large-numbers-of-users"></a><span data-ttu-id="2b8bc-144">Управление большим числом пользователей</span><span class="sxs-lookup"><span data-stu-id="2b8bc-144">Managing large numbers of users</span></span>

<span data-ttu-id="2b8bc-145">Чтобы управлять большим количеством пользователей (1000 или более), необходимо пакетовать команды с помощью блока скриптов с помощью командлета [Invoke-Command.](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/invoke-command?view=powershell-7)</span><span class="sxs-lookup"><span data-stu-id="2b8bc-145">To manage large numbers of users (1000 or more), you need to batch the commands via a script block using the [Invoke-Command](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/invoke-command?view=powershell-7) cmdlet.</span></span>  <span data-ttu-id="2b8bc-146">В предыдущих примерах при каждом выполнении cmdlet необходимо настроить вызов, а затем дождаться результата перед отправкой обратно.</span><span class="sxs-lookup"><span data-stu-id="2b8bc-146">In previous examples, each time a cmdlet is executed, it must set up the call and then wait for the result before sending it back.</span></span>  <span data-ttu-id="2b8bc-147">При использовании блока скриптов это позволяет выполняться удаленно, а после завершения отправлять данные обратно.</span><span class="sxs-lookup"><span data-stu-id="2b8bc-147">When using a script block, this allows the cmdlets to be executed remotely, and once completed, send the data back.</span></span> 

```powershell
$users = Get-CsOnlineUser -Filter { ClientPolicy -eq $null } -ResultSize 500

$batch = 50
$filter = ''
$total = $users.Count
$count = 0
    $users | ForEach-Object {
    $upn = $_.UserPrincipalName
    $filter += "(UserPrincipalName -eq '$upn')"
    $batch--
    $count++
    if (($batch -eq 0) -or ($count -eq $total)) {
        $filterSB=[ScriptBlock]::Create($filter)
        Invoke-Command -Session $s -ScriptBlock {param($f) Get-CsOnlineUser -filter $f | Grant-CsClientPolicy -PolicyName "ClientPolicyNoIMURL" -Passthru | Grant-CsExternalAccessPolicy -PolicyName "FederationAndPICDefault"} -ArgumentList $filterSB

        # Reset
        $batch = 50
        $filter = ''
    } else {
        $filter += " -or "
    }
}
```

<span data-ttu-id="2b8bc-148">Это позволит найти 500 пользователей одновременно, у которых нет клиентской политики.</span><span class="sxs-lookup"><span data-stu-id="2b8bc-148">This will find 500 users at a time who do not have a client policy.</span></span> <span data-ttu-id="2b8bc-149">Он предоставляет им клиентскую политику "ClientPolicyNoIMURL" и политику внешнего доступа "FederationAndPicDefault".</span><span class="sxs-lookup"><span data-stu-id="2b8bc-149">It will grant them the client policy "ClientPolicyNoIMURL" and the external access policy "FederationAndPicDefault".</span></span> <span data-ttu-id="2b8bc-150">Результаты сгруппировали в группы по 50, и каждая партия из 50 затем отправляется на удаленный компьютер.</span><span class="sxs-lookup"><span data-stu-id="2b8bc-150">The results are batched into groups of 50 and each batch of 50 is then sent to the remote machine.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="2b8bc-151">См. также</span><span class="sxs-lookup"><span data-stu-id="2b8bc-151">See also</span></span>

[<span data-ttu-id="2b8bc-152">Управление Skype для бизнеса Online с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="2b8bc-152">Manage Skype for Business Online with PowerShell</span></span>](manage-skype-for-business-online-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="2b8bc-153">Управление Microsoft 365 с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="2b8bc-153">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="2b8bc-154">Начало работы с PowerShell для Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="2b8bc-154">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
