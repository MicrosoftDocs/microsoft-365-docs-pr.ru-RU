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
description: В этой статье объясняется, как использовать PowerShell для просмотра сведений о планах лицензирования, службах и лицензиях, доступных в организации Microsoft 365.
ms.openlocfilehash: 3275a513de3c114076e792ab6c5ef86b1413571c
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/14/2020
ms.locfileid: "46693198"
---
# <a name="view-microsoft-365-licenses-and-services-with-powershell"></a>Просмотр лицензий и служб Microsoft 365 с помощью PowerShell

*Эта статья относится к Microsoft 365 корпоративный и Office 365 корпоративный.*

Каждая подписка на Microsoft 365 состоит из следующих элементов:

- **Планы лицензирования** Они также называются планами лицензирования или планами Microsoft 365. В планах лицензирования определяются службы Microsoft 365, доступные пользователям. Подписка на Microsoft 365 может содержать несколько планов лицензирования. Пример плана лицензирования — Microsoft 365 E3.
    
- **Службы** Они также называются планами обслуживания. Службы — это продукты, функции и возможности Microsoft 365, доступные в каждом плане лицензирования, например Exchange Online и приложения Microsoft 365 для предприятий (ранее называлось Office 365 профессиональный плюс). Пользователям могут быть назначены несколько лицензий из разных планов лицензирования, которые предоставляют доступ к разным службам.
    
- **Licenses (лицензии** ) Каждый план лицензирования содержит количество приобретенных лицензий. Вы назначаете пользователям лицензии, чтобы они могли использовать службы Microsoft 365, определенные планом лицензирования. Каждая учетная запись пользователя должна иметь по крайней мере одну лицензию из одного плана лицензирования, чтобы пользователи могли входить в Microsoft 365 и использовать службы.
    
Вы можете использовать PowerShell для Microsoft 365 для просмотра сведений о доступных планах лицензирования, лицензиях и службах в организации Microsoft 365. Дополнительные сведения о продуктах, возможностях и службах, доступных в различных подписках на Office 365, можно найти в статье [варианты плана office 365](https://go.microsoft.com/fwlink/p/?LinkId=691147).


## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>Использование модуля PowerShell Azure Active Directory для Graph

Сначала [подключитесь к клиенту Microsoft 365](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).
  
Чтобы просмотреть сводную информацию о текущих планах лицензирования и доступных лицензиях для каждого плана, выполните следующую команду:
  
```powershell
Get-AzureADSubscribedSku | Select -Property Sku*,ConsumedUnits -ExpandProperty PrepaidUnits
```

Результаты содержат:
  
- **Скупартнумбер:** Показывает доступные планы лицензирования для вашей организации. Например, `ENTERPRISEPACK` это название плана лицензирования для Office 365 корпоративный E3.
    
- **Включено:** Количество лицензий, приобретенных для определенного плана лицензирования.
    
- **ConsumedUnits:** Количество лицензий, назначенных пользователям из определенного плана лицензирования.
    
Чтобы просмотреть сведения о службах Microsoft 365, доступных во всех планах лицензирования, сначала необходимо отобразить список планов лицензирования.

```powershell
Get-AzureADSubscribedSku | Select SkuPartNumber
```

Затем сохраните сведения о планах лицензии в переменной.

```powershell
$licenses = Get-AzureADSubscribedSku
```

Затем отобразите службы в определенном плане лицензирования.

```powershell
$licenses[<index>].ServicePlans
```

\<index> — Это целое число, определяющее номер строки плана лицензирования из отображения `Get-AzureADSubscribedSku | Select SkuPartNumber` команды минус 1.

Например, если `Get-AzureADSubscribedSku | Select SkuPartNumber` команда имеет следующий вид:

```powershell
SkuPartNumber
-------------
WIN10_VDA_E5
EMSPREMIUM
ENTERPRISEPREMIUM
FLOW_FREE
```

Затем команда отображает службы для плана лицензирования ЕНТЕРПРИСЕПРЕМИУМ следующим образом:

```powershell
$licenses[2].ServicePlans
```

ЕНТЕРПРИСЕПРЕМИУМ — третья строка. Таким образом, значение индекса — (3-1) или 2.

Полный список планов лицензирования (называемых также названиями продуктов), включенных планов обслуживания и соответствующих понятных имен можно узнать в статье [наименования и идентификаторы планов обслуживания для лицензирования](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-service-plan-reference).

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>Использование модуля Microsoft Azure Active Directory для Windows PowerShell

Сначала [подключитесь к клиенту Microsoft 365](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).

>[!Note]
>Кроме того, вы можете воспользоваться сценарием PowerShell, который автоматизирует выполнение процедур, описанных в этой статье. В частности, скрипт позволяет просматривать и отключать службы в организации Microsoft 365, в том числе Sway. Дополнительные сведения см. [в статье Отключение доступа к Sway с помощью PowerShell](disable-access-to-sway-with-microsoft-365-powershell.md).
>
    
Чтобы просмотреть сводную информацию о текущих планах лицензирования и доступных лицензиях для каждого плана, выполните следующую команду:
  
```powershell
Get-MsolAccountSku
```

>[!Note]
>В PowerShell Core не поддерживается модуль Microsoft Azure Active Directory для Windows PowerShell и командлеты с компонентом **Msol** в имени. Чтобы использовать эти командлеты, необходимо запустить их из Windows PowerShell.
>

Результаты содержат сведения, указанные ниже.
  
- **AccountSkuId:** Отображение доступных планов лицензирования для Организации с помощью синтаксиса `<CompanyName>:<LicensingPlan>` .  _\<CompanyName>_ — Это значение, заданное при регистрации в Microsoft 365, и уникальное для Организации. Это _\<LicensingPlan>_ значение одинаково для всех. Например, в значении `litwareinc:ENTERPRISEPACK` название компании  `litwareinc` и название плана лицензирования  `ENTERPRISEPACK` , которое является системным именем для Office 365 корпоративный E3.
    
- **ActiveUnits:** Количество лицензий, приобретенных для определенного плана лицензирования.
    
- **WarningUnits:** Количество лицензий в плане лицензирования, которые вы еще не обновили, и срок действия которых истекает через 30 дней.
    
- **ConsumedUnits:** Количество лицензий, назначенных пользователям из определенного плана лицензирования.
    
Чтобы просмотреть сведения о службах Microsoft 365, доступных во всех планах лицензирования, выполните следующую команду:
  
```powershell
Get-MsolAccountSku | Select -ExpandProperty ServiceStatus
```

В следующей таблице показаны планы обслуживания Microsoft 365 и их понятные имена для наиболее распространенных служб. Ваш список планов обслуживания может отличаться. 
  
|**План обслуживания**|**Описание**|
|:-----|:-----|
| `SWAY` <br/> |Sway  <br/> |
| `TEAMS1` <br/> |Microsoft Teams  <br/> |
| `YAMMER_ENTERPRISE` <br/> |Yammer  <br/> |
| `RMS_S_ENTERPRISE` <br/> |Azure Rights Management (RMS)  <br/> |
| `OFFICESUBSCRIPTION` <br/> |Приложения Microsoft 365 для предприятий *(ранее именуемые Office 365 профессиональный плюс)*  <br/> |
| `MCOSTANDARD` <br/> |Skype для бизнеса Online  <br/> |
| `SHAREPOINTWAC` <br/> |Office  <br/> |
| `SHAREPOINTENTERPRISE` <br/> |SharePoint Online  <br/> |
| `EXCHANGE_S_ENTERPRISE` <br/> |Exchange Online (план 2)  <br/> |
   
Полный список планов лицензирования (называемых также названиями продуктов), включенных планов обслуживания и соответствующих понятных имен можно узнать в статье [наименования и идентификаторы планов обслуживания для лицензирования](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-service-plan-reference).

Чтобы просмотреть сведения о службах Microsoft 365, доступных в определенном плане лицензирования, используйте следующий синтаксис.
  
```powershell
(Get-MsolAccountSku | where {$_.AccountSkuId -eq "<AccountSkuId>"}).ServiceStatus
```

В этом примере показаны службы, доступные в плане лицензирования litwareinc: ENTERPRISEPACK (Office 365 корпоративный E3).
  
```powershell
(Get-MsolAccountSku | where {$_.AccountSkuId -eq "litwareinc:ENTERPRISEPACK"}).ServiceStatus
```

## <a name="see-also"></a>См. также

[Управление учетными записями пользователей Microsoft 365, лицензиями и группами с помощью PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[Управление Microsoft 365 с помощью PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Начало работы с PowerShell для Microsoft 365](getting-started-with-microsoft-365-powershell.md)
