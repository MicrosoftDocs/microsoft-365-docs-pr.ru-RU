---
title: План обслуживания клиентов для Microsoft 365
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 08/10/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-subscription-management
- m365initiative-coredeploy
ms.custom: it-pro
description: План настройки клиентов для Microsoft 365.
ms.openlocfilehash: db0f9552fce460ca6d25ee74ea2031bea388b8dc
ms.sourcegitcommit: 3b1bd8aa1430bc9565743a446bbc27b199f30f73
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/22/2020
ms.locfileid: "48656011"
---
# <a name="tenant-roadmap-for-microsoft-365"></a>План обслуживания клиентов для Microsoft 365

Ваш клиент Microsoft 365 — это набор служб, назначенных Организации. Как правило, этот клиент связан с одним или несколькими доменными именами DNS и выступает в качестве центрального контейнера для различных подписок и лицензий, которые назначаются учетным записям пользователей. Для получения дополнительных сведений см [подписки, лицензии, учетные записи и клиенты для облачных услуг Майкрософт](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md).

При создании клиента Microsoft 365 вы назначаете его определенному географическому расположению. Вы также можете использовать клиент с несколькими географическими расположениями и переместить клиент из одного места в другое.

Чтобы клиент был готов для идентификации, важно тщательно спланировать и выполнить настройку клиента.


## <a name="set-up-your-microsoft-365-tenant"></a>Настройка клиента Microsoft 365

Убедившись, что сеть оптимизирована для доступа к Microsoft 365 для локальных и удаленных сотрудников, следующие крупные задачи планируются, а затем настраивают свой клиент Microsoft 365 для доменных имен DNS, общих служб и этой инфраструктуры удостоверений, которая поддерживает безопасный вход пользователя.

## <a name="plan"></a>План

Чтобы спланировать реализацию клиента, выполните указанные ниже действия.

- [Общие сведения о подписках, лицензиях и клиентах Azure Active Directory (Azure AD)](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md)
- [Сведения об использовании сторонних SSL-сертификатов](plan-for-third-party-ssl-certificates.md)
- [Общие сведения о способах интеграции клиента Microsoft 365 со службами Azure AD](integrated-apps-and-azure-ads.md)
- [Планирование поддержки клиентских приложений](microsoft-365-client-support-certificate-based-authentication.md)
- [Определение способа использования гибридной современной проверки подлинности](hybrid-modern-auth-overview.md)
- [Планирование обновлений для Office 2007 и Office 2010](plan-upgrade-previous-versions-office.md)
- [Общие сведения об изоляции клиентов](microsoft-365-tenant-isolation-overview.md)
- [Получение сведений о службе Microsoft 365 Service Assurance](microsoft-365-administrative-access-controls-overview.md)

### <a name="deploy"></a>Развертывание

Чтобы развернуть клиент: 

- Добавьте [домены DNS](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain) для Организации.
- Используйте [руководства по настройке в центре администрирования Microsoft 365](setup-guides-for-microsoft-365.md).
- Создайте [инфраструктуру идентификации](identity-roadmap-microsoft-365.md) и [Обеспечьте безопасность пользовательских входов](microsoft-365-secure-sign-in.md).

### <a name="move-a-tenants-geographic-locations"></a>Перемещение географических расположений клиента

Корпорация Майкрософт продолжает открывать новые географические расположения центра обработки данных (жеос) для служб Microsoft 365. Эти новые центры обработки данных жеос добавляют ресурсы емкости и вычислительные ресурсы для поддержки роста требований клиентов и использования. Кроме того, новые центры обработки данных жеос предоставляют размещению данных для основных данных клиентов.

Дополнительные сведения см. [в статье Перемещение основных данных в новый центр обработки данных Microsoft 365 жеос](moving-data-to-new-datacenter-geos.md).


## <a name="deploy-microsoft-365-multi-geo"></a>Развертывание Microsoft 365 с поддержкой нескольких регионов

С помощью Microsoft 365 Multi-Geo организация может расширить присутствие Microsoft 365 до нескольких географических регионов или стран в существующем клиенте.

Более подробную информацию можно найти в [статье Microsoft 365 с поддержкой нескольких регионов](microsoft-365-multi-geo.md).

## <a name="manage-multiple-microsoft-365-tenancies"></a>Управление несколькими клиентыми Microsoft 365 

Несмотря на то, что у вас есть один клиент для вашего оганизатион, вы можете столкнуться с одной из многочисленных организаций, имеющих несколько клиенты. Причинами для нескольких клиенты могут быть слияния и приобретения, Административная изоляция или децентрализована.

Если у вас несколько клиенты Microsoft 365, ознакомьтесь со статьями, посвященными следующим статьям.

- [Взаимодействие между клиентами](microsoft-365-inter-tenant-collaboration.md)
- [Миграция почтовых ящиков между клиентами](cross-tenant-mailbox-migration.md)
- [Миграция между клиентами](microsoft-365-tenant-to-tenant-migrations.md)


## <a name="next-step"></a>Следующий шаг

Начните планирование клиентов с помощью [подписок, лицензий, учетных записей и клиентов](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md).
