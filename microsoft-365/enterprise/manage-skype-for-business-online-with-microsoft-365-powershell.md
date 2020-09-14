---
title: Управление Skype для бизнеса Online с помощью PowerShell
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/17/2020
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection: Ent_O365
f1.keywords:
- NOCSH
ms.custom: ''
ms.assetid: 054c16e6-9fd1-4e85-a0e6-81788b8410ea
description: Управляйте политиками, индивидуальными политиками и настройками собраний Skype для бизнеса Online, используя PowerShell для Microsoft 365.
ms.openlocfilehash: d50f35d7d5e81622eb8dfc3bbf8328a8c43e9676
ms.sourcegitcommit: aeb94601a81db3ead8610c2f36cff30eb9fe10e7
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/10/2020
ms.locfileid: "47430038"
---
# <a name="manage-skype-for-business-online-with-powershell"></a>Управление Skype для бизнеса Online с помощью PowerShell

*Эта статья относится к Microsoft 365 корпоративный и Office 365 корпоративный.*

Одной из основных задач администратора Skype для бизнеса Online является управление политиками. Хотя вы можете выполнить некоторые из указанных ниже задач в Центре администрирования Microsoft 365, другие задачи гораздо легче выполнить с помощью PowerShell.

## <a name="before-you-start"></a>Перед началом работы

Скачайте и установите [модуль PowerShell для Skype для бизнеса Online](https://www.microsoft.com/download/details.aspx?id=39366), а затем перезапустите компьютер.


## <a name="connect-using-skype-for-business-online-admin-credentials"></a>Подключение с помощью учетной записи администратора Skype для бизнеса Online

1. Откройте командную строку Windows PowerShell и выполните следующее:
    
   ```powershell
   Import-Module SkypeOnlineConnector
   $userCredential = Get-Credential
   $sfbSession = New-CsOnlineSession -Credential $userCredential
   Import-PSSession $sfbSession
   ```

2. В диалоговом окне **Запрос учетных данных Windows PowerShell** введите имя и пароль учетной записи администратора Skype для бизнеса Online, а затем нажмите кнопку **ОК**.


## <a name="connect-using-an-admin-account-with-multi-factor-authentication"></a>Подключение с помощью учетной записи администратора Skype для бизнеса Online с многофакторной идентификацией

1. Откройте командную строку Windows PowerShell и выполните следующее:

   ```powershell
   Import-Module SkypeOnlineConnector
   $sfbSession = New-CsOnlineSession
   Import-PSSession $sfbSession
   ```

2. По запросу команды **New-CsOnlineSession** введите имя учетной записи администратора Skype для бизнеса Online.

3. В диалоговом окне **Вход в учетную запись** введите пароль администратора Skype для бизнеса Online, а затем нажмите кнопку **Войти**.

4. Следуя инструкциям в диалоговом окне **Вход в учетную запись**, предоставьте дополнительные сведения для идентификации, например код проверки, а затем нажмите кнопку **Проверить**.

Дополнительную информацию см. в следующих статьях:
  
- [Управление политиками Skype для бизнеса Online с помощью PowerShell](manage-skype-for-business-online-policies-with-microsoft-365-powershell.md)
    
- [Назначение индивидуальных политик для Skype для бизнеса Online с помощью PowerShell](assign-per-user-skype-for-business-online-policies-with-microsoft-365-powershell.md)
    
## <a name="see-also"></a>См. также

[Управление Microsoft 365 с помощью PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Начало работы с PowerShell для Microsoft 365](getting-started-with-microsoft-365-powershell.md)

[Справка по командлетам PowerShell в Skype для бизнеса](https://docs.microsoft.com/powershell/module/skype/?view=skype-ps)
