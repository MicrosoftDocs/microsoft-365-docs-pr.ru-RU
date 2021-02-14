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
description: Эта статья содержит общие советы и ссылки на другие ресурсы, которые помогут вам повысить производительность Exchange Online.
ms.openlocfilehash: 495b662aa6ef247a5751febbf2d50e1c1f21a44e
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/14/2020
ms.locfileid: "46693397"
---
# <a name="tune-exchange-online-performance"></a><span data-ttu-id="edc67-103">Настройка производительности Exchange Online</span><span class="sxs-lookup"><span data-stu-id="edc67-103">Tune Exchange Online performance</span></span>

<span data-ttu-id="edc67-104">Эта статья содержит общие советы и ссылки на другие ресурсы, которые помогут вам повысить производительность Exchange Online, особенно перед миграцией.</span><span class="sxs-lookup"><span data-stu-id="edc67-104">This article contains general tips and links to other resources that tell you how to improve performance of Exchange Online, particularly in front of a migration.</span></span> <span data-ttu-id="edc67-105">Эта статья входит в состав проекта "Планирование сети и [настройка производительности для Office 365".](https://aka.ms/tune)</span><span class="sxs-lookup"><span data-stu-id="edc67-105">This article is part of the [Network planning and performance tuning for Office 365](https://aka.ms/tune) project.</span></span>
   
## <a name="things-to-consider-in-order-to-improve-exchange-online-performance"></a><span data-ttu-id="edc67-106">Что следует учитывать для повышения производительности Exchange Online</span><span class="sxs-lookup"><span data-stu-id="edc67-106">Things to consider in order to improve Exchange Online performance</span></span>

<span data-ttu-id="edc67-107">Чтобы повысить скорость миграции и уменьшить ограничения пропускной способности организации для Exchange Online, рассмотрите следующие вопросы:</span><span class="sxs-lookup"><span data-stu-id="edc67-107">To improve the speed of migration and reduce your organization's bandwidth constraints for Exchange Online, consider the following:</span></span>
  
- <span data-ttu-id="edc67-108">**Уменьшите размеры почтовых ящиков.**</span><span class="sxs-lookup"><span data-stu-id="edc67-108">**Reduce mailbox sizes.**</span></span> <span data-ttu-id="edc67-109">Меньший размер почтового ящика повышает скорость миграции.</span><span class="sxs-lookup"><span data-stu-id="edc67-109">Smaller mailbox size improves migration speed.</span></span> 
    
- <span data-ttu-id="edc67-110">**Используйте возможности перемещения почтовых ящиков в гибридном развертывании Exchange.**</span><span class="sxs-lookup"><span data-stu-id="edc67-110">**Use the mailbox move capabilities with an Exchange hybrid deployment.**</span></span> <span data-ttu-id="edc67-111">При гибридном развертывании Exchange автономный почтовый ящик (в формате . OST-файлы) не требуют повторной загрузки при миграции в Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="edc67-111">With an Exchange hybrid deployment, offline mail (in the form of .OST files) does not require re-download when migrating to Exchange Online.</span></span> <span data-ttu-id="edc67-112">Это значительно снижает требования к пропускной способности загрузки.</span><span class="sxs-lookup"><span data-stu-id="edc67-112">This significantly reduces your download bandwidth requirements.</span></span> 
    
- <span data-ttu-id="edc67-113">**Запланировать перемещение почтовых ящиков в периоды низкой стоимости интернет-трафика и низкого использования локальной сети Exchange.**</span><span class="sxs-lookup"><span data-stu-id="edc67-113">**Schedule mailbox moves to occur during periods of low Internet traffic and low on-premises Exchange use.**</span></span> <span data-ttu-id="edc67-114">При планировании перемещения запросы на миграцию будут отправлены на прокси-сервер репликации почтовых ящиков и могут происходить не сразу.</span><span class="sxs-lookup"><span data-stu-id="edc67-114">When scheduling moves, migration requests are submitted to the mailbox replication proxy and may not take place immediately.</span></span> 
    
- <span data-ttu-id="edc67-115">**Используйте нежирные всплывающие окни для Outlook в Интернете.**</span><span class="sxs-lookup"><span data-stu-id="edc67-115">**Use lean popouts for Outlook on the web.**</span></span> <span data-ttu-id="edc67-116">Нежирные всплывающие элементы предоставляют меньшие и менее объемные в памяти версии определенных сообщений электронной почты в Microsoft Edge или Internet Explorer путем отрисовки некоторых компонентов на сервере.</span><span class="sxs-lookup"><span data-stu-id="edc67-116">Lean popouts provide smaller, less memory-intensive versions of certain email messages in Microsoft Edge or Internet Explorer by rendering some components on the server.</span></span> <span data-ttu-id="edc67-117">Дополнительные сведения см. в дополнительных сведениях о том, как уменьшить объем памяти, используемой при чтении сообщений [электронной почты.](https://support.office.com/article/a6d6ba01-2562-4c3d-a8f1-78748dd506cf)</span><span class="sxs-lookup"><span data-stu-id="edc67-117">For more information, see [Use lean popouts to reduce memory used when reading mail messages](https://support.office.com/article/a6d6ba01-2562-4c3d-a8f1-78748dd506cf).</span></span>


## <a name="general-advice"></a><span data-ttu-id="edc67-118">Общие советы</span><span class="sxs-lookup"><span data-stu-id="edc67-118">General advice</span></span>

- <span data-ttu-id="edc67-119">Убедитесь, что DNS-outlook.office.com в центр данных MS входит в расположение логической записи.</span><span class="sxs-lookup"><span data-stu-id="edc67-119">Make certain that DNS lookup for outlook.office.com enters the MS-datacenter at a logical entry location for your location.</span></span>

- <span data-ttu-id="edc67-120">Исследование кэша почтовых ящиков и выбор соответствующих параметров (re.</span><span class="sxs-lookup"><span data-stu-id="edc67-120">Research mailbox caching and choose the appropriate options (re.</span></span> <span data-ttu-id="edc67-121">период кэшинга, кэшинг общих почтовых ящиков и т. п.);</span><span class="sxs-lookup"><span data-stu-id="edc67-121">caching period, shared mailbox caching, et cetera).</span></span>

- <span data-ttu-id="edc67-122">Не передавая данные Outlook через VPN-подключения (в центральный офис), прежде чем они будут проходить через Интернет.</span><span class="sxs-lookup"><span data-stu-id="edc67-122">Keep your Outlook data from passing over VPN connections (to a central office) before it goes over the Internet.</span></span>

- <span data-ttu-id="edc67-123">Убедитесь, что данные почтового ящика соблюдают ограничения на количество папок и элементов.</span><span class="sxs-lookup"><span data-stu-id="edc67-123">Be sure your mailbox data adheres to the limitations on folder, and item, amounts.</span></span>
    
<span data-ttu-id="edc67-124">Дополнительные сведения о производительности миграции Exchange см. в сведениях о производительности миграции [Office 365 и практических методиках.](https://support.office.com/article/d9acb371-fd6c-4c14-aa8e-db5cbe39aa57)</span><span class="sxs-lookup"><span data-stu-id="edc67-124">For more information about Exchange migration performance, see [Office 365 migration performance and best practices](https://support.office.com/article/d9acb371-fd6c-4c14-aa8e-db5cbe39aa57).</span></span>
  

