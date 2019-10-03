---
title: Шаг 5. Оптимизация производительности клиентов и служб Office 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/23/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: В этой статье рассказывается, как настроить параметры протокола TCP и служб Office 365, чтобы повысить их производительность.
ms.openlocfilehash: f89ae816780101c31971c8e3e60df803f82f1e55
ms.sourcegitcommit: 8bcd76e5c8749a5670fbc3356957a089454c03d1
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/02/2019
ms.locfileid: "37370076"
---
# <a name="step-5-optimize-client-and-office-365-service-performance"></a>Шаг 5. Оптимизация производительности клиентов и служб Office 365

*Этот этап не является обязательным. Он применяется к планам E3 и E5 Microsoft 365 корпоративный.*

![Этап 1. Сеть](./media/deploy-foundation-infrastructure/networking_icon-small.png)

Для повышения производительности вы можете выполнить тонкую настройку протокола Transmission Control Protocol (TCP), используемого для обмена данными между клиентскими устройствами и службами Office 365.

Чтобы оптимизировать производительность протокола TCP, можно изменить указанные ниже параметры этого протокола на клиентских устройствах.

- [Масштабирование окна TCP](https://blogs.technet.microsoft.com/onthewire/2014/03/28/ensuring-your-office-365-network-connection-isnt-throttled-by-your-proxy/). Настройте этот параметр, чтобы ваше клиентское устройство отправляло больше данных, прежде чем потребуется подтверждение устройства.
- [Время простоя TCP](https://blogs.technet.microsoft.com/onthewire/2014/03/04/network-perimeters-tcp-idle-session-settings-for-outlook-on-office-365/). Настройте этот параметр, чтобы ваше клиентское устройство могло более эффективно обрабатывать открытые подключения.
- [Максимальный размер сегмента TCP](https://blogs.technet.microsoft.com/onthewire/2014/06/27/checking-your-tcp-packets-are-pulling-their-weight-tcp-max-segment-size-or-mss/). Настройте этот параметр, чтобы ваше клиентское устройство могло отправлять самые большие блоки данных в пакете.
- [Выборочные подтверждения TCP](https://blogs.technet.microsoft.com/onthewire/2014/06/27/ensuring-your-tcp-stack-isnt-throwing-data-away/). Настройте этот параметр, чтобы ваше клиентское устройство могло более эффективно подтверждать принятые данные.

Сведения об оптимизации производительности служб Office 365 см. в указанных ниже дополнительных ресурсах.

- [Exchange Online](https://docs.microsoft.com/office365/enterprise/tune-exchange-online-performance)
- [Skype для бизнеса Online](https://docs.microsoft.com/office365/enterprise/tune-skype-for-business-online-performance)
- [SharePoint Online](https://docs.microsoft.com/office365/enterprise/tune-sharepoint-online-performance)
- [Project Web App в Project Online](https://docs.microsoft.com/ProjectOnline/tune-project-online-performance)

Прежде чем переходить к следующему этапу, проверьте [условия](networking-exit-criteria.md#crit-networking-step5), при выполнении которых можно считать данный этап завершенным.

## <a name="next-step"></a>Следующий шаг

[Условия, при выполнении которых можно считать сетевую инфраструктуру настроенной](networking-exit-criteria.md)
