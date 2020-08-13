---
title: Обнаружение вирусов в SharePoint Online
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- SPO160
- MOE150
- MET150
ms.assetid: e3c6df61-8513-499d-ad8e-8a91770bff63
ms.collection:
- M365-security-compliance
description: Сведения о том, как SharePoint Online обнаруживает вирусы в файлах, отправляемых пользователями, и запрещает пользователям загружать или синхронизировать эти файлы.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 0e58fa8dc8b30c5bc6ff5db1508d8b7f9189b73a
ms.sourcegitcommit: 6a1a8aa024fd685d04da97bfcbc8eadacc488534
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/12/2020
ms.locfileid: "46653513"
---
# <a name="virus-detection-in-sharepoint-online-onedrive-and-microsoft-teams"></a>Обнаружение вирусов в SharePoint Online, OneDrive и Microsoft Teams

Microsoft 365 поможет защитить среду от вредоносных программ, обнаруживая вирусы в файлах, отправляемых пользователями в SharePoint Online, OneDrive и Microsoft Teams. После отправки файлы могут быть проверены на наличие вирусов. Если вирус заражен, для него задается соответствующее свойство, которое не позволяет пользователям скачать его из браузера или синхронизировать.

> [!IMPORTANT]
> Эти возможности в SharePoint Online позволяют включать вирусы. Они не предназначены для защиты от вредоносных программ в вашей среде. Мы рекомендуем всем клиентам оценивать и внедрять защиту от вредоносных программ на различных уровнях и применять рекомендации по обеспечению безопасности корпоративной инфраструктуры. Более подробную информацию о стратегиях и рекомендациях можно узнать в статье [Security Security](security-roadmap.md).

## <a name="what-happens-when-an-infected-file-is-uploaded-to-sharepoint-online"></a>Что происходит при отправке зараженного файла в SharePoint Online?

Microsoft 365 использует общий механизм обнаружения вирусов. Ядро работает асинхронно в SharePoint Online и сканирует некоторые файлы после их отправки. Эвристические алгоритмы используются для определения сканируемых файлов. Если выясняется, что файл содержит вирус, он помечается, чтобы его нельзя было снова скачать. В апреле 2018 был удален лимит в 25 МБ для сканированных файлов.

Ниже вкратце описано, что происходит.

1. Пользователь отправляет файл в SharePoint Online.

2. SharePoint Online определяет, соответствует ли файл условиям проверки.

3. Модуль поиска вирусов проверяет файл.

4. Если обнаружен вирус, антивирусная программа задает для файла свойство, указывающее на то, что оно заражено.

## <a name="what-happens-when-a-user-tries-to-download-an-infected-file-by-using-the-browser"></a>Что происходит, когда пользователь пытается скачать зараженный файл через браузер?

Если файл заражен, пользователи не могут скачать файл из SharePoint Online с помощью браузера.

Ниже вкратце описано, что происходит.

1. Пользователь открывает веб-браузер и пытается скачать зараженный файл из SharePoint Online.

2. Пользователю выдается предупреждение о том, что вирус обнаружен. Пользователю предоставляется возможность загрузить файл и попытаться очистить его с помощью собственного антивирусного программного обеспечения.

> [!NOTE]
>
> Вы можете использовать параметр *дисалловинфектедфиледовнлоад* командлета [Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant) в SharePoint Online PowerShell, чтобы запретить пользователям скачивать зараженный файл даже в окне предупреждения о антивирусной борьбе.
>
> Кроме того, следует учитывать, что при включении параметра *дисалловинфектедфиледовнлоад* доступ к обнаруженным и заблокированным файлам полностью блокируется для пользователей и администраторов.

## <a name="what-happens-when-the-onedrive-sync-client-tries-to-sync-an-infected-file"></a>Что происходит, когда клиент синхронизации OneDrive пытается синхронизировать зараженный файл?

Неважно, какой клиент вы используете  новый клиент синхронизации OneDrive (OneDrive.exe) или старый клиент синхронизации OneDrive для бизнеса(Groove.exe),  если файл содержит вирус, он не будет скачан. Клиент выведет уведомление о том, что файл невозможно синхронизировать.

## <a name="extended-capabilities-with-office-365-atp"></a>Расширенные возможности Office 365 ATP

Пользователи, которым разрешено Office 365 ATP для SharePoint, OneDrive и Microsoft Teams [включают ATP для SharePoint, onedrive и Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md) , могут использовать центр безопасности & соответствия требованиям для управления файлами на карантине для обнаружения AV и ATP. [Только ATP: используйте центр безопасности & соответствия требованиям для управления файлами, помещенными в карантин](manage-quarantined-messages-and-files.md#atp-only-use-the-security--compliance-center-to-manage-quarantined-files).

## <a name="more-information"></a>Дополнительные сведения

Для получения дополнительных сведений о настройке антивирусной программы SharePoint Online обратитесь к разделу [Защита от угроз](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats?view=o365-worldwide#requirements) и [Включение ATP для SharePoint, OneDrive и Microsoft Teams](https://docs.microsoft.com/microsoft-365/security/office-365-security/turn-on-atp-for-spo-odb-and-teams?view=o365-worldwide) .


