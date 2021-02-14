---
title: Просмотр лицензий и служб Microsoft 365 с помощью PowerShell
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
description: Сведения о том, как использовать PowerShell для просмотра сведений о планах лицензирования, службах и лицензиях, доступных в вашей организации Microsoft 365.
ms.openlocfilehash: 3275a513de3c114076e792ab6c5ef86b1413571c
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/14/2020
ms.locfileid: "46693198"
---
# <a name="view-microsoft-365-licenses-and-services-with-powershell"></a>Просмотр лицензий и служб Microsoft 365 с помощью PowerShell

*Эта статья относится к Microsoft 365 корпоративный и Office 365 корпоративный.*

Каждая подписка на Microsoft 365 состоит из следующих элементов:

- **Планы лицензирования** Они также называются планами лицензирования или планами Microsoft 365. Планы лицензирования определяют службы Microsoft 365, доступные пользователям. Ваша подписка на Microsoft 365 может содержать несколько планов лицензирования. Примером плана лицензирования может быть Microsoft 365 E3.
    
- **Службы** Они также называются планами обслуживания. Службы — это продукты, функции и возможности Microsoft 365, доступные в каждом плане лицензирования, например Exchange Online и приложения Microsoft 365 для предприятий (ранее они назывались Office 365 профессиональныйplus). Пользователям может быть назначено несколько лицензий из разных планов лицензирования, которые будут предоставлять доступ к различным службам.
    
- **Лицензии** Каждый план лицензирования содержит количество приобретенных лицензий. Вы назначаете лицензии пользователям, чтобы они могли использовать службы Microsoft 365, определенные в плане лицензирования. Для каждой учетной записи пользователя требуется по крайней мере одна лицензия из одного плана лицензирования, чтобы они могли войти в Microsoft 365 и использовать службы.
    
С помощью PowerShell для Microsoft 365 вы можете просмотреть сведения о доступных планах лицензирования, лицензиях и службах в организации Microsoft 365. Дополнительные сведения о продуктах, функциях и службах, доступных в различных подписках на Office 365, см. в параметрах плана [Office 365.](https://go.microsoft.com/fwlink/p/?LinkId=691147)


## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>Использование модуля PowerShell Azure Active Directory для Graph

Сначала [подключите клиент Microsoft 365.](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)
  
Чтобы просмотреть сводную информацию о текущих планах лицензирования и доступных лицензиях для каждого плана, запустите данная команда:
  
```powershell
Get-AzureADSubscribedSku | Select -Property Sku*,ConsumedUnits -ExpandProperty PrepaidUnits
```

Результаты содержат:
  
- **SkuPartNumber:** Показывает доступные планы лицензирования для вашей организации. Например, `ENTERPRISEPACK` это имя плана лицензии для Office 365 корпоративный E3.
    
- **Включено:** Количество лицензий, приобретенных для определенного плана лицензирования.
    
- **ConsumedUnits:** Количество лицензий, которые вы написали пользователям из определенного плана лицензирования.
    
Чтобы просмотреть сведения о службах Microsoft 365, доступных во всех планах лицензирования, сначала отобразите список планов лицензирования.

```powershell
Get-AzureADSubscribedSku | Select SkuPartNumber
```

Затем храните сведения о планах лицензий в переменной.

```powershell
$licenses = Get-AzureADSubscribedSku
```

Затем отобразить службы в определенном плане лицензирования.

```powershell
$licenses[<index>].ServicePlans
```

\<index> — это целый ряд, который указывает номер строки плана лицензирования из отображения команды `Get-AzureADSubscribedSku | Select SkuPartNumber` минус 1.

Например, если команда отображается `Get-AzureADSubscribedSku | Select SkuPartNumber` так:

```powershell
SkuPartNumber
-------------
WIN10_VDA_E5
EMSPREMIUM
ENTERPRISEPREMIUM
FLOW_FREE
```

Затем команда для отображения служб для плана лицензирования ENTERPRISEPREMIUM будет такой:

```powershell
$licenses[2].ServicePlans
```

ENTERPRISEPREMIUM — это третья строка. Таким образом, индекс имеет значение (3–1) или 2.

Полный список планов лицензирования (также известных как названия продуктов), включенных в них планов обслуживания и соответствующих названий см. в соответствующем списке названий продуктов и идентификаторов планов обслуживания для [лицензирования.](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-service-plan-reference)

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>Использование модуля Microsoft Azure Active Directory для Windows PowerShell

Сначала [подключите клиент Microsoft 365.](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)

>[!Note]
>Кроме того, вы можете воспользоваться сценарием PowerShell, который автоматизирует выполнение процедур, описанных в этой статье. В частности, сценарий позволяет просматривать и отключать службы в организации Microsoft 365, включая Sway. Дополнительные сведения см. в [подстраховке "Отключение доступа к Sway с помощью PowerShell".](disable-access-to-sway-with-microsoft-365-powershell.md)
>
    
Чтобы просмотреть сводную информацию о текущих планах лицензирования и доступных лицензиях для каждого плана, запустите следующую команду:
  
```powershell
Get-MsolAccountSku
```

>[!Note]
>В PowerShell Core не поддерживается модуль Microsoft Azure Active Directory для Windows PowerShell и командлеты с компонентом **Msol** в имени. Чтобы использовать эти командлеты, необходимо запустить их из Windows PowerShell.
>

Результаты содержат сведения, указанные ниже.
  
- **AccountSkuId:** Показать доступные планы лицензирования для организации с помощью синтаксиса. `<CompanyName>:<LicensingPlan>`  _\<CompanyName>_ это значение, которое вы предоставили при регистрации в Microsoft 365 и уникально для вашей организации. Значение _\<LicensingPlan>_ одинаково для всех. Например, в значении название компании — и имя плана лицензирования, которое является системным именем `litwareinc:ENTERPRISEPACK`  `litwareinc` Office  `ENTERPRISEPACK` 365 корпоративный E3.
    
- **ActiveUnits:** Количество лицензий, приобретенных для определенного плана лицензирования.
    
- **WarningUnits:** Количество лицензий в плане лицензирования, которые вы не продлевали и срок действия которых истекает после 30-дневного льготного периода.
    
- **ConsumedUnits:** Количество лицензий, которые вы написали пользователям из определенного плана лицензирования.
    
Чтобы просмотреть сведения о службах Microsoft 365, доступных во всех планах лицензирования, запустите следующую команду:
  
```powershell
Get-MsolAccountSku | Select -ExpandProperty ServiceStatus
```

В следующей таблице показаны планы обслуживания Microsoft 365 и их названия для наиболее распространенных служб. Ваш список планов обслуживания может отличаться. 
  
|**План обслуживания**|**Описание**|
|:-----|:-----|
| `SWAY` <br/> |Sway  <br/> |
| `TEAMS1` <br/> |Microsoft Teams  <br/> |
| `YAMMER_ENTERPRISE` <br/> |Yammer  <br/> |
| `RMS_S_ENTERPRISE` <br/> |Azure Rights Management (RMS)  <br/> |
| `OFFICESUBSCRIPTION` <br/> |Приложения Microsoft 365 для предприятий (ранее называлось *Office 365 профессиональныйplus)*  <br/> |
| `MCOSTANDARD` <br/> |Skype для бизнеса Online  <br/> |
| `SHAREPOINTWAC` <br/> |Office  <br/> |
| `SHAREPOINTENTERPRISE` <br/> |SharePoint Online  <br/> |
| `EXCHANGE_S_ENTERPRISE` <br/> |Exchange Online (план 2)  <br/> |
   
Полный список планов лицензирования (также известных как названия продуктов), включенных в них планов обслуживания и соответствующих названий см. в соответствующем списке названий продуктов и идентификаторов планов обслуживания для [лицензирования.](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-service-plan-reference)

Чтобы просмотреть сведения о службах Microsoft 365, доступных в определенном плане лицензирования, используйте следующий синтаксис.
  
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
