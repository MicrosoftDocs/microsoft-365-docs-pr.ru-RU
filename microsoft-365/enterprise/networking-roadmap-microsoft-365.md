---
title: Сетевая схема для Microsoft 365
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
- Strat_O365_Enterprise
ms.custom: ''
description: Схема реализации сети Microsoft 365.
ms.openlocfilehash: 93d0f253e098815139b431a826f7e5e7a0410b37
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/14/2020
ms.locfileid: "46693250"
---
# <a name="networking-roadmap-for-microsoft-365"></a>Сетевая схема для Microsoft 365

Microsoft 365 для предприятий включает облачные службы для совместной работы и продуктивной работы, Microsoft Intune и многие службы удостоверений и безопасности Microsoft Azure. Для всех этих облачных служб используются безопасные, производительные и надежные подключения с клиентских устройств через Интернет или выделенные каналы. Чтобы разместить эти службы и сделать их доступными клиентам по всему миру, корпорация Майкрософт разработала сетевую инфраструктуру, в которой основное внимание уделено производительности и интеграции. 

Важной частью вашей входящей миграции Microsoft 365 является обеспечение настройки для оптимизированного доступа к сети и подключению к Интернету. Настройка локальной сети для доступа к глобально распределенному облачному программному обеспечению (SaaS) отличается от традиционной сети, оптимизированной для трафика в локальных центрах обработки данных и центрального подключения к Интернету. 

С помощью этих статей можно ознакомиться с основными различиями пограничных устройств, клиентских компьютеров и локальной сети, а также изменять их для обеспечения оптимальной производительности для локальных пользователей.

## <a name="plan"></a>План

На этапе планирования реализации сети:

- [Общие сведения о работе сети Microsoft 365](microsoft-365-networking-overview.md)
- [Оценка текущего сетевого подключения](assessing-network-connectivity.md)
- [Определение правильности ExpressRoute для Организации](network-planning-with-expressroute.md)
- [Планирование сетевых устройств](plan-for-network-devices.md)
- [Настройка сети для миграции](network-and-migration-planning.md)

## <a name="deploy"></a>Развертывание

На этапе развертывания реализации сети:

- [Обеспечение оптимизации корпоративной сети для подключения к Microsoft 365](set-up-network-for-microsoft-365.md)
- [Добавление доменов DNS для Организации](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain)
- [Оптимизация подключения к конечным точкам Microsoft 365](microsoft-365-ip-web-service.md)
- [Оптимизация подключения для удаленных рабочих процессов](microsoft-365-vpn-split-tunnel.md)
- При необходимости [Настройте ExpressRoute](azure-expressroute.md)

## <a name="manage"></a>Управление

На этапе управления вашей реализацией сети:

- [Убедитесь, что сетевые устройства используют последние конечные точки Office 365.](microsoft-365-endpoints.md)
- [Мониторинг и настройка производительности сети](network-planning-and-performance.md)
- [Отслеживание подключений ExpressRoute](managing-expressroute-for-connectivity.md)

## <a name="network-equipment-vendors"></a>Поставщики сетевого оборудования

Если вы являетесь поставщиком сетевого оборудования, присоединитесь к [программе сетевого партнера Microsoft 365](microsoft-365-networking-partner-program.md). Зарегистрируйтесь в программе, чтобы создать принципы сетевого подключения Microsoft 365 к вашим продуктам и решениям. 

## <a name="how-contoso-did-networking-for-microsoft-365"></a>Сведения о том, как компания Contoso выполнила подключение к Microsoft 365

Посмотрите, как корпорация Contoso, вымышленная представительская многонациональная компания, [оптимизировала сетевые устройства и подключения к Интернету](contoso-networking.md) для облачных служб Microsoft 365.

![Корпорация Contoso](../media/contoso-overview/contoso-icon.png)

## <a name="next-step"></a>Следующий шаг

Запустите планирование сети с [обзором сетевого подключения Microsoft 365](microsoft-365-networking-overview.md).
