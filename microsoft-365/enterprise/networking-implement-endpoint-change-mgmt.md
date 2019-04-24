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
# <a name="step-4-plan-for-url-and-ip-address-changes"></a><span data-ttu-id="3c466-102">Шаг 4. Планирование изменений URL- и IP-адресов</span><span class="sxs-lookup"><span data-stu-id="3c466-102">Step 4: Plan for URL and IP address changes</span></span>

<span data-ttu-id="3c466-103">*Этот шаг — необязательный; он применяется к планам E3 и E5 Microsoft 365 корпоративный.*</span><span class="sxs-lookup"><span data-stu-id="3c466-103">*This step is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/networking_icon-small.png)

>[!Note]
><span data-ttu-id="3c466-p101">Прежде чем приступать к данному шагу, необходимо выполнить [шаг 3](networking-configure-proxies-firewalls.md). Если вы не выполнили шаг 3, вы можете перейти к [шагу 5](networking-optimize-tcp-performance.md).</span><span class="sxs-lookup"><span data-stu-id="3c466-p101">This step requires [Step 3](networking-configure-proxies-firewalls.md). If you have not done Step 3, you can skip to [Step 5](networking-optimize-tcp-performance.md).</span></span>
>

<span data-ttu-id="3c466-p102">URL- и IP-адреса, используемые глобальной сетью Microsoft 365, со временем изменяются, поэтому важно планировать обновления этих конечных точек. Например, вам может потребоваться перенастроить ваши устройства периметра безопасности, выполнив указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="3c466-p102">The URLs and IP addresses used by the global Microsoft 365 network change over time, so it’s important to plan for updates to these endpoints. For example, you may need to reconfigure your security perimeter devices with:</span></span>

- <span data-ttu-id="3c466-108">Использовать новые URL-адреса для новых служб, которым нужна обработка без задержек.</span><span class="sxs-lookup"><span data-stu-id="3c466-108">New URLs for new services that will need unhindered processing</span></span>
- <span data-ttu-id="3c466-109">Удалить URL-адреса для служб, которые больше не используются.</span><span class="sxs-lookup"><span data-stu-id="3c466-109">Removed URLs for discontinued services</span></span>
- <span data-ttu-id="3c466-110">Использовать новые диапазоны IP-адресов для новых расположений в сети и серверов Майкрософт в Интернете.</span><span class="sxs-lookup"><span data-stu-id="3c466-110">New IP address ranges for new Microsoft network locations and servers on the Internet</span></span> 
- <span data-ttu-id="3c466-111">Изменить диапазоны IP-адресов для разных служб.</span><span class="sxs-lookup"><span data-stu-id="3c466-111">Changes in IP address ranges for the different services</span></span>

<span data-ttu-id="3c466-112">Дополнительные сведения о создании плана реализации изменений в конечных точках, включающий уведомления об изменениях, см. в разделах о том, как [управлять интеграцией конечных точек Office 365](https://support.office.com/article/Managing-Office-365-endpoints-99cab9d4-ef59-4207-9f2b-3728eb46bf9a?ui=en-US#ID0EABAAA=2._Proxies&ID0EAEAAA=3._Integration) и как [управлять прокси-серверами конечных точек Office 365](https://support.office.com/article/Managing-Office-365-endpoints-99cab9d4-ef59-4207-9f2b-3728eb46bf9a#ID0EABAAA=2._Proxies&ID0EAEAAA=2._Proxies).</span><span class="sxs-lookup"><span data-stu-id="3c466-112">For more information about establishing an implementation plan for changes in endpoints, which includes being notified of changes, see [Managing Office 365 endpoints-Integration](https://support.office.com/article/Managing-Office-365-endpoints-99cab9d4-ef59-4207-9f2b-3728eb46bf9a?ui=en-US#ID0EABAAA=2._Proxies&ID0EAEAAA=3._Integration) and [Managing Office 365 endpoints-Proxies](https://support.office.com/article/Managing-Office-365-endpoints-99cab9d4-ef59-4207-9f2b-3728eb46bf9a#ID0EABAAA=2._Proxies&ID0EAEAAA=2._Proxies).</span></span>

<span data-ttu-id="3c466-113">Прежде чем перейти к следующему шагу, проверьте [условия](networking-exit-criteria.md#crit-networking-step4), при выполнении которых можно считать данный шаг завершенным.</span><span class="sxs-lookup"><span data-stu-id="3c466-113">As an interim checkpoint, you can see the [exit criteria](networking-exit-criteria.md#crit-networking-step4) for this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="3c466-114">Следующий шаг</span><span class="sxs-lookup"><span data-stu-id="3c466-114">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step5.png)|[<span data-ttu-id="3c466-115">Оптимизация производительности клиентов и служб Office 365</span><span class="sxs-lookup"><span data-stu-id="3c466-115">Optimize client and Office 365 service performance</span></span>](networking-optimize-tcp-performance.md)|
