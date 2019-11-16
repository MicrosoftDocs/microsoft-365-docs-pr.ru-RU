---
title: Интеграция сервера SIEM со службами и приложениями Microsoft 365
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: 11/15/2019
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
ms.custom:
- Ent_Solutions
- SIEM
description: В этой статье приводятся общие сведения о интеграции сервера SIEM с Microsoft 365.
ms.openlocfilehash: bea6141022fef1275a7e291217f698f52613f170
ms.sourcegitcommit: d8d001c03c28c10bea005d1c9b5f4a8f393af706
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/16/2019
ms.locfileid: "38677512"
---
# <a name="siem-server-integration-with-microsoft-365-services-and-applications"></a>Интеграция сервера SIEM со службами и приложениями Microsoft 365

## <a name="summary"></a>Описание

Если в Организации используются сведения о безопасности и сервер управления событиями (SIEM) или если вы планируете немедленно получить сервер SIEM, вам может быть интересно узнать, как интегрироваться с Microsoft 365 или Office 365. В этой статье представлен список ресурсов, которые можно использовать для настройки интеграции сервера SIEM с службами и приложениями Microsoft 365.

> [!TIP]
> Если у вас еще нет сервера SIEM и вы изучите свои параметры, рассмотрите **[метку Microsoft Azure](https://docs.microsoft.com/azure/sentinel/overview)**.

## <a name="do-i-need-a-siem-server"></a>Нужен ли сервер SIEM?

Необходимость использования сервера SIEM зависит от многих факторов, таких как требования к безопасности Организации и место хранения данных. Microsoft 365 включает разнообразные функции безопасности, которые отвечают многим потребностям Организации, без дополнительных серверов, таких как сервер SIEM. В некоторых организациях существуют особые обстоятельства, требующие использования сервера SIEM. Ниже приводятся примеры:

- У *Fabrikam* есть локальное содержимое и приложения, а также некоторые в облаке (у них есть гибридное развертывание в облаке). Для получения отчетов о безопасности на всем их контенте и приложениях компания Fabrikam реализовала сервер SIEM. 

- *Contoso* — это организация финансовых служб, которая обладает особенно строгими требованиями к безопасности. Они добавили сервер SIEM в свою среду, чтобы воспользоваться преимуществами дополнительной защиты, которые им необходимы.

## <a name="siem-server-integration-with-microsoft-365"></a>Интеграция сервера SIEM с Microsoft 365

Сервер SIEM может получать данные из разнообразных служб и приложений Microsoft 365. В следующей таблице приведены некоторые приложения и службы Microsoft 365, а также входные данные сервера SIEM, а также ресурсы для получения дополнительных сведений о интеграции сервера SIEM. 

| Служба или приложение Microsoft 365 | Входные данные сервера SIEM | Дополнительные ресурсы |
| --- | --- | --- |
| [Office 365 Advanced Threat Protection](office-365-atp.md)  | Журналы аудита | [Интеграция SIEM с Office 365 Advanced Threat protection](siem-integration-with-office-365-ti.md) |
| [Advanced Threat Protection в Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection/) | Конечная точка HTTPS, размещенная в Azure <br/>REST API| [Получение оповещений о средствах SIEM](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-siem) |
| [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security) | Интеграция журналов | [Интеграция SIEM с Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/siem) |

> [!TIP]
> Взгляните на [метку Azure](https://docs.microsoft.com/azure/sentinel/overview), которая поставляется с несколькими соединителями для решений Майкрософт, которые доступны в режиме реального времени и предоставляют интеграцию в режиме реального времени, в том числе решения Майкрософт для защиты от угроз и источники Microsoft 365, в том числе Office 365, Azure AD, Azure ATP и Microsoft Cloud App Security и многое другое.

### <a name="audit-logging-must-be-turned-on"></a>Необходимо включить ведение журнала аудита

Перед настройкой интеграции сервера SIEM убедитесь, что ведение журнала аудита включено. 

- Для SharePoint Online, OneDrive для бизнеса и Azure Active Directory [ведение журнала аудита включено в центре безопасности & соответствия требованиям](https://docs.microsoft.com/office365/securitycompliance/turn-audit-log-search-on-or-off).

- Для Exchange Online [ведение журнала аудита включено с помощью Windows PowerShell](https://docs.microsoft.com/office365/securitycompliance/enable-mailbox-auditing).
 
## <a name="additional-resources"></a>Дополнительные ресурсы

[Интеграция решений безопасности в центре безопасности Azure](https://docs.microsoft.com/azure/security-center/security-center-partner-integration#exporting-data-to-a-siem)

[Интеграция оповещений API безопасности Microsoft Graph с SIEM](https://docs.microsoft.com/graph/security-integration)