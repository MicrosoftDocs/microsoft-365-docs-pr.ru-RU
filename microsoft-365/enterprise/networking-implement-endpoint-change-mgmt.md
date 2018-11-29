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
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: ''
ms.openlocfilehash: 44990dcfd09e5cc2a44666da43fdeeaffd59da7d
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/28/2018
ms.locfileid: "26870429"
---
# <a name="step-4-plan-for-url-and-ip-address-changes"></a><span data-ttu-id="f9d56-102">Шаг 4. Планирование изменений URL- и IP-адресов</span><span class="sxs-lookup"><span data-stu-id="f9d56-102">Step 4: Plan for URL and IP address changes</span></span>

<span data-ttu-id="f9d56-103">*Этот шаг — необязательный; он применяется к планам E3 и E5 Microsoft 365 корпоративный.*</span><span class="sxs-lookup"><span data-stu-id="f9d56-103">*This step is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/networking_icon-small.png)

>[!Note]
><span data-ttu-id="f9d56-p101">Прежде чем приступать к данному шагу, необходимо выполнить [шаг 3](networking-configure-proxies-firewalls.md). Если вы не выполнили шаг 3, вы можете перейти к [шагу 5](networking-optimize-tcp-performance.md).</span><span class="sxs-lookup"><span data-stu-id="f9d56-p101">This step requires [Step 3](networking-configure-proxies-firewalls.md). If you have not done Step 3, you can skip to [Step 5](networking-optimize-tcp-performance.md).</span></span>
>

<span data-ttu-id="f9d56-p102">URL- и IP-адреса, используемые глобальной сетью Microsoft 365, со временем изменяются, поэтому важно планировать обновления этих конечных точек. Например, вам может потребоваться перенастроить ваши устройства периметра безопасности, выполнив указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="f9d56-p102">The URLs and IP addresses used by the global Microsoft 365 network change over time, so it’s important to plan for updates to these endpoints. For example, you may need to reconfigure your security perimeter devices with:</span></span>

- <span data-ttu-id="f9d56-108">Использовать новые URL-адреса для новых служб, которым нужна обработка без задержек.</span><span class="sxs-lookup"><span data-stu-id="f9d56-108">New URLs for new services that will need unhindered processing</span></span>
- <span data-ttu-id="f9d56-109">Удалить URL-адреса для служб, которые больше не используются.</span><span class="sxs-lookup"><span data-stu-id="f9d56-109">Removed URLs for discontinued services</span></span>
- <span data-ttu-id="f9d56-110">Использовать новые диапазоны IP-адресов для новых расположений в сети и серверов Майкрософт в Интернете.</span><span class="sxs-lookup"><span data-stu-id="f9d56-110">New IP address ranges for new Microsoft network locations and servers on the Internet</span></span> 
- <span data-ttu-id="f9d56-111">Изменить диапазоны IP-адресов для разных служб.</span><span class="sxs-lookup"><span data-stu-id="f9d56-111">Changes in IP address ranges for the different services</span></span>

<span data-ttu-id="f9d56-112">Дополнительные сведения о создании плана реализации изменений в конечных точках, включающий уведомления об изменениях, см. в разделах о том, как [управлять интеграцией конечных точек Office 365](https://support.office.com/article/Managing-Office-365-endpoints-99cab9d4-ef59-4207-9f2b-3728eb46bf9a?ui=en-US#ID0EABAAA=2._Proxies&ID0EAEAAA=3._Integration) и как [управлять прокси-серверами конечных точек Office 365](https://support.office.com/article/Managing-Office-365-endpoints-99cab9d4-ef59-4207-9f2b-3728eb46bf9a#ID0EABAAA=2._Proxies&ID0EAEAAA=2._Proxies).</span><span class="sxs-lookup"><span data-stu-id="f9d56-112">For more information about establishing an implementation plan for changes in endpoints, which includes being notified of changes, see [Managing Office 365 endpoints-Integration](https://support.office.com/article/Managing-Office-365-endpoints-99cab9d4-ef59-4207-9f2b-3728eb46bf9a?ui=en-US#ID0EABAAA=2._Proxies&ID0EAEAAA=3._Integration) and [Managing Office 365 endpoints-Proxies](https://support.office.com/article/Managing-Office-365-endpoints-99cab9d4-ef59-4207-9f2b-3728eb46bf9a#ID0EABAAA=2._Proxies&ID0EAEAAA=2._Proxies).</span></span>

<span data-ttu-id="f9d56-113">Прежде чем перейти к следующему шагу, проверьте [условия](networking-exit-criteria.md#crit-networking-step4), при выполнении которых можно считать данный шаг завершенным.</span><span class="sxs-lookup"><span data-stu-id="f9d56-113">As an interim checkpoint, you can see the [exit criteria](networking-exit-criteria.md#crit-networking-step4) for this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="f9d56-114">Следующий шаг</span><span class="sxs-lookup"><span data-stu-id="f9d56-114">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step5.png)|[<span data-ttu-id="f9d56-115">Оптимизация производительности клиентов и служб Office 365</span><span class="sxs-lookup"><span data-stu-id="f9d56-115">Optimize client and Office 365 service performance</span></span>](networking-optimize-tcp-performance.md)|
