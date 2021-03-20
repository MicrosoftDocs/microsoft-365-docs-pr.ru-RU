---
title: Дорожная карта клиента для Microsoft 365
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
description: Дорожная карта для набора клиентов для Microsoft 365.
ms.openlocfilehash: fb3b6eecd893a5ab9b71bfa7bdfaea53af43470d
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50909458"
---
# <a name="tenant-roadmap-for-microsoft-365"></a>Дорожная карта клиента для Microsoft 365

Клиент Microsoft 365 — это набор служб, которые назначены вашей организации. Как правило, этот клиент связан с одним или более общедоступными доменными именами DNS и выступает в качестве центрального и изолированного контейнера для различных подписок и лицензий, которые вы назначаете учетным записям пользователей. Дополнительные сведения см. [в подписях, лицензиях,](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md)учетных записях и клиентах облачных предложений Майкрософт.

При создании клиента Microsoft 365 вы назначите ему определенное географическое расположение. Вы также можете иметь клиента с несколькими географическими расположениями и перемещать клиента из одного расположения в другое.

Чтобы клиент был готов к пользовательским, группам, лицензиям и облачным приложениям, важно тщательно планировать и выполнять конфигурацию клиента.

## <a name="set-up-your-microsoft-365-tenant"></a>Настройка клиента Microsoft 365

После того, как ваша сеть оптимизирована для доступа к Microsoft 365 как для локального, так и для удаленных сотрудников, в следующих больших задачах планируется настроить клиента Microsoft 365 для доменных имен DNS, общих служб и инфраструктуры удостоверений, поддерживающую безопасный вход пользователя.

### <a name="plan"></a>Планирование

Планирование реализации клиента:

- [Понимание клиентов подписки, лицензий и Azure Active Directory (Azure AD).](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md)
- [Понимание использования сторонних сертификатов SSL](plan-for-third-party-ssl-certificates.md)
- [Понимание способов интеграции клиента Microsoft 365 с службами Azure AD](integrated-apps-and-azure-ads.md)
- [Планирование поддержки клиентских приложений](microsoft-365-client-support-certificate-based-authentication.md)
- [Определение использования гибридной современной проверки подлинности](hybrid-modern-auth-overview.md)
- [Планирование обновлений Office 2007 и Office 2010](plan-upgrade-previous-versions-office.md)
- [Понимание изоляции клиента](microsoft-365-tenant-isolation-overview.md)

### <a name="deploy"></a>Развертывание

Развертывание клиента: 

- Добавление [доменов DNS для](../admin/setup/add-domain.md) организации.
- Используйте руководства [по настройке в центре администрирования Microsoft 365.](setup-guides-for-microsoft-365.md)
- Создайте [инфраструктуру удостоверений](identity-roadmap-microsoft-365.md) [и обезопасите входы пользователя.](microsoft-365-secure-sign-in.md)

### <a name="move-a-tenants-geographic-locations"></a>Перемещение географических местоположений клиента

Корпорация Майкрософт продолжает открывать новые географические расположения центров обработки данных (geos) для служб Microsoft 365. Эти новые геоцентры данных добавляют мощности и вычислительные ресурсы для поддержки спроса клиентов и роста использования. Кроме того, новые геоцентры центра обработки данных предоставляют резидентство данных для основных данных клиентов.

Дополнительные сведения см. в дополнительных сведениях о перемещении основных данных в новые геоцентры центра обработки данных Microsoft [365.](moving-data-to-new-datacenter-geos.md)


## <a name="deploy-microsoft-365-multi-geo"></a>Развертывание Microsoft 365 Multi-Geo

С помощью Microsoft 365 Multi-Geo организация может расширить присутствие Microsoft 365 до нескольких географических регионов или стран в существующем клиенте.

Дополнительные сведения см. на странице [Microsoft 365 Multi-Geo](microsoft-365-multi-geo.md).

## <a name="manage-multiple-microsoft-365-tenants"></a>Управление несколькими клиентами Microsoft 365 

Хотя наличие одного клиента для оганизации идеально подходит, вы можете быть одной из многих организаций с несколькими арендаторами. Причинами могут быть слияния и приобретения, нужна административная изоляция или децентрализованная ИТ-система.

Если у вас несколько клиентов Microsoft 365, см. в этих статьях дополнительные сведения о:

- [Взаимодействие между клиентами](microsoft-365-inter-tenant-collaboration.md)
- [Миграция почтовых ящиков между клиентами](cross-tenant-mailbox-migration.md)
- [Миграция между клиентами](microsoft-365-tenant-to-tenant-migrations.md)

## <a name="next-step"></a>Следующий шаг

Начните планирование клиента [с подписки, лицензий, учетных записей и клиентов.](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md)