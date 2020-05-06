---
title: Шифрование данных при передаче
f1.keywords:
- NOCSH
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
description: В этой статье приводится краткое описание того, как корпорация Майкрософт шифрует данные клиентов корпорации Майкрософт 365 в транзитном месте.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 7ee869308549398a9df00ed42975b4aeedb666a4
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/05/2020
ms.locfileid: "44033607"
---
# <a name="encryption-for-data-in-transit"></a><span data-ttu-id="8ac04-103">Шифрование данных при передаче</span><span class="sxs-lookup"><span data-stu-id="8ac04-103">Encryption for data in transit</span></span>

<span data-ttu-id="8ac04-104">Помимо защиты данных клиентов, корпорация Майкрософт использует технологии шифрования для защиты данных клиентов при их транзитном переносе.</span><span class="sxs-lookup"><span data-stu-id="8ac04-104">In addition to protecting customer data at rest, Microsoft uses encryption technologies to protect customer data in transit.</span></span> 

<span data-ttu-id="8ac04-105">Данные находятся в пути:</span><span class="sxs-lookup"><span data-stu-id="8ac04-105">Data is in transit:</span></span>

- <span data-ttu-id="8ac04-106">Когда клиентский компьютер обменивается данными с сервером Microsoft;</span><span class="sxs-lookup"><span data-stu-id="8ac04-106">when a client machine communicates with a Microsoft server;</span></span>
- <span data-ttu-id="8ac04-107">при взаимодействии Microsoft Server с другим сервером корпорации Майкрософт; с</span><span class="sxs-lookup"><span data-stu-id="8ac04-107">when a Microsoft server communicates with another Microsoft server; and</span></span>
- <span data-ttu-id="8ac04-108">Когда сервер Microsoft Exchange обменивается данными с сервером, отличным от Microsoft (например, Exchange Online доставляет электронную почту на сторонний сервер электронной почты).</span><span class="sxs-lookup"><span data-stu-id="8ac04-108">when a Microsoft server communicates with a non-Microsoft server (e.g., Exchange Online delivering email to a third-party email server).</span></span>

<span data-ttu-id="8ac04-109">Обмен данными между центрами обработки данных между серверами Microsoft выполняется по протоколу TLS или IPsec, а все серверы, подключенные к клиентам, согласовывают безопасный сеанс с помощью протокола TLS с клиентскими компьютерами (например, Exchange Online использует протокол TLS 1,2 с 256-разрядным шифром (проверка подлинности FIPS 140-2 уровня 2).</span><span class="sxs-lookup"><span data-stu-id="8ac04-109">Inter-data center communications between Microsoft servers takes place over TLS or IPsec, and all customer-facing servers negotiate a secure session using TLS with client machines (e.g., Exchange Online uses TLS 1.2 with 256-bit cipher strength is used (FIPS 140-2 Level 2-validated).</span></span> <span data-ttu-id="8ac04-110">(См. [технические сведения о шифровании](technical-reference-details-about-encryption.md) список комплектов шифров TLS, поддерживаемых Office 365.) Это относится к протоколам, используемым клиентами, таким как Outlook, Skype для бизнеса, Microsoft Teams и Outlook в Интернете (например, HTTP, POP3 и т. д.).</span><span class="sxs-lookup"><span data-stu-id="8ac04-110">(See [Technical reference details about encryption](technical-reference-details-about-encryption.md) for a list of TLS cipher suites supported by Office 365.) This applies to the protocols that are used by clients such as Outlook, Skype for Business, Microsoft Teams, and Outlook on the web (e.g., HTTP, POP3, etc.).</span></span>

<span data-ttu-id="8ac04-111">Общедоступные сертификаты выдаются по протоколу Microsoft IT SSL с помощью Ссладмин, внутреннего средства Майкрософт для защиты конфиденциальности передаваемых данных.</span><span class="sxs-lookup"><span data-stu-id="8ac04-111">The public certificates are issued by Microsoft IT SSL using SSLAdmin, an internal Microsoft tool to protect confidentiality of transmitted information.</span></span> <span data-ttu-id="8ac04-112">Все сертификаты, выданные корпорацией Майкрософт, имеют значение не менее 2048 бит, а для обеспечения соответствия требованиям Вебтруст требуется Ссладмин, чтобы сертификаты выдавались только общедоступным IP-адресам, принадлежащим корпорации Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="8ac04-112">All certificates issued by Microsoft IT have a minimum of 2048 bits in length, and Webtrust compliance requires SSLAdmin to make sure that certificates are issued only to public IP addresses owned by Microsoft.</span></span> <span data-ttu-id="8ac04-113">Все IP-адреса, которые не удовлетворяют этому критерию, направляются через процесс исключения.</span><span class="sxs-lookup"><span data-stu-id="8ac04-113">Any IP addresses that fail to meet this criterion are routed through an exception process.</span></span>

<span data-ttu-id="8ac04-114">Все детали реализации, такие как используемая версия протокола TLS, включена ли функция пересылки безопасной (Федерации), порядок комплектов шифров и т. д. доступно в открытых источниках.</span><span class="sxs-lookup"><span data-stu-id="8ac04-114">All implementation details such as the version of TLS being used, whether Forward Secrecy (FS) is enabled, the order of cipher suites, etc., are available publicly.</span></span> <span data-ttu-id="8ac04-115">Одним из способов просмотра этих сведений является использование стороннего веб-сайта, например [куалис](https://www.ssllabs.com).</span><span class="sxs-lookup"><span data-stu-id="8ac04-115">One way to see these details is to use a third-party website, such as [Qualys SSL Labs](https://www.ssllabs.com).</span></span> <span data-ttu-id="8ac04-116">Ниже приведены ссылки на страницы автоматизированного теста из Куалис, отображающие сведения о следующих службах:</span><span class="sxs-lookup"><span data-stu-id="8ac04-116">Below are the links to automated test pages from Qualys that display information for the following services:</span></span>

- [<span data-ttu-id="8ac04-117">Портал Office 365</span><span class="sxs-lookup"><span data-stu-id="8ac04-117">Office 365 Portal</span></span>](https://www.ssllabs.com/ssltest/analyze.html?d=portal.office.com&hideResults=on)
- [<span data-ttu-id="8ac04-118">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="8ac04-118">Exchange Online</span></span>](https://www.ssllabs.com/ssltest/analyze.html?d=outlook.office365.com&hideResults=on)
- [<span data-ttu-id="8ac04-119">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="8ac04-119">SharePoint Online</span></span>](https://www.ssllabs.com/ssltest/analyze.html?d=microsoft-my.sharepoint.com&hideResults=on)
- [<span data-ttu-id="8ac04-120">Skype для бизнеса (SIP)</span><span class="sxs-lookup"><span data-stu-id="8ac04-120">Skype for Business (SIP)</span></span>](https://www.ssllabs.com/ssltest/analyze.html?d=sipdir.online.lync.com)
- [<span data-ttu-id="8ac04-121">Skype для бизнеса (Интернет)</span><span class="sxs-lookup"><span data-stu-id="8ac04-121">Skype for Business (Web)</span></span>](https://www.ssllabs.com/ssltest/analyze.html?d=webdir.online.lync.com&hideResults=on)
- [<span data-ttu-id="8ac04-122">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="8ac04-122">Exchange Online Protection</span></span>](https://ssl-tools.net/mailservers/microsoft-com.mail.protection.outlook.com)
- [<span data-ttu-id="8ac04-123">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="8ac04-123">Microsoft Teams</span></span>](https://www.ssllabs.com/ssltest/analyze.html?d=teams.microsoft.com&latest)

<span data-ttu-id="8ac04-124">Для Exchange Online Protection URL-адреса различаются в зависимости от имен клиентов; Тем не менее, все клиенты могут тестировать Microsoft 365 с помощью **Microsoft-COM.mail.Protection.Outlook.com**.</span><span class="sxs-lookup"><span data-stu-id="8ac04-124">For Exchange Online Protection, URLs vary by tenant names; however, all customers can test Microsoft 365 using **microsoft-com.mail.protection.outlook.com**.</span></span>
