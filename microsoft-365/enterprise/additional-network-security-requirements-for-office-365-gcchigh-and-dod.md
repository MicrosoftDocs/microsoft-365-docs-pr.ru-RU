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
ms.openlocfilehash: f4c03d364e84d89a1b12e4d858ab46eb3be6ae5e
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/14/2021
ms.locfileid: "52926563"
---
# <a name="additional-network-security-requirements-for-office-365-gcc-high-and-dod"></a><span data-ttu-id="3ee96-103">Дополнительные требования сетевой безопасности для Office 365 GCC High и DoD</span><span class="sxs-lookup"><span data-stu-id="3ee96-103">Additional network security requirements for Office 365 GCC High and DOD</span></span>

<span data-ttu-id="3ee96-104">*Эта статья применяется к Office 365 GCC, Office 365, Microsoft 365 GCC и Microsoft 365 DoD.*</span><span class="sxs-lookup"><span data-stu-id="3ee96-104">*This article applies to Office 365 GCC High, Office 365 DOD, Microsoft 365 GCC High, and Microsoft 365 DOD.*</span></span>

<span data-ttu-id="3ee96-105">Office 365 GCC high и DOD — это безопасные облачные среды, которые отвечают потребностям правительства Соединенных Штатов и его поставщиков и подрядчиков.</span><span class="sxs-lookup"><span data-stu-id="3ee96-105">Office 365 GCC High and DOD are secure cloud environments to meet the needs of the United States Government and its suppliers and contractors.</span></span>  <span data-ttu-id="3ee96-106">Эти облачные среды имеют дополнительные сетевые ограничения, к которым разрешен доступ к внешним конечным точкам.</span><span class="sxs-lookup"><span data-stu-id="3ee96-106">These cloud environments have additional network restrictions on which external endpoints the services are permitted to access.</span></span>

<span data-ttu-id="3ee96-107">GCC Для клиентов с высоким уровнем и doD, планируя использовать федерационные удостоверения или гибридное сосуществование, может потребоваться, чтобы Корпорация Майкрософт разрешила входящие и/или исходящие доступы к существующим локальному развертыванию.</span><span class="sxs-lookup"><span data-stu-id="3ee96-107">GCC High and DOD customers planning to use federated identities or hybrid coexistence may require Microsoft to permit inbound and/or outbound access to your existing on-premises deployments.</span></span>  <span data-ttu-id="3ee96-108">Примеры таких действий:</span><span class="sxs-lookup"><span data-stu-id="3ee96-108">Examples of these activities include:</span></span>

* <span data-ttu-id="3ee96-109">Использование федераированных удостоверений (с службами Федерации Active Directory или аналогичной поддержкой STS)</span><span class="sxs-lookup"><span data-stu-id="3ee96-109">Use of federated identities (with Active Directory Federation Services or similar supported STS)</span></span>
* <span data-ttu-id="3ee96-110">Гибридное сосуществование с локальной Exchange Server или Skype для бизнеса развертывания</span><span class="sxs-lookup"><span data-stu-id="3ee96-110">Hybrid coexistence with an on-premises Exchange Server or Skype for Business deployment</span></span>
* <span data-ttu-id="3ee96-111">Перенос существующего пользовательского контента из локальной системы</span><span class="sxs-lookup"><span data-stu-id="3ee96-111">Migration of existing user content from an on-premises system</span></span>

<span data-ttu-id="3ee96-112">Чтобы разрешить службе общаться с конечными точками  на месте, необходимо отправить электронное письмо в Office 365 для изменения сети.</span><span class="sxs-lookup"><span data-stu-id="3ee96-112">To permit the service to communicate with your on-premises endpoints, you **must** send an email to Office 365 engineering for network changes.</span></span>

> [!WARNING]
> <span data-ttu-id="3ee96-113">Все запросы имеют трехнедельный SLA и не могут быть ускоряться **из-за** необходимых элементов управления безопасностью и соответствия требованиям и конвейеров развертывания.</span><span class="sxs-lookup"><span data-stu-id="3ee96-113">All requests have a **three-week** SLA and cannot be expedited due to the required security and compliance controls and deployment pipelines.</span></span>  <span data-ttu-id="3ee96-114">Это включает начальные сетевые запросы, а также любые изменения после перехода в службу.</span><span class="sxs-lookup"><span data-stu-id="3ee96-114">This includes initial onboarding network requests as well as any changes after you have migrated to the service.</span></span>  <span data-ttu-id="3ee96-115">Убедитесь, что сетевые группы знают об этой временной шкале и включают ее в циклы планирования.</span><span class="sxs-lookup"><span data-stu-id="3ee96-115">Make sure that your network teams are aware of this timeline and include it in their planning cycles.</span></span>

<span data-ttu-id="3ee96-116">Отправьте сообщение электронной [почты Office 365 для государственных организаций Allow-List запросы](mailto:o365gwlt@microsoft.com) со следующими сведениями:</span><span class="sxs-lookup"><span data-stu-id="3ee96-116">Send an email to [Office 365 Government Allow-List Requests](mailto:o365gwlt@microsoft.com) with the following information:</span></span>

* <span data-ttu-id="3ee96-117">**Чтобы**: [Office 365 для государственных организаций Allow-List запросы](mailto:o365gwlt@microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="3ee96-117">**To**: [Office 365 Government Allow-List Requests](mailto:o365gwlt@microsoft.com)</span></span>
* <span data-ttu-id="3ee96-118">**От**: Администратор клиента — отправка электронной почты **должна соответствовать** контакту глобального администратора в клиенте</span><span class="sxs-lookup"><span data-stu-id="3ee96-118">**From**: A tenant administrator - the send email **must** match a Global Administrator contact in your tenant</span></span>
* <span data-ttu-id="3ee96-119">**Тема электронной** почты: Office 365 GCC запрос высокой сети — contoso.onmicrosoft.us (замените имя клиента)</span><span class="sxs-lookup"><span data-stu-id="3ee96-119">**Email subject**: Office 365 GCC High Network Request - contoso.onmicrosoft.us (replace with your tenant name)</span></span>

<span data-ttu-id="3ee96-120">В текст сообщения должны быть включены следующие данные:</span><span class="sxs-lookup"><span data-stu-id="3ee96-120">The body of your message should include the following data:</span></span>

* <span data-ttu-id="3ee96-121">Имя Microsoft Online Services клиента (например, contoso.onmicrosoft.com, fabrikam.onmicrosoft.us)</span><span class="sxs-lookup"><span data-stu-id="3ee96-121">Your Microsoft Online Services tenant name (for example, contoso.onmicrosoft.com, fabrikam.onmicrosoft.us)</span></span>
* <span data-ttu-id="3ee96-122">Список рассылки электронной почты, с помощью который Корпорация Майкрософт будет взаимодействовать для связи, связанной с изменением сети и/или последующими решениями для недействительных подсетей.</span><span class="sxs-lookup"><span data-stu-id="3ee96-122">An email distribution list that Microsoft will communicate with for on-going communications related to network changes and/or follow up for invalid subnets</span></span>
* <span data-ttu-id="3ee96-123">Указать, планируете ли вы использовать Microsoft Teams совместное сосуществование с локальной развертыванием</span><span class="sxs-lookup"><span data-stu-id="3ee96-123">Indicate whether you plan to use Microsoft Teams hybrid coexistence with your on-premises deployments</span></span>
* <span data-ttu-id="3ee96-124">Федерационная система удостоверений, внешне доступные URL-адрес (например, sts.contoso.com) и диапазон IP-адресов в области нотации CIDR (например,.</span><span class="sxs-lookup"><span data-stu-id="3ee96-124">Federated identity system externally accessible URL (for example, sts.contoso.com) and IP address range in CIDR notation (for example,.</span></span> <span data-ttu-id="3ee96-125">10.1.1.0/28)</span><span class="sxs-lookup"><span data-stu-id="3ee96-125">10.1.1.0/28)</span></span>
* <span data-ttu-id="3ee96-126">Url-адрес и диапазон IP-адресов локального списка сертификатов PKI в нотации CIDR</span><span class="sxs-lookup"><span data-stu-id="3ee96-126">On-Premises PKI Certificate Revocation List URL and IP address range in CIDR notation</span></span>
* <span data-ttu-id="3ee96-127">Внешне доступный URL-адрес и диапазон IP Exchange Server локального развертывания в ciDR нотации</span><span class="sxs-lookup"><span data-stu-id="3ee96-127">Externally accessible URL and IP address range for Exchange Server on-premises deployment in CIDR notation</span></span>
* <span data-ttu-id="3ee96-128">Внешне доступный URL-адрес и диапазон IP Skype для бизнеса локального развертывания в ciDR нотации</span><span class="sxs-lookup"><span data-stu-id="3ee96-128">Externally accessible URL and IP address range for Skype for Business on-premises deployment in CIDR notation</span></span>

<span data-ttu-id="3ee96-129">В целях безопасности и соответствия требованиям помните о следующих ограничениях на запрос:</span><span class="sxs-lookup"><span data-stu-id="3ee96-129">For security and compliance reasons, keep in mind the following restrictions on your request:</span></span>

* <span data-ttu-id="3ee96-130">Существует четыре ограничения подсети для каждого клиента</span><span class="sxs-lookup"><span data-stu-id="3ee96-130">There is a four subnet limitation per tenant</span></span>
* <span data-ttu-id="3ee96-131">Подсети должны быть в нотации CIDR (например, 10.1.1.0/28)</span><span class="sxs-lookup"><span data-stu-id="3ee96-131">Subnets must be in CIDR Notation (for example, 10.1.1.0/28)</span></span>
* <span data-ttu-id="3ee96-132">Диапазоны подсетей не могут быть больше /24</span><span class="sxs-lookup"><span data-stu-id="3ee96-132">Subnet ranges cannot be larger than /24</span></span>
* <span data-ttu-id="3ee96-133">Мы **не можем** разместить запросы на доступ к коммерческим облачным службам (коммерческим Office 365, Google G-Suite, Amazon Web Services и т.д.)</span><span class="sxs-lookup"><span data-stu-id="3ee96-133">We **cannot** accommodate requests to allow access to commercial cloud services (commercial Office 365, Google G-Suite, Amazon Web Services, etc.)</span></span>

<span data-ttu-id="3ee96-134">После того, как ваш запрос был получен и утвержден Корпорацией Майкрософт, для реализации будет установлен трехнедельный SLA, который не может быть ускоряться.</span><span class="sxs-lookup"><span data-stu-id="3ee96-134">Once your request has been received and approved by Microsoft, there is a three-week SLA for implementation and cannot be expedited.</span></span>  <span data-ttu-id="3ee96-135">Вы получите начальное подтверждение, когда мы получим ваш запрос и окончательное подтверждение после его завершения.</span><span class="sxs-lookup"><span data-stu-id="3ee96-135">You will receive an initial acknowledgment when we’ve received your request and a final acknowledgment once it has been completed.</span></span>
