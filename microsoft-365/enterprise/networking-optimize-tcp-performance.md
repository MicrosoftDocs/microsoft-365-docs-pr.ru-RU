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
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: В этой статье рассказывается, как настроить параметры протокола TCP и служб Office 365, чтобы повысить их производительность.
ms.openlocfilehash: cf172bcaa87b7c69d33d349d18c449efff30a1d9
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "32290886"
---
# <a name="step-5-optimize-client-and-office-365-service-performance"></a><span data-ttu-id="0f2d1-103">Шаг 5. Оптимизация производительности клиентов и служб Office 365</span><span class="sxs-lookup"><span data-stu-id="0f2d1-103">Step 5: Optimize client and Office 365 service performance</span></span>

<span data-ttu-id="0f2d1-104">*Этот шаг — необязательный; он применяется к планам E3 и E5 Microsoft 365 корпоративный.*</span><span class="sxs-lookup"><span data-stu-id="0f2d1-104">*This step is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/networking_icon-small.png)

<span data-ttu-id="0f2d1-105">Для повышения производительности вы можете выполнить тонкую настройку протокола Transmission Control Protocol (TCP), используемого для обмена данными между клиентскими устройствами и службами Office 365.</span><span class="sxs-lookup"><span data-stu-id="0f2d1-105">You can increase performance by fine tuning the way that the Transmission Control Protocol (TCP) works between client devices and Office 365 services.</span></span>

<span data-ttu-id="0f2d1-106">Чтобы оптимизировать производительность протокола TCP, можно изменить указанные ниже параметры этого протокола на клиентских устройствах.</span><span class="sxs-lookup"><span data-stu-id="0f2d1-106">For client devices, you can change the following TCP settings on client devices to optimize TCP performance:</span></span>

- <span data-ttu-id="0f2d1-107">[Масштабирование окна TCP](https://blogs.technet.microsoft.com/onthewire/2014/03/28/ensuring-your-office-365-network-connection-isnt-throttled-by-your-proxy/). Настройте этот параметр, чтобы ваше клиентское устройство отправляло больше данных, прежде чем потребуется подтверждение устройства.</span><span class="sxs-lookup"><span data-stu-id="0f2d1-107">[TCP window scaling](https://blogs.technet.microsoft.com/onthewire/2014/03/28/ensuring-your-office-365-network-connection-isnt-throttled-by-your-proxy/), so your client device can send more data before requiring an acknowledgement</span></span>
- <span data-ttu-id="0f2d1-108">[Время простоя TCP](https://blogs.technet.microsoft.com/onthewire/2014/03/04/network-perimeters-tcp-idle-session-settings-for-outlook-on-office-365/). Настройте этот параметр, чтобы ваше клиентское устройство могло более эффективно обрабатывать открытые подключения.</span><span class="sxs-lookup"><span data-stu-id="0f2d1-108">[TCP idle time](https://blogs.technet.microsoft.com/onthewire/2014/03/04/network-perimeters-tcp-idle-session-settings-for-outlook-on-office-365/), so your client device can handle open connections more efficiently</span></span>
- <span data-ttu-id="0f2d1-109">[Максимальный размер сегмента TCP](https://blogs.technet.microsoft.com/onthewire/2014/06/27/checking-your-tcp-packets-are-pulling-their-weight-tcp-max-segment-size-or-mss/). Настройте этот параметр, чтобы ваше клиентское устройство могло отправлять самые большие блоки данных в пакете.</span><span class="sxs-lookup"><span data-stu-id="0f2d1-109">[TCP maximum segment size](https://blogs.technet.microsoft.com/onthewire/2014/06/27/checking-your-tcp-packets-are-pulling-their-weight-tcp-max-segment-size-or-mss/), so your client device can send the largest blocks of data in a packet</span></span>
- <span data-ttu-id="0f2d1-110">[Выборочные подтверждения TCP](https://blogs.technet.microsoft.com/onthewire/2014/06/27/ensuring-your-tcp-stack-isnt-throwing-data-away/). Настройте этот параметр, чтобы ваше клиентское устройство могло более эффективно подтверждать принятые данные.</span><span class="sxs-lookup"><span data-stu-id="0f2d1-110">[TCP selective acknowledgements](https://blogs.technet.microsoft.com/onthewire/2014/06/27/ensuring-your-tcp-stack-isnt-throwing-data-away/), so your client device can acknowledge received data more efficiently</span></span>

<span data-ttu-id="0f2d1-111">Сведения об оптимизации производительности служб Office 365 см. в указанных ниже дополнительных ресурсах.</span><span class="sxs-lookup"><span data-stu-id="0f2d1-111">For Office 365 services, see these additional resources to optimize performance:</span></span>

- [<span data-ttu-id="0f2d1-112">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="0f2d1-112">Exchange Online</span></span>](https://support.office.com/article/Tune-Exchange-Online-performance-026e83cb-a945-4543-97b0-a8af6e80ac61)
- [<span data-ttu-id="0f2d1-113">Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="0f2d1-113">Skype for Business Online</span></span>](https://support.office.com/article/Tune-Skype-for-Business-Online-performance-beec23c2-c5d6-4e84-a8af-e82aefca7802)
- [<span data-ttu-id="0f2d1-114">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="0f2d1-114">SharePoint Online</span></span>](https://support.office.com/article/Tune-SharePoint-Online-performance-f0522d4a-fbf4-41f9-854e-c9b59555091d)
- [<span data-ttu-id="0f2d1-115">Project Online</span><span class="sxs-lookup"><span data-stu-id="0f2d1-115">Project Online</span></span>](https://support.office.com/article/Tune-Project-Online-performance-12ba0ebd-c616-42e5-b9b6-cad570e8409c)

<span data-ttu-id="0f2d1-116">Прежде чем перейти к следующему шагу, проверьте [условия](networking-exit-criteria.md#crit-networking-step5), при выполнении которых можно считать данный шаг завершенным.</span><span class="sxs-lookup"><span data-stu-id="0f2d1-116">As an interim checkpoint, you can see the [exit criteria](networking-exit-criteria.md#crit-networking-step5) for this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="0f2d1-117">Следующий шаг</span><span class="sxs-lookup"><span data-stu-id="0f2d1-117">Next step</span></span>

[<span data-ttu-id="0f2d1-118">Условия, при выполнении которых можно считать сетевую инфраструктуру настроенной</span><span class="sxs-lookup"><span data-stu-id="0f2d1-118">Networking infrastructure exit criteria</span></span>](networking-exit-criteria.md)
