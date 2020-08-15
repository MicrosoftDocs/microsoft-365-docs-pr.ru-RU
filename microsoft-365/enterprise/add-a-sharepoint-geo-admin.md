---
title: Добавление и удаление администратора геообъектов
ms.reviewer: adwood
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: o365-solutions
ms.collection: SPO_Content
localization_priority: Normal
f1.keywords:
- NOCSH
description: Требуется настроить отдельных администраторов для каждого географического местоположения? Узнайте, как добавить или удалить администратора геообъектов в Microsoft 365 Multi-Geo.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 9a3d916bfec2c53850f923fb5322298e9ff440ca
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/14/2020
ms.locfileid: "46693533"
---
# <a name="add-or-remove-a-geo-administrator-in-microsoft-365-multi-geo"></a>Добавление и удаление администратора геообъектов в Microsoft 365 Multi-Geo.

Можно настроить отдельных администраторов для каждого географического расположения в клиенте. Эти администраторы получат доступ к параметрам SharePoint Online и OneDrive, относящимся к конкретным географическим расположениям.

Некоторые службы, например банк терминов, управляются из центрального расположения и копируются в периферийные расположения. Доступ к ним есть у администратора геообъектов в центральном расположении, но не у администраторов геообъектов в периферийных расположениях.

Глобальные администраторы и администраторы SharePoint Online сохраняют доступ к параметрам в центральном и всех периферийных расположениях.

## <a name="configuring-geo-administrators"></a>Настройка администраторов геообъектов

Для настройки администраторов геообъектов требуется модуль PowerShell в SharePoint Online.

Используйте команду [Connect-SPOService](https://docs.microsoft.com/powershell/module/sharepoint-online/Connect-SPOService) для подключения к центру администрирования геообъекта, для которого нужно добавить администратора. (Например, Connect-SPOService https://ContosoEUR-admin.sharepoint.com.)

Чтобы просмотреть существующих администраторов геообъектов в расположении, выполните команду `Get-SPOGeoAdministrator`

### <a name="adding-a-user-as-a-geo-admin"></a>Добавление пользователя в качестве администратора геообъекта

Чтобы добавить пользователя в качестве администратора геообъекта, выполните команду `Add-SPOGeoAdministrator -UserPrincipalName <UPN>`

Чтобы удалить пользователя из администраторов геообъекта в расположении, выполните команду `Remove-SPOGeoAdministrator -UserPrincipalName <UPN>`

### <a name="adding-a-group-as-a-geo-admin"></a>Добавление группы в качестве администратора геообъекта

Можно добавить группу безопасности или группу безопасности с поддержкой электронной почты в качестве администратора геообъекта. (Группы рассылки и группы Microsoft 365 не поддерживаются.)

Чтобы добавить группу в качестве администратора геообъекта, выполните команду `Add-SPOGeoAdministrator -GroupAlias <alias>`

Чтобы удалить группу из администраторов геообъекта, выполните команду `Remove-SPOGeoAdministrator -GroupAlias <alias>`

Обратите внимание, что не у всех групп безопасности есть псевдоним группы. Если нужно добавить группу безопасности без псевдонима, выполните команду [Get-MsolGroup](https://docs.microsoft.com/powershell/module/msonline/get-msolgroup) для получения списка групп, найдите ObjectID группы безопасности и выполните команду:

`Add-SPOGeoAdministrator -ObjectID <ObjectID>`

Чтобы удалить группу с помощью ObjectID, выполните команду `Remove-SPOGeoAdministrator -ObjectID <ObjectID>`

## <a name="related-topics"></a>Связанные статьи

[Add-SPOGeoAdministrator](https://docs.microsoft.com/powershell/module/sharepoint-online/add-spogeoadministrator)

[Get-SPOGeoAdministrator](https://docs.microsoft.com/powershell/module/sharepoint-online/get-spogeoadministrator)

[Remove-SPOGeoAdministrator](https://docs.microsoft.com/powershell/module/sharepoint-online/remove-spogeoadministrator)

[Установка псевдонима (MailNickName) для группы безопасности](https://docs.microsoft.com/powershell/module/azuread/set-azureadgroup)