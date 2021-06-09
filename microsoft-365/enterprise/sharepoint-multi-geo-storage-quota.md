---
title: Квоты хранилища SharePoint в средах с поддержкой нескольких регионов
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
ms.collection:
- Strat_SP_gtc
- SPO_Content
localization_priority: Normal
description: Узнайте о SharePoint квотах хранения в многоэтабных средах и о том, как управлять квотами может администратор SharePoint Online.
ms.openlocfilehash: ec736a6bd6061f8b028fca7a1c34d5278a84db89
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/14/2020
ms.locfileid: "46693578"
---
# <a name="sharepoint-storage-quotas-in-multi-geo-environments"></a>Квоты хранилища SharePoint в средах с поддержкой нескольких регионов

По умолчанию все регионы среды с поддержкой нескольких регионов совместно используют доступную квоту хранилища клиента.

С помощью параметра квоты хранилища географического расположения SharePoint можно управлять квотой хранилища для каждого географического расположения. При выделении квоты хранилища для географического расположения она определяет максимальный объем дискового пространства, доступного для этого географического расположения, и вычитается из доступного дискового пространства клиента. Оставшееся доступное дисковое пространство клиента затем делится между настроенными географическими расположениями, для которых не выделены определенные квоты хранилища.

Квота хранилища SharePoint для любого географического расположения может быть выделена администратором SharePoint Online путем подключения к центральному расположению. Администраторы геообъектов для периферийных расположений могут просматривать квоту хранилища, но не могут ее выделять.

## <a name="configure-a-storage-quota-for-a-geo-location"></a>Настройка квоты хранилища для географического расположения

Используйте [модуль Microsoft SharePoint Online](https://www.microsoft.com/download/details.aspx?id=35588 ) и подключитесь к центральному расположению, чтобы выделить квоту хранилища для географического расположения. 

Чтобы выделить квоту хранилища для расположения, выполните следующий командлет:

`Set-SPOGeoStorageQuota -GeoLocation <geolocationcode> -StorageQuotaMB <value>`

Чтобы просмотреть квоту хранилища для текущего географического расположения, выполните следующую команду:

`Get-SPOGeoStorageQuota`

![Снимок экрана: окно PowerShell с командлетом Get-SPOGeoStorageQuota](../media/multi-geo-storage-quota.png)

Чтобы просмотреть квоту хранилища для всех географических расположений, выполните следующую команду:

`Get-SPOGeoStorageQuota -AllLocations`

Чтобы удалить квоту хранилища, выделенную для географического расположения, установите параметр `StorageQuota value = 0`:

`Set-SPOGeoStorageQuota -GeoLocation <geolocationcode> -StorageQuotaMB 0`
