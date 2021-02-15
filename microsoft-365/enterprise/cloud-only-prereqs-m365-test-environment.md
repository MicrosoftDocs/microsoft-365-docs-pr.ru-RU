---
title: Предварительные требования к удостоверениям и доступу к устройствам для облачного применения в тестовой среде Microsoft 365
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
description: Создание среды Microsoft 365 для тестирования удостоверений и доступа к устройствам с предварительными требованиями для облачной проверки подлинности.
ms.openlocfilehash: aa18e1a9943ec12465737f6c3f2e12c1fa49e2a3
ms.sourcegitcommit: cd17328baa58448214487e3e68c37590ab9fd08d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/09/2020
ms.locfileid: "48398881"
---
# <a name="identity-and-device-access-prerequisites-for-cloud-only-in-your-microsoft-365-test-environment"></a>Предварительные требования к удостоверениям и доступу к устройствам для облачного применения в тестовой среде Microsoft 365

*Это руководство по лаборатории тестирования можно использовать только для Microsoft 365 для корпоративных тестовых сред.*

[Конфигурации доступа к](../security/office-365-security/microsoft-365-policies-configurations.md) удостоверениям и устройствам — это набор конфигураций и политик условного доступа для защиты доступа ко всем службам, интегрированным с Azure Active Directory (Azure AD).

В этой статье описано, как настроить тестовую среду Microsoft 365, соответствующую требованиям [предварительной настройки облачной среды](../security/office-365-security/identity-access-prerequisites.md#prerequisites) для удостоверений и доступа к устройствам.

Настройка этой тестовой среды состоит из семи следующих этапов:

1.  Создание простой тестовой среды
2.  Настройка именованных расположений
3.  Настройка компонента обратной записи паролей
4.  Настройка самостоятельного сброса пароля
5.  Настройка многофакторной проверки подлинности
6.  Включение защиты идентификации Azure AD
7.  Включение современной проверки подлинности для Exchange Online и Skype для бизнеса Online

## <a name="phase-1-build-out-your-lightweight-microsoft-365-test-environment"></a>Этап 1. Создание упрощенной тестовой среды Microsoft 365

Следуйте инструкциям в статье [Простая базовая конфигурация](lightweight-base-configuration-microsoft-365-enterprise.md).
Ниже показана итоговая конфигурация.

![Простая среда тестирования Microsoft 365 корпоративный](../media/lightweight-base-configuration-microsoft-365-enterprise/Phase4.png)
 

## <a name="phase-2-configure-named-locations"></a>Этап 2. Настройка именованных расположений

Сначала определите общедоступные IP-адреса или диапазоны адресов, используемые в вашей организации.

Затем выполните инструкции из статьи [Настройка именованных расположений в Azure Active Directory](https://docs.microsoft.com/azure/active-directory/reports-monitoring/quickstart-configure-named-locations) для добавления адресов или диапазонов адресов в качестве именованных расположений. 

## <a name="phase-3-configure-password-writeback"></a>Этап 3. Настройка компонента обратной записи паролей

Выполните инструкции [этапа 2 руководства по лаборатории тестирования для обратной записи пароля](password-writeback-m365-ent-test-environment.md#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain).

## <a name="phase-4-configure-self-service-password-reset"></a>Этап 4. Настройка самостоятельного сброса пароля

Выполните инструкции [этапа 3 руководства по лаборатории тестирования для сброса пароля](password-reset-m365-ent-test-environment.md#phase-3-configure-and-test-password-reset). 

При включении сброса пароля для учетных записей в определенной группе Azure AD добавьте эти учетные записи в группу **Сброс пароля**:

- Пользователь 2
- Пользователь 3
- Пользователь 4
- Пользователь 5

Проверьте сброс паролей только для учетной записи "Пользователь 2".

## <a name="phase-5-configure-multi-factor-authentication"></a>Этап 5. Настройка многофакторной проверки подлинности

Выполните инструкции [этапа 2 руководства по лаборатории тестирования для многофакторной проверки подлинности](multi-factor-authentication-microsoft-365-test-environment.md#phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account) для следующих учетных записей пользователей:

- Пользователь 2
- Пользователь 3
- Пользователь 4
- Пользователь 5

Протестируйте многофакторную проверку подлинности только для учетной записи "Пользователь 2".

## <a name="phase-6-enable-azure-ad-identity-protection"></a>Этап 6. Включение защиты идентификации Azure AD

Выполните инструкции [этапа 2 руководства по лаборатории тестирования для защиты идентификации Azure AD](azure-ad-identity-protection-microsoft-365-test-environment.md#phase-2-use-azure-ad-identity-protection). 

## <a name="phase-7-enable-modern-authentication-for-exchange-online-and-skype-for-business-online"></a>Этап 7. Включение современной проверки подлинности для Exchange Online и Skype для бизнеса Online

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

Результатом является тестовая среда, соответствующая требованиям [предварительной настройки облачной среды](../security/office-365-security/identity-access-prerequisites.md#prerequisites) для удостоверений и доступа к устройствам. 

## <a name="next-step"></a>Следующее действие

См. статью [Основные политики доступа для удостоверений и устройств](identity-access-policies.md), чтобы настроить политики, созданные на основе предварительных требований, и защитить удостоверения и устройства.

## <a name="see-also"></a>См. также

[Руководства по лаборатории тестирования для дополнительного удостоверения](m365-enterprise-test-lab-guides.md#identity)

[План удостоверений](identity-roadmap-microsoft-365.md)

[Руководства по лаборатории тестирования для Microsoft 365 для предприятий](m365-enterprise-test-lab-guides.md)

[Обзор Microsoft 365 для предприятий](microsoft-365-overview.md)

[Документация по Microsoft 365 для предприятий](https://docs.microsoft.com/microsoft-365-enterprise/)
