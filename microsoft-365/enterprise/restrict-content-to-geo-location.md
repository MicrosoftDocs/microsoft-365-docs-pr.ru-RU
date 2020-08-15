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
description: В этой статье рассказывается, как ограничить сайты SharePoint указанным географическим расположением в среде с поддержкой нескольких регионов.
ms.openlocfilehash: f2a09f177c68d30121c207287e053b2b25405fbc
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/14/2020
ms.locfileid: "46693022"
---
# <a name="restrict-sharepoint-site-content-to-a-geo-location"></a><span data-ttu-id="97afa-103">Ограничение содержимого сайтов SharePoint по географическому расположению</span><span class="sxs-lookup"><span data-stu-id="97afa-103">Restrict SharePoint site content to a geo location</span></span>

<span data-ttu-id="97afa-104">В некоторых случаях можно выбрать принудительное сохранение сайта и его файлового содержимого в географическом расположении, где он был создан, либо запретив перемещение сайта, либо запретив кэширование его файлового содержимого в другое географическое расположение.</span><span class="sxs-lookup"><span data-stu-id="97afa-104">Under some circumstances you may choose to enforce a site and its file content to remain in the geo location where the site was created, either by preventing the site from being moved or by preventing the caching of the site's file content in another geo location.</span></span>

<span data-ttu-id="97afa-105">Это можно сделать с помощью командлета [Set-SPOSite](https://docs.microsoft.com/powershell/module/sharepoint-online/set-sposite) с параметром **RestrictedToGeo**.</span><span class="sxs-lookup"><span data-stu-id="97afa-105">You can do this by using the [Set-SPOSite](https://docs.microsoft.com/powershell/module/sharepoint-online/set-sposite) cmdlet with the **RestrictedToGeo** parameter.</span></span> <span data-ttu-id="97afa-106">По умолчанию этот параметр имеет значение NULL, но вы можете изменить его на одно из следующих значений:</span><span class="sxs-lookup"><span data-stu-id="97afa-106">This parameter has a default value of NULL, but you can change it to one of the following:</span></span>

|<span data-ttu-id="97afa-107">Ограничение</span><span class="sxs-lookup"><span data-stu-id="97afa-107">Restriction</span></span>|<span data-ttu-id="97afa-108">Описание</span><span class="sxs-lookup"><span data-stu-id="97afa-108">Description</span></span>|
|:----------|:----------|
|<span data-ttu-id="97afa-109">NoRestriction</span><span class="sxs-lookup"><span data-stu-id="97afa-109">NoRestriction</span></span>|<span data-ttu-id="97afa-110">Сайт можно перемещать в другое географическое расположение.</span><span class="sxs-lookup"><span data-stu-id="97afa-110">The site can be moved to another geo location.</span></span>|
|<span data-ttu-id="97afa-111">BlockMoveOnly</span><span class="sxs-lookup"><span data-stu-id="97afa-111">BlockMoveOnly</span></span>|<span data-ttu-id="97afa-112">Сайт нельзя перемещать в другое географическое расположение, но его содержимое можно кэшировать в других географических расположениях.</span><span class="sxs-lookup"><span data-stu-id="97afa-112">Site cannot be moved to another geo location, but site content can be cached in other geo locations.</span></span>|
|<span data-ttu-id="97afa-113">BlockFull</span><span class="sxs-lookup"><span data-stu-id="97afa-113">BlockFull</span></span>|<span data-ttu-id="97afa-114">Сайт нельзя перемещать в другое географическое расположение, и полное файловое содержимое не кэшируется в других географических расположениях.</span><span class="sxs-lookup"><span data-stu-id="97afa-114">Site cannot be moved to another geo location, and full file content is not cached in other geo locations.</span></span> <span data-ttu-id="97afa-115">Заголовок файлов (полученный из содержимого), имя файла и другие свойства файла по-прежнему могут кэшироваться в других географических расположениях.</span><span class="sxs-lookup"><span data-stu-id="97afa-115">Files' title (harvested from the content), file name, and other properties of the file can still be cached in other geo-locations.</span></span><br><span data-ttu-id="97afa-116">Содержимое, сохраненное на сайте до настройки значения BlockFull, можно продолжать кэшировать в других географических расположениях.</span><span class="sxs-lookup"><span data-stu-id="97afa-116">Content stored in the site before it was configured to BlockFull, may continue to be cached in other geo locations.</span></span>|

<span data-ttu-id="97afa-117">Используйте указанный ниже синтаксис.</span><span class="sxs-lookup"><span data-stu-id="97afa-117">Use the following syntax:</span></span>

`Set-SPOSite -Identity <siteURL> -RestrictedToGeo <restriction>`

<span data-ttu-id="97afa-118">Пример:</span><span class="sxs-lookup"><span data-stu-id="97afa-118">For example:</span></span>

`Set-SPOSite -Identity https://contoso.sharepoint.com/sites/RegionRestrictedTeamSite -RestrictedToGeo BlockFull`
