---
title: Поддержка нескольких регионов в OneDrive и SharePoint Online
ms.reviewer: adwood
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: o365-solutions
f1.keywords:
- NOCSH
ms.custom: ''
ms.collection:
- Strat_SP_gtc
- SPO_Content
- m365solution-scenario
- m365solution-spintranet
localization_priority: Normal
ms.assetid: 094e86f2-9ff0-40ac-af31-28fcaba00c1d
description: Расширьте свою географию присутствия Microsoft 365 с поддержкой нескольких регионов в OneDrive Online.
ms.openlocfilehash: 405f876317a6cec6defdf3f1a49b0dc32ac0add2
ms.sourcegitcommit: f7fbf45af64c5c0727fd5eaab309d20ad097a483
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/09/2021
ms.locfileid: "53362286"
---
# <a name="multi-geo-capabilities-in-onedrive-and-sharepoint-online"></a>Поддержка нескольких регионов в OneDrive и SharePoint Online

Возможности multi-Geo в OneDrive и SharePoint Online позволяют управлять общими ресурсами, например сайтами SharePoint и почтовыми ящиками Microsoft 365 Group, хранимых в покое в указанном географическом расположении.

У каждого пользователя, почтового ящика группы и сайта SharePoint есть предпочтительное расположение данных (PDL), обозначающее географическое расположение для хранения соответствующих данных. Персональные данные пользователей (почтовый ящик Exchange и OneDrive), а также любые созданные им группы Microsoft 365 или сайты SharePoint могут храниться в указанном географическом расположении для соблюдения требований к месту расположения данных. Можно [указывать разных администраторов для каждого географического расположения](add-a-sharepoint-geo-admin.md).

Для пользователей обеспечивается удобство взаимодействия при использовании служб Microsoft 365, включая приложения Office, OneDrive и поиск. Подробные сведения см. в статье [Взаимодействие с пользователем в среде с поддержкой нескольких регионов](multi-geo-user-experience.md).

## <a name="onedrive"></a>OneDrive

Хранилище OneDrive каждого пользователя может быть подготовлено или [перемещено администратором](move-onedrive-between-geo-locations.md) в периферийное расположение в соответствии с предпочтительным расположением данных (PDL) пользователя. После этого личные файлы хранятся в этом географическом расположении, но ими можно делиться с пользователями из других географических расположений.

## <a name="sharepoint-sites-and-groups"></a>Сайты и группы SharePoint

Функцией поддержки нескольких регионов можно управлять в Центре администрирования SharePoint. Подробные сведения см. в [соответствующей записи блога](https://techcommunity.microsoft.com/t5/Office-365-Blog/Now-available-Multi-Geo-in-SharePoint-and-Office-365-Groups/ba-p/263302).

Когда пользователь создает подключенный к группе сайт SharePoint в среде с поддержкой нескольких регионов, его значение PDL используется для определения географического расположения, в котором создается сайт и почтовый ящик связанной группы. (Если значение PDL пользователя не задано или присвоено географическое расположение, не настроенное в качестве периферийного расположения, сайт и почтовый ящик создаются в центральном расположении.)

Microsoft 365, кроме Exchange, OneDrive, SharePoint и Teams, не являются Multi-Geo. Однако Microsoft 365 группы, созданные этими службами, будут настроены с помощью PDL создателя и их Exchange группового почтового ящика, SharePoint сайт будет создан в соответствующем geo. 

## <a name="managing-the-multi-geo-environment"></a>Управление средой с поддержкой нескольких регионов

Настройка и управление средой с поддержкой нескольких регионов осуществляется через Центр администрирования SharePoint. 

![Снимок экрана: страница географических расположений в Центре администрирования SharePoint](../media/sharepoint-multi-geo-admin-center.png)

(Некоторые действия, например перемещение сайта SharePoint или сайта OneDrive, требуют использования Microsoft PowerShell.)

## <a name="see-also"></a>См. также

[Поддержка нескольких регионов в SharePoint и группах Microsoft 365](https://techcommunity.microsoft.com/t5/Office-365-Blog/Now-available-Multi-Geo-in-SharePoint-and-Office-365-Groups/ba-p/263302)

[Администрирование среды с поддержкой нескольких регионов](administering-a-multi-geo-environment.md)

[Квоты хранилища SharePoint в средах с поддержкой нескольких регионов](sharepoint-multi-geo-storage-quota.md)

[Администрирование почтовых ящиков Exchange Online в среде с поддержкой нескольких регионов](administering-exchange-online-multi-geo.md)
