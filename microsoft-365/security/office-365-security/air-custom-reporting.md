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
ms.openlocfilehash: 13782a8e0a8c691a66f214d3f9f03ef9cad4da1f
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/18/2021
ms.locfileid: "50287141"
---
# <a name="custom-or-third-party-reporting-solutions-for-microsoft-defender-for-office-365"></a>Пользовательские или сторонние решения для отчетов в Microsoft Defender для Office 365

С [помощью Microsoft Defender для Office 365](office-365-atp.md)вы получаете подробные сведения об [автоматизированных расследованиях.](air-view-investigation-results.md) Однако в некоторых организациях также используется пользовательское или стороне решение для отчетов. Если ваша организация хочет [](office-365-air.md) интегрировать сведения об автоматизированных расследованиях с таким решением, вы можете использовать API действий управления Office 365.

**Область применения**
- [Microsoft Defender для Office 365 (план 2)](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

С [помощью Microsoft Defender для Office 365](office-365-atp.md)вы получаете подробные сведения об [автоматизированных расследованиях.](air-view-investigation-results.md) Однако в некоторых организациях также используется пользовательское или стороне решение для отчетов. Если ваша организация хочет интегрировать сведения об автоматизированных расследованиях с таким решением, вы можете использовать API действий управления Office 365.

|Ресурс|Описание|
|:---|:---|
|[Обзор API управления Office 365](https://docs.microsoft.com/office/office-365-management-api/office-365-management-apis-overview)|API действий управления Office 365 предоставляет сведения о различных действиях и событиях пользователей, администраторов, систем и политик из журналов действий Microsoft 365 и Azure Active Directory.|
|[Начало работы с API управления Office 365](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis)|API управления Office 365 использует Azure AD для предоставления служб проверки подлинности вашему приложению для доступа к данным Microsoft 365. Чтобы настроить эту возможность, выполните действия, которые необходимо предпринять в этой статье.|
|[Справочник по API действий управления Office 365](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference)|Вы можете использовать API действий управления Office 365 для получения сведений о действиях и событиях пользователей, администраторов, систем и политик из журналов действий Microsoft 365 и Azure AD. Прочитайте эту статью, чтобы узнать больше о том, как это работает.|
|[Схема API действий управления Office 365](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema)|Обзор общей схемы и Защитника [Office 365,](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema) а также схемы анализа угроз и реагирования на них, чтобы узнать о конкретных типах данных, доступных через API действий управления Office 365. [](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#common-schema)|
|

## <a name="see-also"></a>См. также

- [Microsoft Defender для Office 365](office-365-atp.md)
- [Автоматическое исследование и реагирование в Microsoft 365 Defender](../mtp/mtp-autoir.md)
