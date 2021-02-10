---
title: Интеграция сервера SIEM со службами и приложениями Microsoft 365
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
description: Обзор интеграции сервера SIEM с облачными службами и приложениями Microsoft 365
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: f29da87aa6eab1852330092d93187a27b2d36eb2
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/09/2021
ms.locfileid: "50167147"
---
# <a name="security-information-and-event-management-siem-server-integration-with-microsoft-365-services-and-applications"></a>Интеграция сервера SIEM со службами и приложениями Microsoft 365

**Область применения**
- [Exchange Online Protection](https://go.microsoft.com/fwlink/?linkid=2148611)
- [Microsoft Defender для Office 365 (план 1 и план 2)](https://go.microsoft.com/fwlink/?linkid=2148715)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

## <a name="summary"></a>Аннотация

Использует ли ваша организация или планирует получить сервер SIEM? Вам может быть интересно, как она интегрируется с Microsoft 365 или Office 365. В этой статье приводится список ресурсов, которые можно использовать для интеграции сервера SIEM со службами и приложениями Microsoft 365.

> [!TIP]
> Если у вас еще нет сервера SIEM и вы изучаете варианты, рассмотрите **[возможность Microsoft Azure Sentinel.](https://docs.microsoft.com/azure/sentinel/overview)**

## <a name="do-i-need-a-siem-server"></a>Нужен ли мне сервер SIEM?

Необходимость сервера SIEM зависит от многих факторов, таких как требования организации к безопасности и место хранения данных. Microsoft 365 включает широкий спектр функций безопасности, которые отвечают требованиям безопасности многих организаций без дополнительных серверов, таких как сервер SIEM. В некоторых организациях имеются особые условия, которые требуют использования сервера SIEM. Ниже приводятся примеры:

- *У Fabrikam* есть некоторое содержимое и приложения локально, а некоторые — в облаке (они имеют гибридное облачное развертывание). Чтобы получить отчеты о безопасности для всего контента и приложений, fabrikam реализовал сервер SIEM.

- *Contoso* — это организация с финансовыми услугами, которая предъявляет особо строгие требования к безопасности. Они добавили сервер SIEM в свою среду, чтобы воспользоваться дополнительной защитой безопасности.

## <a name="siem-server-integration-with-microsoft-365"></a>Интеграция сервера SIEM с Microsoft 365

Сервер SIEM может получать данные из множества служб и приложений Microsoft 365. В следующей таблице перечислены несколько служб и приложений Microsoft 365, а также входные данные сервера SIEM и ресурсы для получения дополнительных данных.

****

|Служба или приложение Microsoft 365|Входные данные и методы сервера SIEM|Дополнительные ресурсы|
|---|---|---|
|[Microsoft Defender для Office 365](office-365-atp.md)|Журналы аудита|[Интеграция SIEM с Microsoft Defender для Office 365](siem-integration-with-office-365-ti.md)|
|[Microsoft Defender для конечной точки](https://docs.microsoft.com/windows/security/threat-protection/)|Конечная точка HTTPS, которая была в Azure <p> REST API|[Вытягивать оповещения в средства SIEM](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-siem)|
|[Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)|Интеграция журналов|[Интеграция SIEM с Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/siem)|
|

> [!TIP]
> Посмотрите на [Azure Sentinel.](https://docs.microsoft.com/azure/sentinel/overview) Azure Sentinel поставляется с соединителями для решений Майкрософт. Эти соединители доступны "из коробки" и обеспечивают интеграцию в режиме реального времени. Azure Sentinel можно использовать с решениями Microsoft 365 Defender и службами Microsoft 365, включая Office 365, Azure AD, Microsoft Defender для удостоверений, Microsoft Cloud App Security и т. д.

### <a name="audit-logging-must-be-turned-on"></a>Ведение журнала аудита должно быть включено

Перед настройкой интеграции сервера SIEM убедитесь, что ведение журнала аудита включено.

- Для SharePoint Online, OneDrive для бизнеса и Azure Active Directory ведение журнала аудита включено в Центре безопасности [& соответствия требованиям.](../../compliance/turn-audit-log-search-on-or-off.md)

- Для Exchange Online см. ["Управление аудитом почтовых ящиков".](../../compliance/enable-mailbox-auditing.md)

## <a name="more-resources"></a>Дополнительные ресурсы

[Интеграция решений безопасности в Защитнике Azure](https://docs.microsoft.com/azure/security-center/security-center-partner-integration#exporting-data-to-a-siem)

[Интеграция оповещений API безопасности Microsoft Graph с SIEM](https://docs.microsoft.com/graph/security-integration)
