---
title: Настройка политик защиты от нежелательной почты
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 6/9/2015
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 31279431-828d-48bd-b979-20b6de15fa4a
ms.collection:
- M365-security-compliance
description: Фильтрация нежелательных сообщений настраивается автоматически для всей компании с помощью политик блокировки таких сообщений (фильтр подключения, фильтр нежелательной почты и фильтр исходящих нежелательных сообщений). Как администратор вы можете просматривать и изменять, но не удалять, политики защиты от нежелательных сообщений так, чтобы они максимально удовлетворяли потребности вашей организации. Для большей детализации можно также создать настраиваемые политики и применять их к определенным пользователям, группам и доменам в организации. По умолчанию пользовательские политики имеют более высокий приоритет, чем политики по умолчанию, однако приоритет политик можно менять.
ms.openlocfilehash: 2ee5833bf476123a84411a7ad645b9f8c5d0b2b8
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "41599586"
---
# <a name="configure-the-anti-spam-policies"></a><span data-ttu-id="7d042-106">Настройка политик защиты от нежелательной почты</span><span class="sxs-lookup"><span data-stu-id="7d042-106">Configure the anti-spam policies</span></span>

<span data-ttu-id="7d042-p102">Фильтрация нежелательных сообщений настраивается автоматически для всей компании с помощью политик блокировки таких сообщений (фильтр подключения, фильтр нежелательной почты и фильтр исходящих нежелательных сообщений). Как администратор вы можете просматривать и изменять, но не удалять, политики защиты от нежелательных сообщений так, чтобы они максимально удовлетворяли потребности вашей организации. Для большей детализации можно также создать настраиваемые политики и применять их к определенным пользователям, группам и доменам в организации. По умолчанию пользовательские политики имеют более высокий приоритет, чем политики по умолчанию, однако приоритет политик можно менять.</span><span class="sxs-lookup"><span data-stu-id="7d042-p102">Spam filtering is automatically enabled company-wide through the default anti-spam policies (connection filter, spam filter, and outbound spam). As an administrator, you can view and edit, but not delete, the default anti-spam policies so that they are tailored to best meet the needs of your organization. For greater granularity, you can also create custom policies and apply them to specified users, groups, or domains in your organization. By default, custom policies take precedence over the default policy, but you can change the priority of your policies.</span></span> 
  
<span data-ttu-id="7d042-111">Дополнительные сведения о настройке политик защиты от нежелательной почты см в следующих статьях:</span><span class="sxs-lookup"><span data-stu-id="7d042-111">For more about configuring your anti-spam policies, see the following topics:</span></span>
  
[<span data-ttu-id="7d042-112">Настройка политики фильтров подключений</span><span class="sxs-lookup"><span data-stu-id="7d042-112">Configure the connection filter policy</span></span>](configure-the-connection-filter-policy.md)
  
[<span data-ttu-id="7d042-113">Настройте политики защиты от спама</span><span class="sxs-lookup"><span data-stu-id="7d042-113">Configure your spam filter policies</span></span>](configure-your-spam-filter-policies.md)
  
> [!IMPORTANT]
> <span data-ttu-id="7d042-114">Для автономных клиентов EOP: по умолчанию фильтры содержимого EOP отправляют нежелательные сообщения в папку нежелательной почты каждого получателя.</span><span class="sxs-lookup"><span data-stu-id="7d042-114">For EOP standalone customers: By default, the EOP content filters send spam-detected messages to each recipients' Junk Email folder.</span></span> <span data-ttu-id="7d042-115">Однако чтобы убедиться, что действие **переместить сообщение в папку нежелательной почты** будет работать с локальными почтовыми ящиками, необходимо настроить два правила для обработки почты Exchange (которые также называются правилами транспорта) на локальных серверах, чтобы обнаружить заголовки нежелательной почты, добавленные EOP.</span><span class="sxs-lookup"><span data-stu-id="7d042-115">However, in order to ensure that the **Move message to Junk Email folder** action will work with on-premises mailboxes, you must configure two Exchange mail flow rules (also known as transport rules) on your on-premises servers to detect spam headers added by EOP.</span></span> <span data-ttu-id="7d042-116">Подробнее о том, что нежелательная [почта направляется в папку нежелательной почты каждого пользователя](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md).</span><span class="sxs-lookup"><span data-stu-id="7d042-116">For details, see [Ensure that spam is routed to each user's Junk Email folder](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md).</span></span> 
  
[<span data-ttu-id="7d042-117">Настройка правил защиты от спама для исходящих сообщений</span><span class="sxs-lookup"><span data-stu-id="7d042-117">Configure the outbound spam policy</span></span>](configure-the-outbound-spam-policy.md)
  

