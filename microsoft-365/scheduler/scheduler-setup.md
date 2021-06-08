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
ms.openlocfilehash: c17cdbbf71359a2725a3b0a145cba5feffd7c853
ms.sourcegitcommit: e1e275eb88153bafddf93327adf8f82318913a8d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2021
ms.locfileid: "52809195"
---
# <a name="setting-up-scheduler-for-microsoft-365"></a><span data-ttu-id="a3852-103">Настройка scheduler для Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="a3852-103">Setting up Scheduler for Microsoft 365</span></span>

<span data-ttu-id="a3852-104">Чтобы настроить планировщик для Microsoft 365, необходимо следующее:</span><span class="sxs-lookup"><span data-stu-id="a3852-104">To set up the Scheduler for Microsoft 365, following are the prerequisites:</span></span>

|<span data-ttu-id="a3852-105">**Что мне нужно?**</span><span class="sxs-lookup"><span data-stu-id="a3852-105">**What do I need?**</span></span> |<span data-ttu-id="a3852-106">**Описание**</span><span class="sxs-lookup"><span data-stu-id="a3852-106">**Description**</span></span> |
|-------------------|-------------|
|<span data-ttu-id="a3852-107">Почтовый ящик Кортаны</span><span class="sxs-lookup"><span data-stu-id="a3852-107">Cortana mailbox</span></span> |<span data-ttu-id="a3852-108">Администраторам клиентов необходимо настроить почтовый ящик в качестве почтового ящика "Кортана" (то есть cortana@yourdomain.com).</span><span class="sxs-lookup"><span data-stu-id="a3852-108">Tenant admins will need to set a mailbox to serve as the “Cortana” mailbox (that is, cortana@yourdomain.com).</span></span>         |
|<span data-ttu-id="a3852-109">Почтовый ящик Exchange Online</span><span class="sxs-lookup"><span data-stu-id="a3852-109">Exchange Online mailbox</span></span> |<span data-ttu-id="a3852-110">Пользователи должны иметь Exchange Online и календарь</span><span class="sxs-lookup"><span data-stu-id="a3852-110">Users must have an Exchange Online mail and calendar</span></span>         |
|<span data-ttu-id="a3852-111">Лицензия планировщика</span><span class="sxs-lookup"><span data-stu-id="a3852-111">Scheduler license</span></span> |<span data-ttu-id="a3852-112">Сведения о лицензировании и ценах [см.](https://www.microsoft.com/microsoft-365/meeting-scheduler-pricing)в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a3852-112">For licensing and pricing information, see [Scheduler for Microsoft 365](https://www.microsoft.com/microsoft-365/meeting-scheduler-pricing).</span></span>        |

## <a name="create-a-mailbox-for-cortana"></a><span data-ttu-id="a3852-113">Создание почтового ящика для Кортаны</span><span class="sxs-lookup"><span data-stu-id="a3852-113">Create a mailbox for Cortana</span></span>
<span data-ttu-id="a3852-114">Почтовый Exchange в клиенте выступает в качестве почтового ящика Кортаны для клиента для отправки и получения сообщений электронной почты в Кортану и из нее.</span><span class="sxs-lookup"><span data-stu-id="a3852-114">An Exchange mailbox in your tenant acts as the Cortana mailbox for your tenant to send and receive emails to and from Cortana.</span></span> <span data-ttu-id="a3852-115">Все электронные письма, отправленные в Кортана, сохраняются в почтовом ящике кортаны клиента на основе политики хранения.</span><span class="sxs-lookup"><span data-stu-id="a3852-115">All emails sent to Cortana are retained in your tenant’s Cortana mailbox based on your retention policy.</span></span>

- <span data-ttu-id="a3852-116">Используйте центр администрирования Microsoft 365 для создания почтового ящика пользователя.</span><span class="sxs-lookup"><span data-stu-id="a3852-116">Use the Microsoft 365 admin center to create a user mailbox.</span></span> <span data-ttu-id="a3852-117">Рекомендуется использовать 30-дневную политику хранения.</span><span class="sxs-lookup"><span data-stu-id="a3852-117">A 30-day retention policy is recommended.</span></span> 
- <span data-ttu-id="a3852-118">Используйте имя Кортана в основном SMTP-адресе почтового ящика.</span><span class="sxs-lookup"><span data-stu-id="a3852-118">Use the name Cortana in your mailbox’s primary SMTP address.</span></span> <span data-ttu-id="a3852-119">Рекомендуется использовать такие имена, как Cortana@yourdomain.com, CortanaScheduler@contoso.com или Cortana.Scheduler@yourdomain.com.</span><span class="sxs-lookup"><span data-stu-id="a3852-119">Names such as “Cortana@yourdomain.com,’ ‘CortanaScheduler@contoso.com,’ or ‘Cortana.Scheduler@yourdomain.com’ are recommended.</span></span>

## <a name="designate-the-mailbox-as-the-scheduler-assistant"></a><span data-ttu-id="a3852-120">Назначь почтовый ящик помощником планировщика</span><span class="sxs-lookup"><span data-stu-id="a3852-120">Designate the mailbox as the Scheduler Assistant</span></span>

<span data-ttu-id="a3852-121">После создания уникального почтового ящика для календаря Кортаны необходимо назначить почтовый ящик Microsoft 365 формально.</span><span class="sxs-lookup"><span data-stu-id="a3852-121">After a unique mailbox for Cortana Scheduler has been created, you must designate the mailbox to Microsoft 365 formally.</span></span> <span data-ttu-id="a3852-122">После того как вы назначите почтовый ящик Планер Кортаны, он будет доступен для расписания собраний от имени пользователей.</span><span class="sxs-lookup"><span data-stu-id="a3852-122">After you designate the Cortana Scheduler mailbox, it will be available to schedule meetings on behalf of your users.</span></span>

<span data-ttu-id="a3852-123">Чтобы назначить почтовый ящик Планиров Кортаны, авторизованный администратор должен запустить команду PowerShell с одной линией.</span><span class="sxs-lookup"><span data-stu-id="a3852-123">To designate the Cortana Scheduler mailbox, an authorized admin must run a one-line PowerShell command.</span></span> 

1. <span data-ttu-id="a3852-124">Подключение для Microsoft 365 PowerShell для запуска пространства для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="a3852-124">Connect to Microsoft 365 remote PowerShell run space for your organization.</span></span>
2. <span data-ttu-id="a3852-125">Запустите следующий скрипт PowerShell, чтобы назначить почтовый ящик для Scheduler:</span><span class="sxs-lookup"><span data-stu-id="a3852-125">Run the following PowerShell script to designate the mailbox for Scheduler:</span></span>

```powershell

Set-mailbox cortana@contoso.com -SchedulerAssistant:$true

```

<span data-ttu-id="a3852-126">После запуска этой "наборной" команды в почтовом ящике Планиров кортаны на почтовом ящике установлен новый "PersistedCapability", чтобы отметить, что этот почтовый ящик является "SchedulerAssistant".</span><span class="sxs-lookup"><span data-stu-id="a3852-126">After running this "set" command on the Cortana Scheduler mailbox, a new "PersistedCapability" is set on the mailbox to note that this mailbox is the "SchedulerAssistant".</span></span>

> [!NOTE]
> <span data-ttu-id="a3852-127">Выполните следующие действия, чтобы подключить организацию к PowerShell, если вы ранее этого не делали: Подключение Microsoft 365 [с PowerShell - Microsoft 365 корпоративный | Документы Майкрософт](../enterprise/connect-to-microsoft-365-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="a3852-127">Follow these steps to connect your organization to PowerShell if you’ve not done so previously: [Connect to Microsoft 365 with PowerShell - Microsoft 365 Enterprise | Microsoft Docs](../enterprise/connect-to-microsoft-365-powershell.md)</span></span>

<span data-ttu-id="a3852-128">Чтобы узнать, какой почтовый ящик в организации в настоящее время задан в качестве помощника планиров Кортаны, запустите функцию get:</span><span class="sxs-lookup"><span data-stu-id="a3852-128">To discover which mailbox in your organization is currently set as the Cortana Scheduler assistant, run the get function:</span></span>
 
```powershell

Get-mailbox -Organization contoso.com | where {($_.PersistedCapabilities -like "SchedulerAssistant")}

```

> [!IMPORTANT]
> <span data-ttu-id="a3852-129">Чтобы выполнить полную подготовка к набору возможности SchedulerAssistant, почтовому ящику Scheduler может потребоваться до двух часов.</span><span class="sxs-lookup"><span data-stu-id="a3852-129">It might take up to two hours for the Scheduler mailbox to complete full provisioning to set the SchedulerAssistant capability.</span></span>

## <a name="exchange-online-mailbox"></a><span data-ttu-id="a3852-130">Почтовый ящик Exchange Online</span><span class="sxs-lookup"><span data-stu-id="a3852-130">Exchange Online mailbox</span></span>
<span data-ttu-id="a3852-131">Scheduler — это надстройка для Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a3852-131">Scheduler is an add-on to Microsoft 365.</span></span> <span data-ttu-id="a3852-132">Организаторы собраний должны иметь Exchange Online почтовый ящик и календарь для работы scheduler.</span><span class="sxs-lookup"><span data-stu-id="a3852-132">Meeting organizers must have an Exchange Online mailbox and calendar for Scheduler to work.</span></span>

## <a name="exchange-requirements"></a><span data-ttu-id="a3852-133">Требования для Exchange</span><span class="sxs-lookup"><span data-stu-id="a3852-133">Exchange requirements</span></span>

<span data-ttu-id="a3852-134">В дополнение к лицензированию Scheduler необходимо иметь одну из следующих лицензий:</span><span class="sxs-lookup"><span data-stu-id="a3852-134">In addition to licensing Scheduler, you must have one of the following licenses:</span></span>

- <span data-ttu-id="a3852-135">Microsoft 365 E3, A3, E5, A5</span><span class="sxs-lookup"><span data-stu-id="a3852-135">Microsoft 365 E3, A3, E5, A5</span></span>
- <span data-ttu-id="a3852-136">Business Basic, Business, Business Standard, Business Premium</span><span class="sxs-lookup"><span data-stu-id="a3852-136">Business Basic, Business, Business Standard, Business Premium</span></span>
- <span data-ttu-id="a3852-137">Office 365 E1, A1, E3, A3, E5, A5</span><span class="sxs-lookup"><span data-stu-id="a3852-137">Office 365 E1, A1, E3, A3, E5, A5</span></span>
- <span data-ttu-id="a3852-138">Основные бизнес-Premium</span><span class="sxs-lookup"><span data-stu-id="a3852-138">Business Essentials, Business Premium</span></span>
- <span data-ttu-id="a3852-139">Exchange Online Лицензия plan 1 или Plan 2.</span><span class="sxs-lookup"><span data-stu-id="a3852-139">Exchange Online Plan 1 or Plan 2 license.</span></span> 

> [!Note]
> <span data-ttu-id="a3852-140">**Планировка Microsoft 365** недоступна для пользователей Office 365 21Vianet в Китае.</span><span class="sxs-lookup"><span data-stu-id="a3852-140">**Scheduler for Microsoft 365** isn't available for users of Office 365 operated by 21Vianet in China.</span></span> <span data-ttu-id="a3852-141">Он также не доступен для пользователей Microsoft 365 с немецким облаком, использующим доверяемого данным немецкого Telekom.</span><span class="sxs-lookup"><span data-stu-id="a3852-141">It's also not available for users of Microsoft 365 with the German cloud that uses the data trustee German Telekom.</span></span> <span data-ttu-id="a3852-142">Средство поддерживается для пользователей в Германии, чьи данные хранятся не в немецком центре обработки данных.</span><span class="sxs-lookup"><span data-stu-id="a3852-142">It is supported for users in Germany whose data location isn't in the German datacenter.</span></span>
>
><span data-ttu-id="a3852-143">Эта функция также не поддерживается для пользователей облака для государственных организаций, включая GCC, Consumer, GCC High и DoD.</span><span class="sxs-lookup"><span data-stu-id="a3852-143">This feature is also not supported for users of the Government Cloud, including GCC, Consumer, GCC High, or DoD.</span></span>
