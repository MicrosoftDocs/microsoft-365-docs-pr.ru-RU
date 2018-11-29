---
title: Руководства по лаборатории тестирования для Microsoft 365 корпоративный
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/19/2018
ms.audience: ITPro
ms.topic: hub-page
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom:
- Ent_TLGs
ms.assetid: 706d5449-45e5-4b0c-a012-ab60501899ad
description: С помощью этих руководств по лаборатории тестирования вы можете настраивать демонстрационные и экспериментальные среды, а также среды разработки и тестирования для Microsoft 365 корпоративный.
ms.openlocfilehash: df723647748532936e40bbdb4e34ff698b9fa650
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/28/2018
ms.locfileid: "26870939"
---
# <a name="microsoft-365-enterprise-test-lab-guides"></a>Руководства по лаборатории тестирования для Microsoft 365 корпоративный

Руководства по лаборатории тестирования помогают быстро знакомиться с продуктами Майкрософт. Они содержат инструкции по настройке упрощенных и наглядных тестовых сред. Эти среды можно использовать для демонстрации и настройки, а также создания сложных экспериментов на протяжении срока действия пробной или платной подписки. 

Руководства по лаборатории тестирования делятся на модули. Каждый из них дополняет предыдущие, отображая несколько конфигураций, наиболее соответствующих вашим требованиям к учебной или тестовой конфигурации. Непосредственное знакомство с новым продуктом или сценарием помогает вам понять требования к его развертыванию, чтобы лучше спланировать его размещение в рабочей среде.

Кроме того, с помощью этих руководств можно создавать типичные среды для разработки и тестирования.
  
![Руководства по лаборатории тестирования для Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> Щелкните [здесь](https://aka.ms/m365etlgstack), чтобы просмотреть схему всех статей, относящихся к руководствам по лаборатории тестирования Microsoft 365 корпоративный.
  
## <a name="base-configuration"></a>Базовая настройка

Вначале нужно создать тестовую среду для [Microsoft 365 корпоративный](https://docs.microsoft.com/microsoft-365-enterprise/), включающую Office 365 E5, Enterprise Mobility + Security (EMS) E5 и Windows 10 Корпоративная. Ви можете создать два типа базовой конфигурации.

- Используйте [простую базовую конфигурацию](lightweight-base-configuration-microsoft-365-enterprise.md), если вы хотите настроить и продемонстрировать функции и возможности Microsoft 365 корпоративный только в облачной среде, которая не включает каких-либо локальных компонентов.

- Используйте [базовую конфигурацию "имитация предприятия"](simulated-ent-base-configuration-microsoft-365-enterprise.md), если вы хотите настроить и продемонстрировать функции и возможности Microsoft 365 корпоративный в гибридной облачной среде, которая использует локальные компоненты, такие как домен Windows Server Active Directory (AD).
    
## <a name="identity"></a>Идентификация

Функции и возможности, связанные с идентификацией, продемонстрированы в следующих статьях:

- [Синхронизация хэшей паролей](password-hash-sync-m365-ent-test-environment.md)
  
   Включение и проверка синхронизации службы каталогов на основе хэша пароля из контроллера домена Windows Server AD.

- [Сквозная проверка подлинности](pass-through-auth-m365-ent-test-environment.md)
  
   Включение и проверка сквозной проверки подлинности на контроллер домена Windows Server AD.

- [Простой единый вход Azure AD](single-sign-on-m365-ent-test-environment.md)
  
   Обеспечение и проверка простого единого входа Azure AD с использованием контроллера домена Windows Server AD.

- [Многофакторная проверка подлинности](multi-factor-authentication-microsoft-365-test-environment.md)
  
   Включение и тестирование многофакторной проверки подлинности с использованием смартфона для определенной учетной записи.

- [Защита учетных записей глобальных администраторов](protect-global-administrator-accounts-microsoft-365-test-environment.md)
 
   Блокировка учетных записей глобального администратора с помощью Office 365 Cloud App Security и политик условного доступа.

- [Сброс пароля](password-reset-m365-ent-test-environment.md)

   Используйте функцию самостоятельного сброса пароля (SSPR) для сброса пароля.

- [Автоматическое лицензирование и членство в группах](automate-licenses-group-membership-microsoft-365-test-environment.md)

   Упрощение администрирования новых учетных записей с помощью автоматического лицензирования и динамического членства в группах.

- [Защита идентификации Azure AD](azure-ad-identity-protection-microsoft-365-test-environment.md)

   Проверка текущих учетных записей пользователей на уязвимости.

## <a name="mobile-device-management"></a>Управление мобильными устройствами

Функции и возможности, связанные с управлением мобильными устройствами, продемонстрированы в следующих статьях:

- [Политики MAM](mam-policies-for-your-microsoft-365-enterprise-dev-test-environment.md)
    
   Создание групп пользователей и политик управления мобильными приложениями (MAM) для устройств с iOS и Android.
    
- [Регистрация устройств с iOS и Android](enroll-ios-and-android-devices-in-your-microsoft-enterprise-365-dev-test-environ.md)
   
   Регистрация устройств с iOS или Android и удаленное управление ими.


## <a name="information-protection"></a>Защита информации

Функции и возможности, связанные с защитой информации, продемонстрированы в следующих статьях:

- [Усиленная защита Office 365](increased-o365-security-microsoft-365-enterprise-dev-test-environment.md)
    
   Настройка параметров для усиления защиты Office 365 и изучение встроенных средств безопасности.
  
- [Классификация данных](data-classification-microsoft-365-enterprise-dev-test-environment.md)
    
   Настройка и присвоение метки Office 365 документу на сайте группы SharePoint Online.
    
- [Управление привилегированным доступом для вашей тестовой среды Microsoft 365 корпоративный](privileged-access-microsoft-365-enterprise-dev-test-environment.md)
    
   Настройка управления привилегированным доступом для своевременного доступа к задачам, требующим привилегий и разрешений повышенного уровня, в вашей организации Office 365.

## <a name="see-also"></a>См. также

[Знакомство с Microsoft Cloud при помощи руководств по лаборатории тестирования для внедрения облачных технологий](https://mva.microsoft.com/training-courses/experience-the-microsoft-cloud-with-cloud-adoption-test-lab-guides-17960?l=LXNRdhSLE_1000115881)
    
[Схема руководств по лаборатории тестирования для One Microsoft Cloud](http://aka.ms/catlgstack)
