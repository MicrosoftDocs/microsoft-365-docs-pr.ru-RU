---
title: Подключение к Microsoft 365 с помощью PowerShell
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
- CSH
ms.custom:
- LIL_Placement
- O365ITProTrain
- Ent_Office_Other
ms.assetid: 5ebc0e21-b72d-46d8-96fa-00643b18eaec
description: Подключитесь к клиенту Microsoft 365, используя PowerShell для Microsoft 365, чтобы выполнять задачи администрирования из командной строки.
ms.openlocfilehash: 33f9af45418ae8a1f126d2b321e7246201bd1f6e
ms.sourcegitcommit: f07442d077eb4357fa5d99d051b035705eb30efa
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/12/2020
ms.locfileid: "49002409"
---
# <a name="connect-to-microsoft-365-with-powershell"></a>Подключение к Microsoft 365 с помощью PowerShell

*Эта статья относится к Microsoft 365 корпоративный и Office 365 корпоративный.*

С помощью PowerShell для Microsoft 365 можно управлять параметрами Microsoft 365 из командной строки. Для подключения к PowerShell достаточно лишь установить необходимое программное обеспечения, а затем подключиться к организации Microsoft 365.

Существует две версии модуля PowerShell, которые используются для подключения к Microsoft 365 и управления учетными записями пользователей, группами и лицензиями:

- Azure Active Directory PowerShell для Graph (имена командлетов содержат *AzureAD* )
- Модуль Microsoft Azure Active Directory для Windows PowerShell (имена командлетов содержат *Msol* )

В настоящее время модуль Azure Active Directory PowerShell для Graph не полностью заменяет функциональность модуля Microsoft Azure Active Directory для Windows PowerShell в отношении администрирования пользователей, групп и лицензий. В некоторых случаях необходимо использовать обе версии. Вы можете безопасно установить обе версии на одном компьютере.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Что нужно знать перед началом работы


**Операционная система**

Требуется 64-разрядная версия Windows. Поддержка 32-разрядной версии модуля Microsoft Azure Active Directory Module для Windows PowerShell прекращена с 2014 года.

Ниже приведены версии Windows, которые можно использовать.
    
  - Windows 10, Windows 8.1, Windows 8 или Windows 7 с пакетом обновления 1 (SP1) 
    
  - Windows Server 2019, Windows Server 2016, Windows Server 2012 R2, Windows Server 2012 или Windows Server 2008 R2 SP1

>[!Note]
>Для Windows 8.1, Windows 8, Windows 7 с пакетом обновления 1 (SP1), Windows Server 2012 R2, Windows Server 2012 и Windows Server 2008 R2 SP1 скачайте и установите [Windows Management Framework 5.1](https://www.microsoft.com/download/details.aspx?id=54616).

**PowerShell**

- Для модуля Azure Active Directory PowerShell для Graph требуется использовать PowerShell версии 5.1 или более поздней.

- Для модуля Microsoft Azure Active Directory для Windows PowerShell требуется использовать PowerShell версии от 5.1 до 6. Использовать PowerShell версии 7 невозможно.
       
>[!Note]
>Эти процедуры предназначены для пользователей, которым назначена роль администраторов Microsoft 365. Дополнительные сведения см. в статье [О ролях администраторов](https://go.microsoft.com/fwlink/p/?LinkId=532367).


## <a name="connect-with-the-azure-active-directory-powershell-for-graph-module"></a>Подключение к модулю Azure Active Directory PowerShell для Graph

Имена командлетов в модуле Azure Active Directory PowerShell для Graph включают компонент *AzureAD*. Вы можете установить модуль [Azure Active Directory PowerShell для Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) или [Azure PowerShell](https://docs.microsoft.com/powershell/azure/install-az-ps).

Если процедурам требуются новые командлеты в модуле PowerShell Azure Active Directory для Graph, выполните эти действия, чтобы установить этот модуль и подключить его к вашей подписке Microsoft 365.

> [!Note]
> Сведения о поддержке различных версий Windows см. в статье [модуль Azure Active Directory PowerShell для Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) .

### <a name="step-1-install-the-required-software"></a>Шаг 1. Установите необходимое программное обеспечение.

Перечисленные действия необходимо выполнить на компьютере только один раз. При этом, вероятно, потребуется регулярно обновлять программное обеспечение.
  
1. Откройте командную строку Windows PowerShell с повышенными правами (запустите Windows PowerShell от имени администратора).
    
2. Выполните следующую команду:
    
    ```powershell
    Install-Module -Name AzureAD
    ```

   Если появится предложение установить модуль из недоверенного репозитория, введите **Y** и нажмите клавишу ВВОД.

### <a name="step-2-connect-to-azure-ad-for-your-microsoft-365-subscription"></a>Шаг 2. Установите подключение к Azure AD для вашей подписки Microsoft 365.

Чтобы установить подключение к Azure Active Directory (Azure AD) для вашей подписки Microsoft 365 с учетной записью и паролем или с многофакторной проверкой подлинности, выполните одну из следующих команд в командной строке Windows PowerShell. (повышенные права не требуются).

| Облачная служба Office 365 | Команда |
|:-------|:-----|
| Office 365 Worldwide (+GCC) | `Connect-AzureAD` |
| Office 365, предоставляемый 21 Vianet | `Connect-AzureAD -AzureEnvironmentName AzureChinaCloud` |
| Office 365 Germany | `Connect-AzureAD -AzureEnvironmentName AzureGermanyCloud` |
| Office 365 для DoD государственных организаций США и Office 365 для GCC High государственных организаций США | `Connect-AzureAD -AzureEnvironmentName AzureUSGovernment` |
|||

В диалоговом окне **Вход в учетную запись** введите имя пользователя и пароль своей рабочей или учебной учетной записи Microsoft 365 и нажмите кнопку **ОК**.

Если используется многофакторная проверка подлинности, следуйте инструкциям в дополнительных диалоговых окнах, чтобы предоставить дополнительные сведения для проверки подлинности, например код проверки.

После подключения можно использовать командлеты для [модуля Azure Active Directory PowerShell для Graph](https://docs.microsoft.com/powershell/module/azuread).

## <a name="connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>Подключение к модулю Microsoft Azure Active Directory для Windows PowerShell

>[!Note]
>Имена командлетов в модуле Microsoft Azure Active Directory для Windows PowerShell содержат *Msol*.

В PowerShell версии 7 и более поздних версиях не поддерживается модуль Microsoft Azure Active Directory для Windows PowerShell и командлеты, имена которых содержат *Msol*. Для PowerShell версии 7 и более поздних версий требуется использовать модуль Azure Active Directory PowerShell для Graph или Azure PowerShell.

В PowerShell Core не поддерживается модуль Microsoft Azure Active Directory для Windows PowerShell и командлеты, имена которых содержат *Msol*. Эти командлеты требуется запускать из Windows PowerShell.
    
### <a name="step-1-install-the-required-software"></a>Шаг 1. Установите необходимое программное обеспечение.

Перечисленные действия необходимо выполнить на компьютере только один раз. При этом, вероятно, потребуется регулярно обновлять программное обеспечение.
  
1.  Если вы не используете операционную систему Windows 10, установите 64-разрядную версию помощника по входу в Microsoft Online Services. См. статью [Помощник по входу в Microsoft Online Services для ИТ-специалистов, RTW](https://go.microsoft.com/fwlink/p/?LinkId=286152).
    
2. Чтобы установить модуль Microsoft Azure Active Directory для Windows PowerShell, выполните следующие действия:
    
   1. Откройте командную строку Windows PowerShell с повышенными привилегиями (запустите Windows PowerShell от имени администратора).
   1.  Выполните команду **Install-Module MSOnline**.
   1. Если будет предложено установить поставщик NuGet, введите **Y** и нажмите клавишу ВВОД.
   1. Если будет предложено установить модуль из PSGallery, введите **Y** и нажмите клавишу ВВОД.
    
### <a name="step-2-connect-to-azure-ad-for-your-microsoft-365-subscription"></a>Шаг 2. Установите подключение к Azure AD для вашей подписки Microsoft 365.

Чтобы установить подключение к Azure AD для вашей подписки Microsoft 365 с учетной записью и паролем или с многофакторной проверкой подлинности, выполните одну из следующих команд в командной строке Windows PowerShell. (повышенные права не требуются).

| Облачная служба Office 365 | Команда |
|:-------|:-----|
| Office 365 Worldwide (+GCC) | `Connect-MsolService` |
| Office 365, предоставляемый 21 Vianet | `Connect-MsolService -AzureEnvironment AzureChinaCloud` |
| Office 365 Germany | `Connect-MsolService -AzureEnvironment AzureGermanyCloud` |
| Office 365 для DoD государственных организаций США и Office 365 для GCC High государственных организаций США | `Connect-MsolService -AzureEnvironment USGovernment` |
|||

В диалоговом окне **Вход в учетную запись** введите имя пользователя и пароль своей рабочей или учебной учетной записи Microsoft 365 и нажмите кнопку **ОК**.

Если используется многофакторная проверка подлинности, следуйте инструкциям в дополнительных диалоговых окнах, чтобы предоставить дополнительные сведения для проверки подлинности, например код проверки.

### <a name="how-do-you-know-it-worked"></a>Как узнать, что все прошло успешно?

Если нет сообщений об ошибках, подключение успешно установлено. Для проверки запустите любой командлет Microsoft 365, например **Get-MsolUser** , и проверьте результаты.
  
Если появится сообщение об ошибке, проверьте следующее:
  
- **Распространенная проблема: неправильный пароль**. Повторите [шаг 2](#step-2-connect-to-azure-ad-for-your-microsoft-365-subscription), внимательно проверив имя пользователя и пароль.
    
- **Для работы модуля Microsoft Azure Active Directory для Windows PowerShell необходимо, чтобы на вашем компьютере был включен компонент Microsoft .NET Framework 3.5.* x*. Скорее всего, на вашем компьютере установлена более новая версия этого компонента (например, 4 или 4.5.* x*). При этом можно включить или отключить режим обратной совместимости с более ранними версиями .NET Framework. Дополнительные сведения см. в следующих статьях:
    
  - Windows Server 2012 или Windows Server 2012 R2: см. статью [Включение .NET Framework 3.5 с помощью мастера добавления ролей и функций](https://go.microsoft.com/fwlink/p/?LinkId=532368).
    
  - Windows 7 или Windows Server 2008 R2: см. статью [Не удается открыть модуль Azure Active Directory для Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=532370).

  - Windows 10, Windows 8.1 и Windows 8: см. статью [Установка .NET Framework 3.5 в Windows 10, Windows 8.1 и Windows 8](https://docs.microsoft.com/dotnet/framework/install/dotnet-35-windows-10).

  
- **Возможно, ваша версия модуля Microsoft Azure Active Directory для Windows PowerShell устарела.** Чтобы проверить, выполните следующую команду в PowerShell для Microsoft 365 или в модуле Microsoft Azure Active Directory для Windows PowerShell:
    
  ```powershell
  (Get-Item C:\Windows\System32\WindowsPowerShell\v1.0\Modules\MSOnline\Microsoft.Online.Administration.Automation.PSModule.dll).VersionInfo.FileVersion
  ```

    Если возвращенный номер версии меньше *1.0.8070.2* , удалите модуль Microsoft Azure Active Directory для Windows PowerShell и выполните установку с [шага 1](#step-1-install-the-required-software), описанного выше.

- **Если появится сообщение об ошибке подключение** , см. статью [Ошибка "Connect-MsolService: исключение типа"](https://go.microsoft.com/fwlink/p/?LinkId=532377).
    
- **Если появляется сообщение об ошибке "Get-Item: не удается найти путь"** , выполните следующую команду:


   ```powershell
     (dir "C:\Program Files\WindowsPowerShell\Modules\MSOnline").Name
   ```

## <a name="see-also"></a>См. также

- [Управление Microsoft 365 с помощью PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
- [Начало работы с PowerShell для Microsoft 365](getting-started-with-microsoft-365-powershell.md)
- [Подключение ко всем службам Microsoft 365 в одном окне Windows PowerShell](connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window.md)
