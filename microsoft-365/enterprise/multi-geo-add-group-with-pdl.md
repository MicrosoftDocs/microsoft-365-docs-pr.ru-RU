---
title: Создание группы Microsoft 365 с определенным предпочтительным расположением данных
ms.reviewer: adwood
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: o365-solutions
f1.keywords:
- NOCSH
ms.collection: Strat_SP_gtc
localization_priority: Normal
description: Узнайте, как создать группу Microsoft 365 с заданным предпочтительным расположением данных в многоэтабной среде.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 41984dc24e0f30e5e7b7eb0f9672c75b6d65388f
ms.sourcegitcommit: 1206319a5d3fed8d52a2581b8beafc34ab064b1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/29/2021
ms.locfileid: "52086828"
---
# <a name="create-a-microsoft-365-group-with-a-specific-preferred-data-location"></a>Создание группы Microsoft 365 с определенным предпочтительным расположением данных

Когда пользователи в многоэтапной среде создают группу Microsoft 365, предпочтительное расположение данных группы (PDL) автоматически задается для расположения пользователя. Глобальные администраторы, администраторы SharePoint и Exchange могут создавать группы в любом выбранном регионе. 

Если нужно создать группу с определенным PDL, можно использовать Центр администрирования SharePoint или командлет Microsoft PowerShell New-UnifiedGroup для Exchange Online. При этом как почтовый ящик группы, так и сайт SharePoint, связанный с группой, подготавливаются в указанном предпочтительном расположении данных (PDL).

Чтобы создать группу Microsoft 365 с задатким PDL, перейдите в центр администрирования SharePoint в географическом расположении, где необходимо создать сайт группы.

Пример:

Если нужно создать сайт группы в Австралии, вы можете перейти на страницу https://ContosoAUS-admin.sharepoint.com/_layouts/15/online/AdminHome.aspx#/siteManagement

1. Нажмите **+ Создать**.
2. Следуйте инструкциям, чтобы создать сайт группы.

Сайт группы будет подготовлен в географическом расположении, соответствующем Центру администрирования SharePoint, из которого вы отправили запрос на создание сайта. 

Использование Exchange PowerShell 

Подключитесь к Exchange Online PowerShell и передайте параметр *- MailBoxRegion* с кодом региона.

Пример: 

```PowerShell
New-UnifiedGroup -DisplayName MultiGeoEUR -Alias "MultiGeoEUR" -AccessType Public -MailboxRegion EUR 
```

![Снимок экрана: командлет PowerShell New-UnifiedGroup с синтаксисом](../media/multi-geo-new-group-with-pdl-powershell.png)

Обратите внимание, что подготовка сайта группы SharePoint выполняется по запросу. В первый раз сайт будет подготовлен владельцем группы или участником, пытающимся получить к нему доступ.

## <a name="geo-location-codes"></a>Коды регионов

[!INCLUDE [Microsoft 365 Multi-Geo locations](../includes/microsoft-365-multi-geo-locations.md)]

## <a name="related-topics"></a>Статьи по теме

[Подключение к PowerShell Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell)
