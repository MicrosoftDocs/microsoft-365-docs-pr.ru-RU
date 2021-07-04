---
title: Назначение политик Skype для бизнеса Для каждого пользователя в PowerShell для Microsoft 365
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
description: Сводка. Используйте PowerShell для Microsoft 365 для назначения параметров связи для каждого пользователя с помощью Skype для бизнеса online политик.
ms.openlocfilehash: d7f369e96f3db95c741e6d4f2178eaf9032ab0bb
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/03/2021
ms.locfileid: "53288087"
---
# <a name="assign-per-user-skype-for-business-online-policies-with-powershell-for-microsoft-365"></a>Назначение политик Skype для бизнеса Для каждого пользователя в PowerShell для Microsoft 365

*Эта статья относится к Microsoft 365 корпоративный и Office 365 корпоративный.*

Использование PowerShell для Microsoft 365 является эффективным способом назначения параметров связи для каждого пользователя с помощью Skype для бизнеса online.
  
## <a name="prepare-to-run-the-powershell-commands"></a>Подготовка к запуску команд PowerShell

Чтобы получить настройки для выполнения команд, воспользуйтесь приведенными ниже инструкциями (пропустите выполненные ранее шаги).
  
  > [!Note]
   > Соединитель Skype для бизнеса Online в настоящее время является частью последнего модуля Teams PowerShell. Если вы используете последний общедоступный выпуск Teams PowerShell, вам не нужно устанавливать соединитель Skype для бизнеса Online.

1. Установите модуль [Teams PowerShell](/microsoftteams/teams-powershell-install).
    
2. Откройте командную строку Windows PowerShell и выполните указанные команды: 
    
   ```powershell
   Import-Module MicrosoftTeams
   Connect-MicrosoftTeams
   ```

   При поступлении соответствующего запроса системы введите имя и пароль учетной записи администратора Skype для бизнеса Online.
    
## <a name="updating-external-communication-settings-for-a-user-account"></a>Обновление параметров внешней связи для учетной записи пользователя

Предположим, вы решили изменить параметры внешней связи для учетной записи пользователя. Например, необходимо разрешить Семену связываться с федеративными пользователями (задав для свойства EnableFederationAccess значение True) и запретить обмениваться данными с пользователями Windows Live (установив для политики EnablePublicCloudAccess значение False). Для этого необходимо выполнить два действия:
  
1. найти политику внешнего доступа, которая отвечает нашим критериям;
    
2. назначить эту политику внешнего доступа пользователю Семену.
    
Как определить, какую политику внешнего доступа назначить Алекс? Приведенная ниже команда возвращает все политики внешнего доступа, в которых для свойства EnableFederationAccess и политики EnablePublicCloudAccess заданы значения "True" и "False" соответственно.
  
```powershell
Get-CsExternalAccessPolicy -Include All| Where-Object {$_.EnableFederationAccess -eq $True -and $_.EnablePublicCloudAccess -eq $False}
```

Если вы не создали настраиваемые экземпляры ExternalAccessPolicy, эта команда возвращает одну политику, которая соответствует нашим критериям (FederationOnly). Пример:
  
```powershell
Identity                          : Tag:FederationOnly
Description                       :
EnableFederationAccess            : True
EnableXmppAccess                  : False
EnablePublicCloudAccess           : False
EnablePublicCloudAudioVideoAccess : False
EnableOutsideAccess               : True
```

Теперь мы знаем, какую политику назначить пользователю Семену, и сделаем это с помощью командлета [Grant-CsExternalAccessPolicy](/powershell/module/skype/Get-CsExternalAccessPolicy). Ниже приведен пример.
  
```powershell
Grant-CsExternalAccessPolicy -Identity "Alex Darrow" -PolicyName "FederationOnly"
```

Назначить политику очень просто: нужно всего лишь указать идентификатор пользователя и имя назначаемой политики. 
  
Что касается политик и их назначений, можно одновременно работать с несколькими учетными записями пользователей. Например, предположим, что вам нужен список всех пользователей, которым разрешено обмениваться данными с федеративными партнерами и пользователями Windows Live. Мы уже знаем, что этим пользователям назначена политика доступа к внешним пользователям FederationAndPICDefault. Благодаря этому мы можем вернуть список всех этих пользователей, выполнив одну простую команду, которая приведена ниже.
  
```powershell
Get-CsOnlineUser -Filter {ExternalAccessPolicy -eq "FederationAndPICDefault"} | Select-Object DisplayName
```

Другими словами, отобразятся все пользователи, для свойства ExternalAccessPolicy которых задано значение FederationAndPICDefault. (Чтобы ограничить объем сведений, которые появляются на экране, используйте командлет Select-Object для показа только отображаемого имени каждого пользователя.) 
  
Для настройки всех учетных записей пользователей на применение одной политики воспользуйтесь следующей командой:
  
```powershell
Get-CsOnlineUser | Grant-CsExternalAccessPolicy "FederationAndPICDefault"
```

С помощью командлета Get-CsOnlineUser эта команда возвращает коллекцию всех пользователей с включенной поддержкой Lync, затем передает эти сведения командлету Grant-CsExternalAccessPolicy, который назначает политику FederationAndPICDefault каждому пользователю в коллекции.
  
В качестве дополнительного примера предположим, что вы ранее назначили пользователю Семену политику FederationAndPICDefault, но передумали и хотите управлять им с помощью глобальной политики внешнего доступа. Глобальную политику нельзя явно назначить какому-либо пользователю. Вместо этого глобальная политика используется для данного пользователя, если ему не назначена политика для каждого пользователя. Таким образом, чтобы пользователем Семеном управляла глобальная политика, необходимо  *отменить*  все ранее назначенные ему индивидуальные политики. Ниже приведен пример соответствующей команды.
  
```powershell
Grant-CsExternalAccessPolicy -Identity "Alex Darrow" -PolicyName $Null
```

Эта команда задает значение Null ($Null) для имени политики внешнего доступа, назначенной Семену. Значение Null означает "ничего". Другими словами, Семену не назначена ни одна политика внешнего доступа. Если пользователю не назначена ни одна политика внешнего доступа, для управления им используется глобальная политика.

## <a name="managing-large-numbers-of-users"></a>Управление большим числом пользователей

Чтобы управлять большим количеством пользователей (1000 или более), необходимо пакетовать команды с помощью блока скриптов с помощью командлета [Invoke-Command.](/powershell/module/microsoft.powershell.core/invoke-command)  В предыдущих примерах при каждом выполнении cmdlet необходимо настроить вызов, а затем дождаться результата перед отправкой обратно.  При использовании блока скриптов это позволяет выполняться удаленно, а после завершения отправлять данные обратно.

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

Это позволит найти 500 пользователей одновременно, у которых нет клиентской политики. Он предоставляет им клиентскую политику "ClientPolicyNoIMURL" и политику внешнего доступа "FederationAndPicDefault". Результаты сгруппировали в группы по 50, и каждая партия из 50 затем отправляется на удаленный компьютер.
  
## <a name="see-also"></a>См. также

[Управление Skype для бизнеса Online с помощью PowerShell](manage-skype-for-business-online-with-microsoft-365-powershell.md)
  
[Управление Microsoft 365 с помощью PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Начало работы с PowerShell для Microsoft 365](getting-started-with-microsoft-365-powershell.md)