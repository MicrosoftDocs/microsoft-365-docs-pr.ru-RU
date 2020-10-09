---
title: Предварительные требования к удостоверениям и доступу к устройствам для синхронизации хэша паролей в тестовой среде Microsoft 365
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 12/12/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Создание среды Microsoft 365 для тестирования удостоверений и доступа к устройствам с предварительными требованиями для проверки подлинности с синхронизацией хэша паролей.
ms.openlocfilehash: 63f433d5297139fcc7f6eb8bd5383a6593c29388
ms.sourcegitcommit: cd17328baa58448214487e3e68c37590ab9fd08d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/09/2020
ms.locfileid: "48399447"
---
# <a name="identity-and-device-access-prerequisites-for-password-hash-synchronization-in-your-microsoft-365-test-environment"></a>Предварительные требования к удостоверениям и доступу к устройствам для синхронизации хэша паролей в тестовой среде Microsoft 365

*Это руководство по лаборатории тестирования можно использовать только для Microsoft 365 для тестовых сред предприятия.*

[Конфигурации доступа для удостоверений и устройств](../security/office-365-security/microsoft-365-policies-configurations.md) — это набор конфигураций и политик условного доступа для защиты доступа ко всем службам в Microsoft 365 для предприятий, интегрированных с Azure Active Directory (Azure AD).

В этой статье описано, как настроить тестовую среду Microsoft 365, соответствующую требованиям [предварительной настройки Active Directory с синхронизацией хэша паролей](../security/office-365-security/identity-access-prerequisites.md#prerequisites) для удостоверений и доступа к устройствам.

Настройка этой тестовой среды состоит из восьми следующих этапов:

1.  Создание тестовой среды смоделированной организации с синхронизацией хэша паролей
2.  Настройка простого единого входа Azure AD
3.  Настройка именованных расположений
4.  Настройка компонента обратной записи паролей
5.  Настройка самостоятельного сброса пароля для всех учетных записей пользователей
6.  Настройка многофакторной проверки подлинности для всех учетных записей пользователей
7.  Включение защиты идентификации Azure AD
8.  Включение современной проверки подлинности для Exchange Online и Skype для бизнеса Online

## <a name="phase-1-build-out-your-simulated-enterprise-with-password-hash-sync-microsoft-365-test-environment"></a>Этап 1. Создание тестовой среды Microsoft 365 смоделированной организации с синхронизацией хэша паролей

Выполните инструкции из статьи [Синхронизация хэша паролей](password-hash-sync-m365-ent-test-environment.md).
Ниже показана итоговая конфигурация.

![Тестовая среда смоделированной организации с синхронизацией хэша паролей](../media/password-hash-sync-m365-ent-test-environment/Phase3.png)
 
## <a name="phase-2-configure-azure-ad-seamless-single-sign-on"></a>Этап 2. Настройка простого единого входа Azure AD

Выполните инструкции [этапа 2 руководства по лаборатории тестирования для простого единого входа Azure AD](single-sign-on-m365-ent-test-environment.md#phase-2-configure-azure-ad-connect-on-app1-for-azure-ad-seamless-sso).

## <a name="phase-3-configure-named-locations"></a>Этап 3. Настройка именованных расположений

Сначала определите общедоступные IP-адреса или диапазоны адресов, используемые в вашей организации.

Затем выполните инструкции из статьи [Настройка именованных расположений в Azure Active Directory](https://docs.microsoft.com/azure/active-directory/reports-monitoring/quickstart-configure-named-locations) для добавления адресов или диапазонов адресов в качестве именованных расположений. 

## <a name="phase-4-configure-password-writeback"></a>Этап 4. Настройка компонента обратной записи паролей

Выполните инструкции [этапа 2 руководства по лаборатории тестирования для обратной записи пароля](password-writeback-m365-ent-test-environment.md#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain).

## <a name="phase-5-configure-self-service-password-reset"></a>Этап 5. Настройка самостоятельного сброса пароля

Выполните инструкции [этапа 3 руководства по лаборатории тестирования для сброса пароля](password-reset-m365-ent-test-environment.md#phase-3-configure-and-test-password-reset). 

При включении сброса пароля для учетных записей в определенной группе Azure AD добавьте эти учетные записи в группу **Сброс пароля**:

- Пользователь 2
- Пользователь 3
- Пользователь 4
- Пользователь 5

Проверьте сброс паролей только для учетной записи "Пользователь 2".

## <a name="phase-6-configure-multi-factor-authentication"></a>Этап 6. Настройка многофакторной проверки подлинности

Выполните инструкции [этапа 2 руководства по лаборатории тестирования для многофакторной проверки подлинности](multi-factor-authentication-microsoft-365-test-environment.md#phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account) для следующих учетных записей пользователей:

- Пользователь 2
- Пользователь 3
- Пользователь 4
- Пользователь 5

Протестируйте многофакторную проверку подлинности только для учетной записи "Пользователь 2".

## <a name="phase-7-enable-azure-ad-identity-protection"></a>Этап 7. Включение защиты идентификации Azure AD

Выполните инструкции [этапа 2 руководства по лаборатории тестирования для защиты идентификации Azure AD](azure-ad-identity-protection-microsoft-365-test-environment.md#phase-2-use-azure-ad-identity-protection). 

## <a name="phase-8-enable-modern-authentication-for-exchange-online-and-skype-for-business-online"></a>Этап 8. Включение современной проверки подлинности для Exchange Online и Skype для бизнеса Online

Для Exchange Online выполните [эти инструкции](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online#enable-or-disable-modern-authentication-in-exchange-online-for-client-connections-in-outlook-2013-or-later). 

Для Skype для бизнеса Online:

1. Подключитесь к [Skype для бизнеса Online](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).

2. Выполните указанную ниже команду.

  ```powershell
  Set-CsOAuthConfiguration -ClientAdalAuthOverride Allowed
  ```

3. Проверьте успешность изменения с помощью указанной ниже команды.

  ```powershell
  Get-CsOAuthConfiguration
  ```

Результатом является тестовая среда, соответствующая требованиям [предварительной настройки Active Directory с синхронизацией хэша паролей](../security/office-365-security/identity-access-prerequisites.md#prerequisites) для удостоверений и доступа к устройствам. 

## <a name="next-step"></a>Следующее действие

См. статью [Основные политики доступа для удостоверений и устройств](identity-access-policies.md), чтобы настроить политики, созданные на основе предварительных требований, и защитить удостоверения и устройства.

## <a name="see-also"></a>См. также

[Руководства по лаборатории тестирования для дополнительного удостоверения](m365-enterprise-test-lab-guides.md#identity)

[Схема удостоверений](identity-roadmap-microsoft-365.md)

[Руководства по лаборатории тестирования для Microsoft 365 для предприятий](m365-enterprise-test-lab-guides.md)

[Обзор Microsoft 365 для предприятий](microsoft-365-overview.md)

[Microsoft 365 для корпоративных документов](https://docs.microsoft.com/microsoft-365-enterprise/)
