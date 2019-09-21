---
title: Интеграция сервера SIEM с Microsoft 365
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: 06/17/2019
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
ms.custom:
- Ent_Solutions
- SIEM
description: Сводка. Ознакомьтесь с этой статьей, чтобы получить обзор интеграции сервера SIEM с Microsoft 365.
ms.openlocfilehash: 97f1c1d1f1862d140e014b4460ac9f40cb1934bb
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/20/2019
ms.locfileid: "37091445"
---
# <a name="siem-server-integration-with-microsoft-365-services-and-applications"></a>Интеграция сервера SIEM со службами и приложениями Microsoft 365

## <a name="overview"></a>Общие сведения

Если в Организации используются сведения о безопасности и управление событиями (SIEM), или если вы планируете немедленно получить сервер SIEM, вам может быть интересно узнать, как будет осуществляться интеграция с Microsoft 365, в том числе Office 365. Необходимость использования сервера SIEM зависит от многих факторов, таких как требования к безопасности в Организации. Microsoft 365 предлагает разнообразные функции обеспечения безопасности. Тем не менее, если в Организации есть контент и приложения в локальной среде и в облаке (как в случае гибридного развертывания в гибридном облаке), вы можете добавить сервер SIEM для дополнительной защиты. Если у вашей организации есть особые требования к безопасности, которые необходимо учитывать, можно добавить сервер SIEM в среду.

## <a name="siem-server-integration-microsoft-365"></a>Интеграция сервера SIEM Microsoft 365

Сервер SIEM может получать данные из разнообразных служб и приложений Microsoft 365. В следующей таблице приведены некоторые приложения и службы Microsoft 365, а также входные данные сервера SIEM, а также дополнительные сведения о интеграции сервера SIEM. 

| Служба или приложение Microsoft 365 | Входные данные сервера SIEM | Ресурсы для получения дополнительных сведений |
| --- | --- | --- |
| [Office 365 Advanced Threat protection](office-365-atp.md) <br/>или<br/>[Office 365 Threat Intelligence](office-365-ti.md) | Журналы аудита | [Интеграция SIEM с Office 365 Advanced Threat protection](siem-integration-with-office-365-ti.md) |
| [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security) | Интеграция журналов | [Интеграция SIEM с Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/siem) |
| [Защита от угроз Майкрософт](https://docs.microsoft.com/windows/security/threat-protection/) | Интеграция журналов | [Получение оповещений о средствах SIEM](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-siem) |
| [Центр безопасности Azure](https://docs.microsoft.com/azure/security-center/security-center-intro) (Защита от угроз и обнаружение угроз) | Оповещения | [Экспорт данных безопасности Azure в SIEM — Настройка конвейера — Предварительная версия](https://docs.microsoft.com/azure/security-center/security-center-export-data-to-siem) |
|[Служба Advanced Threat Analytics для Azure](https://docs.microsoft.com/azure/security/azure-threat-detection) | Azure Monitor | [Блог Интеграция средств SIEM с помощью Azure Monitor](https://azure.microsoft.com/blog/use-azure-monitor-to-integrate-with-siem-tools) |
|[Защита идентификации Azure Active Directory](https://docs.microsoft.com/azure/active-directory/identity-protection/overview) |Интеграция журналов |[Интеграция оповещений API безопасности Microsoft Graph с SIEM](https://docs.microsoft.com/graph/security-siemintegration) |


## <a name="audit-logging-must-be-turned-on"></a>Необходимо включить ведение журнала аудита

Перед настройкой интеграции сервера SIEM убедитесь, что ведение журнала аудита включено. 

- Для SharePoint Online, OneDrive для бизнеса и Azure Active Directory [ведение журнала аудита включено в центре безопасности & соответствия требованиям](https://docs.microsoft.com/office365/securitycompliance/turn-audit-log-search-on-or-off).

- Для Exchange Online [ведение журнала аудита включено с помощью Windows PowerShell](https://docs.microsoft.com/office365/securitycompliance/enable-mailbox-auditing).
 
## <a name="see-also"></a>См. также

[Освоение облака и гибридные решения](https://docs.microsoft.com/office365/enterprise/cloud-adoption-and-hybrid-solutions)
  
[Руководства по лаборатории тестирования для облачных решений](https://docs.microsoft.com/office365/enterprise/cloud-adoption-test-lab-guides-tlgs)


