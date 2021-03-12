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
localization_priority: Normal
search.appverid:
- SPO160
- MOE150
- MET150
ms.assetid: e3c6df61-8513-499d-ad8e-8a91770bff63
ms.collection:
- M365-security-compliance
description: Узнайте, как SharePoint Online обнаруживает вирусы в файлах, которые загружают пользователи, и не позволяет пользователям загружать или синхронизировать файлы.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 9ba3d19c6b04b93d9b1089540b7483d8b2e7246c
ms.sourcegitcommit: 3d48e198e706f22ac903b346cadda06b2368dd1e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/11/2021
ms.locfileid: "50727503"
---
# <a name="built-in-virus-protection-in-sharepoint-online-onedrive-and-microsoft-teams"></a>Встроенная защита от вирусов в SharePoint Online, OneDrive и Microsoft Teams

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Область применения**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender для Office 365 (план 1 и план 2)](office-365-atp.md)

Microsoft 365 использует общий механизм обнаружения вирусов для сканирования файлов, которые пользователи загружают в SharePoint Online, OneDrive и Microsoft Teams. Эта защита включена во все подписки, включаю в себя SharePoint Online, OneDrive и Microsoft Teams.

> [!IMPORTANT]
> Встроенные антивирусные возможности помогают сдержать вирусы. Они не предназначены как одна точка защиты от вредоносных программ для вашей среды. Мы рекомендуем всем клиентам исследовать и внедрять защиту от вредоносных программ на различных уровнях и применять лучшие практики для обеспечения безопасности корпоративной инфраструктуры. Дополнительные сведения о стратегиях и лучших практиках см. в ["Дорожной карте безопасности".](security-roadmap.md)

## <a name="what-happens-if-an-infected-file-is-uploaded-to-sharepoint-online"></a>Что произойдет, если зараженный файл будет загружен в SharePoint Online?

Двигатель обнаружения вирусов Microsoft 365 работает асинхронно (независимо от загрузки файлов) в SharePoint Online. **Все файлы не сканируются автоматически.** Heuristics определяет файлы для сканирования. Если в файле обнаружен вирус, файл помечен. В апреле 2018 г. мы удалили ограничение в 25 МБ для отсканированных файлов.

Ниже вкратце описано, что происходит.

1. Пользователь отправляет файл в SharePoint Online.
2. SharePoint Online в рамках процессов сканирования вирусов позже определяет, соответствует ли файл критериям проверки.
3. Если файл соответствует критериям проверки, двигатель обнаружения вирусов сканирует файл.
4. Если вирус найден в отсканированном файле, вирусный двигатель задает свойство в файле, указывающее, что он заражен.

## <a name="what-happens-when-a-user-tries-to-download-an-infected-file-by-using-the-browser"></a>Что происходит, когда пользователь пытается скачать зараженный файл через браузер?

Если файл заражен, пользователи не могут скачать файл из SharePoint Online с помощью браузера.

Ниже вкратце описано, что происходит.

1. Пользователь открывает веб-браузер и пытается скачать зараженный файл из SharePoint Online.
2. Пользователю дается предупреждение об обнаружении вируса. По умолчанию пользователю предоставляется возможность скачивать файл и пытаться очистить его с помощью антивирусного программного обеспечения на своем устройстве.

> [!NOTE]
>
> Администраторы могут использовать параметр *DisallowInfectedFileDownload* в комлете [Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant) в SharePoint Online PowerShell, чтобы запретить пользователям скачивать зараженные файлы даже в окне предупреждения о вирусе. Инструкции см. в [раздел Использование SharePoint Online PowerShell, чтобы](turn-on-atp-for-spo-odb-and-teams.md#step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files)запретить пользователям скачивать вредоносные файлы.
>
> Как только вы включаете параметр *DisallowInfectedFileDownload,* доступ к обнаруженным/заблокированным файлам полностью блокируется для пользователей и администраторов.

## <a name="what-happens-when-the-onedrive-sync-client-tries-to-sync-an-infected-file"></a>Что происходит, когда клиент синхронизации OneDrive пытается синхронизировать зараженный файл?

Клиенты синхронизации OneDrive не будут загружать файлы, содержащие вирусы. Клиент выведет уведомление о том, что файл невозможно синхронизировать.

## <a name="extended-capabilities-with-microsoft-defender-for-office-365"></a>Расширенные возможности с Microsoft Defender для Office 365

Организации Microsoft 365, включив Microsoft [Defender для Office 365](office-365-atp.md) в подписку или приобретенные в качестве надстройки, могут включить безопасные вложения для SharePoint, OneDrive и Microsoft Teams для расширенной отчетности и защиты. Дополнительные сведения см. в [разделЕ Безопасные вложения для SharePoint, OneDrive и Microsoft Teams.](atp-for-spo-odb-and-teams.md)

## <a name="related-articles"></a>Связанные статьи

[Защита от вредоносных программ и программ-вымогателей в Microsoft 365](https://docs.microsoft.com/compliance/assurance/assurance-malware-and-ransomware-protection)

Дополнительные сведения о антивирусе в SharePoint Online, OneDrive [](protect-against-threats.md) и Microsoft Teams см. в разделе Защита от угроз и включите безопасные вложения [для SharePoint, OneDrive и Microsoft Teams.](turn-on-atp-for-spo-odb-and-teams.md)
