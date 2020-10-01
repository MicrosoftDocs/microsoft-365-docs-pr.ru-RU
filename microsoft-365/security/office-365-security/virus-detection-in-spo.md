---
title: Встроенная защита от вирусов в SharePoint Online, OneDrive и Microsoft Teams
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
ms.openlocfilehash: 38d6111fe665e0af79cbd93f534b1058881ff76c
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/01/2020
ms.locfileid: "48327991"
---
# <a name="built-in-virus-protection-in-sharepoint-online-onedrive-and-microsoft-teams"></a>Встроенная защита от вирусов в SharePoint Online, OneDrive и Microsoft Teams

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

Microsoft 365 использует общий модуль обнаружения вирусов для сканирования файлов, которые пользователи отправляют в SharePoint Online, OneDrive и Microsoft Teams. Эта защита включена со всеми подписками, включающими SharePoint Online, OneDrive и Microsoft Teams.

> [!IMPORTANT]
> Встроенные средства защиты от вирусов позволяют включать вирусы. Они не предназначены для защиты от вредоносных программ в вашей среде. Мы рекомендуем всем пользователям исследовать и внедрять защиту от вредоносных программ на различных уровнях и применять рекомендации по обеспечению безопасности инфраструктуры предприятия. Более подробную информацию о стратегиях и рекомендациях можно узнать в статье [Security Security](security-roadmap.md).

## <a name="what-happens-when-an-infected-file-is-uploaded-to-sharepoint-online"></a>Что происходит при отправке зараженного файла в SharePoint Online?

Антивирусный механизм обнаружения вирусов (Майкрософт 365) запускается асинхронно в SharePoint Online. **При отправке не выполняется автоматический поиск всех файлов**. Эвристические правила определяют сканируемые файлы. Если файл содержит вирус, он помечается с пометкой, поэтому его невозможно скачать повторно. В апреле 2018 был удален лимит в 25 МБ для сканированных файлов.

Ниже вкратце описано, что происходит.

1. Пользователь отправляет файл в SharePoint Online.
2. SharePoint Online определяет, соответствует ли файл условиям проверки.
3. Модуль поиска вирусов проверяет файл.
4. Если обнаружен вирус, антивирусная программа задает для файла свойство, указывающее на то, что оно заражено.

## <a name="what-happens-when-a-user-tries-to-download-an-infected-file-by-using-the-browser"></a>Что происходит, когда пользователь пытается скачать зараженный файл через браузер?

Если файл заражен, пользователи не могут скачать файл из SharePoint Online с помощью браузера.

Ниже вкратце описано, что происходит.

1. Пользователь открывает веб-браузер и пытается скачать зараженный файл из SharePoint Online.
2. Пользователю выдается предупреждение о том, что вирус обнаружен. По умолчанию пользователю предоставляется возможность загрузить файл и попытаться очистить его с помощью антивирусного программного обеспечения на отдельном устройстве.

> [!NOTE]
>
> Администраторы могут использовать параметр *дисалловинфектедфиледовнлоад* в командлете [Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant) в SharePoint Online PowerShell, чтобы запретить пользователям скачивать зараженные файлы даже в окне предупреждения о антивирусной борьбе. Инструкции можно найти [в статье Использование PowerShell для SharePoint Online, чтобы запретить пользователям скачивать вредоносные файлы](turn-on-atp-for-spo-odb-and-teams.md#step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files).
>
> После включения параметра *дисалловинфектедфиледовнлоад* доступ к обнаруженным и заблокированным файлам полностью блокируется для пользователей и администраторов.

## <a name="what-happens-when-the-onedrive-sync-client-tries-to-sync-an-infected-file"></a>Что происходит, когда клиент синхронизации OneDrive пытается синхронизировать зараженный файл?

Клиенты синхронизации OneDrive не будут скачивать файлы, содержащие вирусы. Клиент выведет уведомление о том, что файл невозможно синхронизировать.

## <a name="extended-capabilities-with-office-365-advanced-threat-protection"></a>Расширенные возможности с Office 365 Advanced Threat protection

В организациях Microsoft 365 с поддержкой [Office 365 Advanced Threat protection (ATP)](office-365-atp.md) , включенных в свою подписку или приобретенных в качестве надстройки, можно включить ATP для SharePoint, OneDrive и Microsoft Teams для расширенных отчетов и защиты. Для получения дополнительных сведений ознакомьтесь [со статьей ATP для SharePoint, OneDrive и Microsoft Teams](atp-for-spo-odb-and-teams.md).

## <a name="more-information"></a>Дополнительные сведения

Для получения дополнительных сведений о антивирусной борьбе в SharePoint Online, OneDrive и Microsoft Teams, ознакомьтесь со статьей [Защита от угроз](protect-against-threats.md) и [Включение ATP для SharePoint, OneDrive и Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md).
