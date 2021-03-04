---
title: Ограничения в случае с основными электронными данными
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
description: В этой статье описываются ограничения в случае с основными электронными данными в Microsoft 365.
ms.openlocfilehash: 2699e9b2511c742bb295f69611a976f6a3955980
ms.sourcegitcommit: 355bd51ab6a79d5c36a4e4f57df74ae6873eba19
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2021
ms.locfileid: "50423450"
---
# <a name="limits-in-core-ediscovery"></a>Ограничения в core eDiscovery

В следующей таблице перечислены ограничения для основных случаев, связанных с электронным открытием, и содержится, связанный с случаем, связанным с основными данными об обнаружении электронных обнаружений. Дополнительные сведения о core eDiscovery см. в [обзоре основных сведений об обнаружении электронных данных.](ediscovery-cases.md)
    
  | Описание ограничения | Ограничение |
  |:-----|:-----|
  |Максимальное количество случаев для организации.  <br/> |Нет ограничений  <br/> |
  |Максимальное количество случаев для организации.  <br/> |10 000  <br/> |
  |Максимальное количество почтовых ящиков в одном удержании. Это ограничение включает общее количество почтовых ящиков пользователей и почтовых ящиков, связанных с группами Microsoft 365, Microsoft Teams и Yammer Groups.  <br/> |1,000  <br/> |
  |Максимальное количество сайтов в одном удержании. Это ограничение включает общее количество сайтов OneDrive для бизнеса, сайтов SharePoint и сайтов, связанных с Группами Microsoft 365, Microsoft Teams и Yammer Groups.  <br/> |100  <br/> |
  |Максимальное число случаев, отображаемых на основной домашней странице электронного поиска, и максимальное количество элементов, отображаемых на вкладке "Удерживает", "Поиск" и "Экспорт" в рамках дела. <sup>1</sup> |1,000|
  |||

   > [!NOTE]
   > <sup>1</sup> Чтобы просмотреть список из более чем 1000 дел, удерживаний, поисков или экспортов, можно использовать соответствующие cmdlets Office 365 Security & Compliance PowerShell:
   > 
   > - [Get-ComplianceCase](https://docs.microsoft.com/powershell/module/exchange/get-compliancecase)
   > - [Get-CaseHoldPolicy](https://docs.microsoft.com/powershell/module/exchange/get-caseholdpolicy)
   > - [Get-ComplianceSearch](https://docs.microsoft.com/powershell/module/exchange/get-compliancesearch)
   > - [Get-ComplianceSearchAction](https://docs.microsoft.com/powershell/module/exchange/get-compliancesearchaction)

Дополнительные сведения об ограничениях, связанных с поиском контента и экспортом, связанными с делом об обнаружении основных данных, см. в материалах [Limits for Content Search and Core eDiscovery.](limits-for-content-search.md)