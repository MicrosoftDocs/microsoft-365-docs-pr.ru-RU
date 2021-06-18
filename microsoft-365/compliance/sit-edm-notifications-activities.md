---
title: Создание уведомлений для действий точного соответствия данных
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.date: ''
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Узнайте, как создавать уведомления для действий точного соответствия данных.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 15aa8f2bda76d56d3e35af8e884193193bb78d40
ms.sourcegitcommit: bbad1938b6661d4a6bca99f235c44e521b1fb662
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/18/2021
ms.locfileid: "53007565"
---
# <a name="create-notifications-for-exact-data-match-activities"></a>Создание уведомлений для действий точного соответствия данных

Когда вы создаете [пользовательские типы конфиденциальной информации с точным соответствием данных (EDM)](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md), в [журнале аудита](search-the-audit-log-in-security-and-compliance.md#requirements-to-search-the-audit-log) создается несколько действий. Вы можете использовать командлет [New-ProtectionAlert](/powershell/module/exchange/new-protectionalert?view=exchange-ps) в PowerShell, чтобы создать уведомления, которые будут оповещать вас о таких действиях:

- CreateSchema
- EditSchema
- RemoveSchema
- UploadDataFailed
- UploadDataCompleted

## <a name="pre-requisites"></a>Необходимые условия

Требуется использовать одну из следующих учетных записей:

- глобальный администратор
- администратор соответствия требованиям
- администратор службы Exchange Online

Дополнительные сведения о разрешениях DLP см. в разделе [Разрешения](data-loss-prevention-policies.md#permissions).

Классификация на основе EDM включена в следующие подписки:

- Office 365 E5
- Microsoft 365 E5
- Соответствие требованиям Microsoft 365 E5
- Защита информации и управление данными в Microsoft E5/A5

Дополнительные сведения о лицензировании DLP см. в статье [Руководство по лицензированию Microsoft 365 для обеспечения безопасности и соответствия требованиям](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-protection).

## <a name="configure-notifications-for-edm-activities"></a>Настройка уведомлений для действий EDM

1. Подключитесь к [интерфейсу PowerShell Центра безопасности и соответствия требованиям](/powershell/exchange/connect-to-scc-powershell?view=exchange-ps). 

2. Запустите командлет `New-ProtectionAlert`, используя действие, для которого нужно создать уведомление.  Например, если вы хотите получать уведомление при выполнении действия **UploadDataCompleted**, запустите

```powershell
New-ProtectionAlert -Name "EdmUploadCompleteAlertPolicy" -Category Others -NotifyUser <***address to send  notification to***> -ThreatType Activity -Operation UploadDataCompleted -Description "Custom alert policy to track when EDM upload Completed" -AggregationType None
```

для **UploadDataFailed** можно запустить

```powershell
New-ProtectionAlert -Name "EdmUploadFailAlertPolicy" -Category Others -NotifyUser <***SMTP address to send notification to***> -ThreatType Activity -Operation UploadDataFailed -Description "Custom alert policy to track when EDM upload Failed" -AggregationType None -Severity High
```

## <a name="related-articles"></a>Статьи по теме

- [Создание пользовательских типов конфиденциальной информации с точным соответствием данных](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)
- [New-ProtectionAlert](/powershell/module/exchange/new-protectionalert?view=exchange-ps)