---
title: Пределы базового случая обнаружения электронных данных
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: В этой статье описываются пределы базового случая обнаружения электронных данных в Microsoft 365.
ms.openlocfilehash: 4d91b81caee31e693ce29c6d8d629d563d973ae7
ms.sourcegitcommit: bd51f626f0c7788c2a3cf89deee25264659aebd5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/17/2020
ms.locfileid: "43551486"
---
# <a name="limits-in-core-ediscovery"></a>Пределы в ядре обнаружения электронных данных

В следующей таблице перечислены пределы для основных случаев обнаружения электронных данных и удержания, связанные с основным вариантом обнаружения электронных данных. Дополнительные сведения о базовом обнаружении содержатся в статье [Обзор основных средств обнаружения электронных](ediscovery-cases.md)данных.
    
  |**Описание ограничения**|**Ограничение**|
  |:-----|:-----|
  |Максимальное количество обращений в Организации  <br/> |Нет ограничений  <br/> |
  |Максимальное количество удержаний для Организации  <br/> |10 000  <br/> |
  |Максимальное количество почтовых ящиков в едином случае удержания  <br/> |1,000  <br/> |
  |Максимальное количество сайтов SharePoint и OneDrive для бизнеса в случае единого удержания  <br/> |100  <br/> |
  |Максимальное число обращений, отображаемых на основной странице обнаружения электронных данных, и максимальное количество элементов, отображаемых на вкладках удержания, поиска и экспорта в случае. <sup>1,1</sup> |1,000|
  |||

   > [!NOTE]
   > <sup>1</sup> чтобы просмотреть список более чем 1 000 обращений, удержаний, поисков или экспортов, вы можете использовать соответствующий командлет PowerShell для безопасности & соответствия требованиям для Office 365:<br/> [Get — ComplianceCase](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-ediscovery/get-compliancecase) <br/> [Get — Caseholdpolicy позволяет](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-ediscovery/get-caseholdpolicy)<br/> [Get-ComplianceSearch](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/get-compliancesearch)<br/> [Get — ComplianceSearchAction](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/get-compliancesearchaction)
