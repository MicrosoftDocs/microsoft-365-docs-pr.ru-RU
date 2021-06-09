---
title: Поддержка NAT в Office 365
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 1/24/2017
audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- MET150
- BCS160
ms.assetid: 170e96ea-d65d-4e51-acac-1de56abe39b9
description: В этой статье подробно рассказывается о том, как приблизить число клиентов, которые можно использовать по IP-адресу в организации с помощью NAT.
ms.openlocfilehash: f48874853c3acb80927933761862b14379b6d4bd
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/14/2020
ms.locfileid: "46692952"
---
# <a name="nat-support-with-office-365"></a><span data-ttu-id="9df9f-103">Поддержка NAT в Office 365</span><span class="sxs-lookup"><span data-stu-id="9df9f-103">NAT support with Office 365</span></span>

<span data-ttu-id="9df9f-104">*Эта статья относится к Microsoft 365 корпоративный и Office 365 корпоративный.*</span><span class="sxs-lookup"><span data-stu-id="9df9f-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="9df9f-105">Ранее в руководстве предлагалось, что максимальное число клиентов, Exchange для подключения к Office 365, составляет около 2000 клиентов на один сетевой порт.</span><span class="sxs-lookup"><span data-stu-id="9df9f-105">Previously, guidance suggested that the maximum number of Exchange clients you should use per IP address to connect to Office 365 was about 2,000 clients per network port.</span></span>
  
## <a name="why-use-nat"></a><span data-ttu-id="9df9f-106">Зачем использовать NAT?</span><span class="sxs-lookup"><span data-stu-id="9df9f-106">Why use NAT?</span></span>

<span data-ttu-id="9df9f-107">С помощью NAT тысячи пользователей корпоративной сети могут "поделиться" несколькими общедоступными IP-адресами, которые можно использовать для маршрутивки.</span><span class="sxs-lookup"><span data-stu-id="9df9f-107">By using NAT, thousands of people on a corporate network can "share" a few publicly routable IP addresses.</span></span>
  
<span data-ttu-id="9df9f-108">В большинстве корпоративных сетей используется частное (RFC1918) пространство IP-адресов.</span><span class="sxs-lookup"><span data-stu-id="9df9f-108">Most corporate networks use private (RFC1918) IP address space.</span></span> <span data-ttu-id="9df9f-109">Частное адресное пространство выделяется Управлением номеров в Интернете (IANA) и предназначено исключительно для сетей, которые не маршрутит напрямую в глобальный Интернет и из него.</span><span class="sxs-lookup"><span data-stu-id="9df9f-109">Private address space is allocated by the Internet Assigned Numbers Authority (IANA) and intended solely for networks that do not route directly to and from the global Internet.</span></span>
  
<span data-ttu-id="9df9f-110">Чтобы обеспечить доступ в Интернет к устройствам в частном пространстве IP-адресов, организации используют шлюзовые технологии, такие как брандмауэры и прокси,которые предоставляют службы перевода сетевых адресов (NAT) или портового перевода адресов (PAT).</span><span class="sxs-lookup"><span data-stu-id="9df9f-110">To provide Internet access to devices on a private IP address space, organizations use gateway technologies like firewalls and proxies that provide network address translation (NAT) or port address translation (PAT) services.</span></span> <span data-ttu-id="9df9f-111">Эти шлюзы делают трафик с внутренних устройств в Интернет (в том числе Office 365) как представляется, исходя из одного или более общедоступных IP-адресов.</span><span class="sxs-lookup"><span data-stu-id="9df9f-111">These gateways make traffic from internal devices to the Internet (including Office 365) appear to be coming from one or more publicly routable IP addresses.</span></span> <span data-ttu-id="9df9f-112">Каждое исходящие подключения с внутреннего устройства переводится в другой исходный порт TCP на общедоступный IP-адрес.</span><span class="sxs-lookup"><span data-stu-id="9df9f-112">Each outbound connection from an internal device translates to a different source TCP port on the public IP address.</span></span> 
  
## <a name="why-do-you-need-to-have-so-many-connections-open-to-office-365-at-the-same-time"></a><span data-ttu-id="9df9f-113">Почему необходимо одновременно открыть для Office 365 так много подключений?</span><span class="sxs-lookup"><span data-stu-id="9df9f-113">Why do you need to have so many connections open to Office 365 at the same time?</span></span>

<span data-ttu-id="9df9f-114">Outlook могут открывать восемь или более подключений (в ситуациях, когда есть надстройки, общие календари, почтовые ящики и т.д.).</span><span class="sxs-lookup"><span data-stu-id="9df9f-114">Outlook may open eight or more connections (in situations where there are add-ins, shared calendars, mailboxes, etc.).</span></span> <span data-ttu-id="9df9f-115">Так как на устройстве NAT на Windows на основе Windows доступно не более 64 000 портов, перед истощением портов за IP-адресом может быть не более 8000 пользователей.</span><span class="sxs-lookup"><span data-stu-id="9df9f-115">Because there are a maximum of 64,000 ports available on a Windows-based NAT device, there can be a maximum of 8,000 users behind an IP address before the ports are exhausted.</span></span> <span data-ttu-id="9df9f-116">Обратите внимание, что если клиенты используют Windows устройства на основе ОС для NAT, общие доступные порты зависят от того, какое устройство или программное обеспечение NAT используется.</span><span class="sxs-lookup"><span data-stu-id="9df9f-116">Note that if customers are using non-Windows OS-based devices for NAT, the total available ports are dependent on what NAT device or software is being used.</span></span> <span data-ttu-id="9df9f-117">В этом сценарии максимальное число портов может быть меньше 64 000.</span><span class="sxs-lookup"><span data-stu-id="9df9f-117">In this scenario, the maximum number of ports could be less than 64,000.</span></span> <span data-ttu-id="9df9f-118">На доступность портов влияют и другие факторы Windows например ограничение 4000 портов для собственного использования, что сокращает общее число доступных портов до 60 000.</span><span class="sxs-lookup"><span data-stu-id="9df9f-118">Availability of ports is also affected by other factors such as Windows restricting 4,000 ports for its own use, which reduces the total number of available ports to 60,000.</span></span> <span data-ttu-id="9df9f-119">Могут быть и другие приложения, например Internet Explorer, которые могут подключаться одновременно, требуя дополнительных портов.</span><span class="sxs-lookup"><span data-stu-id="9df9f-119">There may be other applications, such as Internet Explorer, that could connect at the same time, requiring additional ports.</span></span>
  
## <a name="calculating-maximum-supported-devices-behind-a-single-public-ip-address-with-office-365"></a><span data-ttu-id="9df9f-120">Вычисление устройств с максимальной поддержкой за одним общедоступным IP-адресом с Office 365</span><span class="sxs-lookup"><span data-stu-id="9df9f-120">Calculating maximum supported devices behind a single public IP address with Office 365</span></span>

<span data-ttu-id="9df9f-121">Чтобы определить максимальное число устройств за одним общедоступным IP-адресом, необходимо отслеживать сетевой трафик, чтобы определить максимальное потребление порта на каждого клиента.</span><span class="sxs-lookup"><span data-stu-id="9df9f-121">To determine the maximum number of devices behind a single public IP address, you should monitor network traffic to determine peak port consumption per client.</span></span> <span data-ttu-id="9df9f-122">Кроме того, для использования порта следует использовать пиковый фактор (минимум 4).</span><span class="sxs-lookup"><span data-stu-id="9df9f-122">Also, a peak factor should be used for the port usage (minimum 4).</span></span> 
  
 <span data-ttu-id="9df9f-123">**Чтобы рассчитать количество поддерживаемых устройств на IP-адрес, используйте следующую формулу:**</span><span class="sxs-lookup"><span data-stu-id="9df9f-123">**Use the following formula to calculate the number of supported devices per IP address:**</span></span>
  
<span data-ttu-id="9df9f-124">Максимально поддерживаемые устройства за одним общедоступным IP-адресом = (64 000 — ограниченные порты)/(Пиковое потребление порта + пиковый коэффициент)</span><span class="sxs-lookup"><span data-stu-id="9df9f-124">Maximum supported devices behind a single public IP address = (64,000 - restricted ports)/(Peak port consumption + peak factor)</span></span>
  
 <span data-ttu-id="9df9f-125">**Например, если это так:**</span><span class="sxs-lookup"><span data-stu-id="9df9f-125">**For example, if the following were true:**</span></span>
  
- <span data-ttu-id="9df9f-126">**Ограниченные порты:** 4 000 для операционной системы</span><span class="sxs-lookup"><span data-stu-id="9df9f-126">**Restricted ports:** 4,000 for the operating system</span></span>

- <span data-ttu-id="9df9f-127">**Пиковое потребление порта:** 6 на устройство</span><span class="sxs-lookup"><span data-stu-id="9df9f-127">**Peak port consumption:** 6 per device</span></span>

- <span data-ttu-id="9df9f-128">**Пиковый коэффициент:** 4</span><span class="sxs-lookup"><span data-stu-id="9df9f-128">**Peak factor:** 4</span></span>

<span data-ttu-id="9df9f-129">Затем максимально поддерживаемые устройства за одним общедоступным IP-адресом = (64 000 — 4 000)/(6 + 4) = 6 000</span><span class="sxs-lookup"><span data-stu-id="9df9f-129">Then, the maximum supported devices behind a single public IP address = (64,000 - 4,000)/(6 + 4) = 6,000</span></span>
  
<span data-ttu-id="9df9f-130">С выпуском пакета Office 365 хостинга, включенного в обновления с сентября 2011 г. для Microsoft Office Outlook 2007 г. или ноября 2011 г. для Microsoft Outlook 2010, русская версия или более позднего обновления, количество подключений от Outlook (оба Office Outlook 2007 г. с Пакет обновления 2 и Outlook 2010 г.) до Exchange могут быть как 2.</span><span class="sxs-lookup"><span data-stu-id="9df9f-130">With the release of Office 365 hosting pack, included in the updates from September 2011 for Microsoft Office Outlook 2007, or November 2011 for Microsoft Outlook 2010, or a later update, the number of connections from Outlook (both Office Outlook 2007 with Service Pack 2 and Outlook 2010) to Exchange can be as few as 2.</span></span> <span data-ttu-id="9df9f-131">Необходимо учитывать различные операционные системы, поведение пользователей и т. д., чтобы определить минимальное и максимальное число портов, которые потребуются вашей сети на пике.</span><span class="sxs-lookup"><span data-stu-id="9df9f-131">You'll need to factor in the different operating systems, user behaviors, and so on to determine the minimum and maximum number of ports that your network will require at peak.</span></span>
  
<span data-ttu-id="9df9f-132">Если вы хотите поддерживать больше устройств за одним общедоступным IP-адресом, выполните действия, описанные для оценки максимального числа поддерживаемых устройств:</span><span class="sxs-lookup"><span data-stu-id="9df9f-132">If you want to support more devices behind a single public IP address, follow the steps outlined to assess the maximum number of devices that can be supported:</span></span>
  
<span data-ttu-id="9df9f-133">Мониторинг сетевого трафика для определения пикового потребления порта на каждого клиента.</span><span class="sxs-lookup"><span data-stu-id="9df9f-133">Monitor network traffic to determine peak port consumption per client.</span></span> <span data-ttu-id="9df9f-134">Необходимо собрать эти данные:</span><span class="sxs-lookup"><span data-stu-id="9df9f-134">You should collect this data:</span></span>
  
- <span data-ttu-id="9df9f-135">Из нескольких местоположений</span><span class="sxs-lookup"><span data-stu-id="9df9f-135">From multiple locations</span></span>
    
- <span data-ttu-id="9df9f-136">С нескольких устройств</span><span class="sxs-lookup"><span data-stu-id="9df9f-136">From multiple devices</span></span>
    
- <span data-ttu-id="9df9f-137">Несколько раз</span><span class="sxs-lookup"><span data-stu-id="9df9f-137">At multiple times</span></span>
    
<span data-ttu-id="9df9f-138">С помощью предыдущей формулы можно рассчитать максимальное количество пользователей на IP-адрес, которые могут поддерживаться в их среде.</span><span class="sxs-lookup"><span data-stu-id="9df9f-138">Use the preceding formula to calculate the maximum users per IP address that can be supported in their environment.</span></span>
  
<span data-ttu-id="9df9f-139">Существуют различные методы распределения клиентской нагрузки по дополнительным общедоступным IP-адресам.</span><span class="sxs-lookup"><span data-stu-id="9df9f-139">There are various methods for distributing client load across additional public IP addresses.</span></span> <span data-ttu-id="9df9f-140">Доступные стратегии зависят от возможностей решения корпоративных шлюзов.</span><span class="sxs-lookup"><span data-stu-id="9df9f-140">Strategies available depend on the capabilities of the corporate gateway solution.</span></span> <span data-ttu-id="9df9f-141">Простейшее решение — сегментировать пространство адресов пользователей и статически "назначать" ряд IP-адресов для каждого шлюза.</span><span class="sxs-lookup"><span data-stu-id="9df9f-141">The simplest solution is to segment your user address space and statically "assign" a number of IP addresses to each gateway.</span></span> <span data-ttu-id="9df9f-142">Другой альтернативой, которую предлагают многие устройства шлюза, является возможность использования пула IP-адресов.</span><span class="sxs-lookup"><span data-stu-id="9df9f-142">Another alternative that many gateway devices offer is the ability to use a pool of IP addresses.</span></span> <span data-ttu-id="9df9f-143">Преимущество пула адресов в том, что он гораздо динамичнее и с меньшей вероятностью требует корректировки по мере роста пользовательской базы.</span><span class="sxs-lookup"><span data-stu-id="9df9f-143">The benefit of the address pool is that it is much more dynamic and less likely to require adjustment as your user base grows.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="9df9f-144">См. также</span><span class="sxs-lookup"><span data-stu-id="9df9f-144">See also</span></span>

[<span data-ttu-id="9df9f-145">Управление конечными точками Office 365</span><span class="sxs-lookup"><span data-stu-id="9df9f-145">Managing Office 365 endpoints</span></span>](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a)
  
[<span data-ttu-id="9df9f-146">Вопросы и ответы о конечных точках Office 365</span><span class="sxs-lookup"><span data-stu-id="9df9f-146">Office 365 endpoints FAQ</span></span>](https://support.office.com/article/d4088321-1c89-4b96-9c99-54c75cae2e6d)
