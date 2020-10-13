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
ms.openlocfilehash: 0f1fa91bb81fd6cc87820f2b2d48e00e1b75a0c4
ms.sourcegitcommit: 9a764c2aed7338c37f6e92f5fb487f02b3c4dfa1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/13/2020
ms.locfileid: "48446011"
---
# <a name="tenant-roadmap-for-microsoft-365"></a>План обслуживания клиентов для Microsoft 365

Ваш клиент Microsoft 365 — это набор служб, назначенных Организации. Как правило, этот клиент связан с одним или несколькими доменными именами DNS и выступает в качестве центрального контейнера для различных подписок и лицензий, которые назначаются учетным записям пользователей.

При создании клиента Microsoft 365 вы назначаете его определенному географическому расположению. Вы также можете использовать клиент с несколькими географическими расположениями и переместить клиент из одного места в другое.

Чтобы клиент был готов для основных служб сети и удостоверения, необходимо тщательно спланировать и выполнить настройку клиента.

## <a name="plan"></a>План

Чтобы спланировать реализацию клиента, выполните указанные ниже действия.

- [Общие сведения о подписках, лицензиях и клиентах Azure Active Directory (Azure AD)](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md)
- [Сведения об использовании сторонних SSL-сертификатов](plan-for-third-party-ssl-certificates.md)
- [Общие сведения о способах интеграции клиента Microsoft 365 со службами Azure AD](integrated-apps-and-azure-ads.md)
- [Планирование поддержки клиентских приложений](microsoft-365-client-support-certificate-based-authentication.md)
- [Определение способа использования гибридной современной проверки подлинности](hybrid-modern-auth-overview.md)
- [Планирование обновлений для Office 2007 и Office 2010](plan-upgrade-previous-versions-office.md)
- [Общие сведения об изоляции клиентов](microsoft-365-tenant-isolation-overview.md)
- [Получение сведений о службе Microsoft 365 Service Assurance](https://docs.microsoft.com/microsoft-365/compliance/service-assurance)

## <a name="deploy"></a>Развертывание

Чтобы развернуть клиент, [Добавьте домены DNS](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain) для Организации и используйте [руководства по настройке в центре администрирования Microsoft 365](setup-guides-for-microsoft-365.md).

## <a name="tenants-with-multiple-geographic-locations"></a>Клиенты с несколькими географическими расположениями

С помощью Microsoft 365 Multi-Geo организация может расширить присутствие Microsoft 365 до нескольких географических регионов или стран в существующем клиенте.

Для получения сведений о Microsoft 365 с поддержкой нескольких регионов, в том числе о планировании, настройке и администрировании, [Начните отсюда](microsoft-365-multi-geo.md).

## <a name="move-a-tenants-geographic-locations"></a>Перемещение географических расположений клиента

Корпорация Майкрософт продолжает открывать новые географические расположения центра обработки данных (жеос) для служб Microsoft 365. Эти новые центры обработки данных жеос добавляют ресурсы емкости и вычислительные ресурсы для поддержки роста требований клиентов и использования. Кроме того, новые центры обработки данных жеос предоставляют размещению данных для основных данных клиентов.

Сведения о центре обработки данных Майкрософт 365, в том числе о том, как запрашивать перемещение географических данных, [начинаются отсюда](moving-data-to-new-datacenter-geos.md).

## <a name="next-step"></a>Следующий этап

Начните планирование клиентов с помощью [подписок, лицензий, учетных записей и клиентов](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md).

