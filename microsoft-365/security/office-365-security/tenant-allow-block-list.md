---
title: Управление разрешенными и заблокированными URL-адресами в списке разрешенных и запрещенных клиентов
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: Администраторы могут научиться настраивать записи URL-адресов в списке разрешенных и запрещенных клиентов центра безопасности & соответствия требованиям.
ms.openlocfilehash: eb9dcc5b239aae1366a0a2e0eebd68b3f0082e6b
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "48202343"
---
# <a name="manage-urls-in-the-tenant-allowblock-list"></a><span data-ttu-id="f5fee-103">Управление URL-адресами в списке разрешенных и заблокированных клиентов</span><span class="sxs-lookup"><span data-stu-id="f5fee-103">Manage URLs in the Tenant Allow/Block List</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


> [!NOTE]
> <span data-ttu-id="f5fee-104">Функции, описанные в этой статье, в предварительной версии, могут быть изменены и недоступны во всех организациях.</span><span class="sxs-lookup"><span data-stu-id="f5fee-104">The features described in this topic are in Preview, are subject to change, and are not available in all organizations.</span></span>

<span data-ttu-id="f5fee-105">В организациях Microsoft 365 с почтовыми ящиками в организациях Exchange Online или в автономной службе Exchange Online Protection (EOP) без почтовых ящиков Exchange Online вы можете не противовниманияию фильтра EOP вредоносности.</span><span class="sxs-lookup"><span data-stu-id="f5fee-105">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, you might disagree with the EOP filtering verdict.</span></span> <span data-ttu-id="f5fee-106">Например, хорошее сообщение может быть помечено как плохое (ложный положительный результат), или может быть разрешено неправильное сообщение (ложное отрицательное).</span><span class="sxs-lookup"><span data-stu-id="f5fee-106">For example, a good message might be marked as bad (a false positive), or a bad message might be allowed through (a false negative).</span></span>

<span data-ttu-id="f5fee-107">Список разрешенных и заблокированных клиентов в центре безопасности & соответствия требованиям позволяет вручную переопределить вердиктс фильтрации Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f5fee-107">The Tenant Allow/Block List in the Security & Compliance Center gives you a way to manually override the Microsoft 365 filtering verdicts.</span></span> <span data-ttu-id="f5fee-108">Список разрешенных и заблокированных клиентов используется во время процесса обработки почты и при нажатии пользователем.</span><span class="sxs-lookup"><span data-stu-id="f5fee-108">The Tenant Allow/Block List is used during mail flow and at the time of user clicks.</span></span> <span data-ttu-id="f5fee-109">Вы можете указать URL-адреса, которые необходимо разрешить или заблокировать в списке разрешенных или запрещенных клиентов.</span><span class="sxs-lookup"><span data-stu-id="f5fee-109">You can specify URLs to allow or block in the Tenant Allow/Block List.</span></span>

<span data-ttu-id="f5fee-110">В этом разделе описывается, как настроить записи в списке разрешенных и запрещенных клиентов в центре безопасности & соответствия требованиям или в PowerShell (Exchange Online PowerShell для Microsoft 365 организации с почтовыми ящиками в Exchange Online; изолированный EOP PowerShell для организаций без почтовых ящиков Exchange Online).</span><span class="sxs-lookup"><span data-stu-id="f5fee-110">This topic describes how to configure entries in the Tenant Allow/Block List in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="f5fee-111">Что нужно знать перед началом работы</span><span class="sxs-lookup"><span data-stu-id="f5fee-111">What do you need to know before you begin?</span></span>

- <span data-ttu-id="f5fee-112">Откройте Центр безопасности и соответствия требованиям на сайте <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="f5fee-112">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="f5fee-113">Чтобы перейти непосредственно на страницу **списка разрешенных и заблокированных клиентов** , используйте <https://protection.office.com/tenantAllowBlockList> .</span><span class="sxs-lookup"><span data-stu-id="f5fee-113">To go directly to the **Tenant Allow/Block List** page, use <https://protection.office.com/tenantAllowBlockList>.</span></span>

- <span data-ttu-id="f5fee-114">Доступные значения URL-адреса описаны в [синтаксисе URL-адреса для списка разрешений/блокировок клиентов](#url-syntax-for-the-tenant-allowblock-list) далее в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="f5fee-114">The available URL values are described in the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this topic.</span></span>

- <span data-ttu-id="f5fee-115">В списке разрешенных и заблокированных клиентов можно указать не более 500 записей для URL-адресов.</span><span class="sxs-lookup"><span data-stu-id="f5fee-115">The Tenant Allow/Block List allows a maximum of 500 entries for URLs.</span></span>

- <span data-ttu-id="f5fee-116">Запись должна быть активна в течение 15 минут.</span><span class="sxs-lookup"><span data-stu-id="f5fee-116">An entry should be active within 15 minutes.</span></span>

- <span data-ttu-id="f5fee-117">Записи блокировки имеют приоритет над разрешающими записями.</span><span class="sxs-lookup"><span data-stu-id="f5fee-117">Block entries take precedence over allow entries.</span></span>

- <span data-ttu-id="f5fee-118">По умолчанию срок действия записей в списке разрешений/блокировок клиентов истекает через 30 дней.</span><span class="sxs-lookup"><span data-stu-id="f5fee-118">By default, entries in the Tenant Allow/Block List will expire after 30 days.</span></span> <span data-ttu-id="f5fee-119">Вы можете указать дату или запретить срок ее действия.</span><span class="sxs-lookup"><span data-stu-id="f5fee-119">You can specify a date or set them to never expire.</span></span>

- <span data-ttu-id="f5fee-120">Сведения о том, как подключиться к Exchange Online PowerShell, см. в статье [Подключение к Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="f5fee-120">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="f5fee-121">Чтобы подключиться к автономному EOP PowerShell, см. раздел [Подключение к PowerShell Exchange Online Protection](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="f5fee-121">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="f5fee-122">Чтобы вы могли выполнить процедуры, упомянутые в этой теме, вам должны быть назначены соответствующие разрешения.</span><span class="sxs-lookup"><span data-stu-id="f5fee-122">You need to be assigned permissions before you can do the procedures in this topic:</span></span>

  - <span data-ttu-id="f5fee-123">Чтобы добавить или удалить значения из списка разрешенных и заблокированных клиентов, необходимо быть участником одной из следующих групп ролей:</span><span class="sxs-lookup"><span data-stu-id="f5fee-123">To add and remove values from the Tenant Allow/Block List, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="f5fee-124">**Управление организацией** или **Администратор безопасности** в [Центре безопасности и соответствия требованиям](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="f5fee-124">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="f5fee-125">**Управление организацией** или **Управление санацией** в [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="f5fee-125">**Organization Management** or **Hygiene Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

  - <span data-ttu-id="f5fee-126">Для доступа только для чтения к списку разрешенных и запрещенных клиентов необходимо быть участником одной из следующих групп ролей:</span><span class="sxs-lookup"><span data-stu-id="f5fee-126">For read-only access to the Tenant Allow/Block List, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="f5fee-127">**Средство считывания сведений о безопасности** в [Центре безопасности и соответствия требованиям](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="f5fee-127">**Security Reader** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="f5fee-128">**Управление организацией с правами только на просмотр** в [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="f5fee-128">**View-Only Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

## <a name="use-the-security--compliance-center-to-create-url-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="f5fee-129">Использование центра безопасности & соответствия требованиям для создания записей URL-адресов в списке разрешенных и запрещенных клиентов</span><span class="sxs-lookup"><span data-stu-id="f5fee-129">Use the Security & Compliance Center to create URL entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="f5fee-130">Для получения подробных сведений о синтаксисе для записей URL-адресов просмотрите [синтаксис URL-адресов для списка разрешенных и заблокированных адресов](#url-syntax-for-the-tenant-allowblock-list) в разделе далее в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="f5fee-130">For details about the syntax for URL entries, see the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this topic.</span></span>

1. <span data-ttu-id="f5fee-131">В центре безопасности & соответствия требованиям перейдите в **Threat management** \> **Policy** \> **списки разрешенных и**запрещенных клиентов политики управления угрозами.</span><span class="sxs-lookup"><span data-stu-id="f5fee-131">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="f5fee-132">На странице **списка разрешенных и заблокированных клиентов** убедитесь, что выбрана вкладка **URL-адреса** , а затем нажмите кнопку **добавить** .</span><span class="sxs-lookup"><span data-stu-id="f5fee-132">On the **Tenant Allow/Block List** page, verify that the **URLs** tab is selected, and then click **Add**</span></span>

3. <span data-ttu-id="f5fee-133">В появившемся всплывающем окне **Добавление новых URL-адресов** настройте следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="f5fee-133">In the **Add new URLs** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="f5fee-134">**Добавьте URL-адреса с подстановочными знаками**: введите один URL-адрес в строке длиной не более 20.</span><span class="sxs-lookup"><span data-stu-id="f5fee-134">**Add URLs with wildcards**: Enter one URL per line, up to a maximum of 20.</span></span>

   - <span data-ttu-id="f5fee-135">**Блокировать/Разрешить**: укажите, хотите ли вы **Разрешить** или **запретить** указанные URL-адреса.</span><span class="sxs-lookup"><span data-stu-id="f5fee-135">**Block/Allow**: Select whether you want to **Allow** or **Block** the specified URLs.</span></span>

   - <span data-ttu-id="f5fee-136">**Никогда не истечет**: выполните одно из указанных ниже действий.</span><span class="sxs-lookup"><span data-stu-id="f5fee-136">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="f5fee-137">Убедитесь, что параметр отключен (выключен ![ ](../../media/scc-toggle-off.png) ), и в поле **истечение срока действия** указан срок действия для записей.</span><span class="sxs-lookup"><span data-stu-id="f5fee-137">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entries.</span></span>

     <span data-ttu-id="f5fee-138">или</span><span class="sxs-lookup"><span data-stu-id="f5fee-138">or</span></span>

     - <span data-ttu-id="f5fee-139">Переместите переключатель вправо, чтобы задать срок действия бессрочных записей:</span><span class="sxs-lookup"><span data-stu-id="f5fee-139">Move the toggle to the right to configure the entries to never expire:</span></span> ![Включенный переключатель](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)<span data-ttu-id="f5fee-141">.</span><span class="sxs-lookup"><span data-stu-id="f5fee-141">.</span></span>

   - <span data-ttu-id="f5fee-142">**Необязательное примечание**: введите описательный текст для записей.</span><span class="sxs-lookup"><span data-stu-id="f5fee-142">**Optional note**: Enter descriptive text for the entries.</span></span>

4. <span data-ttu-id="f5fee-143">По завершении нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="f5fee-143">When you're finished, click **Add**.</span></span>

## <a name="use-the-security--compliance-center-to-view-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="f5fee-144">Использование центра безопасности & соответствия требованиям для просмотра записей в списке разрешенных и запрещенных клиентов</span><span class="sxs-lookup"><span data-stu-id="f5fee-144">Use the Security & Compliance Center to view entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="f5fee-145">В центре безопасности & соответствия требованиям перейдите в **Threat management** \> **Policy** \> **списки разрешенных и**запрещенных клиентов политики управления угрозами.</span><span class="sxs-lookup"><span data-stu-id="f5fee-145">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="f5fee-146">Перейдите на вкладку **URL-адреса** .</span><span class="sxs-lookup"><span data-stu-id="f5fee-146">Select the **URLs** tab.</span></span>

<span data-ttu-id="f5fee-147">Щелкните следующие заголовки столбцов, чтобы отсортировать их по возрастанию или убыванию:</span><span class="sxs-lookup"><span data-stu-id="f5fee-147">Click on the following column headings to sort in ascending or descending order:</span></span>

- <span data-ttu-id="f5fee-148">**Значение**</span><span class="sxs-lookup"><span data-stu-id="f5fee-148">**Value**</span></span>
- <span data-ttu-id="f5fee-149">**Действие**: **блокировать** или **Разрешить**.</span><span class="sxs-lookup"><span data-stu-id="f5fee-149">**Action**: **Block** or **Allow**.</span></span>
- <span data-ttu-id="f5fee-150">**Дата последнего обновления**</span><span class="sxs-lookup"><span data-stu-id="f5fee-150">**Last updated date**</span></span>
- <span data-ttu-id="f5fee-151">**Дата истечения срока действия**</span><span class="sxs-lookup"><span data-stu-id="f5fee-151">**Expiration date**</span></span>
- <span data-ttu-id="f5fee-152">**Примечание**</span><span class="sxs-lookup"><span data-stu-id="f5fee-152">**Note**</span></span>

<span data-ttu-id="f5fee-153">Щелкните **Group (Группа** ), чтобы сгруппировать записи по **действию** (**блокировать** или **Разрешить**) или **нет**.</span><span class="sxs-lookup"><span data-stu-id="f5fee-153">Click **Group** to group the entries by **Action** (**Block** or **Allow**) or **None**.</span></span>

<span data-ttu-id="f5fee-154">Нажмите кнопку **Поиск**, введите значение полностью или частично, а затем нажмите клавишу ВВОД, чтобы найти конкретное значение.</span><span class="sxs-lookup"><span data-stu-id="f5fee-154">Click **Search**, enter all or part of a value, and then press ENTER to find a specific value.</span></span> <span data-ttu-id="f5fee-155">По завершении нажмите кнопку **очистить** поиск ![ Очистить поиск значок ](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif) .</span><span class="sxs-lookup"><span data-stu-id="f5fee-155">When you're finished, click **Clear search** ![Clear search icon](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif).</span></span>

<span data-ttu-id="f5fee-156">Нажмите кнопку **Фильтр**.</span><span class="sxs-lookup"><span data-stu-id="f5fee-156">Click **Filter**.</span></span> <span data-ttu-id="f5fee-157">В появившемся всплывающем окне **фильтра** настройте любой из следующих параметров:</span><span class="sxs-lookup"><span data-stu-id="f5fee-157">In the **Filter** flyout that appears, configure any of the following settings:</span></span>

- <span data-ttu-id="f5fee-158">**Действие**: выберите **Разрешить**, **блокировать** или и то, и другое.</span><span class="sxs-lookup"><span data-stu-id="f5fee-158">**Action**: Select **Allow**, **Block** or both.</span></span>

- <span data-ttu-id="f5fee-159">**Никогда не истечет**: выберите Выключить (выключить ![ ](../../media/scc-toggle-off.png) ) или включить (включить ![ ](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png) ).</span><span class="sxs-lookup"><span data-stu-id="f5fee-159">**Never expire**: Select off (![Toggle off](../../media/scc-toggle-off.png)) or on (![Toggle on](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)).</span></span>

- <span data-ttu-id="f5fee-160">**Последнее обновление**: выберите дату начала (**from**), конечную дату (конечную) или и**то, и**другое.</span><span class="sxs-lookup"><span data-stu-id="f5fee-160">**Last updated**: Select a start date (**From**), an end date (**To**) or both.</span></span>

- <span data-ttu-id="f5fee-161">**Дата окончания срока действия**: выберите дату начала (**от**), конечную дату (**до**) или и то, и другое.</span><span class="sxs-lookup"><span data-stu-id="f5fee-161">**Expiration date**: Select a start date (**From**), an end date (**To**) or both.</span></span>

<span data-ttu-id="f5fee-162">Когда все будет готово, нажмите кнопку **Применить**.</span><span class="sxs-lookup"><span data-stu-id="f5fee-162">When you're finished, click **Apply**.</span></span>

<span data-ttu-id="f5fee-163">Чтобы очистить существующие фильтры, нажмите кнопку **Фильтр**, а затем в появившемся всплывающем окне **фильтра** щелкните **Очистить фильтры**.</span><span class="sxs-lookup"><span data-stu-id="f5fee-163">To clear existing filters, click **Filter**, and in the **Filter** flyout that appears, click **Clear filters**.</span></span>

## <a name="use-the-security--compliance-center-to-modify-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="f5fee-164">Использование центра безопасности & соответствия требованиям для изменения записей в списке разрешенных и запрещенных клиентов</span><span class="sxs-lookup"><span data-stu-id="f5fee-164">Use the Security & Compliance Center to modify entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="f5fee-165">Невозможно изменить значение URL-адреса.</span><span class="sxs-lookup"><span data-stu-id="f5fee-165">You can't modify the URL value itself.</span></span> <span data-ttu-id="f5fee-166">Вместо этого необходимо удалить запись и создать ее повторно.</span><span class="sxs-lookup"><span data-stu-id="f5fee-166">Instead, you need to delete the entry and recreate it.</span></span>

1. <span data-ttu-id="f5fee-167">В центре безопасности & соответствия требованиям перейдите в **Threat management** \> **Policy** \> **списки разрешенных и**запрещенных клиентов политики управления угрозами.</span><span class="sxs-lookup"><span data-stu-id="f5fee-167">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="f5fee-168">Перейдите на вкладку **URL-адреса** .</span><span class="sxs-lookup"><span data-stu-id="f5fee-168">Select the **URLs** tab.</span></span>

3. <span data-ttu-id="f5fee-169">Выберите запись, которую необходимо изменить, а затем щелкните **изменить** ![ значок редактирования ](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) .</span><span class="sxs-lookup"><span data-stu-id="f5fee-169">Select the entry that you want to modify, and then click **Edit** ![Edit icon](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png).</span></span>

4. <span data-ttu-id="f5fee-170">В появившемся всплывающем меню настройте следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="f5fee-170">In the flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="f5fee-171">**Блокировать/Разрешить**: выберите **Разрешить** или **заблокировать**.</span><span class="sxs-lookup"><span data-stu-id="f5fee-171">**Block/Allow**: Select **Allow** or **Block**.</span></span>

   - <span data-ttu-id="f5fee-172">**Никогда не истечет**: выполните одно из указанных ниже действий.</span><span class="sxs-lookup"><span data-stu-id="f5fee-172">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="f5fee-173">Убедитесь, что параметр отключен (выключен ![ ](../../media/scc-toggle-off.png) ), и укажите срок действия для записи, используя поле **срок действия** .</span><span class="sxs-lookup"><span data-stu-id="f5fee-173">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entry.</span></span>

     <span data-ttu-id="f5fee-174">или</span><span class="sxs-lookup"><span data-stu-id="f5fee-174">or</span></span>

     - <span data-ttu-id="f5fee-175">Переместите переключатель вправо, чтобы задать срок действия бессрочной записи:</span><span class="sxs-lookup"><span data-stu-id="f5fee-175">Move the toggle to the right to configure the entry to never expire:</span></span> ![Включенный переключатель](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)<span data-ttu-id="f5fee-177">.</span><span class="sxs-lookup"><span data-stu-id="f5fee-177">.</span></span>

   - <span data-ttu-id="f5fee-178">**Необязательное примечание**: введите описательный текст для записи.</span><span class="sxs-lookup"><span data-stu-id="f5fee-178">**Optional note**: Enter descriptive text for the entry.</span></span>

5. <span data-ttu-id="f5fee-179">Выполнив необходимые действия, нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="f5fee-179">When you're finished, click **Save**.</span></span>

## <a name="use-the-security--compliance-center-to-remove-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="f5fee-180">Использование центра безопасности & соответствия требованиям для удаления записей из списка разрешенных и запрещенных клиентов</span><span class="sxs-lookup"><span data-stu-id="f5fee-180">Use the Security & Compliance Center to remove entries from the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="f5fee-181">В центре безопасности & соответствия требованиям перейдите в **Threat management** \> **Policy** \> **списки разрешенных и**запрещенных клиентов политики управления угрозами.</span><span class="sxs-lookup"><span data-stu-id="f5fee-181">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="f5fee-182">Перейдите на вкладку **URL-адреса** .</span><span class="sxs-lookup"><span data-stu-id="f5fee-182">Select the **URLs** tab.</span></span>

3. <span data-ttu-id="f5fee-183">Выберите запись, которую нужно удалить, и нажмите кнопку **Удалить** ![ значок удаления ](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png) .</span><span class="sxs-lookup"><span data-stu-id="f5fee-183">Select the entry that you want to remove, and then click **Delete** ![Delete icon](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png).</span></span>

4. <span data-ttu-id="f5fee-184">В появившемся диалоговом окне предупреждения нажмите кнопку **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="f5fee-184">In the warning dialog that appears, click **Delete**.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-the-tenant-allowblock-list"></a><span data-ttu-id="f5fee-185">Настройка списка разрешений/блокировок клиентов с помощью Exchange Online PowerShell или изолированной EOP PowerShell</span><span class="sxs-lookup"><span data-stu-id="f5fee-185">Use Exchange Online PowerShell or standalone EOP PowerShell to configure the Tenant Allow/Block List</span></span>

### <a name="use-powershell-to-add-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="f5fee-186">Добавление записей в список разрешенных и запрещенных клиентов с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="f5fee-186">Use PowerShell to add entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="f5fee-187">Чтобы добавить записи в список разрешенных и запрещенных клиентов, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="f5fee-187">To add entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
New-TenantAllowBlockListItems -ListType Url -Action <Allow | Block> -Entries <String[]> [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

<span data-ttu-id="f5fee-188">В этом примере добавляется запись блока URL-адреса для contoso.com и всех поддоменов (например, contoso.com, www.contoso.com и xyz.abc.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="f5fee-188">This example adds a URL block entry for contoso.com and all subdomains (for example, contoso.com, www.contoso.com, and xyz.abc.contoso.com).</span></span> <span data-ttu-id="f5fee-189">Так как мы не использовали параметры ExpirationDate или параметру expiration, срок действия записи истечет через 30 дней.</span><span class="sxs-lookup"><span data-stu-id="f5fee-189">Because we didn't use the ExpirationDate or NoExpiration parameters, the entry expires after 30 days.</span></span>

```powershell
New-TenantAllowBlockListItem -ListType Url -Action Block -Entries ~contoso.com
```

<span data-ttu-id="f5fee-190">Подробные сведения о синтаксисе и параметрах можно найти в статье [New – тенанталловблокклиститемс](https://docs.microsoft.com/powershell/module/exchange/new-tenantallowblocklistitems).</span><span class="sxs-lookup"><span data-stu-id="f5fee-190">For detailed syntax and parameter information, see [New-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/new-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-view-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="f5fee-191">Просмотр записей в списке разрешенных и запрещенных клиентов с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="f5fee-191">Use PowerShell to view entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="f5fee-192">Чтобы просмотреть записи в списке разрешенных и запрещенных клиентов, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="f5fee-192">To view entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType Url [-Entry <URLValue>] [-Action <Allow | Block>] [-ExpirationDate <DateTime>] [-NoExpiration]
```

<span data-ttu-id="f5fee-193">В этом примере возвращаются все заблокированные URL-адреса.</span><span class="sxs-lookup"><span data-stu-id="f5fee-193">This example returns all blocked URLs.</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType Url -Action Block
```

<span data-ttu-id="f5fee-194">Подробные сведения о синтаксисе и параметрах можно найти в статье [Get – тенанталловблокклиститемс](https://docs.microsoft.com/powershell/module/exchange/get-tenantallowblocklistitems).</span><span class="sxs-lookup"><span data-stu-id="f5fee-194">For detailed syntax and parameter information, see [Get-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/get-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-modify-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="f5fee-195">Изменение записей в списке разрешенных и запрещенных клиентов с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="f5fee-195">Use PowerShell to modify entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="f5fee-196">Невозможно изменить значение URL-адреса.</span><span class="sxs-lookup"><span data-stu-id="f5fee-196">You can't modify the URL value itself.</span></span> <span data-ttu-id="f5fee-197">Вместо этого необходимо удалить запись и создать ее повторно.</span><span class="sxs-lookup"><span data-stu-id="f5fee-197">Instead, you need to delete the entry and recreate it.</span></span>

<span data-ttu-id="f5fee-198">Чтобы изменить записи в списке разрешенных и запрещенных клиентов, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="f5fee-198">To modify entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType Url -Ids <"Id1","Id2",..."IdN"> [-Action <Allow | Block>] [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

<span data-ttu-id="f5fee-199">В этом примере изменяется дата окончания срока действия указанной записи.</span><span class="sxs-lookup"><span data-stu-id="f5fee-199">This example changes the expiration date of the specified entry.</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -ExpirationDate (Get-Date "5/30/2020 9:30 AM").ToUniversalTime()
```

<span data-ttu-id="f5fee-200">Подробные сведения о синтаксисе и параметрах можно найти в статье [Set – тенанталловблокклиститемс](https://docs.microsoft.com/powershell/module/exchange/set-tenantallowblocklistitems).</span><span class="sxs-lookup"><span data-stu-id="f5fee-200">For detailed syntax and parameter information, see [Set-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/set-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-remove-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="f5fee-201">Удаление записей из списка разрешенных и запрещенных клиентов с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="f5fee-201">Use PowerShell to remove entries from the Tenant Allow/Block List</span></span>

<span data-ttu-id="f5fee-202">Чтобы удалить записи из списка разрешенных и запрещенных клиентов, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="f5fee-202">To remove entries from the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType Url -Ids <"Id1","Id2",..."IdN">
```

<span data-ttu-id="f5fee-203">В этом примере из списка разрешенных и запрещенных клиентов удаляется указанная запись URL-адреса.</span><span class="sxs-lookup"><span data-stu-id="f5fee-203">This example removes the specified URL entry from the Tenant Allow/Block List.</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSPAAAA0"
```

<span data-ttu-id="f5fee-204">Подробные сведения о синтаксисе и параметрах можно найти в статье [Remove – тенанталловблокклиститемс](https://docs.microsoft.com/powershell/module/exchange/remove-tenantallowblocklistitems).</span><span class="sxs-lookup"><span data-stu-id="f5fee-204">For detailed syntax and parameter information, see [Remove-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/remove-tenantallowblocklistitems).</span></span>

## <a name="url-syntax-for-the-tenant-allowblock-list"></a><span data-ttu-id="f5fee-205">Синтаксис URL-адреса для списка разрешений/блокировок клиентов</span><span class="sxs-lookup"><span data-stu-id="f5fee-205">URL syntax for the Tenant Allow/Block List</span></span>

- <span data-ttu-id="f5fee-206">IP4v и IPv6-адреса разрешены, но порты TCP/UDP — нет.</span><span class="sxs-lookup"><span data-stu-id="f5fee-206">IP4v and IPv6 addresses are allowed, but TCP/UDP ports are not.</span></span>

- <span data-ttu-id="f5fee-207">Расширения имен файлов не допускаются (например, test.pdf).</span><span class="sxs-lookup"><span data-stu-id="f5fee-207">Filename extensions are not allowed (for example, test.pdf).</span></span>

- <span data-ttu-id="f5fee-208">Юникод не поддерживается, но Punycode — Punycode.</span><span class="sxs-lookup"><span data-stu-id="f5fee-208">Unicode is not supported, but Punycode is.</span></span>

- <span data-ttu-id="f5fee-209">Имена узлов разрешены, если выполняются все приведенные ниже условия.</span><span class="sxs-lookup"><span data-stu-id="f5fee-209">Hostnames are allowed if all of the following statements are true:</span></span>

  - <span data-ttu-id="f5fee-210">Имя узла содержит точку.</span><span class="sxs-lookup"><span data-stu-id="f5fee-210">The hostname contains a period.</span></span>
  - <span data-ttu-id="f5fee-211">Слева от точки есть по крайней мере один символ.</span><span class="sxs-lookup"><span data-stu-id="f5fee-211">There is at least one character to the left of the period.</span></span>
  - <span data-ttu-id="f5fee-212">Справа от точки есть по крайней мере два символа.</span><span class="sxs-lookup"><span data-stu-id="f5fee-212">There are at least two characters to the right of the period.</span></span>

  <span data-ttu-id="f5fee-213">Например, `t.co` разрешено; `.com` или `contoso.` не разрешено.</span><span class="sxs-lookup"><span data-stu-id="f5fee-213">For example, `t.co` is allowed; `.com` or `contoso.` are not allowed.</span></span>

- <span data-ttu-id="f5fee-214">Вложенные пути не являются подразумеваемыми.</span><span class="sxs-lookup"><span data-stu-id="f5fee-214">Subpaths are not implied.</span></span>

  <span data-ttu-id="f5fee-215">Например, не `contoso.com` включается `contoso.com/a` .</span><span class="sxs-lookup"><span data-stu-id="f5fee-215">For example, `contoso.com` does not include `contoso.com/a`.</span></span>

- <span data-ttu-id="f5fee-216">Подстановочные знаки (\*) разрешены в следующих сценариях:</span><span class="sxs-lookup"><span data-stu-id="f5fee-216">Wildcards (\*) are allowed in the following scenarios:</span></span>

  - <span data-ttu-id="f5fee-217">За левым подстановочным знаком должен следовать точка для указания поддомена.</span><span class="sxs-lookup"><span data-stu-id="f5fee-217">A left wildcard must be followed by a period to specify a subdomain.</span></span>

    <span data-ttu-id="f5fee-218">Например, `*.contoso.com` разрешено; запрещено `*contoso.com` .</span><span class="sxs-lookup"><span data-stu-id="f5fee-218">For example, `*.contoso.com` is allowed; `*contoso.com` is not allowed.</span></span>

  - <span data-ttu-id="f5fee-219">Для указания пути должен следовать символу подстановки (/).</span><span class="sxs-lookup"><span data-stu-id="f5fee-219">A right wildcard must follow a forward slash (/) to specify a path.</span></span>

    <span data-ttu-id="f5fee-220">Например, `contoso.com/*` разрешено; `contoso.com*` или `contoso.com/ab*` не разрешено.</span><span class="sxs-lookup"><span data-stu-id="f5fee-220">For example, `contoso.com/*` is allowed; `contoso.com*` or `contoso.com/ab*` are not allowed.</span></span>

  - <span data-ttu-id="f5fee-221">Все подпути не подразумеваются с помощью подстановочного знака справа.</span><span class="sxs-lookup"><span data-stu-id="f5fee-221">All subpaths are not implied by a right wildcard.</span></span>

    <span data-ttu-id="f5fee-222">Например, не `contoso.com/*` включается `contoso.com/a` .</span><span class="sxs-lookup"><span data-stu-id="f5fee-222">For example, `contoso.com/*` does not include `contoso.com/a`.</span></span>

  - <span data-ttu-id="f5fee-223">`*.com*` недействителен (не является разрешимым доменом, а правильный подстановочный знак не следует за косой чертой).</span><span class="sxs-lookup"><span data-stu-id="f5fee-223">`*.com*` is invalid (not a resolvable domain and the right wildcard does not follow a forward slash).</span></span>

  - <span data-ttu-id="f5fee-224">Подстановочные знаки не разрешены в IP-адресах.</span><span class="sxs-lookup"><span data-stu-id="f5fee-224">Wildcards are not allowed in IP addresses.</span></span>

- <span data-ttu-id="f5fee-225">Символ тильды (~) доступен в следующих сценариях:</span><span class="sxs-lookup"><span data-stu-id="f5fee-225">The tilde (~) character is available in the following scenarios:</span></span>

  - <span data-ttu-id="f5fee-226">Левая тильда подразумевает домен и все поддомены.</span><span class="sxs-lookup"><span data-stu-id="f5fee-226">A left tilde implies a domain and all subdomains.</span></span>

    <span data-ttu-id="f5fee-227">Например `~contoso.com` , включает `contoso.com` и `*.contoso.com` .</span><span class="sxs-lookup"><span data-stu-id="f5fee-227">For example `~contoso.com` includes `contoso.com` and `*.contoso.com`.</span></span>

- <span data-ttu-id="f5fee-228">URL-адреса, содержащие протоколы (например,, `http://` `https://` или `ftp://` ), завершатся неуспешно, так как записи URL-адресов применяются ко всем протоколам.</span><span class="sxs-lookup"><span data-stu-id="f5fee-228">URL entries that contain protocols (for example, `http://`, `https://`, or `ftp://`) will fail, because URL entries apply to all protocols.</span></span>

- <span data-ttu-id="f5fee-229">Имя пользователя или пароль не поддерживаются или не являются обязательными.</span><span class="sxs-lookup"><span data-stu-id="f5fee-229">A username or password aren't supported or required.</span></span>

- <span data-ttu-id="f5fee-230">Кавычки (' или ") являются недопустимыми символами.</span><span class="sxs-lookup"><span data-stu-id="f5fee-230">Quotes (' or ") are invalid characters.</span></span>

- <span data-ttu-id="f5fee-231">URL-адрес должен включать все перенаправления, где это возможно.</span><span class="sxs-lookup"><span data-stu-id="f5fee-231">A URL should include all redirects where possible.</span></span>

### <a name="url-entry-scenarios"></a><span data-ttu-id="f5fee-232">Сценарии ввода URL-адресов</span><span class="sxs-lookup"><span data-stu-id="f5fee-232">URL entry scenarios</span></span>

<span data-ttu-id="f5fee-233">Допустимые записи URL-адреса и их результаты описаны в следующих разделах.</span><span class="sxs-lookup"><span data-stu-id="f5fee-233">Valid URL entries and their results are described in the following sections.</span></span>

#### <a name="scenario-no-wildcards"></a><span data-ttu-id="f5fee-234">Сценарий: без подстановочных знаков</span><span class="sxs-lookup"><span data-stu-id="f5fee-234">Scenario: No wildcards</span></span>

<span data-ttu-id="f5fee-235">**Запись**: `contoso.com`</span><span class="sxs-lookup"><span data-stu-id="f5fee-235">**Entry**: `contoso.com`</span></span>

- <span data-ttu-id="f5fee-236">**Разрешить согласование**: contoso.com</span><span class="sxs-lookup"><span data-stu-id="f5fee-236">**Allow match**: contoso.com</span></span>

- <span data-ttu-id="f5fee-237">**Разрешить не сопоставляемые**:</span><span class="sxs-lookup"><span data-stu-id="f5fee-237">**Allow not matched**:</span></span>

  - <span data-ttu-id="f5fee-238">abc-contoso.com</span><span class="sxs-lookup"><span data-stu-id="f5fee-238">abc-contoso.com</span></span>
  - <span data-ttu-id="f5fee-239">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="f5fee-239">contoso.com/a</span></span>
  - <span data-ttu-id="f5fee-240">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f5fee-240">payroll.contoso.com</span></span>
  - <span data-ttu-id="f5fee-241">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="f5fee-241">test.com/contoso.com</span></span>
  - <span data-ttu-id="f5fee-242">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="f5fee-242">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="f5fee-243">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f5fee-243">www.contoso.com</span></span>
  - <span data-ttu-id="f5fee-244">www. contoso. com/q = a@contoso. com</span><span class="sxs-lookup"><span data-stu-id="f5fee-244">www.contoso.com/q=a@contoso.com</span></span>
  
- <span data-ttu-id="f5fee-245">**Согласование блока**:</span><span class="sxs-lookup"><span data-stu-id="f5fee-245">**Block match**:</span></span>

  - <span data-ttu-id="f5fee-246">contoso.com</span><span class="sxs-lookup"><span data-stu-id="f5fee-246">contoso.com</span></span>
  - <span data-ttu-id="f5fee-247">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="f5fee-247">contoso.com/a</span></span>
  - <span data-ttu-id="f5fee-248">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f5fee-248">payroll.contoso.com</span></span>
  - <span data-ttu-id="f5fee-249">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="f5fee-249">test.com/contoso.com</span></span>
  - <span data-ttu-id="f5fee-250">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="f5fee-250">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="f5fee-251">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f5fee-251">www.contoso.com</span></span>
  - <span data-ttu-id="f5fee-252">www. contoso. com/q = a@contoso. com</span><span class="sxs-lookup"><span data-stu-id="f5fee-252">www.contoso.com/q=a@contoso.com</span></span>

- <span data-ttu-id="f5fee-253">**Блок не сопоставлен**: ABC-contoso.com</span><span class="sxs-lookup"><span data-stu-id="f5fee-253">**Block not matched**: abc-contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain"></a><span data-ttu-id="f5fee-254">Сценарий: левый подстановочный знак (поддомен)</span><span class="sxs-lookup"><span data-stu-id="f5fee-254">Scenario: Left wildcard (subdomain)</span></span>

<span data-ttu-id="f5fee-255">**Запись**: `*.contoso.com`</span><span class="sxs-lookup"><span data-stu-id="f5fee-255">**Entry**: `*.contoso.com`</span></span>

- <span data-ttu-id="f5fee-256">**Разрешить согласование** и **согласование блокировок**:</span><span class="sxs-lookup"><span data-stu-id="f5fee-256">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="f5fee-257">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f5fee-257">www.contoso.com</span></span>
  - <span data-ttu-id="f5fee-258">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f5fee-258">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="f5fee-259">**Разрешить не сопоставляемые** и несопоставленные **блоки**:</span><span class="sxs-lookup"><span data-stu-id="f5fee-259">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="f5fee-260">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="f5fee-260">123contoso.com</span></span>
  - <span data-ttu-id="f5fee-261">contoso.com</span><span class="sxs-lookup"><span data-stu-id="f5fee-261">contoso.com</span></span>
  - <span data-ttu-id="f5fee-262">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="f5fee-262">test.com/contoso.com</span></span>
  - <span data-ttu-id="f5fee-263">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="f5fee-263">www.contoso.com/abc</span></span>
  
#### <a name="scenario-right-wildcard-at-top-of-path"></a><span data-ttu-id="f5fee-264">Сценарий: подстановочный знак "справа" в верхней части пути</span><span class="sxs-lookup"><span data-stu-id="f5fee-264">Scenario: Right wildcard at top of path</span></span>

<span data-ttu-id="f5fee-265">**Запись**: `contoso.com/a/*`</span><span class="sxs-lookup"><span data-stu-id="f5fee-265">**Entry**: `contoso.com/a/*`</span></span>

- <span data-ttu-id="f5fee-266">**Разрешить согласование** и **согласование блокировок**:</span><span class="sxs-lookup"><span data-stu-id="f5fee-266">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="f5fee-267">contoso.com/a/b</span><span class="sxs-lookup"><span data-stu-id="f5fee-267">contoso.com/a/b</span></span>
  - <span data-ttu-id="f5fee-268">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="f5fee-268">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="f5fee-269">Contoso. com/a/? q = joe@t. com</span><span class="sxs-lookup"><span data-stu-id="f5fee-269">contoso.com/a/?q=joe@t.com</span></span>

- <span data-ttu-id="f5fee-270">**Разрешить не сопоставляемые** и несопоставленные **блоки**:</span><span class="sxs-lookup"><span data-stu-id="f5fee-270">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="f5fee-271">contoso.com</span><span class="sxs-lookup"><span data-stu-id="f5fee-271">contoso.com</span></span>
  - <span data-ttu-id="f5fee-272">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="f5fee-272">contoso.com/a</span></span>
  - <span data-ttu-id="f5fee-273">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f5fee-273">www.contoso.com</span></span>
  - <span data-ttu-id="f5fee-274">www. contoso. com/q = a@contoso. com</span><span class="sxs-lookup"><span data-stu-id="f5fee-274">www.contoso.com/q=a@contoso.com</span></span>
  
#### <a name="scenario-left-tilde"></a><span data-ttu-id="f5fee-275">Сценарий: левая тильда</span><span class="sxs-lookup"><span data-stu-id="f5fee-275">Scenario: Left tilde</span></span>

<span data-ttu-id="f5fee-276">**Запись**: `~contoso.com`</span><span class="sxs-lookup"><span data-stu-id="f5fee-276">**Entry**: `~contoso.com`</span></span>

- <span data-ttu-id="f5fee-277">**Разрешить согласование** и **согласование блокировок**:</span><span class="sxs-lookup"><span data-stu-id="f5fee-277">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="f5fee-278">contoso.com</span><span class="sxs-lookup"><span data-stu-id="f5fee-278">contoso.com</span></span>
  - <span data-ttu-id="f5fee-279">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f5fee-279">www.contoso.com</span></span>
  - <span data-ttu-id="f5fee-280">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f5fee-280">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="f5fee-281">**Разрешить не сопоставляемые** и несопоставленные **блоки**:</span><span class="sxs-lookup"><span data-stu-id="f5fee-281">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="f5fee-282">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="f5fee-282">123contoso.com</span></span>
  - <span data-ttu-id="f5fee-283">contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="f5fee-283">contoso.com/abc</span></span>
  - <span data-ttu-id="f5fee-284">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="f5fee-284">www.contoso.com/abc</span></span>

#### <a name="scenario-right-wildcard-suffix"></a><span data-ttu-id="f5fee-285">Сценарий: правый подстановочный суффикс</span><span class="sxs-lookup"><span data-stu-id="f5fee-285">Scenario: Right wildcard suffix</span></span>

<span data-ttu-id="f5fee-286">**Запись**: `contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="f5fee-286">**Entry**: `contoso.com/*`</span></span>

- <span data-ttu-id="f5fee-287">**Разрешить согласование** и **согласование блокировок**:</span><span class="sxs-lookup"><span data-stu-id="f5fee-287">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="f5fee-288">Contoso. com/? q = whatever@fabrikam. com</span><span class="sxs-lookup"><span data-stu-id="f5fee-288">contoso.com/?q=whatever@fabrikam.com</span></span>
  - <span data-ttu-id="f5fee-289">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="f5fee-289">contoso.com/a</span></span>
  - <span data-ttu-id="f5fee-290">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="f5fee-290">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="f5fee-291">contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="f5fee-291">contoso.com/ab</span></span>
  - <span data-ttu-id="f5fee-292">contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="f5fee-292">contoso.com/b</span></span>
  - <span data-ttu-id="f5fee-293">contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="f5fee-293">contoso.com/b/a/c</span></span>
  - <span data-ttu-id="f5fee-294">contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="f5fee-294">contoso.com/ba</span></span>

- <span data-ttu-id="f5fee-295">**Разрешить не сопоставляемые** и непарные **блоки**: contoso.com</span><span class="sxs-lookup"><span data-stu-id="f5fee-295">**Allow not matched** and **Block not matched**: contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain-and-right-wildcard-suffix"></a><span data-ttu-id="f5fee-296">Сценарий: левый и правый суффиксы для поддоменов подстановочных знаков</span><span class="sxs-lookup"><span data-stu-id="f5fee-296">Scenario: Left wildcard subdomain and right wildcard suffix</span></span>

<span data-ttu-id="f5fee-297">**Запись**: `*.contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="f5fee-297">**Entry**: `*.contoso.com/*`</span></span>

- <span data-ttu-id="f5fee-298">**Разрешить согласование** и **согласование блокировок**:</span><span class="sxs-lookup"><span data-stu-id="f5fee-298">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="f5fee-299">abc.contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="f5fee-299">abc.contoso.com/ab</span></span>
  - <span data-ttu-id="f5fee-300">abc.xyz.contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="f5fee-300">abc.xyz.contoso.com/a/b/c</span></span>
  - <span data-ttu-id="f5fee-301">www.contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="f5fee-301">www.contoso.com/a</span></span>
  - <span data-ttu-id="f5fee-302">www.contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="f5fee-302">www.contoso.com/b/a/c</span></span>
  - <span data-ttu-id="f5fee-303">xyz.contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="f5fee-303">xyz.contoso.com/ba</span></span>

- <span data-ttu-id="f5fee-304">**Разрешить не сопоставляемые** и непарные **блоки**: contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="f5fee-304">**Allow not matched** and **Block not matched**: contoso.com/b</span></span>

#### <a name="scenario-left-and-right-tilde"></a><span data-ttu-id="f5fee-305">Сценарий: левая и правая тильда</span><span class="sxs-lookup"><span data-stu-id="f5fee-305">Scenario: Left and right tilde</span></span>

<span data-ttu-id="f5fee-306">**Запись**: `~contoso.com~`</span><span class="sxs-lookup"><span data-stu-id="f5fee-306">**Entry**: `~contoso.com~`</span></span>

- <span data-ttu-id="f5fee-307">**Разрешить согласование** и **согласование блокировок**:</span><span class="sxs-lookup"><span data-stu-id="f5fee-307">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="f5fee-308">contoso.com</span><span class="sxs-lookup"><span data-stu-id="f5fee-308">contoso.com</span></span>
  - <span data-ttu-id="f5fee-309">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="f5fee-309">contoso.com/a</span></span>
  - <span data-ttu-id="f5fee-310">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f5fee-310">www.contoso.com</span></span>
  - <span data-ttu-id="f5fee-311">www.contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="f5fee-311">www.contoso.com/b</span></span>
  - <span data-ttu-id="f5fee-312">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f5fee-312">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="f5fee-313">**Разрешить не сопоставляемые** и несопоставленные **блоки**:</span><span class="sxs-lookup"><span data-stu-id="f5fee-313">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="f5fee-314">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="f5fee-314">123contoso.com</span></span>
  - <span data-ttu-id="f5fee-315">contoso.org</span><span class="sxs-lookup"><span data-stu-id="f5fee-315">contoso.org</span></span>

#### <a name="scenario-ip-address"></a><span data-ttu-id="f5fee-316">Сценарий: IP-адрес</span><span class="sxs-lookup"><span data-stu-id="f5fee-316">Scenario: IP address</span></span>

<span data-ttu-id="f5fee-317">**Запись**: `1.2.3.4`</span><span class="sxs-lookup"><span data-stu-id="f5fee-317">**Entry**: `1.2.3.4`</span></span>

- <span data-ttu-id="f5fee-318">**Разрешить ПОИСКПОЗ** и **блокировать ПОИСКПОЗ**: 1.2.3.4</span><span class="sxs-lookup"><span data-stu-id="f5fee-318">**Allow match** and **Block match**: 1.2.3.4</span></span>

- <span data-ttu-id="f5fee-319">**Разрешить не сопоставляемые** и несопоставленные **блоки**:</span><span class="sxs-lookup"><span data-stu-id="f5fee-319">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="f5fee-320">1.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="f5fee-320">1.2.3.4/a</span></span>
  - <span data-ttu-id="f5fee-321">11.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="f5fee-321">11.2.3.4/a</span></span>

#### <a name="ip-address-with-right-wildcard"></a><span data-ttu-id="f5fee-322">IP-адрес с подстановкой по правому краю</span><span class="sxs-lookup"><span data-stu-id="f5fee-322">IP address with right wildcard</span></span>

<span data-ttu-id="f5fee-323">**Запись**: `1.2.3.4/*`</span><span class="sxs-lookup"><span data-stu-id="f5fee-323">**Entry**: `1.2.3.4/*`</span></span>

- <span data-ttu-id="f5fee-324">**Разрешить согласование** и **согласование блокировок**:</span><span class="sxs-lookup"><span data-stu-id="f5fee-324">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="f5fee-325">1.2.3.4/b</span><span class="sxs-lookup"><span data-stu-id="f5fee-325">1.2.3.4/b</span></span>
  - <span data-ttu-id="f5fee-326">1.2.3.4/баааа</span><span class="sxs-lookup"><span data-stu-id="f5fee-326">1.2.3.4/baaaa</span></span>

### <a name="examples-of-invalid-entries"></a><span data-ttu-id="f5fee-327">Примеры недопустимых записей</span><span class="sxs-lookup"><span data-stu-id="f5fee-327">Examples of invalid entries</span></span>

<span data-ttu-id="f5fee-328">Следующие записи недопустимы:</span><span class="sxs-lookup"><span data-stu-id="f5fee-328">The following entries are invalid:</span></span>

- <span data-ttu-id="f5fee-329">**Отсутствующие или недопустимые значения домена**:</span><span class="sxs-lookup"><span data-stu-id="f5fee-329">**Missing or invalid domain values**:</span></span>

  - <span data-ttu-id="f5fee-330">компанией</span><span class="sxs-lookup"><span data-stu-id="f5fee-330">contoso</span></span>
  - <span data-ttu-id="f5fee-331">\*компанией.\*</span><span class="sxs-lookup"><span data-stu-id="f5fee-331">\*.contoso.\*</span></span>
  - <span data-ttu-id="f5fee-332">\*. com</span><span class="sxs-lookup"><span data-stu-id="f5fee-332">\*.com</span></span>
  - <span data-ttu-id="f5fee-333">\*. PDF</span><span class="sxs-lookup"><span data-stu-id="f5fee-333">\*.pdf</span></span>

- <span data-ttu-id="f5fee-334">**Подстановочный знак для текста или без пробелов**:</span><span class="sxs-lookup"><span data-stu-id="f5fee-334">**Wildcard on text or without spacing characters**:</span></span>

  - <span data-ttu-id="f5fee-335">\*contoso.com</span><span class="sxs-lookup"><span data-stu-id="f5fee-335">\*contoso.com</span></span>
  - <span data-ttu-id="f5fee-336">contoso.com\*</span><span class="sxs-lookup"><span data-stu-id="f5fee-336">contoso.com\*</span></span>
  - <span data-ttu-id="f5fee-337">\*1.2.3.4</span><span class="sxs-lookup"><span data-stu-id="f5fee-337">\*1.2.3.4</span></span>
  - <span data-ttu-id="f5fee-338">1.2.3.4\*</span><span class="sxs-lookup"><span data-stu-id="f5fee-338">1.2.3.4\*</span></span>
  - <span data-ttu-id="f5fee-339">contoso.com/a\*</span><span class="sxs-lookup"><span data-stu-id="f5fee-339">contoso.com/a\*</span></span>
  - <span data-ttu-id="f5fee-340">contoso.com/ab\*</span><span class="sxs-lookup"><span data-stu-id="f5fee-340">contoso.com/ab\*</span></span>

- <span data-ttu-id="f5fee-341">**IP-адреса с портами**:</span><span class="sxs-lookup"><span data-stu-id="f5fee-341">**IP addresses with ports**:</span></span>

  - <span data-ttu-id="f5fee-342">contoso.com:443</span><span class="sxs-lookup"><span data-stu-id="f5fee-342">contoso.com:443</span></span>
  - <span data-ttu-id="f5fee-343">abc.contoso.com:25</span><span class="sxs-lookup"><span data-stu-id="f5fee-343">abc.contoso.com:25</span></span>

- <span data-ttu-id="f5fee-344">**Подстановочные знаки, не являющиеся описательными**:</span><span class="sxs-lookup"><span data-stu-id="f5fee-344">**Non-descriptive wildcards**:</span></span>

  - \*
  - <span data-ttu-id="f5fee-345">\*.\*</span><span class="sxs-lookup"><span data-stu-id="f5fee-345">\*.\*</span></span>

- <span data-ttu-id="f5fee-346">**Посрединные подстановочные знаки**:</span><span class="sxs-lookup"><span data-stu-id="f5fee-346">**Middle wildcards**:</span></span>

  - <span data-ttu-id="f5fee-347">Конто \* so.com</span><span class="sxs-lookup"><span data-stu-id="f5fee-347">conto\*so.com</span></span>
  - <span data-ttu-id="f5fee-348">Конто ~ so. com</span><span class="sxs-lookup"><span data-stu-id="f5fee-348">conto~so.com</span></span>

- <span data-ttu-id="f5fee-349">**Знаки подстановки двойной замены**</span><span class="sxs-lookup"><span data-stu-id="f5fee-349">**Double wildcards**</span></span>

  - <span data-ttu-id="f5fee-350">contoso.com/\*\*</span><span class="sxs-lookup"><span data-stu-id="f5fee-350">contoso.com/\*\*</span></span>
  - <span data-ttu-id="f5fee-351">contoso.com/\*/\*</span><span class="sxs-lookup"><span data-stu-id="f5fee-351">contoso.com/\*/\*</span></span>
