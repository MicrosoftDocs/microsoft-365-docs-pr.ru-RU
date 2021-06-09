---
title: Ограничение содержимого сайтов SharePoint по географическому расположению
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
ms.collection: Strat_SP_gtc
localization_priority: Normal
description: В этой статье вы узнаете, как ограничить SharePoint сайтов указанным геолокационным расположением в многоэтабной среде.
ms.openlocfilehash: 74255db19b2ecf9b333d33208c63da260b2bd747
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50927268"
---
# <a name="restrict-sharepoint-site-content-to-a-geo-location"></a>Ограничение содержимого сайтов SharePoint по географическому расположению

В некоторых случаях можно выбрать принудительное сохранение сайта и его файлового содержимого в географическом расположении, где он был создан, либо запретив перемещение сайта, либо запретив кэширование его файлового содержимого в другое географическое расположение.

Это можно сделать с помощью командлета [Set-SPOSite](/powershell/module/sharepoint-online/set-sposite) с параметром **RestrictedToGeo**. По умолчанию этот параметр имеет значение NULL, но вы можете изменить его на одно из следующих значений:

|Ограничение|Описание|
|:----------|:----------|
|NoRestriction|Сайт можно перемещать в другое географическое расположение.|
|BlockMoveOnly|Сайт нельзя перемещать в другое географическое расположение, но его содержимое можно кэшировать в других географических расположениях.|
|BlockFull|Сайт нельзя перемещать в другое географическое расположение, и полное файловое содержимое не кэшируется в других географических расположениях. Заголовок файлов (полученный из содержимого), имя файла и другие свойства файла по-прежнему могут кэшироваться в других географических расположениях.<br>Содержимое, сохраненное на сайте до настройки значения BlockFull, можно продолжать кэшировать в других географических расположениях.|

Используйте указанный ниже синтаксис.

`Set-SPOSite -Identity <siteURL> -RestrictedToGeo <restriction>`

Пример:

`Set-SPOSite -Identity https://contoso.sharepoint.com/sites/RegionRestrictedTeamSite -RestrictedToGeo BlockFull`