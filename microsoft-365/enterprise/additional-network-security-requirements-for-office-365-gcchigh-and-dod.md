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
description: Сводка. Office 365 GCC High и DoD предъявляют дополнительные требования к безопасности сети
hideEdit: true
ms.openlocfilehash: 4817edfcea638324e26eb855d1ea33936be1bfb4
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/14/2020
ms.locfileid: "46693247"
---
# <a name="additional-network-security-requirements-for-office-365-gcc-high-and-dod"></a><span data-ttu-id="e1283-103">Дополнительные требования сетевой безопасности для Office 365 GCC High и DoD</span><span class="sxs-lookup"><span data-stu-id="e1283-103">Additional network security requirements for Office 365 GCC High and DOD</span></span>

<span data-ttu-id="e1283-104">*Эта статья относится к Office 365 GCC High, Office 365 DOD, Microsoft 365 GCC High и Microsoft 365 DOD.*</span><span class="sxs-lookup"><span data-stu-id="e1283-104">*This article applies to Office 365 GCC High, Office 365 DOD, Microsoft 365 GCC High, and Microsoft 365 DOD.*</span></span>

<span data-ttu-id="e1283-105">Office 365 GCC High и DOD — это безопасные облачные среды для удовлетворения потребностей правительства США, а также его поставщиков и подрядчиков.</span><span class="sxs-lookup"><span data-stu-id="e1283-105">Office 365 GCC High and DOD are secure cloud environments to meet the needs of the United States Government and its suppliers and contractors.</span></span>  <span data-ttu-id="e1283-106">Эти облачные среды имеют дополнительные сетевые ограничения, к которым внешние конечные точки могут получать доступ службы.</span><span class="sxs-lookup"><span data-stu-id="e1283-106">These cloud environments have additional network restrictions on which external endpoints the services are permitted to access.</span></span>

<span data-ttu-id="e1283-107">Клиентам GCC High и DOD, планируя использовать федерательные удостоверения или гибридное сосуществование, может потребоваться, чтобы корпорация Майкрософт разрешила входящий и/или исходящие доступ к существующим локально развертываниям.</span><span class="sxs-lookup"><span data-stu-id="e1283-107">GCC High and DOD customers planning to use federated identities or hybrid co-existence may require Microsoft to permit inbound and/or outbound access to your existing on-premises deployments.</span></span>  <span data-ttu-id="e1283-108">Примеры таких действий:</span><span class="sxs-lookup"><span data-stu-id="e1283-108">Examples of these activities include:</span></span>

* <span data-ttu-id="e1283-109">Использование федераированных удостоверений (со службами федерации Active Directory или аналогичной поддерживаемой службой stS)</span><span class="sxs-lookup"><span data-stu-id="e1283-109">Use of federated identities (with Active Directory Federation Services or similar supported STS)</span></span>
* <span data-ttu-id="e1283-110">Гибридное сосуществование с локальной Exchange Server или развертыванием Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="e1283-110">Hybrid coexistence with an on-premises Exchange Server or Skype for Business deployment</span></span>
* <span data-ttu-id="e1283-111">Перенос существующего пользовательского контента из локальной системы</span><span class="sxs-lookup"><span data-stu-id="e1283-111">Migration of existing user content from an on-premises system</span></span>

<span data-ttu-id="e1283-112">Чтобы разрешить службе взаимодействовать с вашими конечными  точками в локальной сети, необходимо отправить электронное письмо инженерной службе Office 365 для изменения сети.</span><span class="sxs-lookup"><span data-stu-id="e1283-112">To permit the service to communicate with your on-premises endpoints, you **must** send an email to Office 365 engineering for network changes.</span></span>

> [!WARNING]
> <span data-ttu-id="e1283-113">Все запросы имеют трехнедельное SLA и не могут быть ускоряться **из-за** необходимых средств контроля безопасности и соответствия требованиям и конвейеров развертывания.</span><span class="sxs-lookup"><span data-stu-id="e1283-113">All requests have a **three-week** SLA and cannot be expedited due to the required security and compliance controls and deployment pipelines.</span></span>  <span data-ttu-id="e1283-114">К ним относятся начальные сетевые запросы, а также любые изменения после миграции в службу.</span><span class="sxs-lookup"><span data-stu-id="e1283-114">This includes initial onboarding network requests as well as any changes after you have migrated to the service.</span></span>  <span data-ttu-id="e1283-115">Убедитесь, что сетевые команды знают об этой временной шкале и включают ее в циклы планирования.</span><span class="sxs-lookup"><span data-stu-id="e1283-115">Please ensure that your network teams are aware of this timeline and include it in their planning cycles.</span></span>

<span data-ttu-id="e1283-116">Отправьте электронное письмо в белый список [сети Office 365](mailto:o365gwlt@microsoft.com) для государственных органов со следующими сведениями:</span><span class="sxs-lookup"><span data-stu-id="e1283-116">Please send an email to [Office 365 Government Network Whitelist](mailto:o365gwlt@microsoft.com) with the following information:</span></span>

* <span data-ttu-id="e1283-117">**To**: [Office 365 Government Network Whitelist](mailto:o365gwlt@microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="e1283-117">**To**: [Office 365 Government Network Whitelist](mailto:o365gwlt@microsoft.com)</span></span>
* <span data-ttu-id="e1283-118">**From**: A tenant administrator - the send email **must** match a Global Administrator contact in your tenant</span><span class="sxs-lookup"><span data-stu-id="e1283-118">**From**: A tenant administrator - the send email **must** match a Global Administrator contact in your tenant</span></span>
* <span data-ttu-id="e1283-119">**Тема электронной** почты: office 365 GCC High Network Request - contoso.onmicrosoft.us (замените это на имя клиента)</span><span class="sxs-lookup"><span data-stu-id="e1283-119">**Email subject**: Office 365 GCC High Network Request - contoso.onmicrosoft.us (replace this with your tenant name)</span></span>

<span data-ttu-id="e1283-120">Текст сообщения должен включать следующие данные:</span><span class="sxs-lookup"><span data-stu-id="e1283-120">The body of your message should include the following data:</span></span>

* <span data-ttu-id="e1283-121">Имя Microsoft Online Services клиента (например, contoso.onmicrosoft.com, fabrikam.onmicrosoft.us)</span><span class="sxs-lookup"><span data-stu-id="e1283-121">Your Microsoft Online Services tenant name (i.e. contoso.onmicrosoft.com, fabrikam.onmicrosoft.us)</span></span>
* <span data-ttu-id="e1283-122">Список рассылки электронной почты, с помощью который корпорация Майкрософт будет взаимодействовать для обеспечения связи в сети, связанной с изменениями сети и/или последующим распространением недопустимых подсетей.</span><span class="sxs-lookup"><span data-stu-id="e1283-122">An email distribution list that Microsoft will communicate with for on-going communications related to network changes and/or follow up for invalid subnets</span></span>
* <span data-ttu-id="e1283-123">Указать, планируете ли вы использовать гибридное сосуществование Microsoft Teams с вашими развертываниями в локальной организации</span><span class="sxs-lookup"><span data-stu-id="e1283-123">Indicate whether you plan to use Microsoft Teams hybrid co-existence with your on-premises deployments</span></span>
* <span data-ttu-id="e1283-124">URL-адрес федерационной системы идентификации, доступный извне (например, sts.contoso.com) и диапазон IP-адресов в нотации CIDR (например, 10.1.1.0/28)</span><span class="sxs-lookup"><span data-stu-id="e1283-124">Federated identity system externally accessible URL (e.g. sts.contoso.com) and IP address range in CIDR notation (e.g. 10.1.1.0/28)</span></span>
* <span data-ttu-id="e1283-125">URL-адрес и диапазон IP-адресов локального списка отзыва сертификатов PKI в нотации CIDR</span><span class="sxs-lookup"><span data-stu-id="e1283-125">On-Premises PKI Certificate Revocation List URL and IP address range in CIDR notation</span></span>
* <span data-ttu-id="e1283-126">Доступный извне URL-адрес и диапазон IP-адресов для Exchange Server локального развертывания в нотации CIDR</span><span class="sxs-lookup"><span data-stu-id="e1283-126">Externally accessible URL and IP address range for Exchange Server on-premises deployment in CIDR notation</span></span>
* <span data-ttu-id="e1283-127">Доступный извне URL-адрес и диапазон IP-адресов для локального развертывания Skype для бизнеса в нотации CIDR</span><span class="sxs-lookup"><span data-stu-id="e1283-127">Externally accessible URL and IP address range for Skype for Business on-premises deployment in CIDR notation</span></span>

<span data-ttu-id="e1283-128">По соображениям безопасности и соответствия требованиям помните о следующих ограничениях для вашего запроса:</span><span class="sxs-lookup"><span data-stu-id="e1283-128">For security and compliance reasons, please keep in mind the following restrictions on your request:</span></span>

* <span data-ttu-id="e1283-129">Существует четыре ограничения подсети для каждого клиента</span><span class="sxs-lookup"><span data-stu-id="e1283-129">There is a four subnet limitation per tenant</span></span>
* <span data-ttu-id="e1283-130">Подсети должны быть в нотации CIDR (например, 10.1.1.0/28)</span><span class="sxs-lookup"><span data-stu-id="e1283-130">Subnets must be in CIDR Notation (e.g. 10.1.1.0/28)</span></span>
* <span data-ttu-id="e1283-131">Диапазоны подсетей не могут быть больше /24</span><span class="sxs-lookup"><span data-stu-id="e1283-131">Subnet ranges cannot be larger than /24</span></span>
* <span data-ttu-id="e1283-132">Мы **не можем** удовлетворить запросы на разрешение доступа к коммерческим облачным службам (коммерческим службам Office 365, Google G-Suite, Amazon Web Services и т. д.)</span><span class="sxs-lookup"><span data-stu-id="e1283-132">We **cannot** accommodate requests to allow access to commercial cloud services (commercial Office 365, Google G-Suite, Amazon Web Services, etc.)</span></span>

<span data-ttu-id="e1283-133">После того как ваш запрос будет получен и утвержден корпорацией Майкрософт, существует трехнедельное SLA для реализации и его нельзя ускорить.</span><span class="sxs-lookup"><span data-stu-id="e1283-133">Once your request has been received and approved by Microsoft, there is a three-week SLA for implementation and cannot be expedited.</span></span>  <span data-ttu-id="e1283-134">После получения запроса вы получите начальное подтверждение и окончательное подтверждение после его выполнения.</span><span class="sxs-lookup"><span data-stu-id="e1283-134">You will receive an initial acknowledgment when we’ve received your request and a final acknowledgement once it has been completed.</span></span>
