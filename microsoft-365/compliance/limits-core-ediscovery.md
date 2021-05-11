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
description: В этой статье описываются ограничения в случае с основными данными об обнаружении электронных Microsoft 365.
ms.openlocfilehash: e7b1013abd9fd94748baf3b83dd04efbc3831a1d
ms.sourcegitcommit: efb932db63ad3ab4af4b585428d567d069410e4e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2021
ms.locfileid: "52311428"
---
# <a name="limits-in-core-ediscovery"></a>Ограничения в core eDiscovery

В следующей таблице перечислены ограничения для основных случаев, связанных с электронным открытием, и содержится, связанный с случаем, связанным с основными данными об обнаружении электронных обнаружений. Дополнительные сведения о core eDiscovery см. в [обзоре основных сведений об обнаружении электронных данных.](./get-started-core-ediscovery.md)
    
  | Описание ограничения | Ограничение |
  |:-----|:-----|
  |Максимальное количество случаев для организации.  <br/> |Нет ограничений  <br/> |
  |Максимальное количество случаев для организации.  <br/> |10,000  <br/> |
  |Максимальное количество почтовых ящиков в одном удержании. Это ограничение включает общее общее число почтовых ящиков пользователей и почтовых ящиков, связанных с Microsoft 365, Microsoft Teams и Yammer групп.  <br/> |1,000  <br/> |
  |Максимальное количество сайтов в одном удержании. Это ограничение включает общее количество OneDrive для бизнеса, SharePoint сайтов и сайтов, связанных с Microsoft 365, Microsoft Teams и Yammer groups.  <br/> |100  <br/> |
  |Максимальное число случаев, отображаемых на основной домашней странице электронного поиска, и максимальное количество элементов, отображаемых на вкладке "Удерживает", "Поиск" и "Экспорт" в рамках дела. <sup>1</sup> |1,000|
  |||

   > [!NOTE]
   > <sup>1</sup> Чтобы просмотреть список из более чем 1000 случаев, удерживаний, поисков или экспорта, можно использовать соответствующие Office 365 безопасности & PowerShell:
   > 
   > - [Get-ComplianceCase](/powershell/module/exchange/get-compliancecase)
   > - [Get-CaseHoldPolicy](/powershell/module/exchange/get-caseholdpolicy)
   > - [Get-ComplianceSearch](/powershell/module/exchange/get-compliancesearch)
   > - [Get-ComplianceSearchAction](/powershell/module/exchange/get-compliancesearchaction)

Дополнительные сведения об ограничениях, связанных с поиском и экспортом, связанным с делом об обнаружении основных электронных данных, см. в материалах [Limits for Content search and Core eDiscovery.](limits-for-content-search.md)