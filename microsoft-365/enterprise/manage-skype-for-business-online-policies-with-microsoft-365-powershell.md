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
description: Сводка. Используйте PowerShell для управления свойствами Skype для бизнеса учетной записи пользователей в Интернете с помощью политик.
ms.openlocfilehash: a10929bbdce499ad26f9714127f675beeef58765
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50916706"
---
# <a name="manage-skype-for-business-online-policies-with-powershell"></a>Управление политиками Skype для бизнеса Online с помощью PowerShell

*Эта статья относится к Microsoft 365 корпоративный и Office 365 корпоративный.*

Чтобы управлять многими свойствами учетной записи пользователя Skype для бизнеса Online, необходимо указать их в качестве свойств политик с PowerShell для Microsoft 365.
  
## <a name="before-you-begin"></a>Перед началом работы

Чтобы получить настройки для выполнения команд, воспользуйтесь приведенными ниже инструкциями (пропустите выполненные ранее шаги).

  > [!Note]
  > Соединитель Skype для бизнеса Online в настоящее время является частью последнего модуля Teams PowerShell. Если вы используете последний общедоступный выпуск Teams PowerShell, вам не нужно устанавливать соединитель Skype для бизнеса Online.

1. Установите модуль [Teams PowerShell](/microsoftteams/teams-powershell-install).
    
2. Откройте командную строку Windows PowerShell и выполните указанные команды: 

   ```powershell
   Import-Module MicrosoftTeams
   $userCredential = Get-Credential
   Connect-MicrosoftTeams -Credential $userCredential
   ```

   При поступлении соответствующего запроса системы введите имя и пароль учетной записи администратора Skype для бизнеса Online.
    
## <a name="manage-user-account-policies"></a>Управление политиками учетной записи пользователя

Многие свойства учетной записи пользователя Skype для бизнеса Online настраиваются с помощью политик. Политики  это просто коллекции параметров, которые можно применить к одному или нескольким пользователям. Чтобы рассмотреть настройки политики, можно воспользоваться приведенной ниже командой для политики FederationAndPICDefault в качестве примера:
  
```powershell
Get-CsExternalAccessPolicy -Identity "FederationAndPICDefault"
```

В ответ вы должны получить что-то вроде этого:
  
```powershell
Identity                          : Tag:FederationAndPICDefault
Description                       :
EnableFederationAccess            : True
EnableXmppAccess                  : False
EnablePublicCloudAccess           : True
EnablePublicCloudAudioVideoAccess : True
EnableOutsideAccess               : True
```

В приведенном примере значения в этих политиках определяют, что именно может делать пользователь в отношении обмена данными с федеративными пользователями. Например, для свойства EnableOutsideAccess необходимо задать значение True, чтобы пользователь мог обмениваться данными с пользователями вне организации. Обратите внимание, что это свойство не появляется в Microsoft 365 центре администрирования. Вместо этого для него автоматически устанавливается значение True или False на основе значений, выбранных для других свойств. Ниже описаны два других интересующих нас свойства:
  
- Свойство **EnableFederationAccess** указывает, может ли пользователь обмениваться данными с пользователями из федеративных доменов.
    
- Свойство **EnablePublicCloudAccess** указывает, может ли пользователь обмениваться данными с пользователями Windows Live.
    
Следовательно, вы не изменяете свойства учетной записи пользователя, связанные с федерацией (например, **Set-CsUser -EnableFederationAccess $True**). Вместо этого вы назначаете пользователю политику внешнего доступа с предварительно настроенными значениями необходимых свойств. Чтобы пользователь смог обмениваться данными с федеративными пользователями и пользователями Windows Live, ему нужно назначить политику, разрешающую такой обмен данными.
  
Чтобы узнать, может ли пользователь обмениваться данными с пользователями вне организации, необходимо выполнить следующие действия:
  
- Определить, какая политика внешнего доступа назначена этому пользователю.
    
- Определить, какие возможности разрешает или запрещает эта политика.
    
Для этого можно воспользоваться указанной командой.
  
```powershell
Get-CsOnlineUser -Identity "Alex Darrow" | ForEach {Get-CsExternalAccessPolicy -Identity $_.ExternalAccessPolicy}
```

Эта команда находит политику, назначенную пользователю, а затем находит возможности, которые включены или отключены в этой политике.
  
Чтобы управлять политиками Skype для бизнеса Online с Помощью PowerShell, см. в cmdlets для:

- [Client policy](/previous-versions//mt228132(v=technet.10)#client-policy-cmdlets) (Политика клиента).
- [Политика конференц-связи](/previous-versions//mt228132(v=technet.10)#conferencing-policy-cmdlets),
- [Политика мобильной связи](/previous-versions//mt228132(v=technet.10)#mobile-policy-cmdlets)
- [Политика голосовой почты в Интернете](/previous-versions//mt228132(v=technet.10)#online-voicemail-policy-cmdlets)
- [Политика маршрутивки голосовой почты](/previous-versions//mt228132(v=technet.10)#voice-routing-policy-cmdlets)


> [!NOTE]
> Абонентская группа Skype для бизнеса Online  это политика во всех отношениях, кроме имени. Название "абонентская группа" выбрано вместо других названий (скажем, "политика набора") для обеспечения обратной совместимости с Office Communications Server и Exchange. 
  
Например, чтобы просмотреть все доступные политики голосовой связи, выполните следующую команду:
  
```powershell
Get-CsVoicePolicy
```

> [!NOTE]
> Будет возвращен список всех доступных политик голосовой связи. Однако имейте в виду, что пользователям нельзя назначить некоторые политики. Это связано с различными ограничениями в отношении [места лицензирования и использования](/previous-versions/azure/dn194136(v=azure.100)). Чтобы узнать, какие политики внешнего доступа и конференций можно назначить пользователю, выполните команды, похожие на следующие: 

```powershell
Get-CsConferencingPolicy -ApplicableTo "Alex Darrow"
Get-CsExternalAccessPolicy -ApplicableTo "Alex Darrow"
```

Параметр ApplicableTo ограничивает данные, возвращаемые политиками, которые можно назначить указанному пользователю (например, Семену Маслову). В зависимости от ограничений в отношении лицензирования и места использования он может представлять подмножество всех доступных политик. 
  
В некоторых случаях свойства политик не используются с Microsoft 365, в то время как другими могут управлять только сотрудники службы поддержки Майкрософт. 
  
С Skype для бизнеса Online для управления пользователями необходимо использовать какую-либо политику. Если допустимое свойство, связанное с политикой, является пустым, значит, для управления рассматриваемым пользователем используется глобальная политика, т. е. политика, которая автоматически применяется к пользователю, если ему не назначена специальная индивидуальная политика. Управление пользователями, которым не назначена политика клиента, осуществляется с помощью глобальной политики. Определить глобальную политику клиента поможет приведенная ниже команда.
  
```powershell
Get-CsClientPolicy -Identity "Global"
```

## <a name="see-also"></a>См. также

[Управление Skype для бизнеса Online с помощью PowerShell](manage-skype-for-business-online-with-microsoft-365-powershell.md)
  
[Управление Microsoft 365 с помощью PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Начало работы с PowerShell для Microsoft 365](getting-started-with-microsoft-365-powershell.md)