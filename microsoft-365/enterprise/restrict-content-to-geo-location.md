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
description: В этой статье вы узнаете, как ограничить сайты SharePoint указанным географическим расположением в среде с несколькими географическими расположениями.
ms.openlocfilehash: f2a09f177c68d30121c207287e053b2b25405fbc
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/14/2020
ms.locfileid: "46693022"
---
# <a name="restrict-sharepoint-site-content-to-a-geo-location"></a>Ограничение содержимого сайтов SharePoint по географическому расположению

В некоторых случаях можно выбрать принудительное сохранение сайта и его файлового содержимого в географическом расположении, где он был создан, либо запретив перемещение сайта, либо запретив кэширование его файлового содержимого в другое географическое расположение.

Это можно сделать с помощью командлета [Set-SPOSite](https://docs.microsoft.com/powershell/module/sharepoint-online/set-sposite) с параметром **RestrictedToGeo**. По умолчанию этот параметр имеет значение NULL, но вы можете изменить его на одно из следующих значений:

|Ограничение|Описание|
|:----------|:----------|
|NoRestriction|Сайт можно перемещать в другое географическое расположение.|
|BlockMoveOnly|Сайт нельзя перемещать в другое географическое расположение, но его содержимое можно кэшировать в других географических расположениях.|
|BlockFull|Сайт нельзя перемещать в другое географическое расположение, и полное файловое содержимое не кэшируется в других географических расположениях. Заголовок файлов (полученный из содержимого), имя файла и другие свойства файла по-прежнему могут кэшироваться в других географических расположениях.<br>Содержимое, сохраненное на сайте до настройки значения BlockFull, можно продолжать кэшировать в других географических расположениях.|

Используйте указанный ниже синтаксис.

`Set-SPOSite -Identity <siteURL> -RestrictedToGeo <restriction>`

Пример:

`Set-SPOSite -Identity https://contoso.sharepoint.com/sites/RegionRestrictedTeamSite -RestrictedToGeo BlockFull`
