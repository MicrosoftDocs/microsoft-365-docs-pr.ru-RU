---
title: Поддержка NAT в Office 365
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
description: В этой статье представлены сведения о том, как оценить количество клиентов, которые можно использовать для каждого IP-адреса в Организации с помощью NAT.
ms.openlocfilehash: f48874853c3acb80927933761862b14379b6d4bd
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/14/2020
ms.locfileid: "46692952"
---
# <a name="nat-support-with-office-365"></a><span data-ttu-id="f9c27-103">Поддержка NAT в Office 365</span><span class="sxs-lookup"><span data-stu-id="f9c27-103">NAT support with Office 365</span></span>

<span data-ttu-id="f9c27-104">*Эта статья относится к Microsoft 365 корпоративный и Office 365 корпоративный.*</span><span class="sxs-lookup"><span data-stu-id="f9c27-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="f9c27-105">Ранее в руководстве было предложено, что максимальное число клиентов Exchange, которые необходимо использовать для подключения к Office 365, составило около 2 000 клиентов на сетевой порт.</span><span class="sxs-lookup"><span data-stu-id="f9c27-105">Previously, guidance suggested that the maximum number of Exchange clients you should use per IP address to connect to Office 365 was about 2,000 clients per network port.</span></span>
  
## <a name="why-use-nat"></a><span data-ttu-id="f9c27-106">Зачем использовать NAT?</span><span class="sxs-lookup"><span data-stu-id="f9c27-106">Why use NAT?</span></span>

<span data-ttu-id="f9c27-107">С помощью NAT тысячи людей в корпоративной сети могут "поделиться" несколькими IP-адресами с общедоступной маршрутизацией.</span><span class="sxs-lookup"><span data-stu-id="f9c27-107">By using NAT, thousands of people on a corporate network can "share" a few publicly routable IP addresses.</span></span>
  
<span data-ttu-id="f9c27-108">Большинство корпоративных сетей используют личное (RFC1918) пространство IP-адресов.</span><span class="sxs-lookup"><span data-stu-id="f9c27-108">Most corporate networks use private (RFC1918) IP address space.</span></span> <span data-ttu-id="f9c27-109">Частное адресное пространство выделяется программой IANA (Internet Assigned Numbers Authority) и предназначено исключительно для сетей, которые не направляются напрямую в Глобальный Интернет.</span><span class="sxs-lookup"><span data-stu-id="f9c27-109">Private address space is allocated by the Internet Assigned Numbers Authority (IANA) and intended solely for networks that do not route directly to and from the global Internet.</span></span>
  
<span data-ttu-id="f9c27-110">Чтобы предоставить доступ к устройствам через Интернет к устройствам в частном IP-адресном пространстве, в организациях используются такие технологии, как брандмауэры и прокси-серверы, обеспечивающие трансляцию сетевых адресов (NAT) или службы преобразования адресов портов (PAT).</span><span class="sxs-lookup"><span data-stu-id="f9c27-110">To provide Internet access to devices on a private IP address space, organizations use gateway technologies like firewalls and proxies that provide network address translation (NAT) or port address translation (PAT) services.</span></span> <span data-ttu-id="f9c27-111">Эти шлюзы делают трафик с внутренних устройств в Интернет (в том числе Office 365) поступают из одного или нескольких IP-адресов с общедоступной маршрутизацией.</span><span class="sxs-lookup"><span data-stu-id="f9c27-111">These gateways make traffic from internal devices to the Internet (including Office 365) appear to be coming from one or more publicly routable IP addresses.</span></span> <span data-ttu-id="f9c27-112">Каждое исходящее подключение с внутреннего устройства переводится на другой TCP-порт источника на общедоступном IP-адресе.</span><span class="sxs-lookup"><span data-stu-id="f9c27-112">Each outbound connection from an internal device translates to a different source TCP port on the public IP address.</span></span> 
  
## <a name="why-do-you-need-to-have-so-many-connections-open-to-office-365-at-the-same-time"></a><span data-ttu-id="f9c27-113">Зачем необходимо, чтобы одновременно было открыто слишком много подключений к Office 365?</span><span class="sxs-lookup"><span data-stu-id="f9c27-113">Why do you need to have so many connections open to Office 365 at the same time?</span></span>

<span data-ttu-id="f9c27-114">Outlook может открыть восемь или более подключений (в ситуациях, когда имеются надстройки, общие календари, почтовые ящики и т. д.).</span><span class="sxs-lookup"><span data-stu-id="f9c27-114">Outlook may open eight or more connections (in situations where there are add-ins, shared calendars, mailboxes, etc.).</span></span> <span data-ttu-id="f9c27-115">Так как на устройстве NAT на основе Windows доступно до 64 000 портов, для них может быть не более 8 000 пользователей за IP-адресом до исчерпания портов.</span><span class="sxs-lookup"><span data-stu-id="f9c27-115">Because there are a maximum of 64,000 ports available on a Windows-based NAT device, there can be a maximum of 8,000 users behind an IP address before the ports are exhausted.</span></span> <span data-ttu-id="f9c27-116">Обратите внимание, что если клиенты используют устройства на основе не Windows OS для NAT, общее количество доступных портов зависит от того, какое устройство NAT или программное обеспечение используется.</span><span class="sxs-lookup"><span data-stu-id="f9c27-116">Note that if customers are using non-Windows OS-based devices for NAT, the total available ports are dependent on what NAT device or software is being used.</span></span> <span data-ttu-id="f9c27-117">В этом случае максимальное число портов может быть меньше 64 000.</span><span class="sxs-lookup"><span data-stu-id="f9c27-117">In this scenario, the maximum number of ports could be less than 64,000.</span></span> <span data-ttu-id="f9c27-118">На доступ к портам также влияют другие факторы, такие как ограничения на порты 4 000 для собственного использования, что позволяет сократить общее число доступных портов до 60 000.</span><span class="sxs-lookup"><span data-stu-id="f9c27-118">Availability of ports is also affected by other factors such as Windows restricting 4,000 ports for its own use, which reduces the total number of available ports to 60,000.</span></span> <span data-ttu-id="f9c27-119">Могут быть другие приложения, например Internet Explorer, которые могут подключаться одновременно, требуя дополнительных портов.</span><span class="sxs-lookup"><span data-stu-id="f9c27-119">There may be other applications, such as Internet Explorer, that could connect at the same time, requiring additional ports.</span></span>
  
## <a name="calculating-maximum-supported-devices-behind-a-single-public-ip-address-with-office-365"></a><span data-ttu-id="f9c27-120">Вычисление максимального числа поддерживаемых устройств под одним общедоступным IP-адресом в Office 365</span><span class="sxs-lookup"><span data-stu-id="f9c27-120">Calculating maximum supported devices behind a single public IP address with Office 365</span></span>

<span data-ttu-id="f9c27-121">Чтобы определить максимальное число устройств за один общедоступный IP-адрес, необходимо отслеживать сетевой трафик, чтобы определить пиковое потребление портов для каждого клиента.</span><span class="sxs-lookup"><span data-stu-id="f9c27-121">To determine the maximum number of devices behind a single public IP address, you should monitor network traffic to determine peak port consumption per client.</span></span> <span data-ttu-id="f9c27-122">Кроме того, для использования порта необходимо использовать пиковый фактор (минимум 4).</span><span class="sxs-lookup"><span data-stu-id="f9c27-122">Also, a peak factor should be used for the port usage (minimum 4).</span></span> 
  
 <span data-ttu-id="f9c27-123">**Чтобы вычислить количество поддерживаемых устройств на один IP-адрес, используйте следующую формулу:**</span><span class="sxs-lookup"><span data-stu-id="f9c27-123">**Use the following formula to calculate the number of supported devices per IP address:**</span></span>
  
<span data-ttu-id="f9c27-124">Максимальное число поддерживаемых устройств за один общий IP-адрес = (64 000-ограниченный порт)/(пиковое потребление портов + пиковый коэффициент)</span><span class="sxs-lookup"><span data-stu-id="f9c27-124">Maximum supported devices behind a single public IP address = (64,000 - restricted ports)/(Peak port consumption + peak factor)</span></span>
  
 <span data-ttu-id="f9c27-125">**Например, при соблюдении следующих условий:**</span><span class="sxs-lookup"><span data-stu-id="f9c27-125">**For example, if the following were true:**</span></span>
  
- <span data-ttu-id="f9c27-126">**Ограниченные порты:** 4 000 для операционной системы</span><span class="sxs-lookup"><span data-stu-id="f9c27-126">**Restricted ports:** 4,000 for the operating system</span></span>

- <span data-ttu-id="f9c27-127">**Пиковое потребление портов:** 6 на устройство</span><span class="sxs-lookup"><span data-stu-id="f9c27-127">**Peak port consumption:** 6 per device</span></span>

- <span data-ttu-id="f9c27-128">**Пиковый коэффициент:** 4</span><span class="sxs-lookup"><span data-stu-id="f9c27-128">**Peak factor:** 4</span></span>

<span data-ttu-id="f9c27-129">Затем максимальное число устройств, поддерживаемых одним общедоступным IP-адресом = (64 000-4000)/(6 + 4) = 6 000</span><span class="sxs-lookup"><span data-stu-id="f9c27-129">Then, the maximum supported devices behind a single public IP address = (64,000 - 4,000)/(6 + 4) = 6,000</span></span>
  
<span data-ttu-id="f9c27-130">В выпуске Office 365 с пакетом хостинга, включенном в обновления от 2011 сентября для Microsoft Office Outlook 2007 или Ноябрь 2011 для Microsoft Outlook 2010 или более позднее обновление, количество подключений из Outlook (как для Office Outlook Server с пакетом обновления 2, так и для Outlook 2007) до Exchange может быть равно 2.</span><span class="sxs-lookup"><span data-stu-id="f9c27-130">With the release of Office 365 hosting pack, included in the updates from September 2011 for Microsoft Office Outlook 2007, or November 2011 for Microsoft Outlook 2010, or a later update, the number of connections from Outlook (both Office Outlook 2007 with Service Pack 2 and Outlook 2010) to Exchange can be as few as 2.</span></span> <span data-ttu-id="f9c27-131">Для определения минимального и максимального числа портов, которые потребуются в максимальной нагрузке для сети, необходимо проделать множитель в различных операционных системах, поведении пользователей и т. д.</span><span class="sxs-lookup"><span data-stu-id="f9c27-131">You'll need to factor in the different operating systems, user behaviors, and so on to determine the minimum and maximum number of ports that your network will require at peak.</span></span>
  
<span data-ttu-id="f9c27-132">Если вы хотите поддерживать больше устройств за один общедоступный IP-адрес, выполните действия, описанные для оценки максимального числа поддерживаемых устройств:</span><span class="sxs-lookup"><span data-stu-id="f9c27-132">If you want to support more devices behind a single public IP address, follow the steps outlined to assess the maximum number of devices that can be supported:</span></span>
  
<span data-ttu-id="f9c27-133">Проследите за сетевым трафиком, чтобы определить пиковое потребление портов для каждого клиента.</span><span class="sxs-lookup"><span data-stu-id="f9c27-133">Monitor network traffic to determine peak port consumption per client.</span></span> <span data-ttu-id="f9c27-134">Необходимо собрать эти данные:</span><span class="sxs-lookup"><span data-stu-id="f9c27-134">You should collect this data:</span></span>
  
- <span data-ttu-id="f9c27-135">Из нескольких расположений</span><span class="sxs-lookup"><span data-stu-id="f9c27-135">From multiple locations</span></span>
    
- <span data-ttu-id="f9c27-136">С нескольких устройств</span><span class="sxs-lookup"><span data-stu-id="f9c27-136">From multiple devices</span></span>
    
- <span data-ttu-id="f9c27-137">В несколько раз</span><span class="sxs-lookup"><span data-stu-id="f9c27-137">At multiple times</span></span>
    
<span data-ttu-id="f9c27-138">Используйте приведенную выше формулу, чтобы рассчитать максимальное число пользователей для каждого IP-адреса, которое может поддерживаться в их среде.</span><span class="sxs-lookup"><span data-stu-id="f9c27-138">Use the preceding formula to calculate the maximum users per IP address that can be supported in their environment.</span></span>
  
<span data-ttu-id="f9c27-139">Существует несколько способов распределения нагрузки клиентов по дополнительным общедоступным IP-адресам.</span><span class="sxs-lookup"><span data-stu-id="f9c27-139">There are various methods for distributing client load across additional public IP addresses.</span></span> <span data-ttu-id="f9c27-140">Доступные стратегии зависят от возможностей решения корпоративного шлюза.</span><span class="sxs-lookup"><span data-stu-id="f9c27-140">Strategies available depend on the capabilities of the corporate gateway solution.</span></span> <span data-ttu-id="f9c27-141">Простейшее решение состоит в том, чтобы сегментировать адресное пространство пользователя и статически "назначить для каждого шлюза несколько IP-адресов.</span><span class="sxs-lookup"><span data-stu-id="f9c27-141">The simplest solution is to segment your user address space and statically "assign" a number of IP addresses to each gateway.</span></span> <span data-ttu-id="f9c27-142">Кроме того, можно использовать пул IP-адресов с помощью многих устройств шлюза.</span><span class="sxs-lookup"><span data-stu-id="f9c27-142">Another alternative that many gateway devices offer is the ability to use a pool of IP addresses.</span></span> <span data-ttu-id="f9c27-143">Преимуществом пула адресов является то, что он является гораздо более динамичным и менее вероятным требованием выполнить корректировку по мере роста базы пользователей.</span><span class="sxs-lookup"><span data-stu-id="f9c27-143">The benefit of the address pool is that it is much more dynamic and less likely to require adjustment as your user base grows.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="f9c27-144">См. также</span><span class="sxs-lookup"><span data-stu-id="f9c27-144">See also</span></span>

[<span data-ttu-id="f9c27-145">Управление конечными точками Office 365</span><span class="sxs-lookup"><span data-stu-id="f9c27-145">Managing Office 365 endpoints</span></span>](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a)
  
[<span data-ttu-id="f9c27-146">Вопросы и ответы о конечных точках Office 365</span><span class="sxs-lookup"><span data-stu-id="f9c27-146">Office 365 endpoints FAQ</span></span>](https://support.office.com/article/d4088321-1c89-4b96-9c99-54c75cae2e6d)
