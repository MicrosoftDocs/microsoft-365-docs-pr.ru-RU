---
title: Дополнительные требования к сетевой безопасности для Office 365 GCC High и DoD
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
description: 'Сводка: Office 365 GCC High и DoD имеют дополнительные требования к сетевой безопасности'
hideEdit: true
ms.openlocfilehash: 4817edfcea638324e26eb855d1ea33936be1bfb4
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/14/2020
ms.locfileid: "46693247"
---
# <a name="additional-network-security-requirements-for-office-365-gcc-high-and-dod"></a><span data-ttu-id="5cc56-103">Дополнительные требования сетевой безопасности для Office 365 GCC High и DoD</span><span class="sxs-lookup"><span data-stu-id="5cc56-103">Additional network security requirements for Office 365 GCC High and DOD</span></span>

<span data-ttu-id="5cc56-104">*Эта статья применяется к Office 365 GCC, Office 365, Microsoft 365 GCC и Microsoft 365 DoD.*</span><span class="sxs-lookup"><span data-stu-id="5cc56-104">*This article applies to Office 365 GCC High, Office 365 DOD, Microsoft 365 GCC High, and Microsoft 365 DOD.*</span></span>

<span data-ttu-id="5cc56-105">Office 365 GCC high и DOD — это безопасные облачные среды, которые отвечают потребностям правительства Соединенных Штатов и его поставщиков и подрядчиков.</span><span class="sxs-lookup"><span data-stu-id="5cc56-105">Office 365 GCC High and DOD are secure cloud environments to meet the needs of the United States Government and its suppliers and contractors.</span></span>  <span data-ttu-id="5cc56-106">Эти облачные среды имеют дополнительные сетевые ограничения, к которым разрешен доступ к внешним конечным точкам.</span><span class="sxs-lookup"><span data-stu-id="5cc56-106">These cloud environments have additional network restrictions on which external endpoints the services are permitted to access.</span></span>

<span data-ttu-id="5cc56-107">GCC Для клиентов с высоким уровнем и службой безопасности, планируя использовать федерательные удостоверения или гибридное сосуществование, может потребоваться, чтобы Корпорация Майкрософт разрешила входящие и/или исходящие доступы к существующим локальному развертыванию.</span><span class="sxs-lookup"><span data-stu-id="5cc56-107">GCC High and DOD customers planning to use federated identities or hybrid co-existence may require Microsoft to permit inbound and/or outbound access to your existing on-premises deployments.</span></span>  <span data-ttu-id="5cc56-108">Примеры таких действий:</span><span class="sxs-lookup"><span data-stu-id="5cc56-108">Examples of these activities include:</span></span>

* <span data-ttu-id="5cc56-109">Использование федераированных удостоверений (с службами Федерации Active Directory или аналогичной поддержкой STS)</span><span class="sxs-lookup"><span data-stu-id="5cc56-109">Use of federated identities (with Active Directory Federation Services or similar supported STS)</span></span>
* <span data-ttu-id="5cc56-110">Гибридное сосуществование с локальной Exchange Server или Skype для бизнеса развертывания</span><span class="sxs-lookup"><span data-stu-id="5cc56-110">Hybrid coexistence with an on-premises Exchange Server or Skype for Business deployment</span></span>
* <span data-ttu-id="5cc56-111">Перенос существующего пользовательского контента из локальной системы</span><span class="sxs-lookup"><span data-stu-id="5cc56-111">Migration of existing user content from an on-premises system</span></span>

<span data-ttu-id="5cc56-112">Чтобы разрешить службе общаться с конечными точками  на месте, необходимо отправить электронное письмо в Office 365 для изменения сети.</span><span class="sxs-lookup"><span data-stu-id="5cc56-112">To permit the service to communicate with your on-premises endpoints, you **must** send an email to Office 365 engineering for network changes.</span></span>

> [!WARNING]
> <span data-ttu-id="5cc56-113">Все запросы имеют трехнедельный SLA и не могут быть ускоряться **из-за** необходимых элементов управления безопасностью и соответствия требованиям и конвейеров развертывания.</span><span class="sxs-lookup"><span data-stu-id="5cc56-113">All requests have a **three-week** SLA and cannot be expedited due to the required security and compliance controls and deployment pipelines.</span></span>  <span data-ttu-id="5cc56-114">Это включает начальные сетевые запросы, а также любые изменения после перехода в службу.</span><span class="sxs-lookup"><span data-stu-id="5cc56-114">This includes initial onboarding network requests as well as any changes after you have migrated to the service.</span></span>  <span data-ttu-id="5cc56-115">Убедитесь, что сетевые группы знают об этой временной шкале, и включите ее в циклы планирования.</span><span class="sxs-lookup"><span data-stu-id="5cc56-115">Please ensure that your network teams are aware of this timeline and include it in their planning cycles.</span></span>

<span data-ttu-id="5cc56-116">Отправьте сообщение электронной [почты в Office 365 для государственных организаций Сетевой список](mailto:o365gwlt@microsoft.com) со следующими сведениями:</span><span class="sxs-lookup"><span data-stu-id="5cc56-116">Please send an email to [Office 365 Government Network Whitelist](mailto:o365gwlt@microsoft.com) with the following information:</span></span>

* <span data-ttu-id="5cc56-117">**Для**: [Office 365 для государственных организаций Белый список сети](mailto:o365gwlt@microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="5cc56-117">**To**: [Office 365 Government Network Whitelist](mailto:o365gwlt@microsoft.com)</span></span>
* <span data-ttu-id="5cc56-118">**От**: Администратор клиента — отправка электронной почты **должна соответствовать** контакту глобального администратора в клиенте</span><span class="sxs-lookup"><span data-stu-id="5cc56-118">**From**: A tenant administrator - the send email **must** match a Global Administrator contact in your tenant</span></span>
* <span data-ttu-id="5cc56-119">**Тема электронной** почты: Office 365 GCC запроса высокой сети — contoso.onmicrosoft.us (замените это именем клиента)</span><span class="sxs-lookup"><span data-stu-id="5cc56-119">**Email subject**: Office 365 GCC High Network Request - contoso.onmicrosoft.us (replace this with your tenant name)</span></span>

<span data-ttu-id="5cc56-120">В текст сообщения должны быть включены следующие данные:</span><span class="sxs-lookup"><span data-stu-id="5cc56-120">The body of your message should include the following data:</span></span>

* <span data-ttu-id="5cc56-121">Имя Microsoft Online Services клиента (например, contoso.onmicrosoft.com, fabrikam.onmicrosoft.us)</span><span class="sxs-lookup"><span data-stu-id="5cc56-121">Your Microsoft Online Services tenant name (i.e. contoso.onmicrosoft.com, fabrikam.onmicrosoft.us)</span></span>
* <span data-ttu-id="5cc56-122">Список рассылки электронной почты, с помощью который Корпорация Майкрософт будет взаимодействовать для связи, связанной с изменением сети и/или последующими решениями для недействительных подсетей.</span><span class="sxs-lookup"><span data-stu-id="5cc56-122">An email distribution list that Microsoft will communicate with for on-going communications related to network changes and/or follow up for invalid subnets</span></span>
* <span data-ttu-id="5cc56-123">Указать, планируете ли вы использовать Microsoft Teams совместное существование с локальной развертыванием</span><span class="sxs-lookup"><span data-stu-id="5cc56-123">Indicate whether you plan to use Microsoft Teams hybrid co-existence with your on-premises deployments</span></span>
* <span data-ttu-id="5cc56-124">Федерационная система удостоверений, внешне доступные URL-адрес (например, sts.contoso.com) и диапазон IP-адресов в нотации CIDR (например, 10.1.1.0/28)</span><span class="sxs-lookup"><span data-stu-id="5cc56-124">Federated identity system externally accessible URL (e.g. sts.contoso.com) and IP address range in CIDR notation (e.g. 10.1.1.0/28)</span></span>
* <span data-ttu-id="5cc56-125">Url-адрес и диапазон IP-адресов локального списка сертификатов PKI в нотации CIDR</span><span class="sxs-lookup"><span data-stu-id="5cc56-125">On-Premises PKI Certificate Revocation List URL and IP address range in CIDR notation</span></span>
* <span data-ttu-id="5cc56-126">Внешне доступный URL-адрес и диапазон IP Exchange Server локального развертывания в ciDR нотации</span><span class="sxs-lookup"><span data-stu-id="5cc56-126">Externally accessible URL and IP address range for Exchange Server on-premises deployment in CIDR notation</span></span>
* <span data-ttu-id="5cc56-127">Внешне доступный URL-адрес и диапазон IP Skype для бизнеса локального развертывания в ciDR нотации</span><span class="sxs-lookup"><span data-stu-id="5cc56-127">Externally accessible URL and IP address range for Skype for Business on-premises deployment in CIDR notation</span></span>

<span data-ttu-id="5cc56-128">В целях безопасности и соответствия требованиям обратите внимание на следующие ограничения на запрос:</span><span class="sxs-lookup"><span data-stu-id="5cc56-128">For security and compliance reasons, please keep in mind the following restrictions on your request:</span></span>

* <span data-ttu-id="5cc56-129">Существует четыре ограничения подсети для каждого клиента</span><span class="sxs-lookup"><span data-stu-id="5cc56-129">There is a four subnet limitation per tenant</span></span>
* <span data-ttu-id="5cc56-130">Подсети должны быть в нотации CIDR (например, 10.1.1.0/28)</span><span class="sxs-lookup"><span data-stu-id="5cc56-130">Subnets must be in CIDR Notation (e.g. 10.1.1.0/28)</span></span>
* <span data-ttu-id="5cc56-131">Диапазоны подсетей не могут быть больше /24</span><span class="sxs-lookup"><span data-stu-id="5cc56-131">Subnet ranges cannot be larger than /24</span></span>
* <span data-ttu-id="5cc56-132">Мы **не можем** разместить запросы на доступ к коммерческим облачным службам (коммерческим Office 365, Google G-Suite, Amazon Web Services и т.д.)</span><span class="sxs-lookup"><span data-stu-id="5cc56-132">We **cannot** accommodate requests to allow access to commercial cloud services (commercial Office 365, Google G-Suite, Amazon Web Services, etc.)</span></span>

<span data-ttu-id="5cc56-133">После того, как ваш запрос был получен и утвержден Корпорацией Майкрософт, для реализации будет установлен трехнедельный SLA, который не может быть ускоряться.</span><span class="sxs-lookup"><span data-stu-id="5cc56-133">Once your request has been received and approved by Microsoft, there is a three-week SLA for implementation and cannot be expedited.</span></span>  <span data-ttu-id="5cc56-134">Вы получите начальное подтверждение, когда мы получим ваш запрос и окончательное подтверждение после его завершения.</span><span class="sxs-lookup"><span data-stu-id="5cc56-134">You will receive an initial acknowledgment when we’ve received your request and a final acknowledgement once it has been completed.</span></span>
