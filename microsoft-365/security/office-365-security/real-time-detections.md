---
title: Обозреватель угроз и обнаружение в режиме реального времени в Microsoft Defender для Office 365
f1.keywords:
- NOCSH
ms.author: dansimp
author: MSFTTracyp
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: 05/05/2021
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Используйте обнаружения Explorer или в режиме реального времени для эффективного расследования и реагирования на угрозы.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 7ab7b5731d121106d930868b03330d4ac7befd77
ms.sourcegitcommit: de5fce90de22ba588e75e1a1d2e87e03b9e25ec7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/10/2021
ms.locfileid: "52300219"
---
# <a name="threat-explorer-and-real-time-detections-basics"></a>Обозреватель угроз и основы обнаружения в режиме реального времени

В этой статье

- [Различия между обнаружением обозревателя угроз и обнаружения в режиме реального времени](#differences-between-threat-explorer-and-real-time-detections)<br/>
- [Обязательные лицензии и разрешения](#required-licenses-and-permissions)

> [!NOTE]
> Это часть трехсерийной серии по обозревателю угроз **(Explorer),** безопасности электронной почты **и** основам обнаружения explorer и в режиме реального времени **(например,** различия между инструментами и разрешениями, необходимыми для их работы).  Другие две статьи в этой серии : "Охота на угрозы в [обозревателе угроз"](threat-hunting-in-threat-explorer.md) и "Безопасность электронной почты [с помощью обозревателя угроз".](email-security-in-microsoft-defender.md)

В этой статье объясняется разница между отчетами об обнаружении угроз и обнаружениями в режиме реального времени, а также требуемой лицензией и разрешениями.

**Область применения**
- [Microsoft Defender для Office 365 (план 1 и план 2)](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Если в вашей организации есть microsoft  [Defender](defender-for-office-365.md)для Office 365, и у вас есть разрешения, для обнаружения и устранения угроз можно использовать обнаружение обозревателя угроз (под названием **Explorer)** или обнаружения в режиме реального времени. [](#required-licenses-and-permissions) 

В  Центре **&** безопасности перейдите к управлению угрозами, а затем выберите обнаружение **Explorer** или в **режиме реального времени.** 

<br>

****

|В Microsoft Defender для Office 365 Plan 2 см.:|В Microsoft Defender для Office 365 1 см.:|
|---|---|
|![Обозреватель угроз](../../media/threatmgmt-explorer.png)|![Обнаружение в режиме реального времени](../../media/threatmgmt-realtimedetections.png)|
|

С помощью этих средств можно выполнять перечисленные ниже действия.

- См. вредоносные программы, обнаруженные Microsoft 365 функциями безопасности.
- Просмотр фишинговых URL-адресов и щелкните данные вердикта.
- Запустите автоматизированный процесс расследования и ответа из представления в Explorer.
- Изучение вредоносных сообщений электронной почты и другие.

Дополнительные сведения см. в [сообщении email security with Threat Explorer.](email-security-in-microsoft-defender.md)

## <a name="differences-between-threat-explorer-and-real-time-detections"></a>Различия между обнаружением обозревателя угроз и обнаружения в режиме реального времени

- *Обнаружение в режиме реального* времени — это средство отчетности, доступное в Defender для Office 365 Plan 1. *Обозреватель угроз* — это средство поиска и устранения угроз, доступное в Defender для Office 365 Plan 2.
- Отчет о обнаружениях в режиме реального времени позволяет просматривать обнаружения в режиме реального времени. Это также делает обозреватель угроз, но он предоставляет дополнительные сведения для данной атаки, например выделение кампаний атак, и предоставляет [](automated-investigation-response-office.md)командам операций безопасности возможность устранять угрозы (включая запуск автоматического расследования и расследования ответов).
- Все *представления электронной* почты доступны в Обозревателе угроз, но не включены в отчет о обнаружениях в режиме реального времени.
- Богатые возможности фильтрации и действия по исправлению включены в Обозреватель угроз. Дополнительные сведения см. в [описании Microsoft Defender для службы Office 365:](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans)доступность функций в Defender для Office 365 планов.

## <a name="required-licenses-and-permissions"></a>Обязательные лицензии и разрешения

Вы должны иметь [Microsoft Defender, Office 365](defender-for-office-365.md) использовать обнаружения Explorer или в режиме реального времени:

- Но Explorer включен только в Defender для Office 365 Plan 2.
- Отчет о обнаружениях в режиме реального времени включен в Defender для Office 365 плана 1.

Группы операций безопасности должны назначать лицензии всем пользователям, которые должны быть защищены defender для Office 365 и знать, что в обнаружениях Explorer и в режиме реального времени имеются данные обнаружения для лицензированных пользователей.

Чтобы просмотреть и использовать обнаружения Explorer *или* в режиме реального времени, необходимо иметь следующее:

- Центр обеспечения & безопасности:

  - Управление организацией
  - Администратор безопасности (это может быть назначено в центре администрирования Azure Active Directory ( <https://aad.portal.azure.com> )
  - Читатель сведений о безопасности

- Для Exchange Online:

  - Управление организацией
  - Управление организацией только с правом на просмотр
  - Получатели только для чтения
  - Управление соответствием требованиям

Дополнительные информацию о ролях и разрешениях см. в следующих ресурсах:

- [Разрешения в Центре безопасности и соответствия требованиям](permissions-in-the-security-and-compliance-center.md)
- [Разрешения компонентов в Exchange Online](/exchange/permissions-exo/feature-permissions)
- [Exchange Online PowerShell](/powershell/exchange/exchange-online-powershell)

## <a name="more-information"></a>Дополнительные сведения
- [Обозреватель угроз собирает сведения электронной почты на странице сущности электронной почты](mdo-email-entity-page.md)
- [Поиск и изучение доставленной нежелательной почты](investigate-malicious-email-that-was-delivered.md)
- [Просмотр вредоносных файлов, обнаруженных в SharePoint Online, OneDrive и Microsoft Teams](mdo-for-spo-odb-and-teams.md)
- [отчет о состоянии защиты от угроз](view-email-security-reports.md#threat-protection-status-report);
- [Автоматизированный анализ угроз и реакция на угрозы в службе защиты от угроз (Майкрософт)](automated-investigation-response-office.md)