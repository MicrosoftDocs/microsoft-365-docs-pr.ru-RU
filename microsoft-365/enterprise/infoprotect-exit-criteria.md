---
title: Условия, при выполнении которых можно считать Information Protection настроенной
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 03/13/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: Изучите условия для служб и инфраструктуры, основанных на Information Protection, и проверьте, соответствует ли используемая вами конфигурация требованиям Microsoft 365 корпоративный.
ms.openlocfilehash: 10d7b3b888999b65e5faff81e9a2d32e595294cf
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/28/2018
ms.locfileid: "26870967"
---
# <a name="information-protection-infrastructure-exit-criteria"></a>Условия, при выполнении которых можно считать Information Protection настроенной

![](./media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

Прежде чем завершить работу над базовой инфраструктурой, убедитесь, что ваша инфраструктура Information Protection соответствует указанным ниже требованиям. 

<a name="crit-infoprotect-step1"></a>
## <a name="required-security-and-information-protection-levels-for-your-organization-are-defined"></a>Обязательное требование: определены уровни безопасности и Information Protection в организации

Вы запланировали и определили уровни безопасности, необходимые вашей организации. Эти уровни определяют минимальный уровень безопасности и дополнительные уровни для конфиденциальной информации и требуемой защиты данных.

Вы используете не менее трех указанных ниже уровней безопасности.

- Базовый уровень
- Конфиденциальный
- Строго регулируемый уровень

Чтобы выполнить это требование, см. [шаг 1](infoprotect-define-sec-infoprotect-levels.md) (при необходимости). 

<a name="crit-infoprotect-step4"></a>
## <a name="required-increased-security-for-office-365-is-configured"></a>Обязательное требование: настроена усиленная защита для Office 365

Вы настроили указанные ниже параметры для усиленной защиты согласно сведениям в статье [Настройка клиента Office 365 для повышения безопасности](https://support.office.com/article/Configure-your-Office-365-tenant-for-increased-security-8d274fe3-db51-4107-ba64-865e7155b355):

- Политики управления угрозами в Центре безопасности и соответствия требованиям Office 365
- Дополнительные параметры, используемые во всем клиенте Exchange Online
- Политики общего доступа, используемые во всем клиенте, в Центре администрирования SharePoint
- Параметры в Azure Active Directory

Вы также [включили Office 365 Advanced Threat Protection](https://support.office.com/article/Office-365-ATP-for-SharePoint-OneDrive-and-Microsoft-Teams-26261670-db33-4c53-b125-af0662c34607#turniton).

Чтобы выполнить это требование, см. [шаг 3](infoprotect-configure-increased-security-office-365.md) (при необходимости). 

<a name="crit-infoprotect-step3"></a>
## <a name="optional-classification-is-configured-across-your-environment"></a>Необязательное требование: в используемой вами среде настроена классификация

Совместно с юридическим отделом и отделом соответствия требованиям вы разработали соответствующую классификацию и схему маркировки для данных вашей организации, включающие следующие элементы:

- типы конфиденциальных данных;
- метки Office 365.
- Метки Azure Information Protection

Чтобы выполнить это требование, см. [шаг 2](infoprotect-configure-classification.md) (при необходимости). 

<a name="crit-infoprotect-step5"></a>
## <a name="optional-configure-privileged-access-management-in-office-365"></a>Необязательное требование: настроено управление привилегированным доступом для Office 365

С помощью сведений в статье [Настройка управления привилегированным доступом в Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration) вы включили привилегированный доступ и создали одну или несколько политик привилегированного доступа в организации Office 365. Вы настроили эти политики и включили своевременный доступ для получения доступа к конфиденциальным данным или важным параметрам конфигурации.

Чтобы выполнить это требование, см. [шаг 4](infoprotect-configure-privileged-access-management.md) (при необходимости). 

## <a name="next-step"></a>Следующий этап

Теперь вы готовы развернуть [рабочие нагрузки и сценарии](deploy-workloads.md), например Microsoft Teams и Exchange Online, работающие на базовой инфраструктуре Microsoft 365 корпоративный.
