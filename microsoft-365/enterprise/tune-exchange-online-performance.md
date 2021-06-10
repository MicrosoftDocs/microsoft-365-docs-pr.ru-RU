---
title: Настройка производительности Exchange Online
ms.author: krowley
author: tracyp
manager: laurawi
ms.date: 12/14/2017
audience: Admin
ms.topic: troubleshooting
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom: Adm_O365
ms.assetid: 026e83cb-a945-4543-97b0-a8af6e80ac61
description: В этой статье содержатся общие советы и ссылки на другие ресурсы, которые рассказывают о том, как повысить производительность Exchange Online.
ms.openlocfilehash: a7d3268f9f3cf1922319b03cf69d3f044272b27f
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50909446"
---
# <a name="tune-exchange-online-performance"></a><span data-ttu-id="057d5-103">Настройка производительности Exchange Online</span><span class="sxs-lookup"><span data-stu-id="057d5-103">Tune Exchange Online performance</span></span>

<span data-ttu-id="057d5-104">В этой статье содержатся общие советы и ссылки на другие ресурсы, которые рассказывают о том, как повысить производительность Exchange Online, особенно перед миграцией.</span><span class="sxs-lookup"><span data-stu-id="057d5-104">This article contains general tips and links to other resources that tell you how to improve performance of Exchange Online, particularly in front of a migration.</span></span> <span data-ttu-id="057d5-105">Эта статья является частью [сетевого планирования и](./network-planning-and-performance.md) настройки производительности для Office 365 проекта.</span><span class="sxs-lookup"><span data-stu-id="057d5-105">This article is part of the [Network planning and performance tuning for Office 365](./network-planning-and-performance.md) project.</span></span>
   
## <a name="things-to-consider-in-order-to-improve-exchange-online-performance"></a><span data-ttu-id="057d5-106">Что следует учитывать для повышения Exchange Online производительности</span><span class="sxs-lookup"><span data-stu-id="057d5-106">Things to consider in order to improve Exchange Online performance</span></span>

<span data-ttu-id="057d5-107">Чтобы повысить скорость миграции и уменьшить ограничения пропускной способности вашей организации для Exchange Online, рассмотрим следующее:</span><span class="sxs-lookup"><span data-stu-id="057d5-107">To improve the speed of migration and reduce your organization's bandwidth constraints for Exchange Online, consider the following:</span></span>
  
- <span data-ttu-id="057d5-108">**Уменьшите размеры почтовых ящиков.**</span><span class="sxs-lookup"><span data-stu-id="057d5-108">**Reduce mailbox sizes.**</span></span> <span data-ttu-id="057d5-109">Меньший размер почтового ящика повышает скорость миграции.</span><span class="sxs-lookup"><span data-stu-id="057d5-109">Smaller mailbox size improves migration speed.</span></span> 
    
- <span data-ttu-id="057d5-110">**Используйте возможности перемещения почтовых ящиков с помощью Exchange гибридного развертывания.**</span><span class="sxs-lookup"><span data-stu-id="057d5-110">**Use the mailbox move capabilities with an Exchange hybrid deployment.**</span></span> <span data-ttu-id="057d5-111">С помощью Exchange гибридного развертывания, автономной почты (в виде . Ost files) не требует повторной загрузки при миграции в Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="057d5-111">With an Exchange hybrid deployment, offline mail (in the form of .OST files) does not require re-download when migrating to Exchange Online.</span></span> <span data-ttu-id="057d5-112">Это значительно снижает требования к пропускной способности загрузки.</span><span class="sxs-lookup"><span data-stu-id="057d5-112">This significantly reduces your download bandwidth requirements.</span></span> 
    
- <span data-ttu-id="057d5-113">**Расписание перемещения почтовых ящиков в периоды низкого трафика в Интернете и низкого локального Exchange использования.**</span><span class="sxs-lookup"><span data-stu-id="057d5-113">**Schedule mailbox moves to occur during periods of low Internet traffic and low on-premises Exchange use.**</span></span> <span data-ttu-id="057d5-114">При переносе планирования запросы на перенос будут отправлены в прокси-сервер репликации почтовых ящиков и могут происходить не сразу.</span><span class="sxs-lookup"><span data-stu-id="057d5-114">When scheduling moves, migration requests are submitted to the mailbox replication proxy and may not take place immediately.</span></span> 
    
- <span data-ttu-id="057d5-115">**Используйте постные всплывающие Outlook в Интернете.**</span><span class="sxs-lookup"><span data-stu-id="057d5-115">**Use lean popouts for Outlook on the web.**</span></span> <span data-ttu-id="057d5-116">Нежирные всплывающие компоненты предоставляют меньшие и менее объемные для памяти версии определенных сообщений электронной почты в Microsoft Edge или Internet Explorer, отрисовка некоторых компонентов на сервере.</span><span class="sxs-lookup"><span data-stu-id="057d5-116">Lean popouts provide smaller, less memory-intensive versions of certain email messages in Microsoft Edge or Internet Explorer by rendering some components on the server.</span></span> <span data-ttu-id="057d5-117">Дополнительные сведения см. в книге Использование постных всплывающих выполнивок для уменьшения памяти, используемой [при чтении почтовых сообщений.](https://support.office.com/article/a6d6ba01-2562-4c3d-a8f1-78748dd506cf)</span><span class="sxs-lookup"><span data-stu-id="057d5-117">For more information, see [Use lean popouts to reduce memory used when reading mail messages](https://support.office.com/article/a6d6ba01-2562-4c3d-a8f1-78748dd506cf).</span></span>


## <a name="general-advice"></a><span data-ttu-id="057d5-118">Общие рекомендации</span><span class="sxs-lookup"><span data-stu-id="057d5-118">General advice</span></span>

- <span data-ttu-id="057d5-119">Убедитесь, что DNS-outlook.office.com входит в центр данных MS в логическом расположении входа для вашего расположения.</span><span class="sxs-lookup"><span data-stu-id="057d5-119">Make certain that DNS lookup for outlook.office.com enters the MS-datacenter at a logical entry location for your location.</span></span>

- <span data-ttu-id="057d5-120">Исследование кэшинга почтовых ящиков и выбор соответствующих параметров (re.</span><span class="sxs-lookup"><span data-stu-id="057d5-120">Research mailbox caching and choose the appropriate options (re.</span></span> <span data-ttu-id="057d5-121">период кэшинга, общего кэшинга почтовых ящиков и т. п.).</span><span class="sxs-lookup"><span data-stu-id="057d5-121">caching period, shared mailbox caching, et cetera).</span></span>

- <span data-ttu-id="057d5-122">Не Outlook данные о передаче VPN-подключений (в центральный офис) перед передачей через Интернет.</span><span class="sxs-lookup"><span data-stu-id="057d5-122">Keep your Outlook data from passing over VPN connections (to a central office) before it goes over the Internet.</span></span>

- <span data-ttu-id="057d5-123">Убедитесь, что данные почтовых ящиков соблюдают ограничения на папку и количество элементов.</span><span class="sxs-lookup"><span data-stu-id="057d5-123">Be sure your mailbox data adheres to the limitations on folder, and item, amounts.</span></span>
    
<span data-ttu-id="057d5-124">Дополнительные сведения о производительности Exchange миграции см. в Office 365 производительности миграции [и лучших практиках.](https://support.office.com/article/d9acb371-fd6c-4c14-aa8e-db5cbe39aa57)</span><span class="sxs-lookup"><span data-stu-id="057d5-124">For more information about Exchange migration performance, see [Office 365 migration performance and best practices](https://support.office.com/article/d9acb371-fd6c-4c14-aa8e-db5cbe39aa57).</span></span>
