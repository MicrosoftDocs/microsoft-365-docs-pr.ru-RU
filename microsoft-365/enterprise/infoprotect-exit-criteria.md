---
title: Условия, при выполнении которых можно считать Information Protection настроенной
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/19/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
ms.custom: ''
description: Изучите условия для служб и инфраструктуры, основанных на Information Protection, и проверьте, соответствует ли используемая вами конфигурация требованиям Microsoft 365 корпоративный.
ms.openlocfilehash: c0b4ff6a0d289b8a8c63255d817ea455df00bf13
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/21/2020
ms.locfileid: "43631637"
---
# <a name="information-protection-infrastructure-exit-criteria"></a>Условия, при выполнении которых можно считать Information Protection настроенной

![Этап 6. Защита данных](../media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

Убедитесь, что инфраструктура защиты информации соответствует указанным ниже обязательным условиям и что рассмотрены необязательные условия.

<a name="crit-infoprotect-step1"></a>
## <a name="required-security-and-information-protection-levels-for-your-organization-are-defined"></a>Обязательное требование: определены уровни безопасности и защиты информации в организации

Вы запланировали и определили уровни безопасности, необходимые вашей организации. Эти уровни определяют минимальный уровень безопасности и дополнительные уровни для конфиденциальной информации и требуемой защиты данных.

Вы используете не менее трех указанных ниже уровней безопасности.

- Базовый уровень
- Конфиденциальный
- Строго регулируемый уровень

Чтобы выполнить это требование, см. [шаг 1](infoprotect-define-sec-infoprotect-levels.md) (при необходимости). 

<a name="crit-infoprotect-step3"></a>
## <a name="required-increased-security-for-microsoft-365-is-configured"></a>Обязательное требование: настроена усиленная защита для Microsoft 365

Вы настроили указанные ниже параметры [для повышения безопасности Microsoft 365](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security):

- Политики управления угрозами в Центре безопасности Microsoft 365
- Дополнительные параметры, используемые во всем клиенте Exchange Online
- Политики общего доступа для всего клиента в Центре администрирования SharePoint Online
- Параметры в Azure Active Directory (Azure AD)

Вы также [включили Office 365 Advanced Threat Protection для SharePoint, OneDrive и Microsoft Teams](https://docs.microsoft.com/office365/securitycompliance/turn-on-atp-for-spo-odb-and-teams).

Чтобы выполнить это требование, см. [шаг 3](infoprotect-configure-increased-security-office-365.md) (при необходимости). 

<a name="crit-infoprotect-step2"></a>
## <a name="optional-classification-is-configured-across-your-environment"></a>Необязательное требование: в используемой вами среде настроена классификация

Совместно с юридическим отделом и отделом соответствия требованиям вы разработали соответствующую классификацию и схему маркировки для управления данными в вашей организации и для политик безопасности. 

Эти политики соответствуют настройке и развертыванию следующих элементов:

- Типы конфиденциальных данных
- Метки хранения
- Метки конфиденциальности
- Метки Azure Information Protection

Чтобы выполнить это требование, см. [шаг 2](infoprotect-configure-classification.md) (при необходимости). 


<a name="crit-infoprotect-step4"></a>
## <a name="optional-windows-information-protection-is-deployed-across-your-environment"></a>Необязательно: функция Windows Information Protection развернута в вашей среде

На ваших зарегистрированных устройствах Windows 10 Корпоративная развернута и применена политика Intune, которая определяет:

- Какие приложения следует защищать.
- Уровень защиты.
- На что распространяется защита.

Чтобы выполнить это требование, см. [шаг 4](infoprotect-deploy-windows-information-protection.md) (при необходимости). 

<a name="crit-infoprotect-step5"></a>
## <a name="optional-data-loss-prevention-dlp-is-deployed"></a>Необязательно: развернута служба защиты от потери данных (DLP)

Вы проанализировали, протестировали, а затем развернули набор политик DLP с указанием местоположений и правил с условиями и действиями, требуемых вашей организацией для защиты данных клиентов и других типов конфиденциальных данных, а также для соблюдения отраслевых и региональных норм и требований.

Ваши сотрудники, ответственные за соблюдение норм и безопасность данных, используют панель мониторинга безопасности и соответствия требованиям для отслеживания инцидентов DLP.

Чтобы выполнить это требование, см. [шаг 5](infoprotect-data-loss-prevention.md) (при необходимости). 

<a name="crit-infoprotect-step6"></a>
## <a name="optional-email-encryption-is-configured"></a>Необязательное требование: настроено шифрование электронной почты

Вы настроили следующий метод шифрования электронной почты в соответствии с требованиями организации:

|||
|:-------|:-----|
| **Метод шифрования** | **При отправке почты** |
| [Шифрование сообщений Office 365 (OME)](https://docs.microsoft.com/Office365/SecurityCompliance/ome)  | За пределы организации с шифрованием |
| [Управление правами на доступ к данным (IRM)](https://docs.microsoft.com/office365/SecurityCompliance/information-rights-management-in-exchange-online) | С шифрованием и разрешениями |
| [Secure/Multipurpose Internet Mail Extensions (S/MIME)](https://docs.microsoft.com/Exchange/policy-and-compliance/smime) | С шифрованием и цифровыми подписями с использованием шифрования с открытым ключом |
|||

Чтобы выполнить это требование, см. [шаг 6](infoprotect-email-encryption.md) (при необходимости).

<a name="crit-infoprotect-step7"></a>
## <a name="optional-configure-privileged-access-management-in-office-365"></a>Необязательное требование: настроено управление привилегированным доступом для Office 365

С помощью сведений в статье [Настройка управления привилегированным доступом в Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration) вы включили привилегированный доступ и создали одну или несколько политик привилегированного доступа в организации. Вы настроили эти политики и включили своевременный доступ для получения доступа к конфиденциальным данным или важным параметрам конфигурации.

Чтобы выполнить это требование, см. [шаг 7](infoprotect-configure-privileged-access-management.md) (при необходимости). 

## <a name="results-and-next-steps"></a>Результаты и дальнейшие действия

Ваша инфраструктура защиты информации для Microsoft 365 корпоративный использует определенные уровни безопасности, усиленную защиту для Office 365, классификацию с применением типов и меток конфиденциальных данных, Windows Information Protection, защиту от потери данных, шифрование электронной почты и управление привилегированным доступом.

Если вы выполняете этапы полного развертывания Microsoft 365 корпоративный, вы готовы к применению в ваших [полезных нагрузках и сценариях](deploy-workloads.md) всех функций и настроек базовой инфраструктуры.
