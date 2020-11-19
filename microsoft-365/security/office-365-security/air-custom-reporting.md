---
title: Использование настраиваемых решений для создания отчетов с автоматизированным исследованием и ответом
keywords: SIEM, API, AIR, Аутоир, ATP, автоматическое исследование, интеграция, настраиваемый отчет
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Сведения о том, как интегрировать автоматическое исследование и отвечать с помощью настраиваемого или стороннего решения для создания отчетов.
ms.date: 09/29/2020
ms.custom:
- air
ms.openlocfilehash: 7b0b0570624b2e0dd40d40b178951a747698afe2
ms.sourcegitcommit: 474bd6a86c3692d11fb2c454591c89029ac5bbd5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/19/2020
ms.locfileid: "49357471"
---
# <a name="use-the-management-activity-api-for-custom-or-third-party-reporting-solutions"></a>Использование API действий управления для настраиваемых и сторонних решений для создания отчетов

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


С помощью [защитника Microsoft для Office 365](office-365-atp.md)вы получаете [подробные сведения об автоматическом расследовании](air-view-investigation-results.md). Однако в некоторых организациях также используется собственное или стороннее решение для создания отчетов. Если в Организации требуется интегрировать сведения об автоматическом расследовании с таким решением, вы можете использовать API действий управления Office 365.

Используйте следующие ресурсы для настройки:

****

|Resource|Описание|
|---|---|
|[Обзор API управления Office 365](https://docs.microsoft.com/office/office-365-management-api/office-365-management-apis-overview)|API действий управления Office 365 предоставляет сведения о различных действиях и событиях пользователя, администратора, системы и политики из Microsoft 365 и журналов активности Azure Active Directory.|
|[Начало работы с API управления Office 365](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis)|API управления Office 365 использует Azure AD для предоставления службам проверки подлинности приложениям доступа к данным Microsoft 365. Выполните действия, описанные в этой статье, чтобы настроить ее.|
|[Справочник по API действий управления Office 365](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference)|Вы можете использовать API действий управления Office 365 для получения сведений о действиях пользователя, администратора, системы, а также событиях и событиях из Microsoft 365 и журналов активности Azure AD. Прочтите эту статью, чтобы узнать больше о том, как это работает.|
|[Схема API действий управления Office 365](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema)|В этой статье приводится обзор [общей схемы](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#common-schema) , а также схема защиты от [защитника для Office 365 и угроз и схема ответов](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema) , чтобы узнать о конкретных типах данных, доступных через API действий управления Office 365.|
|

## <a name="see-also"></a>См. также

- [Microsoft Defender для Office 365](office-365-atp.md)

- [Автоматическое исследование и ответ в защитнике Microsoft 365](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir)
