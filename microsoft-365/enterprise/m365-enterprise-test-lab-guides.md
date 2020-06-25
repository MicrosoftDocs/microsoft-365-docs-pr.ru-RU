---
title: Руководства по лаборатории тестирования для Microsoft 365 на крупных предприятиях
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/20/2019
audience: ITPro
ms.topic: hub-page
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom:
- Ent_TLGs
- seo-marvel-apr2020
ms.assetid: 706d5449-45e5-4b0c-a012-ab60501899ad
description: С помощью этих руководств по лаборатории тестирования вы можете настраивать демонстрационные и экспериментальные среды, а также среды разработки и тестирования для Microsoft 365 на крупных предприятиях.
ms.openlocfilehash: 5907edd1bc42b9d679ed020331f225ef2d2b2594
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/19/2020
ms.locfileid: "44818745"
---
# <a name="microsoft-365-for-enterprise-test-lab-guides"></a>Руководства по лаборатории тестирования для Microsoft 365 на крупных предприятиях

*Это относится к Microsoft 365 для крупных предприятий и Office 365 корпоративный.*

Test Lab Guides (TLGs) help you quickly learn about Microsoft products. They provide prescriptive instructions to configure simplified but representative test environments. You can use these environments for demonstration, customization, or creation of complex proofs of concept for the duration of a trial or paid subscription. 

TLGs are designed to be modular. They build upon each other to create multiple configurations that more closely match your learning or test configuration needs. The "I built it out myself and it works" hands-on experience helps you understand the deployment requirements of a new product or scenario so you can better plan for hosting it in production.

Кроме того, с помощью этих руководств можно создавать типичные среды для разработки и тестирования.
  
![Руководства по лаборатории тестирования для облака Майкрософт](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

Перейдите в раздел [Руководства по лаборатории тестирования](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf)для наглядного отображения всех статей, относящихся к руководствам по лаборатории тестирования Microsoft 365 для крупных предприятий.

[![Руководства по лаборатории тестирования для Microsoft 365 на крупных предприятиях](../media/m365-enterprise-test-lab-guides/microsoft-365-enterprise-tlg-stack.png)](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf)

## <a name="base-configuration"></a>Базовая настройка

First, you create a test environment for [Microsoft 365 for enterprise](https://docs.microsoft.com/microsoft-365-enterprise/) that includes Office 365 E5, Enterprise Mobility + Security (EMS) E5, and Windows 10 Enterprise. You can create two different types of base configurations:

- Используйте [простую базовую конфигурацию](lightweight-base-configuration-microsoft-365-enterprise.md), если вы хотите настроить и продемонстрировать функции и возможности Microsoft 365 для крупных предприятий только в облачной среде, которая не включает каких-либо локальных компонентов.

- Используйте [базовую конфигурацию "имитация предприятия"](simulated-ent-base-configuration-microsoft-365-enterprise.md), если вы хотите настроить и продемонстрировать функции и возможности Microsoft 365 для крупных предприятий в гибридной облачной среде, содержащей локальные компоненты, такие как домен доменных служб Active Directory (AD DS).

Кроме того, вы можете создавать тестовые среды для Office 365 E5, не добавляя лицензию Microsoft 365 E5 в пробную или рабочую тестовую среду.
    
## <a name="identity"></a>Удостоверение

Функции и возможности, связанные с идентификацией, продемонстрированы в следующих статьях:

- [Синхронизация хэшей паролей](password-hash-sync-m365-ent-test-environment.md)
  
   Включение и тестирование синхронизации службы каталогов на основе хэша пароля из контроллера домена AD DS.

- [Сквозная проверка подлинности](pass-through-auth-m365-ent-test-environment.md)
  
   Включение и тестирование сквозной проверки подлинности на контроллере домена AD DS.

- [Федеративная проверка подлинности](federated-identity-for-your-office-365-dev-test-environment.md)
  
   Включение и тестирование федеративной проверки подлинности на контроллере домена AD DS.

- [Простой единый вход Azure AD](single-sign-on-m365-ent-test-environment.md)
  
   Включение и тестирование простого единого входа (SSO) Azure AD с контроллером домена AD DS.

- [Многофакторная проверка подлинности](multi-factor-authentication-microsoft-365-test-environment.md)
  
   Включение и тестирование многофакторной проверки подлинности с использованием смартфона для определенной учетной записи.

- [Защита учетных записей глобальных администраторов](protect-global-administrator-accounts-microsoft-365-test-environment.md)
 
   Блокирование учетных записей глобальных администраторов с помощью политик условного доступа.

- [Обратная запись пароля](password-writeback-m365-ent-test-environment.md)

   Смена пароля учетной записи пользователя AD DS из Azure AD с помощью обратной записи пароля.

- [Сброс пароля](password-reset-m365-ent-test-environment.md)

   Используйте функцию самостоятельного сброса пароля (SSPR) для сброса пароля.

- [Автоматическое лицензирование и членство в группах](automate-licenses-group-membership-microsoft-365-test-environment.md)

   Упрощение администрирования новых учетных записей с помощью автоматического лицензирования и динамического членства в группах.

- [Защита идентификации Azure AD](azure-ad-identity-protection-microsoft-365-test-environment.md)

   Проверка текущих учетных записей пользователей на уязвимости.

- [Доступ к удостоверениям и устройствам](identity-device-access-m365-test-environment.md)

   Создание среды для тестирования рекомендуемых конфигураций доступа к удостоверениям и устройствам и политик условного доступа.


## <a name="mobile-device-management"></a>Управление мобильными устройствами

Функции и возможности, связанные с управлением мобильными устройствами, продемонстрированы в следующих статьях:

- [Политики соответствия требованиям для устройств](mam-policies-for-your-microsoft-365-enterprise-dev-test-environment.md)
    
   Создайте группу пользователей и политику соответствия требованиям для устройств Windows 10.
    
- [Регистрация устройств с iOS и Android](enroll-ios-and-android-devices-in-your-microsoft-enterprise-365-dev-test-environ.md)
   
   Регистрация устройств с iOS или Android и удаленное управление ими.


## <a name="information-protection"></a>Защита информации

Функции и возможности, связанные с защитой информации, продемонстрированы в следующих статьях:

- [Повышенная безопасность в Microsoft 365](increased-o365-security-microsoft-365-enterprise-dev-test-environment.md)
    
   Настройка параметров для усиления защиты Microsoft 365 и изучение встроенных средств безопасности.
  
- [Классификация данных](data-classification-microsoft-365-enterprise-dev-test-environment.md)
    
   Настройка меток и присвоение их документу на сайте группы SharePoint Online.
    
- [Управление привилегированным доступом](privileged-access-microsoft-365-enterprise-dev-test-environment.md)
    
   Настройка управления привилегированным доступом для своевременного доступа к задачам, требующим привилегий и разрешений повышенного уровня, в вашей организации.


