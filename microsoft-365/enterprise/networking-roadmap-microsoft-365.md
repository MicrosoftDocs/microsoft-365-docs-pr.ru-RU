---
title: План сети для Microsoft 365
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
description: План реализации сети Microsoft 365.
ms.openlocfilehash: 2962adf7bdca35d06672696471e0932fd1a7b09c
ms.sourcegitcommit: a76de3d1604d755b29053e7bf557c0008be6ad23
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/08/2021
ms.locfileid: "49787755"
---
# <a name="networking-roadmap-for-microsoft-365"></a>План сети для Microsoft 365

Microsoft 365 для предприятий включает облачные службы для совместной работы и повышения производительности, Microsoft Intune, а также множество служб удостоверений и безопасности Microsoft Azure. Для всех этих облачных служб используются безопасные, производительные и надежные подключения с клиентских устройств через Интернет или выделенные каналы. Чтобы разместить эти службы и сделать их доступными клиентам по всему миру, корпорация Майкрософт разработала сетевую инфраструктуру, в которой основное внимание уделено производительности и интеграции. 

Важной частью подключения Microsoft 365 является настройка сети и подключений к Интернету для оптимизированного доступа. Настройка локальной сети для доступа к глобально распределенному облаку SaaS отличается от традиционной сети, оптимизированной для трафика к локальному центру обработки данных и центральному подключению к Интернету. 

С помощью этих статей можно ознакомиться с основными различиями пограничных устройств, клиентских компьютеров и локальной сети, а также изменять их для обеспечения оптимальной производительности для локальных пользователей.

## <a name="plan"></a>План

На этапе планирования сетевой реализации:

- [Понять, как работает сеть Microsoft 365](microsoft-365-networking-overview.md)
- [Оценка текущего сетевого подключения](assessing-network-connectivity.md)
- [Определение того, является ли ExpressRoute правильным для вашей организации](network-planning-with-expressroute.md)
- [Планирование сетевых устройств](plan-for-network-devices.md)
- [Настройка сети для миграции](network-and-migration-planning.md)

## <a name="deploy"></a>Развертывание

На этапе развертывания сетевой реализации:

- [Убедитесь, что ваша корпоративная сеть оптимизирована для подключения к Microsoft 365](set-up-network-for-microsoft-365.md)
- [Добавление доменов DNS для организации](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain)
- [Оптимизация подключения к конечным точкам Microsoft 365](microsoft-365-ip-web-service.md)
- [Оптимизация подключения для удаленных работников](microsoft-365-vpn-split-tunnel.md)
- При необходимости [настройте ExpressRoute](azure-expressroute.md)

## <a name="manage"></a>Управление

На этапе управления сетевой реализацией:

- [Убедитесь, что сетевые устройства используют последние конечные точки Office 365](microsoft-365-endpoints.md)
- [Мониторинг и настройка производительности сети](network-planning-and-performance.md)
- [Отслеживание подключений ExpressRoute](managing-expressroute-for-connectivity.md)

## <a name="network-equipment-vendors"></a>Поставщики сетевого оборудования

Если вы поставщик сетевого оборудования, присоединяйтесь к партнерской программе [Microsoft 365 networking.](microsoft-365-networking-partner-program.md) Зарегистрироваться в программе, чтобы встроить принципы сетевого подключения Microsoft 365 в свои продукты и решения. 

## <a name="how-contoso-did-networking-for-microsoft-365"></a>Как Contoso в сети для Microsoft 365

Посмотрите, как корпорация Contoso, вымышленная представительская многонациональная компания, [оптимизировала сетевые устройства и подключения к Интернету](contoso-networking.md) для облачных служб Microsoft 365.

![Корпорация Contoso](../media/contoso-overview/contoso-icon.png)

## <a name="next-step"></a>Следующий шаг

Начните планирование сети с помощью обзора сетевых подключений [Microsoft 365.](microsoft-365-networking-overview.md)
