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
ms.openlocfilehash: 84abfc01d5073889e998347f58d4a3e8bb29ea33
ms.sourcegitcommit: 5a355bde865369f64ea1788a378da23c65b1d249
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/06/2020
ms.locfileid: "48930181"
---
# <a name="multi-geo-capabilities-in-onedrive-and-sharepoint-online"></a>Поддержка нескольких регионов в OneDrive и SharePoint Online

Поддержка нескольких регионов в OneDrive и SharePoint Online обеспечивает управление страной или регионом, в котором хранятся общие ресурсы, такие как сайты групп SharePoint и почтовые ящики групп Microsoft 365.

У каждого пользователя, почтового ящика группы и сайта SharePoint есть предпочтительное расположение данных (PDL), обозначающее географическое расположение для хранения соответствующих данных. Персональные данные пользователей (почтовый ящик Exchange и OneDrive), а также любые созданные им группы Microsoft 365 или сайты SharePoint могут храниться в указанном географическом расположении для соблюдения требований к месту расположения данных. Можно [указывать разных администраторов для каждого географического расположения](add-a-sharepoint-geo-admin.md).

Для пользователей обеспечивается удобство взаимодействия при использовании служб Microsoft 365, включая приложения Office, OneDrive и поиск. Подробные сведения см. в статье [Взаимодействие с пользователем в среде с поддержкой нескольких регионов](multi-geo-user-experience.md).

## <a name="onedrive"></a>OneDrive

Хранилище OneDrive каждого пользователя может быть подготовлено или [перемещено администратором](move-onedrive-between-geo-locations.md) в периферийное расположение в соответствии с предпочтительным расположением данных (PDL) пользователя. После этого личные файлы хранятся в этом географическом расположении, но ими можно делиться с пользователями из других географических расположений.

## <a name="sharepoint-sites-and-groups"></a>Сайты и группы SharePoint

Функцией поддержки нескольких регионов можно управлять в Центре администрирования SharePoint. Подробные сведения см. в [соответствующей записи блога](https://techcommunity.microsoft.com/t5/Office-365-Blog/Now-available-Multi-Geo-in-SharePoint-and-Office-365-Groups/ba-p/263302).

Когда пользователь создает подключенный к группе сайт SharePoint в среде с поддержкой нескольких регионов, его значение PDL используется для определения географического расположения, в котором создается сайт и почтовый ящик связанной группы. (Если значение PDL пользователя не задано или присвоено географическое расположение, не настроенное в качестве периферийного расположения, сайт и почтовый ящик создаются в центральном расположении.)

В службах Microsoft 365, кроме Exchange, OneDrive и SharePoint, отсутствует поддержка нескольких регионов. Однако группы Microsoft 365, созданные с помощью этих служб, помечаются значением PDL создавшего их пользователя, а почтовый ящик Exchange группы и сайт группы SharePoint Office 365 подготавливаются в соответствующем географическом расположении. 

## <a name="managing-the-multi-geo-environment"></a>Управление средой с поддержкой нескольких регионов

Настройка и управление средой с поддержкой нескольких регионов осуществляется через Центр администрирования SharePoint. 

![Снимок экрана: страница географических расположений в Центре администрирования SharePoint](../media/sharepoint-multi-geo-admin-center.png)

(Некоторые действия, например перемещение сайта SharePoint или сайта OneDrive, требуют использования Microsoft PowerShell.)

## <a name="see-also"></a>См. также

[Поддержка нескольких регионов в SharePoint и группах Microsoft 365](https://techcommunity.microsoft.com/t5/Office-365-Blog/Now-available-Multi-Geo-in-SharePoint-and-Office-365-Groups/ba-p/263302)

[Администрирование среды с поддержкой нескольких регионов](administering-a-multi-geo-environment.md)

[Квоты хранилища SharePoint в средах с поддержкой нескольких регионов](sharepoint-multi-geo-storage-quota.md)

[Администрирование почтовых ящиков Exchange Online в среде с поддержкой нескольких регионов](administering-exchange-online-multi-geo.md)
