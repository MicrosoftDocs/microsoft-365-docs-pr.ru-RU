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
ms.openlocfilehash: 4d0a9ba7ee40c8ad97df745a20d6b5b3314bb3d8
ms.sourcegitcommit: cd55fe6abe25b1e4f5fbe8295d3a99aebd97ce66
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/23/2021
ms.locfileid: "53083192"
---
# <a name="explorer-and-real-time-detections-basics"></a>Основы обнаружения explorer и обнаружения в режиме реального времени

**Область применения**
- [Microsoft Defender для Office 365 (план 1 и план 2)](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

В этой статье

- [Различия между обнаружениями Explorer и в режиме реального времени](#differences-between-explorer-and-real-time-detections)
- [Обязательные лицензии и разрешения](#required-licenses-and-permissions)

> [!NOTE]
> Это часть трехсерийной серии в Обозревателе (также известном как **Обозреватель угроз),** безопасности электронной почты, а также базовых обнаружениях explorer и в режиме реального времени **(таких** как различия между инструментами и разрешениями, необходимыми для их работы).   Другие две статьи в этой серии : [охота](threat-hunting-in-threat-explorer.md) на угрозы в Explorer и [безопасность электронной почты с помощью Explorer.](email-security-in-microsoft-defender.md)

В этой статье объясняется разница между отчетами об обнаружениях Explorer и обнаружениями в режиме реального времени, а также требуемой лицензией и разрешениями.

Если в вашей организации есть microsoft Defender [для](defender-for-office-365.md)Office 365, и у вас есть [разрешения,](#required-licenses-and-permissions)для  обнаружения и устранения угроз можно использовать **explorer** (также известный как **Explorer** угроз) или обнаружения в режиме реального времени.

На портале Microsoft 365 Defender () перейдите к совместной работе & электронной почты, а затем выберите обнаружение Explorer или в <https://security.microsoft.com>   **режиме реального времени.** 

С помощью этих средств можно выполнять перечисленные ниже действия.

- См. вредоносные программы, обнаруженные Microsoft 365 функциями безопасности.
- Просмотр фишинговых URL-адресов и щелкните данные вердикта.
- Запустите автоматизированный процесс расследования и ответа из представления в Explorer.
- Изучение вредоносных сообщений электронной почты и другие.

Дополнительные сведения см. в [сообщении email security with Explorer.](email-security-in-microsoft-defender.md)

## <a name="differences-between-explorer-and-real-time-detections"></a>Различия между обнаружениями Explorer и в режиме реального времени

- *Обнаружение в режиме реального* времени — это средство отчетности, доступное в Defender для Office 365 Plan 1. *Обозреватель угроз* — это средство поиска и устранения угроз, доступное в Defender для Office 365 Plan 2.
- Отчет о обнаружениях в режиме реального времени позволяет просматривать обнаружения в режиме реального времени. Это также делает обозреватель угроз, но он предоставляет дополнительные сведения для данной атаки, например выделение кампаний атак, и предоставляет [](automated-investigation-response-office.md)командам операций безопасности возможность устранять угрозы (включая запуск автоматического расследования и расследования ответов).
- Все *представления электронной* почты доступны в Обозревателе угроз, но не включены в отчет о обнаружениях в режиме реального времени.
- Богатые возможности фильтрации и действия по исправлению включены в Обозреватель угроз. Дополнительные сведения см. в [описании Microsoft Defender для службы Office 365:](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans)доступность функций в Defender для Office 365 планов.

## <a name="required-licenses-and-permissions"></a>Обязательные лицензии и разрешения

Вы должны иметь [Microsoft Defender, Office 365](defender-for-office-365.md) использовать обнаружения Explorer или в режиме реального времени:

- Explorer включен только в Defender для Office 365 Plan 2.
- Отчет о обнаружениях в режиме реального времени включен в Defender для Office 365 плана 1.

Группы операций безопасности должны назначать лицензии всем пользователям, которые должны быть защищены defender для Office 365 и знать, что в обнаружениях Explorer и в режиме реального времени имеются данные обнаружения для лицензированных пользователей.

Для просмотра и использования обнаружения Explorer *или* в режиме реального времени необходимы следующие разрешения:

- В Defender для Office 365:
  - Управление организацией
  - Администратор безопасности (это может быть назначено в центре администрирования Azure Active Directory ( <https://aad.portal.azure.com> )
  - Читатель сведений о безопасности
- В Exchange Online:
  - Управление организацией
  - Управление организацией только с правом на просмотр
  - Получатели только для чтения
  - Управление соответствием требованиям

Дополнительные информацию о ролях и разрешениях см. в следующих статьях:

- [Разрешения на портале Microsoft 365 Defender](permissions-microsoft-365-security-center.md)
- [Разрешения в Exchange Online](/e/exchange/permissions-exo/permissions-exo)

## <a name="more-information"></a>Дополнительная информация

- [Обозреватель угроз собирает сведения электронной почты на странице сущности электронной почты](mdo-email-entity-page.md)
- [Поиск и изучение доставленной нежелательной почты](investigate-malicious-email-that-was-delivered.md)
- [Просмотр вредоносных файлов, обнаруженных в SharePoint Online, OneDrive и Microsoft Teams](mdo-for-spo-odb-and-teams.md)
- [отчет о состоянии защиты от угроз](view-email-security-reports.md#threat-protection-status-report);
- [Автоматизированный анализ угроз и реакция на угрозы в службе защиты от угроз (Майкрософт)](automated-investigation-response-office.md)
