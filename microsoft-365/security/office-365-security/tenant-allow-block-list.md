---
title: Управление разрешенным и заблокированными URL-адресами в списке разрешений или блокировок клиента
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
description: Администраторы могут узнать, как настраивать URL-адреса в списке разрешений или блокировок клиента в Центре безопасности & требованиям.
ms.openlocfilehash: 888a96f23daf2cf47847466ad4080f310be7f9b4
ms.sourcegitcommit: 260bbb93bbda62db9e88c021ccccfa75ac39a32e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/21/2020
ms.locfileid: "46845946"
---
# <a name="manage-urls-in-the-tenant-allowblock-list"></a><span data-ttu-id="266ee-103">Управление URL-адресами в списке разрешенных и заблокированных клиентов</span><span class="sxs-lookup"><span data-stu-id="266ee-103">Manage URLs in the Tenant Allow/Block List</span></span>

> [!NOTE]
> <span data-ttu-id="266ee-104">Возможности, описанные в этой статье, являются предварительными версиями, могут изменяться и доступны не во всех организациях.</span><span class="sxs-lookup"><span data-stu-id="266ee-104">The features described in this topic are in Preview, are subject to change, and are not available in all organizations.</span></span>

<span data-ttu-id="266ee-105">В организациях Microsoft 365 с почтовыми ящиками в Exchange Online или в организациях с автономной службой Exchange Online Protection (EOP) без почтовых ящиков Exchange Online можно обособить среду, которая не используется для фильтрации EOP.</span><span class="sxs-lookup"><span data-stu-id="266ee-105">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, you might disagree with the EOP filtering verdict.</span></span> <span data-ttu-id="266ee-106">Например, хорошее сообщение может быть помечено как плохое (ложное срабатывание) или сообщение с плохим (ложное отрицательное).</span><span class="sxs-lookup"><span data-stu-id="266ee-106">For example, a good message might be marked as bad (a false positive), or a bad message might be allowed through (a false negative).</span></span>

<span data-ttu-id="266ee-107">Список разрешений или блокировок клиента в Центре безопасности & требованиям позволяет вручную переопределить заявления фильтров Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="266ee-107">The Tenant Allow/Block List in the Security & Compliance Center gives you a way to manually override the Microsoft 365 filtering verdicts.</span></span> <span data-ttu-id="266ee-108">Список разрешений или блокировок клиента используется в потоке почты и во время нажатий пользователем.</span><span class="sxs-lookup"><span data-stu-id="266ee-108">The Tenant Allow/Block List is used during mail flow and at the time of user clicks.</span></span> <span data-ttu-id="266ee-109">Вы можете указать URL-адреса, которые следует разрешить или заблокировать в списке разрешенных или заблокированных клиентов.</span><span class="sxs-lookup"><span data-stu-id="266ee-109">You can specify URLs to allow or block in the Tenant Allow/Block List.</span></span>

<span data-ttu-id="266ee-110">В этом разделе описывается настройка записей в списке разрешений или блокировок клиента в Центре безопасности & соответствия требованиям или в PowerShell (Exchange Online PowerShell для организаций Microsoft 365 с почтовыми ящиками в Exchange Online; автономная оболочка PowerShell EOP для организаций без почтовых ящиков Exchange Online).</span><span class="sxs-lookup"><span data-stu-id="266ee-110">This topic describes how to configure entries in the Tenant Allow/Block List in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="266ee-111">Что нужно знать перед началом работы</span><span class="sxs-lookup"><span data-stu-id="266ee-111">What do you need to know before you begin?</span></span>

- <span data-ttu-id="266ee-112">Откройте Центр безопасности и соответствия требованиям на сайте <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="266ee-112">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="266ee-113">Чтобы перейти непосредственно на страницу **"Список разрешений или блокировок** клиента", используйте <https://protection.office.com/tenantAllowBlockList> этот параметр.</span><span class="sxs-lookup"><span data-stu-id="266ee-113">To go directly to the **Tenant Allow/Block List** page, use <https://protection.office.com/tenantAllowBlockList>.</span></span>

- <span data-ttu-id="266ee-114">Доступные значения URL-адресов описаны в [синтаксисе URL-адресов для раздела "Список разрешенных или заблокированных клиентов"](#url-syntax-for-the-tenant-allowblock-list) далее в этой статье.</span><span class="sxs-lookup"><span data-stu-id="266ee-114">The available URL values are described in the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this topic.</span></span>

- <span data-ttu-id="266ee-115">Список разрешений или блокировок клиента разрешает не более 500 записей для URL-адресов.</span><span class="sxs-lookup"><span data-stu-id="266ee-115">The Tenant Allow/Block List allows a maximum of 500 entries for URLs.</span></span>

- <span data-ttu-id="266ee-116">Запись должна быть активной в течение 15 минут.</span><span class="sxs-lookup"><span data-stu-id="266ee-116">An entry should be active within 15 minutes.</span></span>

- <span data-ttu-id="266ee-117">Блокирование записей имеет приоритет над разрешает.</span><span class="sxs-lookup"><span data-stu-id="266ee-117">Block entries take precedence over allow entries.</span></span>

- <span data-ttu-id="266ee-118">По умолчанию срок действия записей в списках разрешений или блокировок клиента истекает через 30 дней.</span><span class="sxs-lookup"><span data-stu-id="266ee-118">By default, entries in the Tenant Allow/Block List will expire after 30 days.</span></span> <span data-ttu-id="266ee-119">Можно указать дату или задать для них никогда неограниченный срок действия.</span><span class="sxs-lookup"><span data-stu-id="266ee-119">You can specify a date or set them to never expire.</span></span>

- <span data-ttu-id="266ee-120">Сведения о том, как подключиться к Exchange Online PowerShell, см. в статье [Подключение к Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="266ee-120">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="266ee-121">Чтобы подключиться к автономному EOP PowerShell, см. раздел [Подключение к PowerShell Exchange Online Protection](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="266ee-121">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="266ee-122">Чтобы вы могли выполнить процедуры, упомянутые в этой теме, вам должны быть назначены соответствующие разрешения.</span><span class="sxs-lookup"><span data-stu-id="266ee-122">You need to be assigned permissions before you can do the procedures in this topic:</span></span>

  - <span data-ttu-id="266ee-123">Чтобы добавить значения в черный список или черный список клиентов и удалить их из него, вы должны быть членом одной из следующих групп ролей:</span><span class="sxs-lookup"><span data-stu-id="266ee-123">To add and remove values from the Tenant Allow/Block List, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="266ee-124">**Управление организацией** или **Администратор безопасности** в [Центре безопасности и соответствия требованиям](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="266ee-124">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="266ee-125">**Управление организацией** или **Управление санацией** в [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="266ee-125">**Organization Management** or **Hygiene Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

  - <span data-ttu-id="266ee-126">Чтобы получить доступ к белому или запрещающему списку клиентов только для чтения, вы должны быть членом одной из следующих групп ролей:</span><span class="sxs-lookup"><span data-stu-id="266ee-126">For read-only access to the Tenant Allow/Block List, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="266ee-127">**Средство считывания сведений о безопасности** в [Центре безопасности и соответствия требованиям](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="266ee-127">**Security Reader** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="266ee-128">**Управление организацией с правами только на просмотр** в [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="266ee-128">**View-Only Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

## <a name="use-the-security--compliance-center-to-create-url-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="266ee-129">Создание записей URL-& адресов в списке разрешений или блокировок клиента с помощью Центра безопасности</span><span class="sxs-lookup"><span data-stu-id="266ee-129">Use the Security & Compliance Center to create URL entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="266ee-130">Дополнительные сведения о синтаксисе URL-адресов см. в [синтаксисе URL-адреса для раздела списка разрешенных и заблокированных](#url-syntax-for-the-tenant-allowblock-list) клиентов далее в этой статье.</span><span class="sxs-lookup"><span data-stu-id="266ee-130">For details about the syntax for URL entries, see the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this topic.</span></span>

1. <span data-ttu-id="266ee-131">В Центре безопасности & выберите списки разрешенных или блокирующих **Threat management** \> **Policy** \> **клиентов политики управления угрозами.**</span><span class="sxs-lookup"><span data-stu-id="266ee-131">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="266ee-132">На странице **"Список разрешений или блокировок** клиента" убедитесь, **что выбрана вкладка** URL-адресов, и нажмите кнопку **"Добавить"**</span><span class="sxs-lookup"><span data-stu-id="266ee-132">On the **Tenant Allow/Block List** page, verify that the **URLs** tab is selected, and then click **Add**</span></span>

3. <span data-ttu-id="266ee-133">В **появившемся** окне "Добавление новых URL-адресов" настройте следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="266ee-133">In the **Add new URLs** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="266ee-134">**Добавьте URL-адреса с подстановочными**знаками: введите по одному URL-адресу на строке до 20.</span><span class="sxs-lookup"><span data-stu-id="266ee-134">**Add URLs with wildcards**: Enter one URL per line, up to a maximum of 20.</span></span>

   - <span data-ttu-id="266ee-135">**Блокировать/разрешить:** выберите, следует ли **разрешить** или **заблокировать** указанные URL-адреса.</span><span class="sxs-lookup"><span data-stu-id="266ee-135">**Block/Allow**: Select whether you want to **Allow** or **Block** the specified URLs.</span></span>

   - <span data-ttu-id="266ee-136">**Срок действия никогда не**истекает: выполните одно из указанных ниже действий.</span><span class="sxs-lookup"><span data-stu-id="266ee-136">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="266ee-137">Убедитесь, что параметр выключен (выключен) и используйте поле "Срок действия элемента" для указания ![ ](../../media/scc-toggle-off.png) срока действия записей. **Expires on**</span><span class="sxs-lookup"><span data-stu-id="266ee-137">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entries.</span></span>

     <span data-ttu-id="266ee-138">или</span><span class="sxs-lookup"><span data-stu-id="266ee-138">or</span></span>

     - <span data-ttu-id="266ee-139">Чтобы настроить такой переключатель вправо, переместите переключатель вправо, чтобы настроить неограниченный срок действия записей:</span><span class="sxs-lookup"><span data-stu-id="266ee-139">Move the toggle to the right to configure the entries to never expire:</span></span> ![Включенный переключатель](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)<span data-ttu-id="266ee-141">.</span><span class="sxs-lookup"><span data-stu-id="266ee-141">.</span></span>

   - <span data-ttu-id="266ee-142">**Необязательное примечание:** введите текст с описательным текстом записей.</span><span class="sxs-lookup"><span data-stu-id="266ee-142">**Optional note**: Enter descriptive text for the entries.</span></span>

4. <span data-ttu-id="266ee-143">По завершении нажмите кнопку **"Добавить".**</span><span class="sxs-lookup"><span data-stu-id="266ee-143">When you're finished, click **Add**.</span></span>

## <a name="use-the-security--compliance-center-to-view-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="266ee-144">Использование Центра безопасности & соответствия требованиям для просмотра записей в списке разрешенных или заблокированных клиентов</span><span class="sxs-lookup"><span data-stu-id="266ee-144">Use the Security & Compliance Center to view entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="266ee-145">В Центре безопасности & выберите списки разрешенных или блокирующих **Threat management** \> **Policy** \> **клиентов политики управления угрозами.**</span><span class="sxs-lookup"><span data-stu-id="266ee-145">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="266ee-146">Перейдите на **вкладку "URL-адреса".**</span><span class="sxs-lookup"><span data-stu-id="266ee-146">Select the **URLs** tab.</span></span>

<span data-ttu-id="266ee-147">Чтобы отсортировать по возрастанию или убыванию, щелкните следующие заголовки столбцов:</span><span class="sxs-lookup"><span data-stu-id="266ee-147">Click on the following column headings to sort in ascending or descending order:</span></span>

- <span data-ttu-id="266ee-148">**Значение**</span><span class="sxs-lookup"><span data-stu-id="266ee-148">**Value**</span></span>
- <span data-ttu-id="266ee-149">**Действие:** **заблокировать или** **разрешить.**</span><span class="sxs-lookup"><span data-stu-id="266ee-149">**Action**: **Block** or **Allow**.</span></span>
- <span data-ttu-id="266ee-150">**Дата последнего обновления**</span><span class="sxs-lookup"><span data-stu-id="266ee-150">**Last updated date**</span></span>
- <span data-ttu-id="266ee-151">**Дата окончания срок**</span><span class="sxs-lookup"><span data-stu-id="266ee-151">**Expiration date**</span></span>
- <span data-ttu-id="266ee-152">**Примечание**</span><span class="sxs-lookup"><span data-stu-id="266ee-152">**Note**</span></span>

<span data-ttu-id="266ee-153">Выберите **"Групповая",** чтобы сгруппировать **записи** по действиям **(запретить** **или**разрешить) **или "Нет".**</span><span class="sxs-lookup"><span data-stu-id="266ee-153">Click **Group** to group the entries by **Action** (**Block** or **Allow**) or **None**.</span></span>

<span data-ttu-id="266ee-154">Нажмите **"Поиск"**(или введите значение целиком) или часть значения и нажмите клавишу ВВОД, чтобы найти нужное значение.</span><span class="sxs-lookup"><span data-stu-id="266ee-154">Click **Search**, enter all or part of a value, and then press ENTER to find a specific value.</span></span> <span data-ttu-id="266ee-155">Когда все будет готово, щелкните значок **очистить** ![ ](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif) поиск.</span><span class="sxs-lookup"><span data-stu-id="266ee-155">When you're finished, click **Clear search** ![Clear search icon](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif).</span></span>

<span data-ttu-id="266ee-156">Щелкните **"Фильтр".**</span><span class="sxs-lookup"><span data-stu-id="266ee-156">Click **Filter**.</span></span> <span data-ttu-id="266ee-157">В **появившемся** окне "Фильтр" настройте любые из следующих параметров:</span><span class="sxs-lookup"><span data-stu-id="266ee-157">In the **Filter** flyout that appears, configure any of the following settings:</span></span>

- <span data-ttu-id="266ee-158">**Действие:** выберите **"Разрешить",** **"Блокировать" или** "оба".</span><span class="sxs-lookup"><span data-stu-id="266ee-158">**Action**: Select **Allow**, **Block** or both.</span></span>

- <span data-ttu-id="266ee-159">**Срок действия не истекает:** выбирайте ![ (переключатель) ](../../media/scc-toggle-off.png) или включите ( ![ установите переключатель). ](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)</span><span class="sxs-lookup"><span data-stu-id="266ee-159">**Never expire**: Select off (![Toggle off](../../media/scc-toggle-off.png)) or on (![Toggle on](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)).</span></span>

- <span data-ttu-id="266ee-160">**Last updated**: Select a start date (**From),** an end date (**To)** or both.</span><span class="sxs-lookup"><span data-stu-id="266ee-160">**Last updated**: Select a start date (**From**), an end date (**To**) or both.</span></span>

- <span data-ttu-id="266ee-161">**Дата окончания**срока действия: выберите дату начала (**"Из")** и /оба**варианта.**</span><span class="sxs-lookup"><span data-stu-id="266ee-161">**Expiration date**: Select a start date (**From**), an end date (**To**) or both.</span></span>

<span data-ttu-id="266ee-162">Закончив, нажмите кнопку **"Применить".**</span><span class="sxs-lookup"><span data-stu-id="266ee-162">When you're finished, click **Apply**.</span></span>

<span data-ttu-id="266ee-163">Чтобы очистить существующие фильтры, щелкните **"Фильтр"** и в появившемся окне **"Фильтр"** нажмите кнопку **"Очистить фильтры".**</span><span class="sxs-lookup"><span data-stu-id="266ee-163">To clear existing filters, click **Filter**, and in the **Filter** flyout that appears, click **Clear filters**.</span></span>

## <a name="use-the-security--compliance-center-to-modify-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="266ee-164">Использование Центра безопасности & безопасности для изменения записей в списке разрешенных или заблокированных клиентов</span><span class="sxs-lookup"><span data-stu-id="266ee-164">Use the Security & Compliance Center to modify entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="266ee-165">Нельзя изменить само значение URL-адреса.</span><span class="sxs-lookup"><span data-stu-id="266ee-165">You can't modify the URL value itself.</span></span> <span data-ttu-id="266ee-166">Необходимо удалить запись, а затем воссоздать ее.</span><span class="sxs-lookup"><span data-stu-id="266ee-166">Instead, you need to delete the entry and recreate it.</span></span>

1. <span data-ttu-id="266ee-167">В Центре безопасности & выберите списки разрешенных или блокирующих **Threat management** \> **Policy** \> **клиентов политики управления угрозами.**</span><span class="sxs-lookup"><span data-stu-id="266ee-167">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="266ee-168">Перейдите на **вкладку "URL-адреса".**</span><span class="sxs-lookup"><span data-stu-id="266ee-168">Select the **URLs** tab.</span></span>

3. <span data-ttu-id="266ee-169">Выберите запись, которую вы хотите изменить, и нажмите значок **"Изменить** ![ изменить". ](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png)</span><span class="sxs-lookup"><span data-stu-id="266ee-169">Select the entry that you want to modify, and then click **Edit** ![Edit icon](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png).</span></span>

4. <span data-ttu-id="266ee-170">В отображенной всплывающем элементе настройте следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="266ee-170">In the flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="266ee-171">**Блокировать/разрешить:** выберите **"Разрешить или** **заблокировать".**</span><span class="sxs-lookup"><span data-stu-id="266ee-171">**Block/Allow**: Select **Allow** or **Block**.</span></span>

   - <span data-ttu-id="266ee-172">**Срок действия никогда не**истекает: выполните одно из указанных ниже действий.</span><span class="sxs-lookup"><span data-stu-id="266ee-172">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="266ee-173">Убедитесь, что параметр выключен (выключен) и используйте поле "Срок действия элемента" для указания ![ ](../../media/scc-toggle-off.png) даты срока действия записи. **Expires on**</span><span class="sxs-lookup"><span data-stu-id="266ee-173">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entry.</span></span>

     <span data-ttu-id="266ee-174">или</span><span class="sxs-lookup"><span data-stu-id="266ee-174">or</span></span>

     - <span data-ttu-id="266ee-175">Чтобы настроить срок действия записи, переместите вправо перемещаемый переключатель:</span><span class="sxs-lookup"><span data-stu-id="266ee-175">Move the toggle to the right to configure the entry to never expire:</span></span> ![Включенный переключатель](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)<span data-ttu-id="266ee-177">.</span><span class="sxs-lookup"><span data-stu-id="266ee-177">.</span></span>

   - <span data-ttu-id="266ee-178">**Необязательное примечание:** введите текст с текстом, который появляется для записи.</span><span class="sxs-lookup"><span data-stu-id="266ee-178">**Optional note**: Enter descriptive text for the entry.</span></span>

5. <span data-ttu-id="266ee-179">Выполнив необходимые действия, нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="266ee-179">When you're finished, click **Save**.</span></span>

## <a name="use-the-security--compliance-center-to-remove-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="266ee-180">Удаление записей из списка & разрешений или блокировок клиента с помощью Центра безопасности для доступа</span><span class="sxs-lookup"><span data-stu-id="266ee-180">Use the Security & Compliance Center to remove entries from the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="266ee-181">В Центре безопасности & выберите списки разрешенных или блокирующих **Threat management** \> **Policy** \> **клиентов политики управления угрозами.**</span><span class="sxs-lookup"><span data-stu-id="266ee-181">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="266ee-182">Перейдите на **вкладку "URL-адреса".**</span><span class="sxs-lookup"><span data-stu-id="266ee-182">Select the **URLs** tab.</span></span>

3. <span data-ttu-id="266ee-183">Выберите удаляемую запись и нажмите значок **Delete** ![ "Удалить". ](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png)</span><span class="sxs-lookup"><span data-stu-id="266ee-183">Select the entry that you want to remove, and then click **Delete** ![Delete icon](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png).</span></span>

4. <span data-ttu-id="266ee-184">В появившемся диалоговом окне предупреждения нажмите кнопку **"Удалить".**</span><span class="sxs-lookup"><span data-stu-id="266ee-184">In the warning dialog that appears, click **Delete**.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-the-tenant-allowblock-list"></a><span data-ttu-id="266ee-185">Использование Exchange Online PowerShell или автономной службы EOP PowerShell для настройки списка разрешенных или заблокированных клиентов</span><span class="sxs-lookup"><span data-stu-id="266ee-185">Use Exchange Online PowerShell or standalone EOP PowerShell to configure the Tenant Allow/Block List</span></span>

### <a name="use-powershell-to-add-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="266ee-186">Добавление записей в черный или черный список клиентов с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="266ee-186">Use PowerShell to add entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="266ee-187">Чтобы добавить записи в черный список или блокировок клиента, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="266ee-187">To add entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
New-TenantAllowBlockListItems -ListType Url -Action <Allow | Block> -Entries <String[]> [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

<span data-ttu-id="266ee-188">В этом примере добавляется запись блокировки URL-адресов для contoso.com всех дочерних доменов (например, contoso.com, www.contoso.com и xyz.abc.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="266ee-188">This example adds a URL block entry for contoso.com and all subdomains (for example, contoso.com, www.contoso.com, and xyz.abc.contoso.com).</span></span> <span data-ttu-id="266ee-189">Так как мы не использули параметры ExpirationDate или NoExpiration, срок действия записи истекает через 30 дней.</span><span class="sxs-lookup"><span data-stu-id="266ee-189">Because we didn't use the ExpirationDate or NoExpiration parameters, the entry expires after 30 days.</span></span>

```powershell
New-TenantAllowBlockListItem -ListType Url -Action Block -Entries ~contoso.com
```

<span data-ttu-id="266ee-190">Дополнительные сведения о синтаксисе и параметрах [см. в разделе New-TenantAllowBlockListItems.](https://docs.microsoft.com/powershell/module/exchange/new-tenantallowblocklistitems)</span><span class="sxs-lookup"><span data-stu-id="266ee-190">For detailed syntax and parameter information, see [New-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/new-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-view-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="266ee-191">Просмотр записей в черных или блокируемых списках клиентов с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="266ee-191">Use PowerShell to view entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="266ee-192">Чтобы просмотреть записи в черных или заблокированных списках клиентов, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="266ee-192">To view entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType Url [-Entry <URLValue>] [-Action <Allow | Block>] [-ExpirationDate <DateTime>] [-NoExpiration]
```

<span data-ttu-id="266ee-193">В этом примере возвращаются все заблокированные URL-адреса.</span><span class="sxs-lookup"><span data-stu-id="266ee-193">This example returns all blocked URLs.</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType Url -Action Block
```

<span data-ttu-id="266ee-194">Дополнительные сведения о синтаксисе и параметрах см. в [статье Get-TenantAllowBlockListItems.](https://docs.microsoft.com/powershell/module/exchange/get-tenantallowblocklistitems)</span><span class="sxs-lookup"><span data-stu-id="266ee-194">For detailed syntax and parameter information, see [Get-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/get-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-modify-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="266ee-195">Использование PowerShell для изменения записей в списке разрешений или блокировок клиента</span><span class="sxs-lookup"><span data-stu-id="266ee-195">Use PowerShell to modify entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="266ee-196">Нельзя изменить само значение URL-адреса.</span><span class="sxs-lookup"><span data-stu-id="266ee-196">You can't modify the URL value itself.</span></span> <span data-ttu-id="266ee-197">Необходимо удалить запись, а затем воссоздать ее.</span><span class="sxs-lookup"><span data-stu-id="266ee-197">Instead, you need to delete the entry and recreate it.</span></span>

<span data-ttu-id="266ee-198">Чтобы изменить записи в черных или заблокированных списках клиентов, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="266ee-198">To modify entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType Url -Ids <"Id1","Id2",..."IdN"> [-Action <Allow | Block>] [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

<span data-ttu-id="266ee-199">В этом примере изменяется срок действия указанной записи.</span><span class="sxs-lookup"><span data-stu-id="266ee-199">This example changes the expiration date of the specified entry.</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -ExpirationDate (Get-Date "5/30/2020 9:30 AM").ToUniversalTime()
```

<span data-ttu-id="266ee-200">Дополнительные сведения о синтаксисе и параметрах см. в [разделе Set-TenantAllowBlockListItems.](https://docs.microsoft.com/powershell/module/exchange/set-tenantallowblocklistitems)</span><span class="sxs-lookup"><span data-stu-id="266ee-200">For detailed syntax and parameter information, see [Set-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/set-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-remove-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="266ee-201">Использование PowerShell для удаления записей из черного списка или разрешений клиентов</span><span class="sxs-lookup"><span data-stu-id="266ee-201">Use PowerShell to remove entries from the Tenant Allow/Block List</span></span>

<span data-ttu-id="266ee-202">Чтобы удалить записи из черного или черного списка клиентов, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="266ee-202">To remove entries from the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType Url -Ids <"Id1","Id2",..."IdN">
```

<span data-ttu-id="266ee-203">Этот пример удаляет запись URL-адреса из списка разрешенных или заблокированных доменов для клиента.</span><span class="sxs-lookup"><span data-stu-id="266ee-203">This example removes the specified URL entry from the Tenant Allow/Block List.</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSPAAAA0"
```

<span data-ttu-id="266ee-204">Дополнительные сведения о синтаксисе и параметрах [см. в статье Remove-TenantAllowBlockListItems.](https://docs.microsoft.com/powershell/module/exchange/remove-tenantallowblocklistitems)</span><span class="sxs-lookup"><span data-stu-id="266ee-204">For detailed syntax and parameter information, see [Remove-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/remove-tenantallowblocklistitems).</span></span>

## <a name="url-syntax-for-the-tenant-allowblock-list"></a><span data-ttu-id="266ee-205">Синтаксис URL-адреса для списка разрешенных или заблокированных адресов клиента</span><span class="sxs-lookup"><span data-stu-id="266ee-205">URL syntax for the Tenant Allow/Block List</span></span>

- <span data-ttu-id="266ee-206">Адреса IP4v и IPv6 разрешены, а TCP/UDP-порты не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="266ee-206">IP4v and IPv6 addresses are allowed, but TCP/UDP ports are not.</span></span>

- <span data-ttu-id="266ee-207">Расширения файлов не допускаются (например, test.pdf).</span><span class="sxs-lookup"><span data-stu-id="266ee-207">Filename extensions are not allowed (for example, test.pdf).</span></span>

- <span data-ttu-id="266ee-208">Юникод не поддерживается, а Punycode — код.</span><span class="sxs-lookup"><span data-stu-id="266ee-208">Unicode is not supported, but Punycode is.</span></span>

- <span data-ttu-id="266ee-209">Имена узлов допускаются, если собираются все следующие операторы:</span><span class="sxs-lookup"><span data-stu-id="266ee-209">Hostnames are allowed if all of the following statements are true:</span></span>

  - <span data-ttu-id="266ee-210">Имя узла содержит точку.</span><span class="sxs-lookup"><span data-stu-id="266ee-210">The hostname contains a period.</span></span>
  - <span data-ttu-id="266ee-211">Слева от точки назначается хотя бы один знак.</span><span class="sxs-lookup"><span data-stu-id="266ee-211">There is at least one character to the left of the period.</span></span>
  - <span data-ttu-id="266ee-212">Точка содержит по крайней мере два символа.</span><span class="sxs-lookup"><span data-stu-id="266ee-212">There are at least two characters to the right of the period.</span></span>

  <span data-ttu-id="266ee-213">Например, `t.co` это допускается или `.com` `contoso.` запрещено.</span><span class="sxs-lookup"><span data-stu-id="266ee-213">For example, `t.co` is allowed; `.com` or `contoso.` are not allowed.</span></span>

- <span data-ttu-id="266ee-214">Вложенные пути не подходят.</span><span class="sxs-lookup"><span data-stu-id="266ee-214">Subpaths are not implied.</span></span>

  <span data-ttu-id="266ee-215">Например, без `contoso.com` включения. `contoso.com/a`</span><span class="sxs-lookup"><span data-stu-id="266ee-215">For example, `contoso.com` does not include `contoso.com/a`.</span></span>

- <span data-ttu-id="266ee-216">Подстановочные знаки (\*) разрешены в следующих сценариях.</span><span class="sxs-lookup"><span data-stu-id="266ee-216">Wildcards (\*) are allowed in the following scenarios:</span></span>

  - <span data-ttu-id="266ee-217">Следует за простым подстановочным знаком задать поддомен точку.</span><span class="sxs-lookup"><span data-stu-id="266ee-217">A left wildcard must be followed by a period to specify a subdomain.</span></span>

    <span data-ttu-id="266ee-218">Например, `*.contoso.com` разрешено; `*contoso.com` не разрешено.</span><span class="sxs-lookup"><span data-stu-id="266ee-218">For example, `*.contoso.com` is allowed; `*contoso.com` is not allowed.</span></span>

  - <span data-ttu-id="266ee-219">Чтобы указать путь, необходимо следовать указаниям правого подстановочного знака косой черты (/).</span><span class="sxs-lookup"><span data-stu-id="266ee-219">A right wildcard must follow a forward slash (/) to specify a path.</span></span>

    <span data-ttu-id="266ee-220">Например, `contoso.com/*` это допускается или `contoso.com*` `contoso.com/ab*` запрещено.</span><span class="sxs-lookup"><span data-stu-id="266ee-220">For example, `contoso.com/*` is allowed; `contoso.com*` or `contoso.com/ab*` are not allowed.</span></span>

  - <span data-ttu-id="266ee-221">Все дочерние пути не подразумевается соответствующим подстановочным знаком.</span><span class="sxs-lookup"><span data-stu-id="266ee-221">All subpaths are not implied by a right wildcard.</span></span>

    <span data-ttu-id="266ee-222">Например, без `contoso.com/*` включения. `contoso.com/a`</span><span class="sxs-lookup"><span data-stu-id="266ee-222">For example, `contoso.com/*` does not include `contoso.com/a`.</span></span>

  - <span data-ttu-id="266ee-223">`*.com*` является недопустимым (не допустимым доменом, для которых реакция в качестве подходящего подстановочного знака не следует символу косой черты).</span><span class="sxs-lookup"><span data-stu-id="266ee-223">`*.com*` is invalid (not a resolvable domain and the right wildcard does not follow a forward slash).</span></span>

  - <span data-ttu-id="266ee-224">В IP-адресах нельзя использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="266ee-224">Wildcards are not allowed in IP addresses.</span></span>

- <span data-ttu-id="266ee-225">Символ тильда (~) доступен в следующих сценариях:</span><span class="sxs-lookup"><span data-stu-id="266ee-225">The tilde (~) character is available in the following scenarios:</span></span>

  - <span data-ttu-id="266ee-226">Левая тильда подразумевает домен и все дочерние домены.</span><span class="sxs-lookup"><span data-stu-id="266ee-226">A left tilde implies a domain and all subdomains.</span></span>

    <span data-ttu-id="266ee-227">Например, `~contoso.com` включает `contoso.com` `*.contoso.com` и.</span><span class="sxs-lookup"><span data-stu-id="266ee-227">For example `~contoso.com` includes `contoso.com` and `*.contoso.com`.</span></span>

- <span data-ttu-id="266ee-228">URL-адреса, содержащие протоколы (например, , или) не будут `http://` `https://` `ftp://` работать, потому что URL-записи применяются ко всем протоколам.</span><span class="sxs-lookup"><span data-stu-id="266ee-228">URL entries that contain protocols (for example, `http://`, `https://`, or `ftp://`) will fail, because URL entries apply to all protocols.</span></span>

- <span data-ttu-id="266ee-229">Имя пользователя и пароль не поддерживаются и не обязательны.</span><span class="sxs-lookup"><span data-stu-id="266ee-229">A username or password aren't supported or required.</span></span>

- <span data-ttu-id="266ee-230">Кавычки (' или ") предусмайствует недопустимые символы.</span><span class="sxs-lookup"><span data-stu-id="266ee-230">Quotes (' or ") are invalid characters.</span></span>

- <span data-ttu-id="266ee-231">URL-адрес должен по возможности включать все перенаправления.</span><span class="sxs-lookup"><span data-stu-id="266ee-231">A URL should include all redirects where possible.</span></span>

### <a name="url-entry-scenarios"></a><span data-ttu-id="266ee-232">Сценарии ввода URL-адресов</span><span class="sxs-lookup"><span data-stu-id="266ee-232">URL entry scenarios</span></span>

<span data-ttu-id="266ee-233">Допустимые записи URL-адресов и их результаты описаны в следующих разделах.</span><span class="sxs-lookup"><span data-stu-id="266ee-233">Valid URL entries and their results are described in the following sections.</span></span>

#### <a name="scenario-no-wildcards"></a><span data-ttu-id="266ee-234">Сценарий: подстановочные знаки отсутствуют</span><span class="sxs-lookup"><span data-stu-id="266ee-234">Scenario: No wildcards</span></span>

<span data-ttu-id="266ee-235">**Entry**: `contoso.com`</span><span class="sxs-lookup"><span data-stu-id="266ee-235">**Entry**: `contoso.com`</span></span>

- <span data-ttu-id="266ee-236">**Разрешить совпадение:** contoso.com</span><span class="sxs-lookup"><span data-stu-id="266ee-236">**Allow match**: contoso.com</span></span>

- <span data-ttu-id="266ee-237">**Разрешить не совпадение:**</span><span class="sxs-lookup"><span data-stu-id="266ee-237">**Allow not matched**:</span></span>

  - <span data-ttu-id="266ee-238">abc-contoso.com</span><span class="sxs-lookup"><span data-stu-id="266ee-238">abc-contoso.com</span></span>
  - <span data-ttu-id="266ee-239">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="266ee-239">contoso.com/a</span></span>
  - <span data-ttu-id="266ee-240">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="266ee-240">payroll.contoso.com</span></span>
  - <span data-ttu-id="266ee-241">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="266ee-241">test.com/contoso.com</span></span>
  - <span data-ttu-id="266ee-242">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="266ee-242">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="266ee-243">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="266ee-243">www.contoso.com</span></span>
  - <span data-ttu-id="266ee-244">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="266ee-244">www.contoso.com/q=a@contoso.com</span></span>
  
- <span data-ttu-id="266ee-245">**Block match**:</span><span class="sxs-lookup"><span data-stu-id="266ee-245">**Block match**:</span></span>

  - <span data-ttu-id="266ee-246">contoso.com</span><span class="sxs-lookup"><span data-stu-id="266ee-246">contoso.com</span></span>
  - <span data-ttu-id="266ee-247">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="266ee-247">contoso.com/a</span></span>
  - <span data-ttu-id="266ee-248">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="266ee-248">payroll.contoso.com</span></span>
  - <span data-ttu-id="266ee-249">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="266ee-249">test.com/contoso.com</span></span>
  - <span data-ttu-id="266ee-250">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="266ee-250">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="266ee-251">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="266ee-251">www.contoso.com</span></span>
  - <span data-ttu-id="266ee-252">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="266ee-252">www.contoso.com/q=a@contoso.com</span></span>

- <span data-ttu-id="266ee-253">**Блокировать не совпадений:** abc-contoso.com</span><span class="sxs-lookup"><span data-stu-id="266ee-253">**Block not matched**: abc-contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain"></a><span data-ttu-id="266ee-254">Сценарий: левый подстановочный знак (дочерний домен)</span><span class="sxs-lookup"><span data-stu-id="266ee-254">Scenario: Left wildcard (subdomain)</span></span>

<span data-ttu-id="266ee-255">**Entry**: `*.contoso.com`</span><span class="sxs-lookup"><span data-stu-id="266ee-255">**Entry**: `*.contoso.com`</span></span>

- <span data-ttu-id="266ee-256">**Разрешить совпадение** **и блокировку:**</span><span class="sxs-lookup"><span data-stu-id="266ee-256">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="266ee-257">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="266ee-257">www.contoso.com</span></span>
  - <span data-ttu-id="266ee-258">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="266ee-258">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="266ee-259">**Разрешить несовпадение** и блокировку не **совпадает:**</span><span class="sxs-lookup"><span data-stu-id="266ee-259">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="266ee-260">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="266ee-260">123contoso.com</span></span>
  - <span data-ttu-id="266ee-261">contoso.com</span><span class="sxs-lookup"><span data-stu-id="266ee-261">contoso.com</span></span>
  - <span data-ttu-id="266ee-262">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="266ee-262">test.com/contoso.com</span></span>
  - <span data-ttu-id="266ee-263">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="266ee-263">www.contoso.com/abc</span></span>
  
#### <a name="scenario-right-wildcard-at-top-of-path"></a><span data-ttu-id="266ee-264">Сценарий: прямой подстановочный знак вверху пути</span><span class="sxs-lookup"><span data-stu-id="266ee-264">Scenario: Right wildcard at top of path</span></span>

<span data-ttu-id="266ee-265">**Entry**: `contoso.com/a/*`</span><span class="sxs-lookup"><span data-stu-id="266ee-265">**Entry**: `contoso.com/a/*`</span></span>

- <span data-ttu-id="266ee-266">**Разрешить совпадение** **и блокировку:**</span><span class="sxs-lookup"><span data-stu-id="266ee-266">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="266ee-267">contoso.com/a/b</span><span class="sxs-lookup"><span data-stu-id="266ee-267">contoso.com/a/b</span></span>
  - <span data-ttu-id="266ee-268">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="266ee-268">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="266ee-269">contoso.com/a/?q=joe@t.com</span><span class="sxs-lookup"><span data-stu-id="266ee-269">contoso.com/a/?q=joe@t.com</span></span>

- <span data-ttu-id="266ee-270">**Разрешить несовпадение** и блокировку не **совпадает:**</span><span class="sxs-lookup"><span data-stu-id="266ee-270">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="266ee-271">contoso.com</span><span class="sxs-lookup"><span data-stu-id="266ee-271">contoso.com</span></span>
  - <span data-ttu-id="266ee-272">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="266ee-272">contoso.com/a</span></span>
  - <span data-ttu-id="266ee-273">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="266ee-273">www.contoso.com</span></span>
  - <span data-ttu-id="266ee-274">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="266ee-274">www.contoso.com/q=a@contoso.com</span></span>
  
#### <a name="scenario-left-tilde"></a><span data-ttu-id="266ee-275">Сценарий: левая тильда</span><span class="sxs-lookup"><span data-stu-id="266ee-275">Scenario: Left tilde</span></span>

<span data-ttu-id="266ee-276">**Entry**: `~contoso.com`</span><span class="sxs-lookup"><span data-stu-id="266ee-276">**Entry**: `~contoso.com`</span></span>

- <span data-ttu-id="266ee-277">**Разрешить совпадение** **и блокировку:**</span><span class="sxs-lookup"><span data-stu-id="266ee-277">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="266ee-278">contoso.com</span><span class="sxs-lookup"><span data-stu-id="266ee-278">contoso.com</span></span>
  - <span data-ttu-id="266ee-279">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="266ee-279">www.contoso.com</span></span>
  - <span data-ttu-id="266ee-280">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="266ee-280">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="266ee-281">**Разрешить несовпадение** и блокировку не **совпадает:**</span><span class="sxs-lookup"><span data-stu-id="266ee-281">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="266ee-282">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="266ee-282">123contoso.com</span></span>
  - <span data-ttu-id="266ee-283">contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="266ee-283">contoso.com/abc</span></span>
  - <span data-ttu-id="266ee-284">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="266ee-284">www.contoso.com/abc</span></span>

#### <a name="scenario-right-wildcard-suffix"></a><span data-ttu-id="266ee-285">Сценарий: подходящий суффикс подстановочных знаков</span><span class="sxs-lookup"><span data-stu-id="266ee-285">Scenario: Right wildcard suffix</span></span>

<span data-ttu-id="266ee-286">**Entry**: `contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="266ee-286">**Entry**: `contoso.com/*`</span></span>

- <span data-ttu-id="266ee-287">**Разрешить совпадение** **и блокировку:**</span><span class="sxs-lookup"><span data-stu-id="266ee-287">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="266ee-288">contoso.com/?q=whatever@fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="266ee-288">contoso.com/?q=whatever@fabrikam.com</span></span>
  - <span data-ttu-id="266ee-289">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="266ee-289">contoso.com/a</span></span>
  - <span data-ttu-id="266ee-290">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="266ee-290">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="266ee-291">contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="266ee-291">contoso.com/ab</span></span>
  - <span data-ttu-id="266ee-292">contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="266ee-292">contoso.com/b</span></span>
  - <span data-ttu-id="266ee-293">contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="266ee-293">contoso.com/b/a/c</span></span>
  - <span data-ttu-id="266ee-294">contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="266ee-294">contoso.com/ba</span></span>

- <span data-ttu-id="266ee-295">**Разрешить несовпадение** **и блокировку:** contoso.com</span><span class="sxs-lookup"><span data-stu-id="266ee-295">**Allow not matched** and **Block not matched**: contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain-and-right-wildcard-suffix"></a><span data-ttu-id="266ee-296">Сценарий: левый поддомен с подстановочными знаками и правой суффикс подстановочных знаков</span><span class="sxs-lookup"><span data-stu-id="266ee-296">Scenario: Left wildcard subdomain and right wildcard suffix</span></span>

<span data-ttu-id="266ee-297">**Entry**: `*.contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="266ee-297">**Entry**: `*.contoso.com/*`</span></span>

- <span data-ttu-id="266ee-298">**Разрешить совпадение** **и блокировку:**</span><span class="sxs-lookup"><span data-stu-id="266ee-298">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="266ee-299">abc.contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="266ee-299">abc.contoso.com/ab</span></span>
  - <span data-ttu-id="266ee-300">abc.xyz.contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="266ee-300">abc.xyz.contoso.com/a/b/c</span></span>
  - <span data-ttu-id="266ee-301">www.contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="266ee-301">www.contoso.com/a</span></span>
  - <span data-ttu-id="266ee-302">www.contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="266ee-302">www.contoso.com/b/a/c</span></span>
  - <span data-ttu-id="266ee-303">xyz.contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="266ee-303">xyz.contoso.com/ba</span></span>

- <span data-ttu-id="266ee-304">**Разрешить несовпадение** **и блокировку:** contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="266ee-304">**Allow not matched** and **Block not matched**: contoso.com/b</span></span>

#### <a name="scenario-left-and-right-tilde"></a><span data-ttu-id="266ee-305">Сценарий: левая и правая тильда</span><span class="sxs-lookup"><span data-stu-id="266ee-305">Scenario: Left and right tilde</span></span>

<span data-ttu-id="266ee-306">**Entry**: `~contoso.com~`</span><span class="sxs-lookup"><span data-stu-id="266ee-306">**Entry**: `~contoso.com~`</span></span>

- <span data-ttu-id="266ee-307">**Разрешить совпадение** **и блокировку:**</span><span class="sxs-lookup"><span data-stu-id="266ee-307">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="266ee-308">contoso.com</span><span class="sxs-lookup"><span data-stu-id="266ee-308">contoso.com</span></span>
  - <span data-ttu-id="266ee-309">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="266ee-309">contoso.com/a</span></span>
  - <span data-ttu-id="266ee-310">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="266ee-310">www.contoso.com</span></span>
  - <span data-ttu-id="266ee-311">www.contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="266ee-311">www.contoso.com/b</span></span>
  - <span data-ttu-id="266ee-312">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="266ee-312">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="266ee-313">**Разрешить несовпадение** и блокировку не **совпадает:**</span><span class="sxs-lookup"><span data-stu-id="266ee-313">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="266ee-314">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="266ee-314">123contoso.com</span></span>
  - <span data-ttu-id="266ee-315">contoso.org</span><span class="sxs-lookup"><span data-stu-id="266ee-315">contoso.org</span></span>

#### <a name="scenario-ip-address"></a><span data-ttu-id="266ee-316">Сценарий: IP-адрес</span><span class="sxs-lookup"><span data-stu-id="266ee-316">Scenario: IP address</span></span>

<span data-ttu-id="266ee-317">**Entry**: `1.2.3.4`</span><span class="sxs-lookup"><span data-stu-id="266ee-317">**Entry**: `1.2.3.4`</span></span>

- <span data-ttu-id="266ee-318">**Разрешить** **совпадение и блокировку:** 1.2.3.4</span><span class="sxs-lookup"><span data-stu-id="266ee-318">**Allow match** and **Block match**: 1.2.3.4</span></span>

- <span data-ttu-id="266ee-319">**Разрешить несовпадение** и блокировку не **совпадает:**</span><span class="sxs-lookup"><span data-stu-id="266ee-319">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="266ee-320">1.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="266ee-320">1.2.3.4/a</span></span>
  - <span data-ttu-id="266ee-321">11.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="266ee-321">11.2.3.4/a</span></span>

#### <a name="ip-address-with-right-wildcard"></a><span data-ttu-id="266ee-322">IP-адрес с правильным подстановочным знаком</span><span class="sxs-lookup"><span data-stu-id="266ee-322">IP address with right wildcard</span></span>

<span data-ttu-id="266ee-323">**Entry**: `1.2.3.4/*`</span><span class="sxs-lookup"><span data-stu-id="266ee-323">**Entry**: `1.2.3.4/*`</span></span>

- <span data-ttu-id="266ee-324">**Разрешить совпадение** **и блокировку:**</span><span class="sxs-lookup"><span data-stu-id="266ee-324">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="266ee-325">1.2.3.4/b</span><span class="sxs-lookup"><span data-stu-id="266ee-325">1.2.3.4/b</span></span>
  - <span data-ttu-id="266ee-326">1.2.3.4/baaaa</span><span class="sxs-lookup"><span data-stu-id="266ee-326">1.2.3.4/baaaa</span></span>

### <a name="examples-of-invalid-entries"></a><span data-ttu-id="266ee-327">Примеры недопустимых записей</span><span class="sxs-lookup"><span data-stu-id="266ee-327">Examples of invalid entries</span></span>

<span data-ttu-id="266ee-328">Следующие записи являются недопустимыми:</span><span class="sxs-lookup"><span data-stu-id="266ee-328">The following entries are invalid:</span></span>

- <span data-ttu-id="266ee-329">**Отсутствуют или недопустимые значения доменов:**</span><span class="sxs-lookup"><span data-stu-id="266ee-329">**Missing or invalid domain values**:</span></span>

  - <span data-ttu-id="266ee-330">contoso</span><span class="sxs-lookup"><span data-stu-id="266ee-330">contoso</span></span>
  - <span data-ttu-id="266ee-331">\*.contoso.\*</span><span class="sxs-lookup"><span data-stu-id="266ee-331">\*.contoso.\*</span></span>
  - <span data-ttu-id="266ee-332">\*.com</span><span class="sxs-lookup"><span data-stu-id="266ee-332">\*.com</span></span>
  - <span data-ttu-id="266ee-333">\*PDF</span><span class="sxs-lookup"><span data-stu-id="266ee-333">\*.pdf</span></span>

- <span data-ttu-id="266ee-334">**Подстановочный знак для текста или без пробелов:**</span><span class="sxs-lookup"><span data-stu-id="266ee-334">**Wildcard on text or without spacing characters**:</span></span>

  - <span data-ttu-id="266ee-335">\*contoso.com</span><span class="sxs-lookup"><span data-stu-id="266ee-335">\*contoso.com</span></span>
  - <span data-ttu-id="266ee-336">contoso.com\*</span><span class="sxs-lookup"><span data-stu-id="266ee-336">contoso.com\*</span></span>
  - <span data-ttu-id="266ee-337">\*1.2.3.4</span><span class="sxs-lookup"><span data-stu-id="266ee-337">\*1.2.3.4</span></span>
  - <span data-ttu-id="266ee-338">1.2.3.4\*</span><span class="sxs-lookup"><span data-stu-id="266ee-338">1.2.3.4\*</span></span>
  - <span data-ttu-id="266ee-339">contoso.com/a\*</span><span class="sxs-lookup"><span data-stu-id="266ee-339">contoso.com/a\*</span></span>
  - <span data-ttu-id="266ee-340">contoso.com/ab\*</span><span class="sxs-lookup"><span data-stu-id="266ee-340">contoso.com/ab\*</span></span>

- <span data-ttu-id="266ee-341">**IP-адреса с портами:**</span><span class="sxs-lookup"><span data-stu-id="266ee-341">**IP addresses with ports**:</span></span>

  - <span data-ttu-id="266ee-342">contoso.com:443</span><span class="sxs-lookup"><span data-stu-id="266ee-342">contoso.com:443</span></span>
  - <span data-ttu-id="266ee-343">abc.contoso.com:25</span><span class="sxs-lookup"><span data-stu-id="266ee-343">abc.contoso.com:25</span></span>

- <span data-ttu-id="266ee-344">**Недействующие подстановочные знаки:**</span><span class="sxs-lookup"><span data-stu-id="266ee-344">**Non-descriptive wildcards**:</span></span>

  - \*
  - <span data-ttu-id="266ee-345">\*.\*</span><span class="sxs-lookup"><span data-stu-id="266ee-345">\*.\*</span></span>

- <span data-ttu-id="266ee-346">**Средние подстановочные знаки:**</span><span class="sxs-lookup"><span data-stu-id="266ee-346">**Middle wildcards**:</span></span>

  - <span data-ttu-id="266ee-347">отклонник \* so.com</span><span class="sxs-lookup"><span data-stu-id="266ee-347">conto\*so.com</span></span>
  - <span data-ttu-id="266ee-348">conto~so.com</span><span class="sxs-lookup"><span data-stu-id="266ee-348">conto~so.com</span></span>

- <span data-ttu-id="266ee-349">**Двойной подстановочные**</span><span class="sxs-lookup"><span data-stu-id="266ee-349">**Double wildcards**</span></span>

  - <span data-ttu-id="266ee-350">contoso.com/\*\*</span><span class="sxs-lookup"><span data-stu-id="266ee-350">contoso.com/\*\*</span></span>
  - <span data-ttu-id="266ee-351">contoso.com/\*/\*</span><span class="sxs-lookup"><span data-stu-id="266ee-351">contoso.com/\*/\*</span></span>
