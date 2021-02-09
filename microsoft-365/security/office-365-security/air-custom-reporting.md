---
title: Пользовательские решения для отчетов с автоматизированным исследованием и реагированием
keywords: SIEM, API, AIR, autoIR, ATP, автоматизированное исследование, интеграция, настраиваемый отчет
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Узнайте, как интегрировать автоматизированное исследование и реагирование на них с пользовательским или сторонним решением для отчетности.
ms.date: 01/29/2021
ms.custom:
- air
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 3d8363ada4de60d37cb0d247d8b1af74df4226d1
ms.sourcegitcommit: d739f48b991793c08522a3d5323beba27f0111b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/08/2021
ms.locfileid: "50142979"
---
# <a name="custom-or-third-party-reporting-solutions-for-microsoft-defender-for-office-365"></a>Пользовательские или сторонние решения для отчетов в Microsoft Defender для Office 365

С [помощью Microsoft Defender для Office 365](office-365-atp.md)вы получаете подробные сведения об [автоматизированных расследованиях.](air-view-investigation-results.md) Однако в некоторых организациях также используется пользовательское или стороне решение для отчетов. Если вашей организации нужно [](office-365-air.md) интегрировать сведения об автоматизированных расследованиях с таким решением, можно использовать API действий управления Office 365.

Ресурсы для настройки интеграции

|Ресурс|Описание|
|:---|:---|
|[Обзор API управления Office 365](https://docs.microsoft.com/office/office-365-management-api/office-365-management-apis-overview)|API действий управления Office 365 предоставляет сведения о различных действиях и событиях пользователей, администраторов, систем и политик из журналов действий Microsoft 365 и Azure Active Directory.|
|[Начало работы с API управления Office 365](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis)|API управления Office 365 использует Azure AD для предоставления служб проверки подлинности вашему приложению для доступа к данным Microsoft 365. Чтобы настроить эту возможность, выполните действия, которые необходимо предпринять в этой статье.|
|[Справочник по API действий управления Office 365](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference)|Вы можете использовать API действий управления Office 365 для получения сведений о действиях и событиях пользователей, администраторов, систем и политик из журналов действий Microsoft 365 и Azure AD. Прочитайте эту статью, чтобы узнать больше о том, как это работает.|
|[Схема API действий управления Office 365](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema)|Обзор общей схемы и Защитника [Office 365,](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema) а также схемы анализа угроз и реагирования на них, чтобы узнать о конкретных типах данных, доступных через API действий управления Office 365. [](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#common-schema)|
|

## <a name="see-also"></a>См. также

- [Microsoft Defender для Office 365](office-365-atp.md)
- [Автоматическое исследование и реагирование в Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir)
