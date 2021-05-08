---
title: Настройка scheduler для Microsoft 365.
ms.author: v-aiyengar
author: AshaIyengar21
manager: serdars
audience: Admin
ms.topic: article
ms.service: scheduler
localization_priority: Normal
description: Настройка scheduler для Microsoft 365.
ms.openlocfilehash: 79e1596288836770c720cb312580fc706bb7b95f
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2021
ms.locfileid: "52286254"
---
# <a name="setting-up-scheduler-for-microsoft-365"></a><span data-ttu-id="9c5ba-103">Настройка scheduler для Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="9c5ba-103">Setting up Scheduler for Microsoft 365</span></span>

<span data-ttu-id="9c5ba-104">Чтобы настроить планировщик для Microsoft 365, необходимо следующее:</span><span class="sxs-lookup"><span data-stu-id="9c5ba-104">To set up the Scheduler for Microsoft 365, following are the prerequisites:</span></span>

|<span data-ttu-id="9c5ba-105">**Что мне нужно?**</span><span class="sxs-lookup"><span data-stu-id="9c5ba-105">**What do I need?**</span></span> |<span data-ttu-id="9c5ba-106">**Описание**</span><span class="sxs-lookup"><span data-stu-id="9c5ba-106">**Description**</span></span> |
|-------------------|-------------|
|<span data-ttu-id="9c5ba-107">Почтовый ящик Кортаны</span><span class="sxs-lookup"><span data-stu-id="9c5ba-107">Cortana mailbox</span></span> |<span data-ttu-id="9c5ba-108">Администраторам клиентов необходимо настроить почтовый ящик в качестве почтового ящика "Кортана" (то есть cortana@yourdomain.com).</span><span class="sxs-lookup"><span data-stu-id="9c5ba-108">Tenant admins will need to set a mailbox to serve as the “Cortana” mailbox (that is, cortana@yourdomain.com).</span></span>         |
|<span data-ttu-id="9c5ba-109">Почтовый ящик Exchange Online</span><span class="sxs-lookup"><span data-stu-id="9c5ba-109">Exchange Online mailbox</span></span> |<span data-ttu-id="9c5ba-110">Пользователи должны иметь Exchange Online и календарь</span><span class="sxs-lookup"><span data-stu-id="9c5ba-110">Users must have an Exchange Online mail and calendar</span></span>         |
|<span data-ttu-id="9c5ba-111">Лицензия планировщика</span><span class="sxs-lookup"><span data-stu-id="9c5ba-111">Scheduler license</span></span> |<span data-ttu-id="9c5ba-112">Сведения о лицензировании и ценах [см.](https://www.microsoft.com/microsoft-365/meeting-scheduler-pricing)в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="9c5ba-112">For licensing and pricing information, see [Scheduler for Microsoft 365](https://www.microsoft.com/microsoft-365/meeting-scheduler-pricing).</span></span>        |

## <a name="create-a-mailbox-for-cortana"></a><span data-ttu-id="9c5ba-113">Создание почтового ящика для Кортаны</span><span class="sxs-lookup"><span data-stu-id="9c5ba-113">Create a mailbox for Cortana</span></span>
<span data-ttu-id="9c5ba-114">Почтовый Exchange в клиенте выступает в качестве почтового ящика Кортаны для клиента для отправки и получения сообщений электронной почты в Кортану и из нее.</span><span class="sxs-lookup"><span data-stu-id="9c5ba-114">An Exchange mailbox in your tenant acts as the Cortana mailbox for your tenant to send and receive emails to and from Cortana.</span></span> <span data-ttu-id="9c5ba-115">Все электронные письма, отправленные в Кортана, сохраняются в почтовом ящике кортаны клиента на основе политики хранения.</span><span class="sxs-lookup"><span data-stu-id="9c5ba-115">All emails sent to Cortana are retained in your tenant’s Cortana mailbox based on your retention policy.</span></span>

- <span data-ttu-id="9c5ba-116">Используйте центр администрирования Microsoft 365 для создания нового почтового ящика.</span><span class="sxs-lookup"><span data-stu-id="9c5ba-116">Use the Microsoft 365 admin center to create a new mailbox.</span></span> <span data-ttu-id="9c5ba-117">Рекомендуется использовать 30-дневную политику хранения.</span><span class="sxs-lookup"><span data-stu-id="9c5ba-117">A 30-day retention policy is recommended.</span></span> <span data-ttu-id="9c5ba-118">Используйте имя Кортана в основном SMTP-адресе почтового ящика.</span><span class="sxs-lookup"><span data-stu-id="9c5ba-118">Use the name Cortana in your mailbox’s primary SMTP address.</span></span> <span data-ttu-id="9c5ba-119">Рекомендуется использовать такие имена, как Cortana@yourdomain.com, CortanaScheduler@contoso.com или Cortana.Scheduler@yourdomain.com.</span><span class="sxs-lookup"><span data-stu-id="9c5ba-119">Names such as “Cortana@yourdomain.com,’ ‘CortanaScheduler@contoso.com,’ or ‘Cortana.Scheduler@yourdomain.com’ are recommended.</span></span>
- <span data-ttu-id="9c5ba-120">Свяжитесь с корпорацией Майкрософт (scheduler_m365@microsoft.com), чтобы включить почтовый ящик Кортаны.</span><span class="sxs-lookup"><span data-stu-id="9c5ba-120">Contact Microsoft (scheduler_m365@microsoft.com) to enable your Cortana mailbox.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="9c5ba-121">Чтобы настроить почтовый ящик Кортаны для использования службы Scheduler, необходимо связаться с Корпорацией Майкрософт, чтобы он scheduler_m365@microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="9c5ba-121">You must contact Microsoft to configure your Cortana mailbox to use the Scheduler service by emailing scheduler_m365@microsoft.com.</span></span> <span data-ttu-id="9c5ba-122">Включение почтового ящика Кортаны может занять до двух недель.</span><span class="sxs-lookup"><span data-stu-id="9c5ba-122">Enabling your Cortana mailbox may take up to two weeks.</span></span>

## <a name="exchange-online-mailbox"></a><span data-ttu-id="9c5ba-123">Почтовый ящик Exchange Online</span><span class="sxs-lookup"><span data-stu-id="9c5ba-123">Exchange Online mailbox</span></span>
<span data-ttu-id="9c5ba-124">Scheduler — это надстройка для Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="9c5ba-124">Scheduler is an add-on to Microsoft 365.</span></span> <span data-ttu-id="9c5ba-125">Организаторы собраний должны иметь Exchange Online почтовый ящик и календарь для работы scheduler.</span><span class="sxs-lookup"><span data-stu-id="9c5ba-125">Meeting organizers must have an Exchange Online mailbox and calendar for Scheduler to work.</span></span>

## <a name="exchange-requirements"></a><span data-ttu-id="9c5ba-126">Требования для Exchange</span><span class="sxs-lookup"><span data-stu-id="9c5ba-126">Exchange requirements</span></span>

<span data-ttu-id="9c5ba-127">В дополнение к лицензированию Scheduler необходимо иметь одну из следующих лицензий:</span><span class="sxs-lookup"><span data-stu-id="9c5ba-127">In addition to licensing Scheduler, you must have one of the following licenses:</span></span>

- <span data-ttu-id="9c5ba-128">Microsoft 365 E3, A3, E5, A5</span><span class="sxs-lookup"><span data-stu-id="9c5ba-128">Microsoft 365 E3, A3, E5, A5</span></span>
- <span data-ttu-id="9c5ba-129">Business Basic, Business, Business Standard, Business Premium</span><span class="sxs-lookup"><span data-stu-id="9c5ba-129">Business Basic, Business, Business Standard, Business Premium</span></span>
- <span data-ttu-id="9c5ba-130">Office 365 E1, A1, E3, A3, E5, A5</span><span class="sxs-lookup"><span data-stu-id="9c5ba-130">Office 365 E1, A1, E3, A3, E5, A5</span></span>
- <span data-ttu-id="9c5ba-131">Основные бизнес-Premium</span><span class="sxs-lookup"><span data-stu-id="9c5ba-131">Business Essentials, Business Premium</span></span>
- <span data-ttu-id="9c5ba-132">Exchange Online Лицензия plan 1 или Plan 2.</span><span class="sxs-lookup"><span data-stu-id="9c5ba-132">Exchange Online Plan 1 or Plan 2 license.</span></span> 

> [!Note]
> <span data-ttu-id="9c5ba-133">**Планировка Microsoft 365** недоступна для пользователей Office 365 21Vianet в Китае.</span><span class="sxs-lookup"><span data-stu-id="9c5ba-133">**Scheduler for Microsoft 365** isn't available for users of Office 365 operated by 21Vianet in China.</span></span> <span data-ttu-id="9c5ba-134">Он также не доступен для пользователей Microsoft 365 с немецким облаком, использующим доверяемого данным немецкого Telekom.</span><span class="sxs-lookup"><span data-stu-id="9c5ba-134">It's also not available for users of Microsoft 365 with the German cloud that uses the data trustee German Telekom.</span></span> <span data-ttu-id="9c5ba-135">Средство поддерживается для пользователей в Германии, чьи данные хранятся не в немецком центре обработки данных.</span><span class="sxs-lookup"><span data-stu-id="9c5ba-135">It is supported for users in Germany whose data location isn't in the German datacenter.</span></span>
>
><span data-ttu-id="9c5ba-136">Эта функция также не поддерживается для пользователей облака для государственных организаций, включая GCC, Consumer, GCC High и DoD.</span><span class="sxs-lookup"><span data-stu-id="9c5ba-136">This feature is also not supported for users of the Government Cloud, including GCC, Consumer, GCC High, or DoD.</span></span>
