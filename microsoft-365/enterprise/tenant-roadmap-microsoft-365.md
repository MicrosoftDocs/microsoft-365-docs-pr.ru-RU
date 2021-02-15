---
title: План клиента для Microsoft 365
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-subscription-management
- m365initiative-coredeploy
ms.custom: it-pro
description: План по настройкам клиентов для Microsoft 365.
ms.openlocfilehash: d2640a036eedda0b0962a15a03dcf0211ea0209b
ms.sourcegitcommit: c84cceb07e748969723a31b350e37f3ec79255ab
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/09/2020
ms.locfileid: "48948401"
---
# <a name="tenant-roadmap-for-microsoft-365"></a>План клиента для Microsoft 365

Клиент Microsoft 365 — это набор служб, которые назначены вашей организации. Как правило, этот клиент связан с одним или более вашими общедоступными доменными именами DNS и выступает в качестве центрального и изолированного контейнера для различных подписок и лицензий, которые вы назначаете учетным записям пользователей. Дополнительные сведения см. в подписках, лицензиях, учетных записях и клиентах [облачных предложений Майкрософт.](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md)

При создании клиента Microsoft 365 вы назначаете его определенному географическому расположению. Вы также можете иметь клиент с несколькими географическими расположениями и перемещать его из одного расположения в другое.

Чтобы клиент был готов к пользователям, группам, лицензиям и облачным приложениям, важно тщательно спланировать и выполнить настройку клиента.

## <a name="set-up-your-microsoft-365-tenant"></a>Настройка клиента Microsoft 365

Убедившись, что сеть оптимизирована для доступа к Microsoft 365 как для локального, так и для удаленных сотрудников, следующие важные задачи — планирование и настройка клиента Microsoft 365 для доменных имен DNS, общих служб и для инфраструктуры удостоверений, поддерживающую безопасный вход пользователей.

### <a name="plan"></a>План

Чтобы спланировать реализацию клиента, спланируйте:

- [Подписки, лицензии и клиенты Azure Active Directory (Azure AD)](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md)
- [Использование сторонних SSL-сертификатов](plan-for-third-party-ssl-certificates.md)
- [Способы интеграции клиента Microsoft 365 со службами Azure AD](integrated-apps-and-azure-ads.md)
- [Планирование поддержки клиентских приложений](microsoft-365-client-support-certificate-based-authentication.md)
- [Определение использования гибридной современной проверки подлинности](hybrid-modern-auth-overview.md)
- [Планирование обновлений Office 2007 и Office 2010](plan-upgrade-previous-versions-office.md)
- [Понимание изоляции клиента](microsoft-365-tenant-isolation-overview.md)

### <a name="deploy"></a>Развертывание

Чтобы развернуть клиент: 

- Добавьте [домены DNS](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain) для организации.
- Используйте руководства [по настройке в Центре администрирования Microsoft 365.](setup-guides-for-microsoft-365.md)
- Создайте [инфраструктуру удостоверений](identity-roadmap-microsoft-365.md) и [забезопасные входы пользователей.](microsoft-365-secure-sign-in.md)

### <a name="move-a-tenants-geographic-locations"></a>Перемещение географических местоположений клиента

Корпорация Майкрософт продолжает открывать новые географические расположения центров обработки данных для служб Microsoft 365. Эти новые геополии центра обработки данных добавляют мощности и вычислительные ресурсы для поддержки роста потребностей клиентов и использования. Кроме того, новые геополии центра обработки данных предлагают географическое место хранения данных для основных данных клиента.

Дополнительные сведения см. в теме "Перемещение основных данных в новые географические области центра обработки данных [Microsoft 365".](moving-data-to-new-datacenter-geos.md)


## <a name="deploy-microsoft-365-multi-geo"></a>Развертывание Microsoft 365 с несколькими географическими службами

С помощью Microsoft 365 Multi-Geo организация может расширить присутствие Microsoft 365 до нескольких географических регионов или стран в существующем клиенте.

Дополнительные сведения см. на странице [Microsoft 365 Multi-Geo](microsoft-365-multi-geo.md).

## <a name="manage-multiple-microsoft-365-tenants"></a>Управление несколькими клиентами Microsoft 365 

Хотя один клиент идеально подходит для вашей оганизации, вы можете быть одной из многих организаций с несколькими арендаторами. Причины могут включать слияния и приобретения, административную изоляцию или децентрализованную ИТ-структуру.

Если у вас несколько клиентов Microsoft 365, дополнительные сведения см. в указанных здесь статьях.

- [Взаимодействие между клиентами](microsoft-365-inter-tenant-collaboration.md)
- [Миграция почтовых ящиков между клиентами](cross-tenant-mailbox-migration.md)
- [Миграция между клиентами](microsoft-365-tenant-to-tenant-migrations.md)

## <a name="next-step"></a>Следующий этап

Начните планирование клиентов с [помощью подписок, лицензий, учетных записей и клиентов.](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md)
