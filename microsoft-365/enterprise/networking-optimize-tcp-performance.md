---
title: Шаг 5. Оптимизация производительности клиентов и служб Office 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 03/13/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: В этой статье рассказывается, как настроить параметры протокола TCP и служб Office 365, чтобы повысить их производительность.
ms.openlocfilehash: 40f99f1b50a324af0650382de165dcfd3df97b0c
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/28/2018
ms.locfileid: "26870645"
---
# <a name="step-5-optimize-client-and-office-365-service-performance"></a>Шаг 5. Оптимизация производительности клиентов и служб Office 365

*Этот шаг — необязательный; он применяется к планам E3 и E5 Microsoft 365 корпоративный.*

![](./media/deploy-foundation-infrastructure/networking_icon-small.png)

Для повышения производительности вы можете выполнить тонкую настройку протокола Transmission Control Protocol (TCP), используемого для обмена данными между клиентскими устройствами и службами Office 365.

Чтобы оптимизировать производительность протокола TCP, можно изменить указанные ниже параметры этого протокола на клиентских устройствах.

- [Масштабирование окна TCP](https://blogs.technet.microsoft.com/onthewire/2014/03/28/ensuring-your-office-365-network-connection-isnt-throttled-by-your-proxy/). Настройте этот параметр, чтобы ваше клиентское устройство отправляло больше данных, прежде чем потребуется подтверждение устройства.
- [Время простоя TCP](https://blogs.technet.microsoft.com/onthewire/2014/03/04/network-perimeters-tcp-idle-session-settings-for-outlook-on-office-365/). Настройте этот параметр, чтобы ваше клиентское устройство могло более эффективно обрабатывать открытые подключения.
- [Максимальный размер сегмента TCP](https://blogs.technet.microsoft.com/onthewire/2014/06/27/checking-your-tcp-packets-are-pulling-their-weight-tcp-max-segment-size-or-mss/). Настройте этот параметр, чтобы ваше клиентское устройство могло отправлять самые большие блоки данных в пакете.
- [Выборочные подтверждения TCP](https://blogs.technet.microsoft.com/onthewire/2014/06/27/ensuring-your-tcp-stack-isnt-throwing-data-away/). Настройте этот параметр, чтобы ваше клиентское устройство могло более эффективно подтверждать принятые данные.

Сведения об оптимизации производительности служб Office 365 см. в указанных ниже дополнительных ресурсах.

- [Exchange Online](https://support.office.com/article/Tune-Exchange-Online-performance-026e83cb-a945-4543-97b0-a8af6e80ac61)
- [Skype для бизнеса Online](https://support.office.com/article/Tune-Skype-for-Business-Online-performance-beec23c2-c5d6-4e84-a8af-e82aefca7802)
- [SharePoint Online](https://support.office.com/article/Tune-SharePoint-Online-performance-f0522d4a-fbf4-41f9-854e-c9b59555091d)
- [Project Online](https://support.office.com/article/Tune-Project-Online-performance-12ba0ebd-c616-42e5-b9b6-cad570e8409c)

Прежде чем перейти к следующему шагу, проверьте [условия](networking-exit-criteria.md#crit-networking-step5), при выполнении которых можно считать данный шаг завершенным.

## <a name="next-step"></a>Следующий шаг

[Условия, при выполнении которых можно считать сетевую инфраструктуру настроенной](networking-exit-criteria.md)
