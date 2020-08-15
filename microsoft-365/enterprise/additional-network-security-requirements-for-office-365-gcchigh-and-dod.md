---
title: Дополнительные требования к безопасности сети для Office 365 GCC High и DoD
ms.author: dzazzo
author: dzazzo
manager: dzazzo
ms.date: 05/19/2020
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: Adm_O365
search.appverid:
- OGA150m
- OGC150
- OGD150
- MOE150
ms.assetid: ''
description: 'Сводка: Office 365 GCC High и DoD имеют дополнительные требования к безопасности сети'
hideEdit: true
ms.openlocfilehash: 4817edfcea638324e26eb855d1ea33936be1bfb4
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/14/2020
ms.locfileid: "46693247"
---
# <a name="additional-network-security-requirements-for-office-365-gcc-high-and-dod"></a><span data-ttu-id="38077-103">Дополнительные требования к безопасности сети для Office 365 GCC High и DOD</span><span class="sxs-lookup"><span data-stu-id="38077-103">Additional network security requirements for Office 365 GCC High and DOD</span></span>

<span data-ttu-id="38077-104">*Эта статья относится к пакету Office 365 GCC High, Office 365 DOD, Microsoft 365 GCC High и Microsoft 365 DOD.*</span><span class="sxs-lookup"><span data-stu-id="38077-104">*This article applies to Office 365 GCC High, Office 365 DOD, Microsoft 365 GCC High, and Microsoft 365 DOD.*</span></span>

<span data-ttu-id="38077-105">Office 365 GCC High и DOD — это защищенные облачные среды для удовлетворения потребностей правительства США и ее поставщиков и подрядчиков.</span><span class="sxs-lookup"><span data-stu-id="38077-105">Office 365 GCC High and DOD are secure cloud environments to meet the needs of the United States Government and its suppliers and contractors.</span></span>  <span data-ttu-id="38077-106">В этих облачных средах есть дополнительные ограничения сети, к которым у служб разрешен доступ к внешним конечным точкам.</span><span class="sxs-lookup"><span data-stu-id="38077-106">These cloud environments have additional network restrictions on which external endpoints the services are permitted to access.</span></span>

<span data-ttu-id="38077-107">Для использования федеративных удостоверений или гибридного сосуществования пользователи GCC High и DOD могут потребовать от Майкрософт разрешить входящий и/или исходящий доступ к существующим локальным развертываниям.</span><span class="sxs-lookup"><span data-stu-id="38077-107">GCC High and DOD customers planning to use federated identities or hybrid co-existence may require Microsoft to permit inbound and/or outbound access to your existing on-premises deployments.</span></span>  <span data-ttu-id="38077-108">Ниже приведены примеры этих действий.</span><span class="sxs-lookup"><span data-stu-id="38077-108">Examples of these activities include:</span></span>

* <span data-ttu-id="38077-109">Использование федеративных удостоверений (со службами федерации Active Directory или похожими поддерживаемыми STS)</span><span class="sxs-lookup"><span data-stu-id="38077-109">Use of federated identities (with Active Directory Federation Services or similar supported STS)</span></span>
* <span data-ttu-id="38077-110">Гибридное сосуществование с локальным развертыванием Exchange Server или Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="38077-110">Hybrid coexistence with an on-premises Exchange Server or Skype for Business deployment</span></span>
* <span data-ttu-id="38077-111">Миграция контента существующего пользователя из локальной системы</span><span class="sxs-lookup"><span data-stu-id="38077-111">Migration of existing user content from an on-premises system</span></span>

<span data-ttu-id="38077-112">Чтобы разрешить службе обмениваться данными с локальными конечными точками, **необходимо** отправить электронное письмо в Office 365 проектирование изменений в сети.</span><span class="sxs-lookup"><span data-stu-id="38077-112">To permit the service to communicate with your on-premises endpoints, you **must** send an email to Office 365 engineering for network changes.</span></span>

> [!WARNING]
> <span data-ttu-id="38077-113">Все запросы имеют соглашение об уровне обслуживания за **три недели** и не могут быть обработаны из-за необходимых элементов управления безопасностью и соответствия требованиям и конвейеров развертывания.</span><span class="sxs-lookup"><span data-stu-id="38077-113">All requests have a **three-week** SLA and cannot be expedited due to the required security and compliance controls and deployment pipelines.</span></span>  <span data-ttu-id="38077-114">Сюда входят первоначальные сетевые запросы на переплату, а также любые изменения, внесенные после миграции в службу.</span><span class="sxs-lookup"><span data-stu-id="38077-114">This includes initial onboarding network requests as well as any changes after you have migrated to the service.</span></span>  <span data-ttu-id="38077-115">Убедитесь, что сетевые команды знают об этой временной шкале и включают ее в циклы планирования.</span><span class="sxs-lookup"><span data-stu-id="38077-115">Please ensure that your network teams are aware of this timeline and include it in their planning cycles.</span></span>

<span data-ttu-id="38077-116">Отправьте сообщение электронной почты в [Office 365 для государственных организаций белом](mailto:o365gwlt@microsoft.com) со следующими сведениями:</span><span class="sxs-lookup"><span data-stu-id="38077-116">Please send an email to [Office 365 Government Network Whitelist](mailto:o365gwlt@microsoft.com) with the following information:</span></span>

* <span data-ttu-id="38077-117">**В**: [Office 365 для государственных сетей белом](mailto:o365gwlt@microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="38077-117">**To**: [Office 365 Government Network Whitelist](mailto:o365gwlt@microsoft.com)</span></span>
* <span data-ttu-id="38077-118">**От**: Администратор клиента — отправка электронной почты **должна** сопоставляться с контактом глобального администратора в клиенте.</span><span class="sxs-lookup"><span data-stu-id="38077-118">**From**: A tenant administrator - the send email **must** match a Global Administrator contact in your tenant</span></span>
* <span data-ttu-id="38077-119">**Тема сообщения**: Office 365 GCC High Network Request-contoso.onmicrosoft.US (замените это на имя вашего клиента).</span><span class="sxs-lookup"><span data-stu-id="38077-119">**Email subject**: Office 365 GCC High Network Request - contoso.onmicrosoft.us (replace this with your tenant name)</span></span>

<span data-ttu-id="38077-120">В тексте сообщения должны содержаться следующие данные:</span><span class="sxs-lookup"><span data-stu-id="38077-120">The body of your message should include the following data:</span></span>

* <span data-ttu-id="38077-121">Имя клиента Microsoft Online Services (например, contoso.onmicrosoft.com, fabrikam.onmicrosoft.us)</span><span class="sxs-lookup"><span data-stu-id="38077-121">Your Microsoft Online Services tenant name (i.e. contoso.onmicrosoft.com, fabrikam.onmicrosoft.us)</span></span>
* <span data-ttu-id="38077-122">Список рассылки электронной почты, с которым будет общаться Корпорация Майкрософт для обеспечения непрерывной связи, связанной с изменениями сети и/или отслеживанием недопустимых подсетей</span><span class="sxs-lookup"><span data-stu-id="38077-122">An email distribution list that Microsoft will communicate with for on-going communications related to network changes and/or follow up for invalid subnets</span></span>
* <span data-ttu-id="38077-123">Указывает, планируется ли использование гибридного сосуществования Microsoft Teams в локальных развертываниях</span><span class="sxs-lookup"><span data-stu-id="38077-123">Indicate whether you plan to use Microsoft Teams hybrid co-existence with your on-premises deployments</span></span>
* <span data-ttu-id="38077-124">Доступ к внешней системе федеративного удостоверения URL-адрес (например, sts.contoso.com) и диапазон IP-адресов в нотации CIDR (например, 10.1.1.0/28).</span><span class="sxs-lookup"><span data-stu-id="38077-124">Federated identity system externally accessible URL (e.g. sts.contoso.com) and IP address range in CIDR notation (e.g. 10.1.1.0/28)</span></span>
* <span data-ttu-id="38077-125">URL-адрес локального списка отзыва сертификатов PKI и диапазон IP-адресов в нотации CIDR</span><span class="sxs-lookup"><span data-stu-id="38077-125">On-Premises PKI Certificate Revocation List URL and IP address range in CIDR notation</span></span>
* <span data-ttu-id="38077-126">Доступный извне URL-адрес и диапазон IP-адресов для локального развертывания Exchange Server в нотации CIDR</span><span class="sxs-lookup"><span data-stu-id="38077-126">Externally accessible URL and IP address range for Exchange Server on-premises deployment in CIDR notation</span></span>
* <span data-ttu-id="38077-127">Доступный извне URL-адрес и диапазон IP-адресов для локального развертывания Skype для бизнеса в нотации CIDR</span><span class="sxs-lookup"><span data-stu-id="38077-127">Externally accessible URL and IP address range for Skype for Business on-premises deployment in CIDR notation</span></span>

<span data-ttu-id="38077-128">В целях обеспечения безопасности и соответствия необходимо иметь в виду следующие ограничения на запрос:</span><span class="sxs-lookup"><span data-stu-id="38077-128">For security and compliance reasons, please keep in mind the following restrictions on your request:</span></span>

* <span data-ttu-id="38077-129">Существует четыре ограничения подсети для каждого клиента</span><span class="sxs-lookup"><span data-stu-id="38077-129">There is a four subnet limitation per tenant</span></span>
* <span data-ttu-id="38077-130">Подсети должны находиться в нотации CIDR (например, 10.1.1.0/28).</span><span class="sxs-lookup"><span data-stu-id="38077-130">Subnets must be in CIDR Notation (e.g. 10.1.1.0/28)</span></span>
* <span data-ttu-id="38077-131">Диапазоны подсетей не могут превышать/24</span><span class="sxs-lookup"><span data-stu-id="38077-131">Subnet ranges cannot be larger than /24</span></span>
* <span data-ttu-id="38077-132">Мы **не** можем разместить запросы на предоставление коммерческих облачных служб (коммерческая версия Office 365, Google G-Suite, веб-службы Amazon и т. д.)</span><span class="sxs-lookup"><span data-stu-id="38077-132">We **cannot** accommodate requests to allow access to commercial cloud services (commercial Office 365, Google G-Suite, Amazon Web Services, etc.)</span></span>

<span data-ttu-id="38077-133">После того как ваш запрос будет получен и утвержден корпорацией Майкрософт, для реализации необходимо выполнить соглашение об уровне обслуживания за три недели.</span><span class="sxs-lookup"><span data-stu-id="38077-133">Once your request has been received and approved by Microsoft, there is a three-week SLA for implementation and cannot be expedited.</span></span>  <span data-ttu-id="38077-134">Вы получите начальное подтверждение, когда мы получили ваш запрос и завершающее подтверждение после его завершения.</span><span class="sxs-lookup"><span data-stu-id="38077-134">You will receive an initial acknowledgment when we’ve received your request and a final acknowledgement once it has been completed.</span></span>
