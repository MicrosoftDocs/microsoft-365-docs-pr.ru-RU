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
description: Узнайте, как SharePoint Online обнаруживает вирусы в файлах, которые пользователи загружают, и не позволяет пользователям скачивать или синхронизировать файлы.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: f0eafb9e5e2f0c9d86791fe83931276e420afcd9
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/18/2021
ms.locfileid: "50286505"
---
# <a name="built-in-virus-protection-in-sharepoint-online-onedrive-and-microsoft-teams"></a>Встроенная защита от вирусов в SharePoint Online, OneDrive и Microsoft Teams

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Область применения**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender для Office 365 (план 1 и план 2)](office-365-atp.md)

Microsoft 365 использует распространенный механизм обнаружения вирусов для сканирования файлов, которые пользователи загружают в SharePoint Online, OneDrive и Microsoft Teams. Эта защита включена во все подписки, в том числе SharePoint Online, OneDrive и Microsoft Teams.

> [!IMPORTANT]
> Встроенные антивирусные возможности помогают сдержать вирусы. Они не предназначены в качестве единой точки защиты от вредоносных программ в вашей среде. Мы рекомендуем всем клиентам изучить и внедрить защиту от вредоносных программ на различных уровнях и применить лучшие методики защиты корпоративной инфраструктуры. Дополнительные сведения о стратегиях и советах см. в [стратегии безопасности.](security-roadmap.md)

## <a name="what-happens-when-an-infected-file-is-uploaded-to-sharepoint-online"></a>Что происходит при отправке зараженного файла в SharePoint Online?

Механизм обнаружения вирусов Microsoft 365 работает в SharePoint Online асинхронно. **Все файлы не проверяются автоматически при отправке.** Сканируйте файлы, которые необходимо сканировать, с его целью сканироваться с 1 по 100 000. Если файл содержит вирус, он помечается, поэтому его нельзя загрузить снова. В апреле 2018 г. мы удалили ограничение в 25 МБ для отсканированных файлов.

Ниже вкратце описано, что происходит.

1. Пользователь отправляет файл в SharePoint Online.
2. SharePoint Online определяет, соответствует ли файл критериям проверки.
3. Модуль поиска вирусов проверяет файл.
4. Если вирус найден, антивирусная система задает свойство файла, указывающее на то, что он заражен.

## <a name="what-happens-when-a-user-tries-to-download-an-infected-file-by-using-the-browser"></a>Что происходит, когда пользователь пытается скачать зараженный файл через браузер?

Если файл заражен, пользователи не смогут скачать его из SharePoint Online с помощью браузера.

Ниже вкратце описано, что происходит.

1. Пользователь открывает веб-браузер и пытается скачать зараженный файл из SharePoint Online.
2. Пользователю выдается предупреждение об обнаружении вируса. По умолчанию пользователю предоставляется возможность скачать файл и попытаться очистить его с помощью антивирусного программного обеспечения на своем устройстве.

> [!NOTE]
>
> Администраторы могут использовать параметр *DisallowInfectedFileDownload* в cmdlet [Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant) в SharePoint Online PowerShell, чтобы запретить пользователям скачивать зараженные файлы даже в окне предупреждения антивируса. Инструкции см. в [sharePoint Online PowerShell, чтобы](turn-on-atp-for-spo-odb-and-teams.md#step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files)запретить пользователям скачивать вредоносные файлы.
>
> Как только вы включаете параметр *DisallowInfectedFileDownload,* доступ к обнаруженным или заблокированным файлам полностью блокируется для пользователей и администраторов.

## <a name="what-happens-when-the-onedrive-sync-client-tries-to-sync-an-infected-file"></a>Что происходит, когда клиент синхронизации OneDrive пытается синхронизировать зараженный файл?

Клиенты синхронизации OneDrive не будут скачивать файлы, содержащие вирусы. Клиент выведет уведомление о том, что файл невозможно синхронизировать.

## <a name="extended-capabilities-with-microsoft-defender-for-office-365"></a>Расширенные возможности с помощью Microsoft Defender для Office 365

Организации Microsoft 365 с Microsoft [Defender для Office 365,](office-365-atp.md) включенными в подписку или приобретенными в качестве надстройки, могут включить безопасные вложения для SharePoint, OneDrive и Microsoft Teams для улучшенной отчетности и защиты. Дополнительные сведения см. в записях ["Безопасные вложения" для SharePoint, OneDrive и Microsoft Teams.](atp-for-spo-odb-and-teams.md)

## <a name="related-articles"></a>Связанные статьи

[Защита от вредоносных программ и программ-вымогателей в Microsoft 365](https://docs.microsoft.com/compliance/assurance/assurance-malware-and-ransomware-protection)

Дополнительные сведения о антивирусной защите в SharePoint Online, [](protect-against-threats.md) OneDrive и Microsoft Teams см. в подзащите от угроз и включите безопасные вложения для [SharePoint, OneDrive](turn-on-atp-for-spo-odb-and-teams.md)и Microsoft Teams.
