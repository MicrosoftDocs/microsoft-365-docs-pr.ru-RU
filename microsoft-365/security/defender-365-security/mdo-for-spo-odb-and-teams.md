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
ms.openlocfilehash: 80e30a52ef77dad32450bdfecc5010752b199b37
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51071325"
---
# <a name="safe-attachments-for-sharepoint-onedrive-and-microsoft-teams"></a>Безопасные вложения для SharePoint, OneDrive и Microsoft Teams

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Область применения**
- [Microsoft Defender для Office 365 (план 1 и план 2)](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Безопасные вложения для SharePoint, OneDrive и Microsoft Teams в [Microsoft Defender для Office 365](whats-new-in-defender-for-office-365.md) обеспечивают дополнительный уровень защиты для файлов, которые уже отсканированы во время отправки общим механизмом обнаружения вирусов в Microsoft [365](virus-detection-in-spo.md). Безопасные вложения для SharePoint, OneDrive и Microsoft Teams помогают обнаруживать и блокировать существующие файлы, которые идентифицированы как вредоносные на сайтах групп и библиотеках документов.

Безопасные вложения для SharePoint, OneDrive и Microsoft Teams не включены по умолчанию. Чтобы включить его, включив безопасные вложения [для SharePoint, OneDrive и Microsoft Teams.](turn-on-mdo-for-spo-odb-and-teams.md)

## <a name="how-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams-works"></a>Как работают безопасные вложения для SharePoint, OneDrive и Microsoft Teams

При включении безопасных вложений для SharePoint, OneDrive и Microsoft Teams и идентифицирует файл как вредоносный, файл блокируется с помощью прямой интеграции с хранилищами файлов. На следующем изображении показан пример вредоносного файла, обнаруженного в библиотеке.

![Файлы в OneDrive для бизнеса с одним, обнаруженным как вредоносные](../../media/2bba71cc-7ad1-4799-8b9d-d56f923db3a7.png)

Несмотря на то, что заблокированный файл по-прежнему перечислены в библиотеке документов и в веб-, мобильных или настольных приложениях, люди не могут открывать, копировать, перемещать или делиться файлом. Но они могут удалить заблокированный файл.

Вот пример того, как заблокированный файл выглядит на мобильном устройстве:

![Удаление заблокированного файла из OneDrive для бизнеса из мобильного приложения OneDrive](../../media/cb1c1705-fd0a-45b8-9a26-c22503011d54.png)

По умолчанию люди могут скачать заблокированный файл. Вот как выглядит загрузка заблокированного файла на мобильном устройстве:

![Загрузка заблокированного файла в OneDrive для бизнеса](../../media/be288a82-bdd8-4371-93d8-1783db3b61bc.png)

Администраторы SharePoint Online могут запретить людям скачивать вредоносные файлы. Инструкции см. в [раздел Использование SharePoint Online PowerShell, чтобы](turn-on-mdo-for-spo-odb-and-teams.md#step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files)запретить пользователям скачивать вредоносные файлы.

Дополнительные данные о пользовательском опыте, когда файл был обнаружен как вредоносный, см. в разделЕ Что делать при обнаружении вредоносного файла в [SharePoint Online, OneDrive или Microsoft Teams.](https://support.microsoft.com/office/01e902ad-a903-4e0f-b093-1e1ac0c37ad2)

## <a name="view-information-about-malicious-files-detected-by-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams"></a>Просмотр сведений о вредоносных файлах, обнаруженных в безопасных вложениях для SharePoint, OneDrive и Microsoft Teams

Файлы, которые определены как вредоносные в Microsoft Defender для Office 365, будут показываться в отчетах для Microsoft Defender для [Office 365](view-reports-for-mdo.md) и в Explorer (и обнаружения в режиме [реального времени).](threat-explorer.md)

С мая 2018 г., когда microsoft Defender для Office 365 выявляет файл как вредоносный, он также доступен в карантине. Дополнительные сведения см. в материалах Центра & безопасности для управления [карантинными файлами.](manage-quarantined-messages-and-files.md#microsoft-defender-for-office-365-only-use-the-security--compliance-center-to-manage-quarantined-files)

## <a name="keep-these-points-in-mind"></a>Имейте в виду эти точки

- Defender for Office 365 не будет сканировать каждый файл в SharePoint Online, OneDrive для бизнеса или Microsoft Teams. Данное поведение является особенностью продукта. Файлы сканируют асинхронно. В этом процессе для выявления вредоносных файлов используются события совместной и гостевой активности, а также интеллектуальные heuristics и сигналы угрозы.

- Убедитесь, что сайты SharePoint настроены для использования современного [опыта.](/sharepoint/guide-to-sharepoint-modern-experience) Защита Defender для Office 365 применяется независимо от того, используется ли современный опыт или классическое представление; Однако визуальные индикаторы блокировки файла доступны только в современном опыте.

- Безопасные вложения для SharePoint, OneDrive и Microsoft Teams являются частью общей стратегии защиты от угроз организации, которая включает защиту от нежелательной почты и вредоносных программ в Exchange Online Protection (EOP), а также безопасные ссылки и безопасные вложения в Microsoft Defender для Office 365. Дополнительные новости см. в см. в руб. Защита от [угроз в Office 365.](protect-against-threats.md)