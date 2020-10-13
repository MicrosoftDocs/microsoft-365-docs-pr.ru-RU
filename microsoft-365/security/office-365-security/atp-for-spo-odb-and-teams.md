---
title: ATP для SharePoint, OneDrive и Microsoft Teams
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.date: ''
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 26261670-db33-4c53-b125-af0662c34607
ms.collection:
- M365-security-compliance
- SPO_Content
- m365initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
description: Сведения о Advanced Threat Protection в Office 365 для файлов в SharePoint Online, OneDrive для бизнеса и Microsoft Teams.
ms.openlocfilehash: e536809c74abbe87e1250acda3f3922180cfae97
ms.sourcegitcommit: 9a764c2aed7338c37f6e92f5fb487f02b3c4dfa1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/13/2020
ms.locfileid: "48446267"
---
# <a name="atp-for-sharepoint-onedrive-and-microsoft-teams"></a>ATP для SharePoint, OneDrive и Microsoft Teams

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

ATP для SharePoint, OneDrive и Microsoft Teams в [Office 365 Advanced Threat protection (ATP)](office-365-atp.md) обеспечивает дополнительный уровень защиты для файлов, которые уже были проверены во время отправки с помощью [общего модуля обнаружения вирусов в Microsoft 365](virus-detection-in-spo.md). ATP для SharePoint, OneDrive и Microsoft Teams помогает обнаруживать и блокировать существующие файлы, которые определены как вредоносные на сайтах групп и библиотеках документов.

Служба ATP для SharePoint, OneDrive и Microsoft Teams по умолчанию отключена. Чтобы включить его, ознакомьтесь со статьей [Включение ATP для SharePoint, OneDrive и Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md).

## <a name="how-atp-for-sharepoint-onedrive-and-microsoft-teams-works"></a>Принципы работы ATP для SharePoint, OneDrive и Microsoft Teams

Когда ATP для SharePoint, OneDrive и Microsoft Teams включается и определяет файл как вредоносный, файл блокируется с помощью непосредственной интеграции с хранилищами файлов. На следующем рисунке показан пример вредоносного файла, обнаруженного в библиотеке.

![Файлы в OneDrive для бизнеса с одной обнаруженной вредоносной службой](../../media/2bba71cc-7ad1-4799-8b9d-d56f923db3a7.png)

Несмотря на то, что заблокированный файл все еще отображается в библиотеке документов, в веб-приложениях, мобильных или настольных компьютерах, пользователи не могут открывать, копировать, перемещать файлы и предоставлять к ним общий доступ. Но они могут удалить заблокированный файл.

Ниже приведен пример того, как выглядит заблокированный файл на мобильном устройстве:

![Удаление заблокированного файла из OneDrive для бизнеса из мобильного приложения OneDrive](../../media/cb1c1705-fd0a-45b8-9a26-c22503011d54.png)

По умолчанию пользователи могут скачать заблокированный файл. Ниже показано, как выполняется загрузка заблокированного файла на мобильном устройстве.

![Скачивание заблокированного файла в OneDrive для бизнеса](../../media/be288a82-bdd8-4371-93d8-1783db3b61bc.png)

Администраторы SharePoint Online могут запретить пользователям загружать вредоносные файлы. Инструкции можно найти [в статье Использование PowerShell для SharePoint Online, чтобы запретить пользователям скачивать вредоносные файлы](turn-on-atp-for-spo-odb-and-teams.md#step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files).

Чтобы узнать больше о пользовательском интерфейсе, когда файл был определен как вредоносный, посмотрите, [что делать, когда вредоносный файл обнаружен в SharePoint Online, OneDrive или Microsoft Teams](https://support.microsoft.com/office/01e902ad-a903-4e0f-b093-1e1ac0c37ad2).

## <a name="view-information-about-malicious-files-detected-by-atp-for-sharepoint-onedrive-and-microsoft-teams"></a>Просмотр сведений о вредоносных файлах, обнаруженных ATP для SharePoint, OneDrive и Microsoft Teams

Файлы, идентифицируемые средством ATP, будут отображаться в [отчетах для Office 365 Advanced Threat protection](view-reports-for-atp.md) и в [Проводнике (и обнаружения в режиме реального времени)](threat-explorer.md).

По достижении мая 2018, когда файл определяется как вредоносный для ATP, он также доступен в карантине. Дополнительные сведения можно найти [в статье Использование центра безопасности & соответствия требованиям для управления файлами, помещенными в карантин](manage-quarantined-messages-and-files.md#atp-only-use-the-security--compliance-center-to-manage-quarantined-files).

## <a name="keep-these-points-in-mind"></a>Помните об этих моментах

- ATP не будет сканировать каждый отдельный файл в SharePoint Online, OneDrive для бизнеса или Microsoft Teams. Данное поведение является особенностью продукта. Файлы сканируются асинхронно. Процесс использует события общего доступа и гостевых действий, а также интеллектуальные эвристики и сигналы угроз для определения вредоносных файлов.

- Убедитесь, что сайты SharePoint настроены на использование [современного интерфейса](https://docs.microsoft.com/sharepoint/guide-to-sharepoint-modern-experience). Защита ATP определяет, используется ли современный интерфейс или классическое представление; Однако визуальные индикаторы, заблокированные файлом, доступны только в современном интерфейсе.

- ATP для SharePoint, OneDrive и Microsoft Teams является частью общей стратегии защиты от угроз, включающей защиту от нежелательной почты и вредоносных программ в Exchange Online Protection (EOP), а также безопасные ссылки и безопасные вложения в Office 365 ATP. Чтобы узнать больше, ознакомьтесь [со статьей защита от угроз в Office 365](protect-against-threats.md).
