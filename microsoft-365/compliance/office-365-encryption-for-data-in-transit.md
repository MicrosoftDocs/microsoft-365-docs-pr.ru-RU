---
title: Шифрование в Office 365 для пересылки данных
ms.author: krowley
author: kccross
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
search.appverid:
- MET150
ms.collection:
- Strat_O365_Enterprise
- M365-security-compliance
- Strat_O365_Enterprise
description: Сводка. краткое объяснение того, как корпорация Майкрософт шифрует данные при передаче.
ms.openlocfilehash: ba1317a0a2a685d0f3ac2216939d04e402503e49
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/20/2019
ms.locfileid: "37091070"
---
# <a name="office-365-encryption-for-data-in-transit"></a><span data-ttu-id="998cb-103">Шифрование в Office 365 для пересылки данных</span><span class="sxs-lookup"><span data-stu-id="998cb-103">Office 365 encryption for data in transit</span></span>

<span data-ttu-id="998cb-104">Помимо защиты данных клиентов, корпорация Майкрософт использует технологии шифрования для защиты данных клиентов Office 365 в транзитном офисе.</span><span class="sxs-lookup"><span data-stu-id="998cb-104">In addition to protecting customer data at rest, Microsoft uses encryption technologies to protect Office 365 customer data in transit.</span></span> 

<span data-ttu-id="998cb-105">Данные находятся в пути:</span><span class="sxs-lookup"><span data-stu-id="998cb-105">Data is in transit:</span></span>

- <span data-ttu-id="998cb-106">Когда клиентский компьютер обменивается данными с сервером Office 365;</span><span class="sxs-lookup"><span data-stu-id="998cb-106">when a client machine communicates with an Office 365 server;</span></span>
- <span data-ttu-id="998cb-107">Когда сервер Office 365 обменивается данными с другим сервером Office 365; с</span><span class="sxs-lookup"><span data-stu-id="998cb-107">when an Office 365 server communicates with another Office 365 server; and</span></span>
- <span data-ttu-id="998cb-108">Когда сервер Office 365 обменивается данными с сервером, отличным от Office 365 (например, Exchange Online доставляет электронную почту на инородный сервер электронной почты).</span><span class="sxs-lookup"><span data-stu-id="998cb-108">when an Office 365 server communicates with a non-Office 365 server (e.g., Exchange Online delivering email to a foreign email server).</span></span>

<span data-ttu-id="998cb-109">Обмен данными между центрами обработки данных между серверами Office 365 выполняется по протоколу TLS или IPsec, а все серверы, подключенные к клиентам, согласовывают безопасный сеанс с помощью протокола TLS с клиентскими компьютерами (например, Exchange Online использует TLS 1,2 с 256-разрядным шифром (FIPS). 140-2 — проверенный уровень 2).</span><span class="sxs-lookup"><span data-stu-id="998cb-109">Inter-datacenter communications between Office 365 servers takes place over TLS or IPsec, and all customer-facing servers negotiate a secure session using TLS with client machines (e.g., Exchange Online uses TLS 1.2 with 256-bit cipher strength is used (FIPS 140-2 Level 2-validated).</span></span> <span data-ttu-id="998cb-110">(Просмотрите [технические справочные сведения о шифровании в office 365](https://support.office.com/article/Technical-reference-details-about-encryption-in-Office-365-862CBE93-4268-4EF9-BA79-277545ECF221) , чтобы получить список комплектов шифров TLS, поддерживаемых в Office 365.) Это относится к протоколам, используемым клиентами, таким как Outlook, Skype для бизнеса и Outlook в Интернете (например, HTTP, POP3 и т. д.).</span><span class="sxs-lookup"><span data-stu-id="998cb-110">(See [Technical reference details about encryption in Office 365](https://support.office.com/article/Technical-reference-details-about-encryption-in-Office-365-862CBE93-4268-4EF9-BA79-277545ECF221) for a list of TLS cipher suites supported by Office 365.) This applies to the protocols that are used by clients such as Outlook, Skype for Business, and Outlook on the web (e.g., HTTP, POP3, etc.).</span></span>

<span data-ttu-id="998cb-111">Общедоступные сертификаты выдаются по протоколу Microsoft IT SSL с помощью Ссладмин, внутреннего средства Майкрософт для защиты конфиденциальности передаваемых данных.</span><span class="sxs-lookup"><span data-stu-id="998cb-111">The public certificates are issued by Microsoft IT SSL using SSLAdmin, an internal Microsoft tool to protect confidentiality of transmitted information.</span></span> <span data-ttu-id="998cb-112">Все сертификаты, выданные корпорацией Майкрософт, имеют значение не менее 2048 бит, а для обеспечения соответствия требованиям [вебтруст](http://www.webtrust.org/homepage-documents/item70372.pdf) требуется ссладмин, чтобы сертификаты выдавались только общедоступным IP-адресам, принадлежащим корпорации Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="998cb-112">All certificates issued by Microsoft IT have a minimum of 2048 bits in length, and [Webtrust](http://www.webtrust.org/homepage-documents/item70372.pdf) compliance requires SSLAdmin to make sure that certificates are issued only to public IP addresses owned by Microsoft.</span></span> <span data-ttu-id="998cb-113">Все IP-адреса, которые не удовлетворяют этому критерию, направляются через процесс исключения.</span><span class="sxs-lookup"><span data-stu-id="998cb-113">Any IP addresses that fail to meet this criterion are routed through an exception process.</span></span>

<span data-ttu-id="998cb-114">Все детали реализации, такие как используемая версия протокола TLS, включена ли функция пересылки безопасной (Федерации), порядок комплектов шифров и т. д. доступно в открытых источниках.</span><span class="sxs-lookup"><span data-stu-id="998cb-114">All implementation details such as the version of TLS being used, whether Forward Secrecy (FS) is enabled, the order of cipher suites, etc., are available publicly.</span></span> <span data-ttu-id="998cb-115">Один из способов просмотреть эти сведения — использовать сторонний веб-сайт, такой как Куалис SSL (www.ssllabs.com).</span><span class="sxs-lookup"><span data-stu-id="998cb-115">One way to see these details is to use a third-party website, such as Qualys SSL Labs (www.ssllabs.com).</span></span> <span data-ttu-id="998cb-116">Ниже приведены ссылки на страницы автоматизированного теста из Куалис, отображающие сведения о следующих службах:</span><span class="sxs-lookup"><span data-stu-id="998cb-116">Below are the links to automated test pages from Qualys that display information for the following services:</span></span>

- [<span data-ttu-id="998cb-117">Портал Office 365</span><span class="sxs-lookup"><span data-stu-id="998cb-117">Office 365 Portal</span></span>](https://www.ssllabs.com/ssltest/analyze.html?d=portal.office.com&hideResults=on)
- [<span data-ttu-id="998cb-118">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="998cb-118">Exchange Online</span></span>](https://www.ssllabs.com/ssltest/analyze.html?d=outlook.office365.com&hideResults=on)
- [<span data-ttu-id="998cb-119">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="998cb-119">SharePoint Online</span></span>](https://www.ssllabs.com/ssltest/analyze.html?d=microsoft-my.sharepoint.com&hideResults=on)
- [<span data-ttu-id="998cb-120">Skype для бизнеса (SIP)</span><span class="sxs-lookup"><span data-stu-id="998cb-120">Skype for Business (SIP)</span></span>](https://www.ssllabs.com/ssltest/analyze.html?d=sipdir.online.lync.com)
- [<span data-ttu-id="998cb-121">Skype для бизнеса (Интернет)</span><span class="sxs-lookup"><span data-stu-id="998cb-121">Skype for Business (Web)</span></span>](https://www.ssllabs.com/ssltest/analyze.html?d=webdir.online.lync.com&hideResults=on)
- [<span data-ttu-id="998cb-122">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="998cb-122">Exchange Online Protection</span></span>](https://ssl-tools.net/mailservers/microsoft-com.mail.protection.outlook.com)
- [<span data-ttu-id="998cb-123">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="998cb-123">Microsoft Teams</span></span>](https://www.ssllabs.com/ssltest/analyze.html?d=teams.microsoft.com&latest)

<span data-ttu-id="998cb-124">Для Exchange Online Protection URL-адреса различаются в зависимости от имен клиентов; Тем не менее, все клиенты могут тестировать Office 365 с помощью **Microsoft-COM.mail.Protection.Outlook.com**.</span><span class="sxs-lookup"><span data-stu-id="998cb-124">For Exchange Online Protection, URLs vary by tenant names; however, all customers can test Office 365 using **microsoft-com.mail.protection.outlook.com**.</span></span>
