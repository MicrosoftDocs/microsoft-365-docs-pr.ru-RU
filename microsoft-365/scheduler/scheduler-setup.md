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
ms.openlocfilehash: 924b25e3d921f402c97632f7475ed5beea98d5c7
ms.sourcegitcommit: f7fbf45af64c5c0727fd5eaab309d20ad097a483
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/09/2021
ms.locfileid: "53362550"
---
# <a name="setting-up-scheduler-for-microsoft-365"></a><span data-ttu-id="4543a-103">Настройка планировщика для Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="4543a-103">Setting up Scheduler for Microsoft 365</span></span>


<span data-ttu-id="4543a-104">Чтобы настроить планировщик для Microsoft 365, необходимо следующее:</span><span class="sxs-lookup"><span data-stu-id="4543a-104">To set up the Scheduler for Microsoft 365, following are the prerequisites:</span></span>

| <span data-ttu-id="4543a-105">Что мне нужно?</span><span class="sxs-lookup"><span data-stu-id="4543a-105">What do I need?</span></span> | <span data-ttu-id="4543a-106">Описание</span><span class="sxs-lookup"><span data-stu-id="4543a-106">Description</span></span> |
|-------------------|-------------|
|<span data-ttu-id="4543a-107">Кортана почтовый ящик</span><span class="sxs-lookup"><span data-stu-id="4543a-107">Cortana mailbox</span></span> |<span data-ttu-id="4543a-108">Администраторам клиента необходимо настроить почтовый ящик в качестве почтового ящика "Кортана" (то есть cortana@yourdomain.com).</span><span class="sxs-lookup"><span data-stu-id="4543a-108">Tenant admins will need to set a mailbox to serve as the “Cortana” mailbox (that is, cortana@yourdomain.com).</span></span>         |
|<span data-ttu-id="4543a-109">Почтовый ящик Exchange Online</span><span class="sxs-lookup"><span data-stu-id="4543a-109">Exchange Online mailbox</span></span> |<span data-ttu-id="4543a-110">Пользователи должны иметь Exchange Online и календарь</span><span class="sxs-lookup"><span data-stu-id="4543a-110">Users must have an Exchange Online mail and calendar</span></span>         |
|<span data-ttu-id="4543a-111">Лицензия планировщика</span><span class="sxs-lookup"><span data-stu-id="4543a-111">Scheduler license</span></span> |<span data-ttu-id="4543a-112">Сведения о лицензировании и ценах [см.](https://www.microsoft.com/en-us/microsoft-365/meeting-scheduler-pricing)в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4543a-112">For licensing and pricing information, see [Scheduler for Microsoft 365](https://www.microsoft.com/en-us/microsoft-365/meeting-scheduler-pricing).</span></span>        |

## <a name="create-a-mailbox-for-cortana"></a><span data-ttu-id="4543a-113">Создание почтового ящика для Кортана</span><span class="sxs-lookup"><span data-stu-id="4543a-113">Create a mailbox for Cortana</span></span>

<span data-ttu-id="4543a-114">Почтовый Exchange в клиенте выступает в качестве Кортана для клиента для отправки и получения сообщений электронной почты в Кортана.</span><span class="sxs-lookup"><span data-stu-id="4543a-114">An Exchange mailbox in your tenant acts as the Cortana mailbox for your tenant to send and receive emails to and from Cortana.</span></span> <span data-ttu-id="4543a-115">Все электронные сообщения, отправленные Кортана, сохраняются в почтовом ящике Кортана клиента на основе политики хранения.</span><span class="sxs-lookup"><span data-stu-id="4543a-115">All emails sent to Cortana are retained in your tenant’s Cortana mailbox based on your retention policy.</span></span>

- <span data-ttu-id="4543a-116">Используйте Центр администрирования Microsoft 365 для создания почтового ящика пользователя.</span><span class="sxs-lookup"><span data-stu-id="4543a-116">Use the Microsoft 365 admin center to create a user mailbox.</span></span> <span data-ttu-id="4543a-117">Рекомендуется использовать 30-дневную политику хранения.</span><span class="sxs-lookup"><span data-stu-id="4543a-117">A 30-day retention policy is recommended.</span></span> 
- <span data-ttu-id="4543a-118">Используйте имя Кортана в основном SMTP-адресе почтового ящика.</span><span class="sxs-lookup"><span data-stu-id="4543a-118">Use the name Cortana in your mailbox’s primary SMTP address.</span></span> <span data-ttu-id="4543a-119">Такие имена, как "Кортана@yourdomain.com", "CortanaScheduler@contoso.com", "Кортана". Scheduler@yourdomain.com рекомендуется.</span><span class="sxs-lookup"><span data-stu-id="4543a-119">Names such as “Cortana@yourdomain.com,’ ‘CortanaScheduler@contoso.com,’ or ‘Cortana.Scheduler@yourdomain.com’ are recommended.</span></span>

## <a name="designate-the-mailbox-as-the-scheduler-assistant"></a><span data-ttu-id="4543a-120">Назначь почтовый ящик помощником планировщика</span><span class="sxs-lookup"><span data-stu-id="4543a-120">Designate the mailbox as the Scheduler Assistant</span></span>

<span data-ttu-id="4543a-121">После создания уникального почтового ящика Кортана scheduler необходимо назначить почтовый ящик для Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4543a-121">After a unique mailbox for Cortana Scheduler has been created, you must designate the mailbox to Microsoft 365 formally.</span></span> <span data-ttu-id="4543a-122">После того как вы назначите Кортана scheduler, он будет доступен для расписания собраний от имени пользователей.</span><span class="sxs-lookup"><span data-stu-id="4543a-122">After you designate the Cortana Scheduler mailbox, it will be available to schedule meetings on behalf of your users.</span></span>

<span data-ttu-id="4543a-123">Чтобы назначить Кортана scheduler, авторизованный администратор должен запустить команду PowerShell с одной линией.</span><span class="sxs-lookup"><span data-stu-id="4543a-123">To designate the Cortana Scheduler mailbox, an authorized admin must run a one-line PowerShell command.</span></span> 

1. <span data-ttu-id="4543a-124">Подключение для Microsoft 365 PowerShell для запуска пространства для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="4543a-124">Connect to Microsoft 365 remote PowerShell run space for your organization.</span></span>

2. <span data-ttu-id="4543a-125">Запустите следующий скрипт PowerShell, чтобы назначить почтовый ящик для Scheduler:</span><span class="sxs-lookup"><span data-stu-id="4543a-125">Run the following PowerShell script to designate the mailbox for Scheduler:</span></span>

    ```powershell
    Set-mailbox cortana@contoso.com -SchedulerAssistant:$true
    ```
    
    <span data-ttu-id="4543a-126">После запуска этой команды "set" в почтовом ящике Кортана Scheduler на почтовом ящике установлена новая "PersistedCapability", чтобы отметить, что этот почтовый ящик является "SchedulerAssistant".</span><span class="sxs-lookup"><span data-stu-id="4543a-126">After running this "set" command on the Cortana Scheduler mailbox, a new "PersistedCapability" is set on the mailbox to note that this mailbox is the "SchedulerAssistant".</span></span>

> [!NOTE]
> <span data-ttu-id="4543a-127">Выполните следующие действия, чтобы подключить организацию к PowerShell, если вы не сделали этого ранее: Подключение Microsoft 365 [с PowerShell](../enterprise/connect-to-microsoft-365-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="4543a-127">Follow these steps to connect your organization to PowerShell if you’ve not done so previously: [Connect to Microsoft 365 with PowerShell](../enterprise/connect-to-microsoft-365-powershell.md).</span></span>

<span data-ttu-id="4543a-128">Чтобы узнать, какой почтовый ящик в организации в настоящее время Кортана помощником по расписанию, запустите функцию get:</span><span class="sxs-lookup"><span data-stu-id="4543a-128">To discover which mailbox in your organization is currently set as the Cortana Scheduler assistant, run the get function:</span></span>

```powershell
Get-mailbox | where {$_.PersistedCapabilities -Match "SchedulerAssistant"}
```

> [!IMPORTANT]
> <span data-ttu-id="4543a-129">Чтобы выполнить полную подготовка к набору возможности SchedulerAssistant, почтовому ящику Scheduler может потребоваться до двух часов.</span><span class="sxs-lookup"><span data-stu-id="4543a-129">It might take up to two hours for the Scheduler mailbox to complete full provisioning to set the SchedulerAssistant capability.</span></span>

## <a name="exchange-online-mailbox"></a><span data-ttu-id="4543a-130">Почтовый ящик Exchange Online</span><span class="sxs-lookup"><span data-stu-id="4543a-130">Exchange Online mailbox</span></span>
<span data-ttu-id="4543a-131">Лицензия Scheduler — это надстройка для Microsoft 365, которая позволяет организатору собраний делегировать свои задачи планирования собраний своему помощнику-планировщику.</span><span class="sxs-lookup"><span data-stu-id="4543a-131">A Scheduler license is an add-on to Microsoft 365, that enables the meeting organizer to delegate their meeting scheduling tasks to their Scheduler assistant.</span></span> <span data-ttu-id="4543a-132">Для работы scheduler, как правило, Microsoft 365 лицензии, организаторам собраний требуются следующие компоненты:</span><span class="sxs-lookup"><span data-stu-id="4543a-132">For the Scheduler to work, typically through Microsoft 365 license, meeting organizers require the following components:</span></span>

- <span data-ttu-id="4543a-133">Почтовый ящик, назначенный в качестве почтового ящика помощника планировщика</span><span class="sxs-lookup"><span data-stu-id="4543a-133">A mailbox designated as Scheduler assistant mailbox</span></span>
- <span data-ttu-id="4543a-134">Лицензия планировщика</span><span class="sxs-lookup"><span data-stu-id="4543a-134">Scheduler license</span></span>
- <span data-ttu-id="4543a-135">Exchange Online почтовый ящик и календарь</span><span class="sxs-lookup"><span data-stu-id="4543a-135">Exchange Online mailbox and calendar</span></span>

<span data-ttu-id="4543a-136">Участникам собрания не требуется лицензия scheduler или Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4543a-136">The meeting attendees do not require Scheduler or Microsoft 365 license.</span></span>

## <a name="scheduler-end-user-license-requirements"></a><span data-ttu-id="4543a-137">Требования к лицензии конечных пользователей scheduler</span><span class="sxs-lookup"><span data-stu-id="4543a-137">Scheduler end-user license requirements</span></span>

<span data-ttu-id="4543a-138">Лицензия scheduler требует одну из следующих лицензий:</span><span class="sxs-lookup"><span data-stu-id="4543a-138">A Scheduler license requires one of the following licenses:</span></span>

- <span data-ttu-id="4543a-139">Microsoft 365 E3, A3, E5, A5</span><span class="sxs-lookup"><span data-stu-id="4543a-139">Microsoft 365 E3, A3, E5, A5</span></span>
- <span data-ttu-id="4543a-140">Business Basic, Business, Business Standard, Business Premium</span><span class="sxs-lookup"><span data-stu-id="4543a-140">Business Basic, Business, Business Standard, Business Premium</span></span>
- <span data-ttu-id="4543a-141">Office 365 E1, A1, E3, A3, E5, A5</span><span class="sxs-lookup"><span data-stu-id="4543a-141">Office 365 E1, A1, E3, A3, E5, A5</span></span>
- <span data-ttu-id="4543a-142">Основные бизнес-Premium</span><span class="sxs-lookup"><span data-stu-id="4543a-142">Business Essentials, Business Premium</span></span>
- <span data-ttu-id="4543a-143">Exchange Online Лицензия plan 1 или Plan 2.</span><span class="sxs-lookup"><span data-stu-id="4543a-143">Exchange Online Plan 1 or Plan 2 license.</span></span> 

> [!Note]

> <span data-ttu-id="4543a-144">Планировщик Microsoft 365 доступен в разных средах на английском языке.</span><span class="sxs-lookup"><span data-stu-id="4543a-144">Scheduler for Microsoft 365 is available in worldwide multi-tenant environments in English only.</span></span> <span data-ttu-id="4543a-145">**Планировка Microsoft 365** недоступна пользователям:</span><span class="sxs-lookup"><span data-stu-id="4543a-145">**Scheduler for Microsoft 365** isn't available to users of:</span></span>

- <span data-ttu-id="4543a-146">Microsoft 365 21Vianet в Китае</span><span class="sxs-lookup"><span data-stu-id="4543a-146">Microsoft 365 operated by 21Vianet in China</span></span>
- <span data-ttu-id="4543a-147">Microsoft 365 с немецким облаком, использующим доверителем данных немецкий Telekom</span><span class="sxs-lookup"><span data-stu-id="4543a-147">Microsoft 365 with German cloud that uses the data trustee German Telekom</span></span>
- <span data-ttu-id="4543a-148">Облако правительства, включая GCC, consumer, GCC high или DoD</span><span class="sxs-lookup"><span data-stu-id="4543a-148">Government cloud including GCC, Consumer, GCC High, or DoD</span></span>

<span data-ttu-id="4543a-149">Планировщик поддерживает пользователей в Германии, расположение данных которых не находится в немецком центрах обработки данных.</span><span class="sxs-lookup"><span data-stu-id="4543a-149">Scheduler does support users in Germany whose data location is not in the German datacenter.</span></span>
