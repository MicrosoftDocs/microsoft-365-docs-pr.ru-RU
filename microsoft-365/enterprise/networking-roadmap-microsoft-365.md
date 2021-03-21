---
title: Дорожная карта сети для Microsoft 365
f1.keywords:
- NOCSH
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 08/10/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Дорожная карта для реализации сетевой сети Microsoft 365.
ms.openlocfilehash: be1691138290a592822bfb4d59286fe795270450
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50923556"
---
# <a name="networking-roadmap-for-microsoft-365"></a>Дорожная карта сети для Microsoft 365

Microsoft 365 для предприятия включает облачные службы совместной работы и производительности, Microsoft Intune и многие службы удостоверений и безопасности Microsoft Azure. Для всех этих облачных служб используются безопасные, производительные и надежные подключения с клиентских устройств через Интернет или выделенные каналы. Чтобы разместить эти службы и сделать их доступными клиентам по всему миру, корпорация Майкрософт разработала сетевую инфраструктуру, в которой основное внимание уделено производительности и интеграции. 

Важной частью подключения к Microsoft 365 является настройка сетевых и интернет-подключений для оптимизации доступа. Настройка локальной сети для доступа к глобально распределенному облаку Software-as-a-Service (SaaS) отличается от традиционной сети, оптимизированной для трафика в локальном центре обработки данных и центральном подключении к Интернету. 

С помощью этих статей можно ознакомиться с основными различиями пограничных устройств, клиентских компьютеров и локальной сети, а также изменять их для обеспечения оптимальной производительности для локальных пользователей.

## <a name="plan"></a>Планирование

На этапе планирования реализации сети:

- [Понять, как работает сеть Microsoft 365](microsoft-365-networking-overview.md)
- [Оценка текущего подключения к сети](assessing-network-connectivity.md)
- [Определите, правильно ли ExpressRoute для организации](network-planning-with-expressroute.md)
- [Планирование сетевых устройств](plan-for-network-devices.md)
- [Настройка сети для миграции](network-and-migration-planning.md)

## <a name="deploy"></a>Развертывание

На этапе развертывания сетевой реализации:

- [Убедитесь, что корпоративная сеть оптимизирована для подключения Microsoft 365](set-up-network-for-microsoft-365.md)
- [Добавление доменов DNS для организации](../admin/setup/add-domain.md)
- [Оптимизация подключения к конечным точкам Microsoft 365](microsoft-365-ip-web-service.md)
- [Оптимизация подключения для удаленных сотрудников](microsoft-365-vpn-split-tunnel.md)
- При необходимости [настройте ExpressRoute](azure-expressroute.md)

## <a name="manage"></a>Управление

На этапе управления реализацией сети:

- [Убедитесь, что сетевые устройства используют последние конечные точки Office 365](microsoft-365-endpoints.md)
- [Мониторинг и настройка производительности сети](network-planning-and-performance.md)
- [Мониторинг подключений ExpressRoute](managing-expressroute-for-connectivity.md)

## <a name="network-equipment-vendors"></a>Поставщики сетевого оборудования

Если вы поставщик сетевого оборудования, присоединяйтесь к партнерской программе [Microsoft 365 Networking.](microsoft-365-networking-partner-program.md) Регистрация в программе для создания принципов сетевого подключения Microsoft 365 к продуктам и решениям. 

## <a name="how-contoso-did-networking-for-microsoft-365"></a>Как Contoso сделала сеть для Microsoft 365

Посмотрите, как корпорация Contoso, вымышленная представительская многонациональная компания, [оптимизировала сетевые устройства и подключения к Интернету](contoso-networking.md) для облачных служб Microsoft 365.

![Корпорация Contoso](../media/contoso-overview/contoso-icon.png)

## <a name="next-step"></a>Следующий шаг

Начните планирование сетей с помощью обзора подключения к сети [Microsoft 365.](microsoft-365-networking-overview.md)