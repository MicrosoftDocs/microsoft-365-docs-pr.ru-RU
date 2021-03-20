---
title: Предварительные требования к удостоверениям и доступу к устройствам для облачного применения в тестовой среде Microsoft 365
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Создание среды Microsoft 365 для тестирования удостоверений и доступа к устройствам с предварительными требованиями для облачной проверки подлинности.
ms.openlocfilehash: 3e5a9ef1f610bf3dc6d23c9e584e179fb8ab9ca9
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905144"
---
# <a name="identity-and-device-access-prerequisites-for-cloud-only-in-your-microsoft-365-test-environment"></a>Предварительные требования к удостоверениям и доступу к устройствам для облачного применения в тестовой среде Microsoft 365

*Это руководство по тестовой лаборатории можно использовать только для Microsoft 365 для корпоративных тестовых сред.*

[Конфигурации удостоверений](../security/office-365-security/microsoft-365-policies-configurations.md) и доступа к устройствам — это набор рекомендуемых конфигураций и политики условного доступа для защиты доступа ко всем службам, интегрированным с Azure Active Directory (Azure AD).

В этой статье описано, как настроить тестовую среду Microsoft 365, соответствующую требованиям [предварительной настройки облачной среды](../security/office-365-security/identity-access-prerequisites.md#prerequisites) для удостоверений и доступа к устройствам.

Настройка этой тестовой среды состоит из восьми следующих этапов:

1. Создание простой тестовой среды
2. Настройка именованных расположений
3. Настройка самостоятельного сброса пароля
4. Настройка многофакторной проверки подлинности
5. Включить автоматическую регистрацию устройств на компьютерах Windows, присоединив к домену
6. Настройка защиты паролей Azure AD 
7. Включение защиты идентификации Azure AD
8. Включение современной проверки подлинности для Exchange Online и Skype для бизнеса Online

## <a name="phase-1-build-out-your-lightweight-microsoft-365-test-environment"></a>Этап 1. Создание упрощенной тестовой среды Microsoft 365

Следуйте инструкциям в статье [Простая базовая конфигурация](lightweight-base-configuration-microsoft-365-enterprise.md).
Ниже показана итоговая конфигурация.

![Простая среда тестирования Microsoft 365 корпоративный](../media/lightweight-base-configuration-microsoft-365-enterprise/Phase4.png)
 
## <a name="phase-2-configure-named-locations"></a>Этап 2. Настройка именованных расположений

Сначала определите общедоступные IP-адреса или диапазоны адресов, используемые в вашей организации.

Затем выполните инструкции из статьи [Настройка именованных расположений в Azure Active Directory](/azure/active-directory/reports-monitoring/quickstart-configure-named-locations) для добавления адресов или диапазонов адресов в качестве именованных расположений. 

## <a name="phase-3-configure-self-service-password-reset"></a>Этап 3. Настройка сброса пароля самообслуживки

Выполните инструкции [этапа 3 руководства по лаборатории тестирования для сброса пароля](password-reset-m365-ent-test-environment.md#phase-3-configure-and-test-password-reset). 

При включении сброса пароля для учетных записей в определенной группе Azure AD добавьте эти учетные записи в группу **Сброс пароля**:

- Пользователь 2
- Пользователь 3
- Пользователь 4
- Пользователь 5

Проверьте сброс паролей только для учетной записи "Пользователь 2".

## <a name="phase-4-configure-multi-factor-authentication"></a>Этап 4. Настройка многофакторной проверки подлинности

Выполните инструкции [этапа 2 руководства по лаборатории тестирования для многофакторной проверки подлинности](multi-factor-authentication-microsoft-365-test-environment.md#phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account) для следующих учетных записей пользователей:

- Пользователь 2
- Пользователь 3
- Пользователь 4
- Пользователь 5

Протестируйте многофакторную проверку подлинности только для учетной записи "Пользователь 2".

## <a name="phase-5-enable-automatic-device-registration-of-domain-joined-windows-computers"></a>Этап 5. Включить автоматическую регистрацию устройств на компьютерах Windows, присоединив к домену 

Следуйте [этим инструкциям,](/azure/active-directory/devices/hybrid-azuread-join-plan) чтобы включить автоматическую регистрацию устройств на компьютерах Windows, присоединив к домену.

## <a name="phase-6-configure-azure-ad-password-protection"></a>Этап 6. Настройка защиты паролей Azure AD 

Следуйте [этим инструкциям,](/azure/active-directory/authentication/concept-password-ban-bad) чтобы заблокировать известные слабые пароли и их варианты.

## <a name="phase-7-enable-azure-ad-identity-protection"></a>Этап 7. Включение защиты идентификации Azure AD

Выполните инструкции [этапа 2 руководства по лаборатории тестирования для защиты идентификации Azure AD](azure-ad-identity-protection-microsoft-365-test-environment.md#phase-2-use-azure-ad-identity-protection). 

## <a name="phase-8-enable-modern-authentication-for-exchange-online-and-skype-for-business-online"></a>Этап 8. Включение современной проверки подлинности для Exchange Online и Skype для бизнеса Online

Для Exchange Online выполните [эти инструкции](/Exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online#enable-or-disable-modern-authentication-in-exchange-online-for-client-connections-in-outlook-2013-or-later). 

Для Skype для бизнеса Online:

1. Подключитесь к [Skype для бизнеса Online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).

2. Выполните указанную ниже команду.

  ```powershell
  Set-CsOAuthConfiguration -ClientAdalAuthOverride Allowed
  ```

3. Проверьте успешность изменения с помощью указанной ниже команды.

  ```powershell
  Get-CsOAuthConfiguration
  ```

Результатом является тестовая среда, которая соответствует [](../security/office-365-security/identity-access-prerequisites.md#prerequisites) требованиям конфигурации для удостоверений и доступа к устройствам только для облачной среды. 

## <a name="next-step"></a>Следующее действие

См. статью [Основные политики доступа для удостоверений и устройств](../security/office-365-security/identity-access-policies.md), чтобы настроить политики, созданные на основе предварительных требований, и защитить удостоверения и устройства.

## <a name="see-also"></a>См. также

[Руководства по лаборатории тестирования для дополнительного удостоверения](m365-enterprise-test-lab-guides.md#identity)

[Дорожная карта удостоверений](identity-roadmap-microsoft-365.md)

[Руководства по лаборатории тестирования для Microsoft 365 для предприятий](m365-enterprise-test-lab-guides.md)

[Обзор Microsoft 365 для предприятий](microsoft-365-overview.md)

[Документация по Microsoft 365 для предприятий](/microsoft-365-enterprise/)