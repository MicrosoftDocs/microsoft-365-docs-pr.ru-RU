---
title: Шаг 4. Планирование изменений URL- и IP-адресов
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 03/05/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: ''
ms.openlocfilehash: 626d0e242c549fb16880710bbca31db0bdee9029
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "32291328"
---
# <a name="step-4-plan-for-url-and-ip-address-changes"></a>Шаг 4. Планирование изменений URL- и IP-адресов

*Этот шаг — необязательный; он применяется к планам E3 и E5 Microsoft 365 корпоративный.*

![](./media/deploy-foundation-infrastructure/networking_icon-small.png)

>[!Note]
>Прежде чем приступать к данному шагу, необходимо выполнить [шаг 3](networking-configure-proxies-firewalls.md). Если вы не выполнили шаг 3, вы можете перейти к [шагу 5](networking-optimize-tcp-performance.md).
>

URL- и IP-адреса, используемые глобальной сетью Microsoft 365, со временем изменяются, поэтому важно планировать обновления этих конечных точек. Например, вам может потребоваться перенастроить ваши устройства периметра безопасности, выполнив указанные ниже действия.

- Использовать новые URL-адреса для новых служб, которым нужна обработка без задержек.
- Удалить URL-адреса для служб, которые больше не используются.
- Использовать новые диапазоны IP-адресов для новых расположений в сети и серверов Майкрософт в Интернете. 
- Изменить диапазоны IP-адресов для разных служб.

Дополнительные сведения о создании плана реализации изменений в конечных точках, включающий уведомления об изменениях, см. в разделах о том, как [управлять интеграцией конечных точек Office 365](https://support.office.com/article/Managing-Office-365-endpoints-99cab9d4-ef59-4207-9f2b-3728eb46bf9a?ui=en-US#ID0EABAAA=2._Proxies&ID0EAEAAA=3._Integration) и как [управлять прокси-серверами конечных точек Office 365](https://support.office.com/article/Managing-Office-365-endpoints-99cab9d4-ef59-4207-9f2b-3728eb46bf9a#ID0EABAAA=2._Proxies&ID0EAEAAA=2._Proxies).

Прежде чем перейти к следующему шагу, проверьте [условия](networking-exit-criteria.md#crit-networking-step4), при выполнении которых можно считать данный шаг завершенным.

## <a name="next-step"></a>Следующий шаг

|||
|:-------|:-----|
|![](./media/stepnumbers/Step5.png)|[Оптимизация производительности клиентов и служб Office 365](networking-optimize-tcp-performance.md)|
