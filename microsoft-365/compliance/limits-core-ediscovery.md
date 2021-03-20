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
ms.openlocfilehash: e18e1e6c1d9d7ecd78deaf267be72ccdc9d1ba5d
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905891"
---
# <a name="limits-in-core-ediscovery"></a>Ограничения в core eDiscovery

В следующей таблице перечислены ограничения для основных случаев, связанных с электронным открытием, и содержится, связанный с случаем, связанным с основными данными об обнаружении электронных обнаружений. Дополнительные сведения о core eDiscovery см. в [обзоре основных сведений об обнаружении электронных данных.](./get-started-core-ediscovery.md)
    
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
   > - [Get-ComplianceCase](/powershell/module/exchange/get-compliancecase)
   > - [Get-CaseHoldPolicy](/powershell/module/exchange/get-caseholdpolicy)
   > - [Get-ComplianceSearch](/powershell/module/exchange/get-compliancesearch)
   > - [Get-ComplianceSearchAction](/powershell/module/exchange/get-compliancesearchaction)

Дополнительные сведения об ограничениях, связанных с поиском контента и экспортом, связанными с делом об обнаружении основных данных, см. в материалах [Limits for Content Search and Core eDiscovery.](limits-for-content-search.md)