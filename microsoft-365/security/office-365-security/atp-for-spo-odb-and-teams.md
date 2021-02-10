---
title: Безопасные вложения для SharePoint, OneDrive и Microsoft Teams
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.date: ''
ms.topic: conceptual
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
description: Узнайте о Microsoft Defender для Office 365 для файлов в SharePoint Online, OneDrive для бизнеса и Microsoft Teams.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 640867cb38dab650bca990fe36c0b7cea7f6a0d8
ms.sourcegitcommit: 3dc795ea862b180484f76b3eb5d046e74041252b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/10/2021
ms.locfileid: "50175731"
---
# <a name="safe-attachments-for-sharepoint-onedrive-and-microsoft-teams"></a>Безопасные вложения для SharePoint, OneDrive и Microsoft Teams

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Область применения**
- [Microsoft Defender для Office 365 (план 1 и план 2)](https://go.microsoft.com/fwlink/?linkid=2148715)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

Безопасные вложения для SharePoint, OneDrive и Microsoft Teams в [Microsoft Defender для Office 365](office-365-atp.md) обеспечивают дополнительный уровень защиты файлов, которые уже были сканированы во время отправки распространенным механизмом обнаружения вирусов в Microsoft [365.](virus-detection-in-spo.md) Безопасные вложения для SharePoint, OneDrive и Microsoft Teams помогают обнаруживать и блокировать существующие файлы, которые определены как вредоносные на сайтах групп и в библиотеках документов.

Безопасные вложения для SharePoint, OneDrive и Microsoft Teams по умолчанию не включены. Чтобы включить его, см. раздел "Включить безопасные [вложения для SharePoint, OneDrive и Microsoft Teams".](turn-on-atp-for-spo-odb-and-teams.md)

## <a name="how-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams-works"></a>Как работают безопасные вложения для SharePoint, OneDrive и Microsoft Teams

Если в SharePoint, OneDrive и Microsoft Teams включены безопасные вложения и файл идентифицируется как вредоносный, файл блокируется с помощью прямой интеграции с хранилищами файлов. На следующем рисунке показан пример вредоносного файла, обнаруженного в библиотеке.

![Файлы в OneDrive для бизнеса с одним из них, обнаруженными как вредоносные](../../media/2bba71cc-7ad1-4799-8b9d-d56f923db3a7.png)

Хотя заблокированный файл по-прежнему находится в библиотеке документов и в веб-приложениях, мобильных или классических приложениях, пользователи не могут открывать, копировать, перемещать или делиться файлом. Но они могут удалить заблокированный файл.

Вот пример того, как заблокированный файл выглядит на мобильном устройстве:

![Удаление заблокированного файла из OneDrive для бизнеса из мобильного приложения OneDrive](../../media/cb1c1705-fd0a-45b8-9a26-c22503011d54.png)

По умолчанию люди могут скачать заблокированный файл. Вот как выглядит скачивание заблокированного файла на мобильном устройстве:

![Скачивание заблокированного файла в OneDrive для бизнеса](../../media/be288a82-bdd8-4371-93d8-1783db3b61bc.png)

Администраторы SharePoint Online могут запретить скачивание вредоносных файлов. Инструкции см. в [sharePoint Online PowerShell, чтобы](turn-on-atp-for-spo-odb-and-teams.md#step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files)запретить пользователям скачивать вредоносные файлы.

Чтобы узнать больше о пользовательском интерфейсе при обнаружении файла как вредоносного, см. раздел "Что делать при обнаружении вредоносного файла в [SharePoint Online, OneDrive или Microsoft Teams".](https://support.microsoft.com/office/01e902ad-a903-4e0f-b093-1e1ac0c37ad2)

## <a name="view-information-about-malicious-files-detected-by-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams"></a>Просмотр сведений о вредоносных файлах, обнаруженных с помощью безопасных вложений для SharePoint, OneDrive и Microsoft Teams

Файлы, которые определены Как вредоносные в Microsoft Defender для Office 365, будут показываться в отчетах для Microsoft Defender для [Office 365](view-reports-for-atp.md) и [в проводнике (и](threat-explorer.md)обнаружения в режиме реального времени).

С мая 2018 г., когда Microsoft Defender для Office 365 определил файл как вредоносный, он также доступен в карантине. Дополнительные сведения см. в центре безопасности & соответствия требованиям для управления файлами [на карантине.](manage-quarantined-messages-and-files.md#microsoft-defender-for-office-365-only-use-the-security--compliance-center-to-manage-quarantined-files)

## <a name="keep-these-points-in-mind"></a>Помните об этих моментах

- Защитник Office 365 не будет сканировать каждый файл в SharePoint Online, OneDrive для бизнеса или Microsoft Teams. Данное поведение является особенностью продукта. Файлы проверяются асинхронно. Этот процесс использует события общего доступа и гостевой активности, а также интеллектуальные сигналы и сигналы угроз для идентификации вредоносных файлов.

- Убедитесь, что сайты SharePoint настроены на использование современного [опыта.](https://docs.microsoft.com/sharepoint/guide-to-sharepoint-modern-experience) Защита в Защитнике Office 365 применяется как в современном, так и в классическом представлении; Однако визуальные индикаторы блокировки файла доступны только в современном средстве.

- Безопасные вложения для SharePoint, OneDrive и Microsoft Teams входят в общую стратегию вашей организации по защите от угроз, которая включает защиту от нежелательной почты и вредоносных программ в Exchange Online Protection (EOP), а также безопасные ссылки и безопасные вложения в Microsoft Defender для Office 365. Дополнительные информации см. в этой [теме, в этой теме вы узнаете, как защититься от угроз в Office 365.](protect-against-threats.md)
