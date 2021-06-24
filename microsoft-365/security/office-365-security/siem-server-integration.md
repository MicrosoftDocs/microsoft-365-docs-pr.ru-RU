---
title: Интеграция сервера SIEM с Microsoft 365 службами и приложениями
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: 11/18/2019
localization_priority: Normal
ms.collection:
- M365-security-compliance
ms.custom:
- Ent_Solutions
- SIEM
- seo-marvel-apr2020
description: Получение обзора интеграции серверов служб безопасности и управления событиями (SIEM) с Microsoft 365 облачными службами и приложениями
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: ea4d844595aaab8d8148666430187edef463b92e
ms.sourcegitcommit: ccbdf2638fc6646bfb89450169953f4c3ce4b9b0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/24/2021
ms.locfileid: "53105600"
---
# <a name="security-information-and-event-management-siem-server-integration-with-microsoft-365-services-and-applications"></a>Интеграция серверов с данными о безопасности и управление событиями (SIEM) с Microsoft 365 службами и приложениями

**Область применения**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender для Office 365 (план 1 и план 2)](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

## <a name="summary"></a>Сводка

Использует ли ваша организация или планирует получить сервер управления сведениями о безопасности и событиями (SIEM)? Возможно, вам будет интересно, как она интегрируется с Microsoft 365 или Office 365. В этой статье приводится список ресурсов, которые можно использовать для интеграции сервера SIEM с Microsoft 365 службами и приложениями.

> [!TIP]
> Если у вас еще нет сервера SIEM и вы изучаете параметры, Microsoft Azure **[Sentinel](/azure/sentinel/overview)**.

## <a name="do-i-need-a-siem-server"></a>Нужен ли мне siEM-сервер?

Потребность в siEM-сервере зависит от многих факторов, таких как требования к безопасности организации и место хранения данных. Microsoft 365 включает широкий спектр функций безопасности, которые отвечают требованиям безопасности многих организаций без дополнительных серверов, таких как сервер SIEM. В некоторых организациях имеются особые условия, которые требуют использования сервера SIEM. Ниже приводятся примеры:

- *Fabrikam* имеет некоторое содержимое и приложения на месте, а некоторые в облаке (они имеют гибридное развертывание облака). Чтобы получить отчеты о безопасности во всем их контенте и приложениях, Fabrikam реализовал сервер SIEM.
- *Contoso* — это организация финансовых служб, которая предъявляет особо строгие требования к безопасности. Они добавили сервер SIEM в свою среду, чтобы воспользоваться необходимой дополнительной защитой безопасности.

## <a name="siem-server-integration-with-microsoft-365"></a>Интеграция сервера SIEM с Microsoft 365

Сервер SIEM может получать данные из различных Microsoft 365 и приложений. В следующей таблице перечислены несколько Microsoft 365 и приложений, а также входные данные и ресурсы сервера SIEM, чтобы узнать больше.

<br>

****

|Microsoft 365 Служба или приложение|Входные данные и методы сервера SIEM|Дополнительные ресурсы|
|---|---|---|
|[Microsoft Defender для Office 365](defender-for-office-365.md)|Журналы аудита|[Интеграция SIEM с Microsoft Defender для Office 365](siem-integration-with-office-365-ti.md)|
|[Microsoft Defender для конечной точки](/windows/security/threat-protection/)|Конечная точка HTTPS, организованная в Azure <p> REST API|[Вытащать оповещения в инструменты SIEM](../defender-endpoint/configure-siem.md)|
|[Microsoft Cloud App Security](/cloud-app-security/what-is-cloud-app-security)|Интеграция журнала|[Интеграция SIEM с Microsoft Cloud App Security](/cloud-app-security/siem)|
|

> [!TIP]
> Взгляните на [Azure Sentinel](/azure/sentinel/overview). Azure Sentinel поставляется с соединителями для решений Майкрософт. Эти соединители доступны "из окна" и обеспечивают интеграцию в режиме реального времени. Вы можете использовать Azure Sentinel с Microsoft 365 Defender решениями и Microsoft 365 службами, включая Office 365, Azure AD, Microsoft Defender for Identity, Microsoft Cloud App Security и другие.

### <a name="audit-logging-must-be-turned-on"></a>Необходимо включить журнал аудита

Убедитесь, что журнал аудита включен перед настройкой интеграции серверов SIEM.

- Для SharePoint Online, OneDrive для бизнеса и Azure Active Directory см. в включите аудит или [отключение.](../../compliance/turn-audit-log-search-on-or-off.md)
- Для Exchange Online см. в этой Exchange Online [Управление аудитом почтовых ящиков.](../../compliance/enable-mailbox-auditing.md)

## <a name="more-resources"></a>Дополнительные ресурсы

[Интеграция решений безопасности в Azure Defender](/azure/security-center/security-center-partner-integration#exporting-data-to-a-siem)

[Интеграция оповещений API безопасности Microsoft Graph с SIEM](/graph/security-integration)
