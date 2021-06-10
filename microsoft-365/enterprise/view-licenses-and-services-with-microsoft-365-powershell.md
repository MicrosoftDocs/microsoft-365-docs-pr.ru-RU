---
title: Просмотр Microsoft 365 лицензий и служб с помощью PowerShell
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/17/2020
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- Ent_Office_Other
- O365ITProTrain
- LIL_Placement
- PowerShell
ms.assetid: bb5260a9-a6a3-4f34-b19a-06c6699f6723
description: Объясняет, как использовать PowerShell для просмотра сведений о планах лицензирования, службах и лицензиях, доступных в Microsoft 365 организации.
ms.openlocfilehash: 08f48301001ee6a40318428f3310eab8b0d0a351
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50924640"
---
# <a name="view-microsoft-365-licenses-and-services-with-powershell"></a>Просмотр Microsoft 365 лицензий и служб с помощью PowerShell

*Эта статья относится к Microsoft 365 корпоративный и Office 365 корпоративный.*

Каждая Microsoft 365 подписка состоит из следующих элементов:

- **Планы лицензирования** Они также известны как планы лицензий или Microsoft 365 планы. Планы лицензирования определяют Microsoft 365, доступные пользователям. Ваша Microsoft 365 подписка может содержать несколько планов лицензирования. Пример плана лицензирования будет Microsoft 365 E3.
    
- **Службы** Они также называются планами службы. Службы — это Microsoft 365, функции и возможности, доступные в каждом плане лицензирования, например Exchange Online и Приложения Microsoft 365 для предприятий (ранее именуемая Office 365 профессиональный плюс). Пользователям может быть назначено несколько лицензий из различных планов лицензирования, дающих доступ к различным службам.
    
- **Лицензии** Каждый план лицензирования содержит количество приобретенных лицензий. Вы назначаете лицензии пользователям, чтобы они могли использовать Microsoft 365 службы, определенные планом лицензирования. Для каждой учетной записи пользователя требуется по крайней мере одна лицензия из одного плана лицензирования, чтобы они могли войти Microsoft 365 и использовать службы.
    
Вы можете использовать PowerShell для Microsoft 365 для просмотра сведений о доступных планах лицензирования, лицензиях и службах в Microsoft 365 организации. Дополнительные сведения о продуктах, особенностях и службах, доступных в различных Office 365 подписках, см. в Office 365 [Plan Options.](/office365/servicedescriptions/office-365-platform-service-description/office-365-plan-options)


## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>Использование модуля PowerShell Azure Active Directory для Graph

[Во-первых, подключите Microsoft 365 клиента.](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)
  
Чтобы просмотреть сводную информацию о текущих планах лицензирования и доступных лицензиях для каждого плана, запустите эту команду:
  
```powershell
Get-AzureADSubscribedSku | Select -Property Sku*,ConsumedUnits -ExpandProperty PrepaidUnits
```

Результаты содержат:
  
- **SkuPartNumber:** Отображает доступные планы лицензирования для вашей организации. Например, `ENTERPRISEPACK` это имя плана лицензии для Office 365 корпоративный E3.
    
- **Включено:** Количество лицензий, приобретенных для определенного плана лицензирования.
    
- **ConsumedUnits:** Количество лицензий, которые вы назначены пользователям из определенного плана лицензирования.
    
Чтобы просмотреть сведения о Microsoft 365, доступных во всех планах лицензий, сначала отобразите список планов лицензии.

```powershell
Get-AzureADSubscribedSku | Select SkuPartNumber
```

Далее храните сведения о планах лицензии в переменной.

```powershell
$licenses = Get-AzureADSubscribedSku
```

Далее отобразить службы в определенной лицензии.

```powershell
$licenses[<index>].ServicePlans
```

\<index> это целый ряд, который указывает номер строки плана лицензии из отображения команды `Get-AzureADSubscribedSku | Select SkuPartNumber` минус 1.

Например, если отображение команды `Get-AzureADSubscribedSku | Select SkuPartNumber` является таким:

```powershell
SkuPartNumber
-------------
WIN10_VDA_E5
EMSPREMIUM
ENTERPRISEPREMIUM
FLOW_FREE
```

Затем команда отображения служб для лицензионного плана ENTERPRISEPREMIUM будет такой:

```powershell
$licenses[2].ServicePlans
```

ENTERPRISEPREMIUM — это третья строка. Таким образом, значение индекса (3 — 1) или 2.

Полный список лицензионных планов (также известных как имена продуктов), включенных планов обслуживания и соответствующих дружественных имен см. в документе Имена продуктов и идентификаторы плана обслуживания для [лицензирования.](/azure/active-directory/users-groups-roles/licensing-service-plan-reference)

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>Использование модуля Microsoft Azure Active Directory для Windows PowerShell

[Во-первых, подключите Microsoft 365 клиента.](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)

>[!Note]
>Кроме того, вы можете воспользоваться сценарием PowerShell, который автоматизирует выполнение процедур, описанных в этой статье. В частности, скрипт позволяет просматривать и отключать службы в Microsoft 365 организации, включая Sway. Дополнительные сведения см. [в обзоре Отключение доступа к Sway с Помощью PowerShell.](disable-access-to-sway-with-microsoft-365-powershell.md)
>
    
Чтобы просмотреть сводную информацию о текущих планах лицензирования и доступных лицензиях для каждого плана, запустите следующую команду:
  
```powershell
Get-MsolAccountSku
```

>[!Note]
>В PowerShell Core не поддерживается модуль Microsoft Azure Active Directory для Windows PowerShell и командлеты с компонентом **Msol** в имени. Чтобы использовать эти командлеты, необходимо запустить их из Windows PowerShell.
>

Результаты содержат сведения, указанные ниже.
  
- **AccountSkuId:** Показать доступные планы лицензирования для организации с помощью синтаксиса `<CompanyName>:<LicensingPlan>` .  _\<CompanyName>_ это значение, которое вы предоставили при регистрации в Microsoft 365, и является уникальным для вашей организации. Значение _\<LicensingPlan>_ одинаково для всех. Например, в значении имя компании и имя плана лицензирования , которое является системным `litwareinc:ENTERPRISEPACK` `litwareinc` `ENTERPRISEPACK` именем Office 365 корпоративный E3.
    
- **ActiveUnits:** Количество лицензий, приобретенных для определенного плана лицензирования.
    
- **WarningUnits:** Количество лицензий в плане лицензирования, которое вы не продлили, и которое истекает после 30-дневного льготного периода.
    
- **ConsumedUnits:** Количество лицензий, которые вы назначены пользователям из определенного плана лицензирования.
    
Чтобы просмотреть сведения о Microsoft 365 службах, доступных во всех планах лицензий, запустите следующую команду:
  
```powershell
Get-MsolAccountSku | Select -ExpandProperty ServiceStatus
```

В следующей таблице показаны Microsoft 365 и их дружественные имена для наиболее распространенных служб. Ваш список планов обслуживания может отличаться. 
  
|**План обслуживания**|**Описание**|
|:-----|:-----|
| `SWAY` <br/> |Sway  <br/> |
| `TEAMS1` <br/> |Microsoft Teams  <br/> |
| `YAMMER_ENTERPRISE` <br/> |Yammer  <br/> |
| `RMS_S_ENTERPRISE` <br/> |Azure Rights Management (RMS)  <br/> |
| `OFFICESUBSCRIPTION` <br/> |Приложения Microsoft 365 для предприятий *(ранее назывался Office 365 профессиональный плюс)*  <br/> |
| `MCOSTANDARD` <br/> |Skype для бизнеса Online  <br/> |
| `SHAREPOINTWAC` <br/> |Office  <br/> |
| `SHAREPOINTENTERPRISE` <br/> |SharePoint Online  <br/> |
| `EXCHANGE_S_ENTERPRISE` <br/> |Exchange Online (план 2)  <br/> |
   
Полный список лицензионных планов (также известных как имена продуктов), включенных планов обслуживания и соответствующих дружественных имен см. в документе Имена продуктов и идентификаторы плана обслуживания для [лицензирования.](/azure/active-directory/users-groups-roles/licensing-service-plan-reference)

Чтобы просмотреть сведения о Microsoft 365, доступных в определенном плане лицензирования, используйте следующий синтаксис.
  
```powershell
(Get-MsolAccountSku | where {$_.AccountSkuId -eq "<AccountSkuId>"}).ServiceStatus
```

В этом примере показаны службы, доступные в плане лицензирования litwareinc:ENTERPRISEPACK (Office 365 корпоративный E3).
  
```powershell
(Get-MsolAccountSku | where {$_.AccountSkuId -eq "litwareinc:ENTERPRISEPACK"}).ServiceStatus
```

## <a name="see-also"></a>См. также

[Управление учетными записями пользователей Microsoft 365, лицензиями и группами с помощью PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[Управление Microsoft 365 с помощью PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Начало работы с PowerShell для Microsoft 365](getting-started-with-microsoft-365-powershell.md)