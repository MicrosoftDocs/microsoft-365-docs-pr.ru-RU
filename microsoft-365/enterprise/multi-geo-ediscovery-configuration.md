---
title: Настройка обнаружения электронных данных в Microsoft 365 Multi-Geo
ms.reviewer: adwood
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: o365-solutions
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
localization_priority: Normal
ms.collection: Strat_SP_gtc
description: Узнайте, как использовать параметр Region для настройки обнаружения электронных данных для использования в вспомогательных расположениях в Microsoft 365 с поддержкой нескольких регионов.
ms.openlocfilehash: 216012791473776395d27821293e8fc565568c2c
ms.sourcegitcommit: 27daadad9ca0f02a833ff3cff8a574551b9581da
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2020
ms.locfileid: "47547954"
---
# <a name="microsoft-365-multi-geo-ediscovery-configuration"></a>Настройка обнаружения электронных данных в Microsoft 365 Multi-Geo

По умолчанию менеджер по обнаружению электронных данных или администратор в клиенте с поддержкой нескольких регионов сможет обнаруживать электронные данные только в центральном расположении для этого клиента. Чтобы обеспечить поддержку обнаружения электронных данных для периферийных расположений, в PowerShell добавлен новый параметр Region для фильтра соответствия требованиям безопасности.

Глобальный администратор Microsoft 365 должен предоставить менеджеру по обнаружению электронных данных право разрешать другим пользователям выполнять обнаружение электронных данных и назначать параметр Region в соответствующем фильтре соответствия требованиям безопасности, чтобы указывать вспомогательное расположение в качестве региона для обнаружения электронных данных. В противном случае обнаружение электронных данных не будет выполняться для вспомогательного расположения.

Если роль менеджера по обнаружению электронных данных или администратора задана для определенного периферийного расположения, то соответствующий пользователь сможет выполнять операции поиска с обнаружением электронных данных только на сайтах SharePoint и OneDrive, расположенных в этом периферийном расположении. Если менеджер по обнаружению электронных данных попробует выполнить поиск на сайтах SharePoint или OneDrive за пределами указанного периферийного расположения, результаты не будут возвращаться. Кроме того, когда менеджер по обнаружению электронных данных или администратор для периферийного расположения запускает экспорт, данные экспортируются в экземпляр Azure в этом регионе. Это помогает организациям обеспечивать соответствие требованиям, не разрешая экспорт содержимого через контролируемые границы.

> [!NOTE]
> Если менеджеру по обнаружению электронных данных требуется искать содержимое в нескольких периферийных расположениях SharePoint, необходимо создать для него еще одну учетную запись, указывающую альтернативное периферийное расположение, где находятся сайты OneDrive или SharePoint.

[!INCLUDE [Microsoft 365 Multi-Geo locations](../includes/microsoft-365-multi-geo-locations.md)]

Установка фильтра соответствия требованиям безопасности для региона:

1. [Подключение к PowerShell в Центре безопасности и соответствия требованиям Microsoft 365](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell)

2. Используйте следующий синтаксис:

   ```powershell
   New-ComplianceSecurityFilter -Action All -FilterName <TheNameYouWantToAssign> -Region <RegionValue> -Users <UserPrincipalName>
   ```

   Пример:

   ```powershell
   New-ComplianceSecurityFilter -Action All -FilterName "NAM eDiscovery Managers" -Region NAM -Users adwood@contoso.onmicrosoft.com
   ```

Дополнительные параметры и синтаксис рассматриваются в статье [New-ComplianceSecurityFilter](https://docs.microsoft.com/powershell/module/exchange/new-compliancesecurityfilter).
