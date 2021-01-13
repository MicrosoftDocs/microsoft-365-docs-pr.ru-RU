---
title: Ограничения в основных случаях eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: В этой статье описываются ограничения в основных случаях eDiscovery в Microsoft 365.
ms.openlocfilehash: 43d267acdb0c1fee0202c74832b376e066241d7c
ms.sourcegitcommit: 495b66b77d6dbe6d69e5b06b304089e4e476e568
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49799666"
---
# <a name="limits-in-core-ediscovery"></a>Ограничения в core eDiscovery

В следующей таблице перечислены ограничения для основных дел eDiscovery и случаев, связанных с основным делом eDiscovery. Дополнительные сведения о core eDiscovery см. в [обзоре core eDiscovery.](ediscovery-cases.md)
    
  | Описание ограничения | Ограничение |
  |:-----|:-----|
  |Максимальное количество дел в организации  <br/> |Нет ограничений  <br/> |
  |Максимальное количество случаев, когда дело удерживается в организации  <br/> |10 000  <br/> |
  |Максимальное количество почтовых ящиков в одном удержании дела  <br/> |1,000  <br/> |
  |Максимальное число сайтов SharePoint и OneDrive для бизнеса в одном удержании дел  <br/> |100  <br/> |
  |Максимальное количество дел, отображаемого на основной домашней странице eDiscovery, и максимальное количество элементов, отображаемого на вкладке "Содержит", "Поиск" и "Экспорт" в рамках дела. <sup>1</sup> |1,000|
  |||

   > [!NOTE]
   > <sup>1</sup> Чтобы просмотреть список из более чем 1000 дел, совмещаний, поисков или экспорта, можно использовать соответствующие & PowerShell для обеспечения безопасности и соответствия требованиям Office 365:
   > 
   > - [Get-ComplianceCase](https://docs.microsoft.com/powershell/module/exchange/get-compliancecase)
   > - [Get-CaseHoldPolicy](https://docs.microsoft.com/powershell/module/exchange/get-caseholdpolicy)
   > - [Get-ComplianceSearch](https://docs.microsoft.com/powershell/module/exchange/get-compliancesearch)
   > - [Get-ComplianceSearchAction](https://docs.microsoft.com/powershell/module/exchange/get-compliancesearchaction)

Дополнительные сведения об ограничениях, связанных с поиском контента и экспортом, связанным с основным делом eDiscovery, см. в поддомене "Ограничения для поиска контента и основного [eDiscovery".](limits-for-content-search.md)