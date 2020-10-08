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
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
ms.custom:
- Ent_Solutions
- SIEM
- seo-marvel-apr2020
description: Обзор сведений о безопасности и службах управления событиями (SIEM) для интеграции с облачными службами и приложениями Microsoft 365
ms.openlocfilehash: 6d657990417cab2a8cbb1b03b8b79a65c095d1a5
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "48202213"
---
# <a name="security-information-and-event-management-siem-server-integration-with-microsoft-365-services-and-applications"></a>Интеграция серверов и управления событиями (SIEM) с помощью служб и приложений Microsoft 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


## <a name="summary"></a>Аннотация

Используется ли в организации или планируется получение сведений о безопасности и управления событиями (SIEM)? Возможно, вы захотите узнать, как она интегрируется с Microsoft 365 или Office 365. В этой статье представлен список ресурсов, которые можно использовать для интеграции сервера SIEM со службами и приложениями Microsoft 365.

> [!TIP]
> Если у вас еще нет сервера SIEM и вы изучите свои параметры, рассмотрите **[метку Microsoft Azure](https://docs.microsoft.com/azure/sentinel/overview)**.

## <a name="do-i-need-a-siem-server"></a>Нужен ли сервер SIEM?

Необходимость использования сервера SIEM зависит от многих факторов, таких как требования к безопасности Организации и место хранения данных. Microsoft 365 включает разнообразные функции безопасности, которые отвечают многим потребностям Организации, без дополнительных серверов, таких как сервер SIEM. В некоторых организациях существуют особые обстоятельства, требующие использования сервера SIEM. Ниже приводятся примеры:

- У *Fabrikam* есть локальное содержимое и приложения, а также некоторые в облаке (у них есть гибридное развертывание в облаке). Для получения отчетов о безопасности на всем их контенте и приложениях компания Fabrikam реализовала сервер SIEM.

- *Contoso* — это организация финансовых служб, которая обладает особенно строгими требованиями к безопасности. Они добавили сервер SIEM в свою среду, чтобы воспользоваться преимуществами дополнительной защиты, которые им необходимы.

## <a name="siem-server-integration-with-microsoft-365"></a>Интеграция сервера SIEM с Microsoft 365

Сервер SIEM может получать данные из разнообразных служб и приложений Microsoft 365. В приведенной ниже таблице перечислены некоторые приложения и службы Microsoft 365, а также входные данные и ресурсы сервера SIEM для получения дополнительных сведений.

****

|Служба или приложение Microsoft 365|Входные данные и методы сервера SIEM|Дополнительные ресурсы|
|---|---|---|
|[Office 365 Advanced Threat Protection](office-365-atp.md)|Журналы аудита|[Интеграция SIEM с Office 365 Advanced Threat protection](siem-integration-with-office-365-ti.md)|
|[Advanced Threat Protection в Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection/)|Конечная точка HTTPS, размещенная в Azure <br/>REST API|[Получение оповещений о средствах SIEM](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-siem)|
|[Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)|Интеграция журналов|[Интеграция SIEM с Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/siem)|
|

> [!TIP]
> Рассмотрим [метку Azure](https://docs.microsoft.com/azure/sentinel/overview). В составе Azure Sentinel имеются соединители для решений Майкрософт. Эти соединители доступны "из поля" и обеспечивают интеграцию в режиме реального времени. Вы можете использовать метку Azure с решениями для защиты от угроз Майкрософт и службами Microsoft 365, в том числе Office 365, Azure AD, Azure ATP, Microsoft Cloud App Security и т. д.

### <a name="audit-logging-must-be-turned-on"></a>Необходимо включить ведение журнала аудита

Перед настройкой интеграции сервера SIEM убедитесь, что ведение журнала аудита включено.

- Для SharePoint Online, OneDrive для бизнеса и Azure Active Directory [ведение журнала аудита включено в центре безопасности & соответствия требованиям](../../compliance/turn-audit-log-search-on-or-off.md).

- В разделе [Управление аудитом почтовых ящиков](../../compliance/enable-mailbox-auditing.md)в Exchange Online.

## <a name="more-resources"></a>Дополнительные ресурсы

[Интеграция решений безопасности в центре безопасности Azure](https://docs.microsoft.com/azure/security-center/security-center-partner-integration#exporting-data-to-a-siem)

[Интеграция оповещений API безопасности Microsoft Graph с SIEM](https://docs.microsoft.com/graph/security-integration)
