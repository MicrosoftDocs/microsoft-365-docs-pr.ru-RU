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
ms.openlocfilehash: 1aae54ffd6026a7fc131017a10f9676d96be9b69
ms.sourcegitcommit: d81c7cea85af6ad5fef81d3c930514a51464368c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/04/2020
ms.locfileid: "49572649"
---
# <a name="manage-urls-in-the-tenant-allowblock-list"></a><span data-ttu-id="880c2-103">Управление URL-адресами в списке разрешенных и заблокированных клиентов</span><span class="sxs-lookup"><span data-stu-id="880c2-103">Manage URLs in the Tenant Allow/Block List</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


> [!NOTE]
> <span data-ttu-id="880c2-104">Функции, описанные в этой статье, в предварительной версии, могут быть изменены и недоступны во всех организациях.</span><span class="sxs-lookup"><span data-stu-id="880c2-104">The features described in this topic are in Preview, are subject to change, and are not available in all organizations.</span></span>

<span data-ttu-id="880c2-105">В организациях Microsoft 365 с почтовыми ящиками в организациях Exchange Online или в автономной службе Exchange Online Protection (EOP) без почтовых ящиков Exchange Online вы можете не противовниманияию фильтра EOP вредоносности.</span><span class="sxs-lookup"><span data-stu-id="880c2-105">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, you might disagree with the EOP filtering verdict.</span></span> <span data-ttu-id="880c2-106">Например, хорошее сообщение может быть помечено как плохое (ложный положительный результат), или может быть разрешено неправильное сообщение (ложное отрицательное).</span><span class="sxs-lookup"><span data-stu-id="880c2-106">For example, a good message might be marked as bad (a false positive), or a bad message might be allowed through (a false negative).</span></span>

<span data-ttu-id="880c2-107">Список разрешенных и заблокированных клиентов в центре безопасности & соответствия требованиям позволяет вручную переопределить вердиктс фильтрации Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="880c2-107">The Tenant Allow/Block List in the Security & Compliance Center gives you a way to manually override the Microsoft 365 filtering verdicts.</span></span> <span data-ttu-id="880c2-108">Список разрешенных и заблокированных клиентов используется во время процесса обработки почты и при нажатии пользователем.</span><span class="sxs-lookup"><span data-stu-id="880c2-108">The Tenant Allow/Block List is used during mail flow and at the time of user clicks.</span></span> <span data-ttu-id="880c2-109">Вы можете указать URL-адреса, которые необходимо разрешить или заблокировать в списке разрешенных или запрещенных клиентов.</span><span class="sxs-lookup"><span data-stu-id="880c2-109">You can specify URLs to allow or block in the Tenant Allow/Block List.</span></span>

<span data-ttu-id="880c2-110">В этом разделе описывается, как настроить записи в списке разрешенных и запрещенных клиентов в центре безопасности & соответствия требованиям или в PowerShell (Exchange Online PowerShell для Microsoft 365 организации с почтовыми ящиками в Exchange Online; изолированный EOP PowerShell для организаций без почтовых ящиков Exchange Online).</span><span class="sxs-lookup"><span data-stu-id="880c2-110">This topic describes how to configure entries in the Tenant Allow/Block List in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="880c2-111">Что нужно знать перед началом работы</span><span class="sxs-lookup"><span data-stu-id="880c2-111">What do you need to know before you begin?</span></span>

- <span data-ttu-id="880c2-112">Откройте Центр безопасности и соответствия требованиям на сайте <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="880c2-112">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="880c2-113">Чтобы перейти непосредственно на страницу **списка разрешенных и заблокированных клиентов** , используйте <https://protection.office.com/tenantAllowBlockList> .</span><span class="sxs-lookup"><span data-stu-id="880c2-113">To go directly to the **Tenant Allow/Block List** page, use <https://protection.office.com/tenantAllowBlockList>.</span></span>

- <span data-ttu-id="880c2-114">Доступные значения URL-адреса описаны в [синтаксисе URL-адреса для списка разрешений/блокировок клиентов](#url-syntax-for-the-tenant-allowblock-list) далее в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="880c2-114">The available URL values are described in the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this topic.</span></span>

- <span data-ttu-id="880c2-115">В списке разрешенных и заблокированных клиентов можно указать не более 500 записей для URL-адресов.</span><span class="sxs-lookup"><span data-stu-id="880c2-115">The Tenant Allow/Block List allows a maximum of 500 entries for URLs.</span></span>

- <span data-ttu-id="880c2-116">Запись должна быть активна в течение 15 минут.</span><span class="sxs-lookup"><span data-stu-id="880c2-116">An entry should be active within 15 minutes.</span></span>

- <span data-ttu-id="880c2-117">Записи блокировки имеют приоритет над разрешающими записями.</span><span class="sxs-lookup"><span data-stu-id="880c2-117">Block entries take precedence over allow entries.</span></span>

- <span data-ttu-id="880c2-118">По умолчанию срок действия записей в списке разрешений/блокировок клиентов истекает через 30 дней.</span><span class="sxs-lookup"><span data-stu-id="880c2-118">By default, entries in the Tenant Allow/Block List will expire after 30 days.</span></span> <span data-ttu-id="880c2-119">Вы можете указать дату или запретить срок ее действия.</span><span class="sxs-lookup"><span data-stu-id="880c2-119">You can specify a date or set them to never expire.</span></span>

- <span data-ttu-id="880c2-120">Сведения о том, как подключиться к Exchange Online PowerShell, см. в статье [Подключение к Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="880c2-120">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="880c2-121">Чтобы подключиться к автономному EOP PowerShell, см. раздел [Подключение к PowerShell Exchange Online Protection](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="880c2-121">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="880c2-122">Прежде чем выполнять процедуры, описанные в этой статье, необходимо назначить разрешения в центре безопасности & соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="880c2-122">You need to be assigned permissions in the Security & Compliance Center before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="880c2-123">Чтобы добавить или удалить значения из списка разрешенных и заблокированных клиентов, необходимо быть участником группы ролей " **Управление организацией** " или " **администратор безопасности** ".</span><span class="sxs-lookup"><span data-stu-id="880c2-123">To add and remove values from the Tenant Allow/Block List, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="880c2-124">Для доступа только для чтения к списку разрешенных и запрещенных клиентов необходимо быть членом группы ролей " **глобальный читатель** " или " **читатель безопасности** ".</span><span class="sxs-lookup"><span data-stu-id="880c2-124">For read-only access to the Tenant Allow/Block List, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="880c2-125">Дополнительные сведения см. в статье [Разрешения в Центре безопасности и соответствия требованиям](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="880c2-125">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

  <span data-ttu-id="880c2-126">**Примечания**:</span><span class="sxs-lookup"><span data-stu-id="880c2-126">**Notes**:</span></span>

  - <span data-ttu-id="880c2-127">Добавление пользователей в соответствующую роль Azure Active Directory в центре администрирования Microsoft 365 предоставляет пользователям необходимые разрешения в центре безопасности & соответствия требованиям _и_ разрешениях для других функций в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="880c2-127">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="880c2-128">Дополнительные сведения см. в статье [О ролях администраторов](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span><span class="sxs-lookup"><span data-stu-id="880c2-128">For more information, see [About admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span></span>
  - <span data-ttu-id="880c2-129">Группа ролей **Управление организацией только для просмотра** в [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) также предоставляет доступ к компоненту только для чтения.</span><span class="sxs-lookup"><span data-stu-id="880c2-129">The **View-Only Organization Management** role group in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

## <a name="use-the-security--compliance-center-to-create-url-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="880c2-130">Использование центра безопасности & соответствия требованиям для создания записей URL-адресов в списке разрешенных и запрещенных клиентов</span><span class="sxs-lookup"><span data-stu-id="880c2-130">Use the Security & Compliance Center to create URL entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="880c2-131">Для получения подробных сведений о синтаксисе для записей URL-адресов просмотрите [синтаксис URL-адресов для списка разрешенных и заблокированных адресов](#url-syntax-for-the-tenant-allowblock-list) в разделе далее в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="880c2-131">For details about the syntax for URL entries, see the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this topic.</span></span>

1. <span data-ttu-id="880c2-132">В центре безопасности & соответствия требованиям перейдите в **Threat management** \> **Policy** \> **списки разрешенных и** запрещенных клиентов политики управления угрозами.</span><span class="sxs-lookup"><span data-stu-id="880c2-132">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="880c2-133">На странице **списка разрешенных и заблокированных клиентов** убедитесь, что выбрана вкладка **URL-адреса** , а затем нажмите кнопку **добавить** .</span><span class="sxs-lookup"><span data-stu-id="880c2-133">On the **Tenant Allow/Block List** page, verify that the **URLs** tab is selected, and then click **Add**</span></span>

3. <span data-ttu-id="880c2-134">В появившемся всплывающем окне **Добавление новых URL-адресов** настройте следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="880c2-134">In the **Add new URLs** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="880c2-135">**Добавьте URL-адреса с подстановочными знаками**: введите один URL-адрес в строке длиной не более 20.</span><span class="sxs-lookup"><span data-stu-id="880c2-135">**Add URLs with wildcards**: Enter one URL per line, up to a maximum of 20.</span></span>

   - <span data-ttu-id="880c2-136">**Блокировать/Разрешить**: укажите, хотите ли вы **Разрешить** или **запретить** указанные URL-адреса.</span><span class="sxs-lookup"><span data-stu-id="880c2-136">**Block/Allow**: Select whether you want to **Allow** or **Block** the specified URLs.</span></span>

   - <span data-ttu-id="880c2-137">**Никогда не истечет**: выполните одно из указанных ниже действий.</span><span class="sxs-lookup"><span data-stu-id="880c2-137">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="880c2-138">Убедитесь, что параметр отключен (выключен ![ ](../../media/scc-toggle-off.png) ), и в поле **истечение срока действия** указан срок действия для записей.</span><span class="sxs-lookup"><span data-stu-id="880c2-138">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entries.</span></span>

     <span data-ttu-id="880c2-139">или</span><span class="sxs-lookup"><span data-stu-id="880c2-139">or</span></span>

     - <span data-ttu-id="880c2-140">Переместите переключатель вправо, чтобы задать срок действия бессрочных записей:</span><span class="sxs-lookup"><span data-stu-id="880c2-140">Move the toggle to the right to configure the entries to never expire:</span></span> ![Включенный переключатель](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)<span data-ttu-id="880c2-142">.</span><span class="sxs-lookup"><span data-stu-id="880c2-142">.</span></span>

   - <span data-ttu-id="880c2-143">**Необязательное примечание**: введите описательный текст для записей.</span><span class="sxs-lookup"><span data-stu-id="880c2-143">**Optional note**: Enter descriptive text for the entries.</span></span>

4. <span data-ttu-id="880c2-144">По завершении нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="880c2-144">When you're finished, click **Add**.</span></span>

## <a name="use-the-security--compliance-center-to-view-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="880c2-145">Использование центра безопасности & соответствия требованиям для просмотра записей в списке разрешенных и запрещенных клиентов</span><span class="sxs-lookup"><span data-stu-id="880c2-145">Use the Security & Compliance Center to view entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="880c2-146">В центре безопасности & соответствия требованиям перейдите в **Threat management** \> **Policy** \> **списки разрешенных и** запрещенных клиентов политики управления угрозами.</span><span class="sxs-lookup"><span data-stu-id="880c2-146">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="880c2-147">Перейдите на вкладку **URL-адреса** .</span><span class="sxs-lookup"><span data-stu-id="880c2-147">Select the **URLs** tab.</span></span>

<span data-ttu-id="880c2-148">Щелкните следующие заголовки столбцов, чтобы отсортировать их по возрастанию или убыванию:</span><span class="sxs-lookup"><span data-stu-id="880c2-148">Click on the following column headings to sort in ascending or descending order:</span></span>

- <span data-ttu-id="880c2-149">**Значение**</span><span class="sxs-lookup"><span data-stu-id="880c2-149">**Value**</span></span>
- <span data-ttu-id="880c2-150">**Действие**: **блокировать** или **Разрешить**.</span><span class="sxs-lookup"><span data-stu-id="880c2-150">**Action**: **Block** or **Allow**.</span></span>
- <span data-ttu-id="880c2-151">**Дата последнего обновления**</span><span class="sxs-lookup"><span data-stu-id="880c2-151">**Last updated date**</span></span>
- <span data-ttu-id="880c2-152">**Дата истечения срока действия**</span><span class="sxs-lookup"><span data-stu-id="880c2-152">**Expiration date**</span></span>
- <span data-ttu-id="880c2-153">**Примечание**</span><span class="sxs-lookup"><span data-stu-id="880c2-153">**Note**</span></span>

<span data-ttu-id="880c2-154">Щелкните **Group (Группа** ), чтобы сгруппировать записи по **действию** (**блокировать** или **Разрешить**) или **нет**.</span><span class="sxs-lookup"><span data-stu-id="880c2-154">Click **Group** to group the entries by **Action** (**Block** or **Allow**) or **None**.</span></span>

<span data-ttu-id="880c2-155">Нажмите кнопку **Поиск**, введите значение полностью или частично, а затем нажмите клавишу ВВОД, чтобы найти конкретное значение.</span><span class="sxs-lookup"><span data-stu-id="880c2-155">Click **Search**, enter all or part of a value, and then press ENTER to find a specific value.</span></span> <span data-ttu-id="880c2-156">По завершении нажмите кнопку **очистить** поиск ![ Очистить поиск значок ](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif) .</span><span class="sxs-lookup"><span data-stu-id="880c2-156">When you're finished, click **Clear search** ![Clear search icon](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif).</span></span>

<span data-ttu-id="880c2-157">Нажмите кнопку **Фильтр**.</span><span class="sxs-lookup"><span data-stu-id="880c2-157">Click **Filter**.</span></span> <span data-ttu-id="880c2-158">В появившемся всплывающем окне **фильтра** настройте любой из следующих параметров:</span><span class="sxs-lookup"><span data-stu-id="880c2-158">In the **Filter** flyout that appears, configure any of the following settings:</span></span>

- <span data-ttu-id="880c2-159">**Действие**: выберите **Разрешить**, **блокировать** или и то, и другое.</span><span class="sxs-lookup"><span data-stu-id="880c2-159">**Action**: Select **Allow**, **Block** or both.</span></span>

- <span data-ttu-id="880c2-160">**Никогда не истечет**: выберите Выключить (выключить ![ ](../../media/scc-toggle-off.png) ) или включить (включить ![ ](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png) ).</span><span class="sxs-lookup"><span data-stu-id="880c2-160">**Never expire**: Select off (![Toggle off](../../media/scc-toggle-off.png)) or on (![Toggle on](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)).</span></span>

- <span data-ttu-id="880c2-161">**Последнее обновление**: выберите дату начала (**from**), конечную дату (конечную) или и **то, и** другое.</span><span class="sxs-lookup"><span data-stu-id="880c2-161">**Last updated**: Select a start date (**From**), an end date (**To**) or both.</span></span>

- <span data-ttu-id="880c2-162">**Дата окончания срока действия**: выберите дату начала (**от**), конечную дату (**до**) или и то, и другое.</span><span class="sxs-lookup"><span data-stu-id="880c2-162">**Expiration date**: Select a start date (**From**), an end date (**To**) or both.</span></span>

<span data-ttu-id="880c2-163">Когда все будет готово, нажмите кнопку **Применить**.</span><span class="sxs-lookup"><span data-stu-id="880c2-163">When you're finished, click **Apply**.</span></span>

<span data-ttu-id="880c2-164">Чтобы очистить существующие фильтры, нажмите кнопку **Фильтр**, а затем в появившемся всплывающем окне **фильтра** щелкните **Очистить фильтры**.</span><span class="sxs-lookup"><span data-stu-id="880c2-164">To clear existing filters, click **Filter**, and in the **Filter** flyout that appears, click **Clear filters**.</span></span>

## <a name="use-the-security--compliance-center-to-modify-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="880c2-165">Использование центра безопасности & соответствия требованиям для изменения записей в списке разрешенных и запрещенных клиентов</span><span class="sxs-lookup"><span data-stu-id="880c2-165">Use the Security & Compliance Center to modify entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="880c2-166">Невозможно изменить значение URL-адреса.</span><span class="sxs-lookup"><span data-stu-id="880c2-166">You can't modify the URL value itself.</span></span> <span data-ttu-id="880c2-167">Вместо этого необходимо удалить запись и создать ее повторно.</span><span class="sxs-lookup"><span data-stu-id="880c2-167">Instead, you need to delete the entry and recreate it.</span></span>

1. <span data-ttu-id="880c2-168">В центре безопасности & соответствия требованиям перейдите в **Threat management** \> **Policy** \> **списки разрешенных и** запрещенных клиентов политики управления угрозами.</span><span class="sxs-lookup"><span data-stu-id="880c2-168">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="880c2-169">Перейдите на вкладку **URL-адреса** .</span><span class="sxs-lookup"><span data-stu-id="880c2-169">Select the **URLs** tab.</span></span>

3. <span data-ttu-id="880c2-170">Выберите запись, которую необходимо изменить, а затем щелкните **изменить** ![ значок редактирования ](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) .</span><span class="sxs-lookup"><span data-stu-id="880c2-170">Select the entry that you want to modify, and then click **Edit** ![Edit icon](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png).</span></span>

4. <span data-ttu-id="880c2-171">В появившемся всплывающем меню настройте следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="880c2-171">In the flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="880c2-172">**Блокировать/Разрешить**: выберите **Разрешить** или **заблокировать**.</span><span class="sxs-lookup"><span data-stu-id="880c2-172">**Block/Allow**: Select **Allow** or **Block**.</span></span>

   - <span data-ttu-id="880c2-173">**Никогда не истечет**: выполните одно из указанных ниже действий.</span><span class="sxs-lookup"><span data-stu-id="880c2-173">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="880c2-174">Убедитесь, что параметр отключен (выключен ![ ](../../media/scc-toggle-off.png) ), и укажите срок действия для записи, используя поле **срок действия** .</span><span class="sxs-lookup"><span data-stu-id="880c2-174">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entry.</span></span>

     <span data-ttu-id="880c2-175">или</span><span class="sxs-lookup"><span data-stu-id="880c2-175">or</span></span>

     - <span data-ttu-id="880c2-176">Переместите переключатель вправо, чтобы задать срок действия бессрочной записи:</span><span class="sxs-lookup"><span data-stu-id="880c2-176">Move the toggle to the right to configure the entry to never expire:</span></span> ![Включенный переключатель](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)<span data-ttu-id="880c2-178">.</span><span class="sxs-lookup"><span data-stu-id="880c2-178">.</span></span>

   - <span data-ttu-id="880c2-179">**Необязательное примечание**: введите описательный текст для записи.</span><span class="sxs-lookup"><span data-stu-id="880c2-179">**Optional note**: Enter descriptive text for the entry.</span></span>

5. <span data-ttu-id="880c2-180">Выполнив необходимые действия, нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="880c2-180">When you're finished, click **Save**.</span></span>

## <a name="use-the-security--compliance-center-to-remove-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="880c2-181">Использование центра безопасности & соответствия требованиям для удаления записей из списка разрешенных и запрещенных клиентов</span><span class="sxs-lookup"><span data-stu-id="880c2-181">Use the Security & Compliance Center to remove entries from the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="880c2-182">В центре безопасности & соответствия требованиям перейдите в **Threat management** \> **Policy** \> **списки разрешенных и** запрещенных клиентов политики управления угрозами.</span><span class="sxs-lookup"><span data-stu-id="880c2-182">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="880c2-183">Перейдите на вкладку **URL-адреса** .</span><span class="sxs-lookup"><span data-stu-id="880c2-183">Select the **URLs** tab.</span></span>

3. <span data-ttu-id="880c2-184">Выберите запись, которую нужно удалить, и нажмите кнопку **Удалить** ![ значок удаления ](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png) .</span><span class="sxs-lookup"><span data-stu-id="880c2-184">Select the entry that you want to remove, and then click **Delete** ![Delete icon](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png).</span></span>

4. <span data-ttu-id="880c2-185">В появившемся диалоговом окне предупреждения нажмите кнопку **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="880c2-185">In the warning dialog that appears, click **Delete**.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-the-tenant-allowblock-list"></a><span data-ttu-id="880c2-186">Настройка списка разрешений/блокировок клиентов с помощью Exchange Online PowerShell или изолированной EOP PowerShell</span><span class="sxs-lookup"><span data-stu-id="880c2-186">Use Exchange Online PowerShell or standalone EOP PowerShell to configure the Tenant Allow/Block List</span></span>

### <a name="use-powershell-to-add-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="880c2-187">Добавление записей в список разрешенных и запрещенных клиентов с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="880c2-187">Use PowerShell to add entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="880c2-188">Чтобы добавить записи в список разрешенных и запрещенных клиентов, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="880c2-188">To add entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
New-TenantAllowBlockListItems -ListType Url -Action <Allow | Block> -Entries <String[]> [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

<span data-ttu-id="880c2-189">В этом примере добавляется запись блока URL-адреса для contoso.com и всех поддоменов (например, contoso.com, www.contoso.com и xyz.abc.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="880c2-189">This example adds a URL block entry for contoso.com and all subdomains (for example, contoso.com, www.contoso.com, and xyz.abc.contoso.com).</span></span> <span data-ttu-id="880c2-190">Так как мы не использовали параметры ExpirationDate или параметру expiration, срок действия записи истечет через 30 дней.</span><span class="sxs-lookup"><span data-stu-id="880c2-190">Because we didn't use the ExpirationDate or NoExpiration parameters, the entry expires after 30 days.</span></span>

```powershell
New-TenantAllowBlockListItem -ListType Url -Action Block -Entries ~contoso.com
```

<span data-ttu-id="880c2-191">Подробные сведения о синтаксисе и параметрах можно найти в статье [New – тенанталловблокклиститемс](https://docs.microsoft.com/powershell/module/exchange/new-tenantallowblocklistitems).</span><span class="sxs-lookup"><span data-stu-id="880c2-191">For detailed syntax and parameter information, see [New-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/new-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-view-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="880c2-192">Просмотр записей в списке разрешенных и запрещенных клиентов с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="880c2-192">Use PowerShell to view entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="880c2-193">Чтобы просмотреть записи в списке разрешенных и запрещенных клиентов, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="880c2-193">To view entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType Url [-Entry <URLValue>] [-Action <Allow | Block>] [-ExpirationDate <DateTime>] [-NoExpiration]
```

<span data-ttu-id="880c2-194">В этом примере возвращаются все заблокированные URL-адреса.</span><span class="sxs-lookup"><span data-stu-id="880c2-194">This example returns all blocked URLs.</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType Url -Action Block
```

<span data-ttu-id="880c2-195">Подробные сведения о синтаксисе и параметрах можно найти в статье [Get – тенанталловблокклиститемс](https://docs.microsoft.com/powershell/module/exchange/get-tenantallowblocklistitems).</span><span class="sxs-lookup"><span data-stu-id="880c2-195">For detailed syntax and parameter information, see [Get-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/get-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-modify-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="880c2-196">Изменение записей в списке разрешенных и запрещенных клиентов с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="880c2-196">Use PowerShell to modify entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="880c2-197">Невозможно изменить значение URL-адреса.</span><span class="sxs-lookup"><span data-stu-id="880c2-197">You can't modify the URL value itself.</span></span> <span data-ttu-id="880c2-198">Вместо этого необходимо удалить запись и создать ее повторно.</span><span class="sxs-lookup"><span data-stu-id="880c2-198">Instead, you need to delete the entry and recreate it.</span></span>

<span data-ttu-id="880c2-199">Чтобы изменить записи в списке разрешенных и запрещенных клиентов, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="880c2-199">To modify entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType Url -Ids <"Id1","Id2",..."IdN"> [-Action <Allow | Block>] [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

<span data-ttu-id="880c2-200">В этом примере изменяется дата окончания срока действия указанной записи.</span><span class="sxs-lookup"><span data-stu-id="880c2-200">This example changes the expiration date of the specified entry.</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -ExpirationDate (Get-Date "5/30/2020 9:30 AM").ToUniversalTime()
```

<span data-ttu-id="880c2-201">Подробные сведения о синтаксисе и параметрах можно найти в статье [Set – тенанталловблокклиститемс](https://docs.microsoft.com/powershell/module/exchange/set-tenantallowblocklistitems).</span><span class="sxs-lookup"><span data-stu-id="880c2-201">For detailed syntax and parameter information, see [Set-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/set-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-remove-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="880c2-202">Удаление записей из списка разрешенных и запрещенных клиентов с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="880c2-202">Use PowerShell to remove entries from the Tenant Allow/Block List</span></span>

<span data-ttu-id="880c2-203">Чтобы удалить записи из списка разрешенных и запрещенных клиентов, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="880c2-203">To remove entries from the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType Url -Ids <"Id1","Id2",..."IdN">
```

<span data-ttu-id="880c2-204">В этом примере из списка разрешенных и запрещенных клиентов удаляется указанная запись URL-адреса.</span><span class="sxs-lookup"><span data-stu-id="880c2-204">This example removes the specified URL entry from the Tenant Allow/Block List.</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSPAAAA0"
```

<span data-ttu-id="880c2-205">Подробные сведения о синтаксисе и параметрах можно найти в статье [Remove – тенанталловблокклиститемс](https://docs.microsoft.com/powershell/module/exchange/remove-tenantallowblocklistitems).</span><span class="sxs-lookup"><span data-stu-id="880c2-205">For detailed syntax and parameter information, see [Remove-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/remove-tenantallowblocklistitems).</span></span>

## <a name="url-syntax-for-the-tenant-allowblock-list"></a><span data-ttu-id="880c2-206">Синтаксис URL-адреса для списка разрешений/блокировок клиентов</span><span class="sxs-lookup"><span data-stu-id="880c2-206">URL syntax for the Tenant Allow/Block List</span></span>

- <span data-ttu-id="880c2-207">IP4v и IPv6-адреса разрешены, но порты TCP/UDP — нет.</span><span class="sxs-lookup"><span data-stu-id="880c2-207">IP4v and IPv6 addresses are allowed, but TCP/UDP ports are not.</span></span>

- <span data-ttu-id="880c2-208">Расширения имен файлов не допускаются (например, test.pdf).</span><span class="sxs-lookup"><span data-stu-id="880c2-208">Filename extensions are not allowed (for example, test.pdf).</span></span>

- <span data-ttu-id="880c2-209">Юникод не поддерживается, но Punycode — Punycode.</span><span class="sxs-lookup"><span data-stu-id="880c2-209">Unicode is not supported, but Punycode is.</span></span>

- <span data-ttu-id="880c2-210">Имена узлов разрешены, если выполняются все приведенные ниже условия.</span><span class="sxs-lookup"><span data-stu-id="880c2-210">Hostnames are allowed if all of the following statements are true:</span></span>

  - <span data-ttu-id="880c2-211">Имя узла содержит точку.</span><span class="sxs-lookup"><span data-stu-id="880c2-211">The hostname contains a period.</span></span>
  - <span data-ttu-id="880c2-212">Слева от точки есть по крайней мере один символ.</span><span class="sxs-lookup"><span data-stu-id="880c2-212">There is at least one character to the left of the period.</span></span>
  - <span data-ttu-id="880c2-213">Справа от точки есть по крайней мере два символа.</span><span class="sxs-lookup"><span data-stu-id="880c2-213">There are at least two characters to the right of the period.</span></span>

  <span data-ttu-id="880c2-214">Например, `t.co` разрешено; `.com` или `contoso.` не разрешено.</span><span class="sxs-lookup"><span data-stu-id="880c2-214">For example, `t.co` is allowed; `.com` or `contoso.` are not allowed.</span></span>

- <span data-ttu-id="880c2-215">Вложенные пути не являются подразумеваемыми.</span><span class="sxs-lookup"><span data-stu-id="880c2-215">Subpaths are not implied.</span></span>

  <span data-ttu-id="880c2-216">Например, не `contoso.com` включается `contoso.com/a` .</span><span class="sxs-lookup"><span data-stu-id="880c2-216">For example, `contoso.com` does not include `contoso.com/a`.</span></span>

- <span data-ttu-id="880c2-217">Подстановочные знаки (\*) разрешены в следующих сценариях:</span><span class="sxs-lookup"><span data-stu-id="880c2-217">Wildcards (\*) are allowed in the following scenarios:</span></span>

  - <span data-ttu-id="880c2-218">За левым подстановочным знаком должен следовать точка для указания поддомена.</span><span class="sxs-lookup"><span data-stu-id="880c2-218">A left wildcard must be followed by a period to specify a subdomain.</span></span>

    <span data-ttu-id="880c2-219">Например, `*.contoso.com` разрешено; запрещено `*contoso.com` .</span><span class="sxs-lookup"><span data-stu-id="880c2-219">For example, `*.contoso.com` is allowed; `*contoso.com` is not allowed.</span></span>

  - <span data-ttu-id="880c2-220">Для указания пути должен следовать символу подстановки (/).</span><span class="sxs-lookup"><span data-stu-id="880c2-220">A right wildcard must follow a forward slash (/) to specify a path.</span></span>

    <span data-ttu-id="880c2-221">Например, `contoso.com/*` разрешено; `contoso.com*` или `contoso.com/ab*` не разрешено.</span><span class="sxs-lookup"><span data-stu-id="880c2-221">For example, `contoso.com/*` is allowed; `contoso.com*` or `contoso.com/ab*` are not allowed.</span></span>

  - <span data-ttu-id="880c2-222">Все подпути не подразумеваются с помощью подстановочного знака справа.</span><span class="sxs-lookup"><span data-stu-id="880c2-222">All subpaths are not implied by a right wildcard.</span></span>

    <span data-ttu-id="880c2-223">Например, не `contoso.com/*` включается `contoso.com/a` .</span><span class="sxs-lookup"><span data-stu-id="880c2-223">For example, `contoso.com/*` does not include `contoso.com/a`.</span></span>

  - <span data-ttu-id="880c2-224">`*.com*` недействителен (не является разрешимым доменом, а правильный подстановочный знак не следует за косой чертой).</span><span class="sxs-lookup"><span data-stu-id="880c2-224">`*.com*` is invalid (not a resolvable domain and the right wildcard does not follow a forward slash).</span></span>

  - <span data-ttu-id="880c2-225">Подстановочные знаки не разрешены в IP-адресах.</span><span class="sxs-lookup"><span data-stu-id="880c2-225">Wildcards are not allowed in IP addresses.</span></span>

- <span data-ttu-id="880c2-226">Символ тильды (~) доступен в следующих сценариях:</span><span class="sxs-lookup"><span data-stu-id="880c2-226">The tilde (~) character is available in the following scenarios:</span></span>

  - <span data-ttu-id="880c2-227">Левая тильда подразумевает домен и все поддомены.</span><span class="sxs-lookup"><span data-stu-id="880c2-227">A left tilde implies a domain and all subdomains.</span></span>

    <span data-ttu-id="880c2-228">Например `~contoso.com` , включает `contoso.com` и `*.contoso.com` .</span><span class="sxs-lookup"><span data-stu-id="880c2-228">For example `~contoso.com` includes `contoso.com` and `*.contoso.com`.</span></span>

- <span data-ttu-id="880c2-229">URL-адреса, содержащие протоколы (например,, `http://` `https://` или `ftp://` ), завершатся неуспешно, так как записи URL-адресов применяются ко всем протоколам.</span><span class="sxs-lookup"><span data-stu-id="880c2-229">URL entries that contain protocols (for example, `http://`, `https://`, or `ftp://`) will fail, because URL entries apply to all protocols.</span></span>

- <span data-ttu-id="880c2-230">Имя пользователя или пароль не поддерживаются или не являются обязательными.</span><span class="sxs-lookup"><span data-stu-id="880c2-230">A username or password aren't supported or required.</span></span>

- <span data-ttu-id="880c2-231">Кавычки (' или ") являются недопустимыми символами.</span><span class="sxs-lookup"><span data-stu-id="880c2-231">Quotes (' or ") are invalid characters.</span></span>

- <span data-ttu-id="880c2-232">URL-адрес должен включать все перенаправления, где это возможно.</span><span class="sxs-lookup"><span data-stu-id="880c2-232">A URL should include all redirects where possible.</span></span>

### <a name="url-entry-scenarios"></a><span data-ttu-id="880c2-233">Сценарии ввода URL-адресов</span><span class="sxs-lookup"><span data-stu-id="880c2-233">URL entry scenarios</span></span>

<span data-ttu-id="880c2-234">Допустимые записи URL-адреса и их результаты описаны в следующих разделах.</span><span class="sxs-lookup"><span data-stu-id="880c2-234">Valid URL entries and their results are described in the following sections.</span></span>

#### <a name="scenario-no-wildcards"></a><span data-ttu-id="880c2-235">Сценарий: без подстановочных знаков</span><span class="sxs-lookup"><span data-stu-id="880c2-235">Scenario: No wildcards</span></span>

<span data-ttu-id="880c2-236">**Запись**: `contoso.com`</span><span class="sxs-lookup"><span data-stu-id="880c2-236">**Entry**: `contoso.com`</span></span>

- <span data-ttu-id="880c2-237">**Разрешить согласование**: contoso.com</span><span class="sxs-lookup"><span data-stu-id="880c2-237">**Allow match**: contoso.com</span></span>

- <span data-ttu-id="880c2-238">**Разрешить не сопоставляемые**:</span><span class="sxs-lookup"><span data-stu-id="880c2-238">**Allow not matched**:</span></span>

  - <span data-ttu-id="880c2-239">abc-contoso.com</span><span class="sxs-lookup"><span data-stu-id="880c2-239">abc-contoso.com</span></span>
  - <span data-ttu-id="880c2-240">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="880c2-240">contoso.com/a</span></span>
  - <span data-ttu-id="880c2-241">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="880c2-241">payroll.contoso.com</span></span>
  - <span data-ttu-id="880c2-242">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="880c2-242">test.com/contoso.com</span></span>
  - <span data-ttu-id="880c2-243">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="880c2-243">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="880c2-244">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="880c2-244">www.contoso.com</span></span>
  - <span data-ttu-id="880c2-245">www. contoso. com/q = a@contoso. com</span><span class="sxs-lookup"><span data-stu-id="880c2-245">www.contoso.com/q=a@contoso.com</span></span>
  
- <span data-ttu-id="880c2-246">**Согласование блока**:</span><span class="sxs-lookup"><span data-stu-id="880c2-246">**Block match**:</span></span>

  - <span data-ttu-id="880c2-247">contoso.com</span><span class="sxs-lookup"><span data-stu-id="880c2-247">contoso.com</span></span>
  - <span data-ttu-id="880c2-248">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="880c2-248">contoso.com/a</span></span>
  - <span data-ttu-id="880c2-249">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="880c2-249">payroll.contoso.com</span></span>
  - <span data-ttu-id="880c2-250">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="880c2-250">test.com/contoso.com</span></span>
  - <span data-ttu-id="880c2-251">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="880c2-251">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="880c2-252">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="880c2-252">www.contoso.com</span></span>
  - <span data-ttu-id="880c2-253">www. contoso. com/q = a@contoso. com</span><span class="sxs-lookup"><span data-stu-id="880c2-253">www.contoso.com/q=a@contoso.com</span></span>

- <span data-ttu-id="880c2-254">**Блок не сопоставлен**: ABC-contoso.com</span><span class="sxs-lookup"><span data-stu-id="880c2-254">**Block not matched**: abc-contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain"></a><span data-ttu-id="880c2-255">Сценарий: левый подстановочный знак (поддомен)</span><span class="sxs-lookup"><span data-stu-id="880c2-255">Scenario: Left wildcard (subdomain)</span></span>

<span data-ttu-id="880c2-256">**Запись**: `*.contoso.com`</span><span class="sxs-lookup"><span data-stu-id="880c2-256">**Entry**: `*.contoso.com`</span></span>

- <span data-ttu-id="880c2-257">**Разрешить согласование** и **согласование блокировок**:</span><span class="sxs-lookup"><span data-stu-id="880c2-257">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="880c2-258">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="880c2-258">www.contoso.com</span></span>
  - <span data-ttu-id="880c2-259">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="880c2-259">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="880c2-260">**Разрешить не сопоставляемые** и несопоставленные **блоки**:</span><span class="sxs-lookup"><span data-stu-id="880c2-260">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="880c2-261">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="880c2-261">123contoso.com</span></span>
  - <span data-ttu-id="880c2-262">contoso.com</span><span class="sxs-lookup"><span data-stu-id="880c2-262">contoso.com</span></span>
  - <span data-ttu-id="880c2-263">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="880c2-263">test.com/contoso.com</span></span>
  - <span data-ttu-id="880c2-264">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="880c2-264">www.contoso.com/abc</span></span>
  
#### <a name="scenario-right-wildcard-at-top-of-path"></a><span data-ttu-id="880c2-265">Сценарий: подстановочный знак "справа" в верхней части пути</span><span class="sxs-lookup"><span data-stu-id="880c2-265">Scenario: Right wildcard at top of path</span></span>

<span data-ttu-id="880c2-266">**Запись**: `contoso.com/a/*`</span><span class="sxs-lookup"><span data-stu-id="880c2-266">**Entry**: `contoso.com/a/*`</span></span>

- <span data-ttu-id="880c2-267">**Разрешить согласование** и **согласование блокировок**:</span><span class="sxs-lookup"><span data-stu-id="880c2-267">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="880c2-268">contoso.com/a/b</span><span class="sxs-lookup"><span data-stu-id="880c2-268">contoso.com/a/b</span></span>
  - <span data-ttu-id="880c2-269">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="880c2-269">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="880c2-270">Contoso. com/a/? q = joe@t. com</span><span class="sxs-lookup"><span data-stu-id="880c2-270">contoso.com/a/?q=joe@t.com</span></span>

- <span data-ttu-id="880c2-271">**Разрешить не сопоставляемые** и несопоставленные **блоки**:</span><span class="sxs-lookup"><span data-stu-id="880c2-271">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="880c2-272">contoso.com</span><span class="sxs-lookup"><span data-stu-id="880c2-272">contoso.com</span></span>
  - <span data-ttu-id="880c2-273">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="880c2-273">contoso.com/a</span></span>
  - <span data-ttu-id="880c2-274">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="880c2-274">www.contoso.com</span></span>
  - <span data-ttu-id="880c2-275">www. contoso. com/q = a@contoso. com</span><span class="sxs-lookup"><span data-stu-id="880c2-275">www.contoso.com/q=a@contoso.com</span></span>
  
#### <a name="scenario-left-tilde"></a><span data-ttu-id="880c2-276">Сценарий: левая тильда</span><span class="sxs-lookup"><span data-stu-id="880c2-276">Scenario: Left tilde</span></span>

<span data-ttu-id="880c2-277">**Запись**: `~contoso.com`</span><span class="sxs-lookup"><span data-stu-id="880c2-277">**Entry**: `~contoso.com`</span></span>

- <span data-ttu-id="880c2-278">**Разрешить согласование** и **согласование блокировок**:</span><span class="sxs-lookup"><span data-stu-id="880c2-278">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="880c2-279">contoso.com</span><span class="sxs-lookup"><span data-stu-id="880c2-279">contoso.com</span></span>
  - <span data-ttu-id="880c2-280">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="880c2-280">www.contoso.com</span></span>
  - <span data-ttu-id="880c2-281">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="880c2-281">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="880c2-282">**Разрешить не сопоставляемые** и несопоставленные **блоки**:</span><span class="sxs-lookup"><span data-stu-id="880c2-282">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="880c2-283">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="880c2-283">123contoso.com</span></span>
  - <span data-ttu-id="880c2-284">contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="880c2-284">contoso.com/abc</span></span>
  - <span data-ttu-id="880c2-285">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="880c2-285">www.contoso.com/abc</span></span>

#### <a name="scenario-right-wildcard-suffix"></a><span data-ttu-id="880c2-286">Сценарий: правый подстановочный суффикс</span><span class="sxs-lookup"><span data-stu-id="880c2-286">Scenario: Right wildcard suffix</span></span>

<span data-ttu-id="880c2-287">**Запись**: `contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="880c2-287">**Entry**: `contoso.com/*`</span></span>

- <span data-ttu-id="880c2-288">**Разрешить согласование** и **согласование блокировок**:</span><span class="sxs-lookup"><span data-stu-id="880c2-288">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="880c2-289">Contoso. com/? q = whatever@fabrikam. com</span><span class="sxs-lookup"><span data-stu-id="880c2-289">contoso.com/?q=whatever@fabrikam.com</span></span>
  - <span data-ttu-id="880c2-290">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="880c2-290">contoso.com/a</span></span>
  - <span data-ttu-id="880c2-291">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="880c2-291">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="880c2-292">contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="880c2-292">contoso.com/ab</span></span>
  - <span data-ttu-id="880c2-293">contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="880c2-293">contoso.com/b</span></span>
  - <span data-ttu-id="880c2-294">contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="880c2-294">contoso.com/b/a/c</span></span>
  - <span data-ttu-id="880c2-295">contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="880c2-295">contoso.com/ba</span></span>

- <span data-ttu-id="880c2-296">**Разрешить не сопоставляемые** и непарные **блоки**: contoso.com</span><span class="sxs-lookup"><span data-stu-id="880c2-296">**Allow not matched** and **Block not matched**: contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain-and-right-wildcard-suffix"></a><span data-ttu-id="880c2-297">Сценарий: левый и правый суффиксы для поддоменов подстановочных знаков</span><span class="sxs-lookup"><span data-stu-id="880c2-297">Scenario: Left wildcard subdomain and right wildcard suffix</span></span>

<span data-ttu-id="880c2-298">**Запись**: `*.contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="880c2-298">**Entry**: `*.contoso.com/*`</span></span>

- <span data-ttu-id="880c2-299">**Разрешить согласование** и **согласование блокировок**:</span><span class="sxs-lookup"><span data-stu-id="880c2-299">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="880c2-300">abc.contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="880c2-300">abc.contoso.com/ab</span></span>
  - <span data-ttu-id="880c2-301">abc.xyz.contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="880c2-301">abc.xyz.contoso.com/a/b/c</span></span>
  - <span data-ttu-id="880c2-302">www.contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="880c2-302">www.contoso.com/a</span></span>
  - <span data-ttu-id="880c2-303">www.contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="880c2-303">www.contoso.com/b/a/c</span></span>
  - <span data-ttu-id="880c2-304">xyz.contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="880c2-304">xyz.contoso.com/ba</span></span>

- <span data-ttu-id="880c2-305">**Разрешить не сопоставляемые** и непарные **блоки**: contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="880c2-305">**Allow not matched** and **Block not matched**: contoso.com/b</span></span>

#### <a name="scenario-left-and-right-tilde"></a><span data-ttu-id="880c2-306">Сценарий: левая и правая тильда</span><span class="sxs-lookup"><span data-stu-id="880c2-306">Scenario: Left and right tilde</span></span>

<span data-ttu-id="880c2-307">**Запись**: `~contoso.com~`</span><span class="sxs-lookup"><span data-stu-id="880c2-307">**Entry**: `~contoso.com~`</span></span>

- <span data-ttu-id="880c2-308">**Разрешить согласование** и **согласование блокировок**:</span><span class="sxs-lookup"><span data-stu-id="880c2-308">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="880c2-309">contoso.com</span><span class="sxs-lookup"><span data-stu-id="880c2-309">contoso.com</span></span>
  - <span data-ttu-id="880c2-310">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="880c2-310">contoso.com/a</span></span>
  - <span data-ttu-id="880c2-311">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="880c2-311">www.contoso.com</span></span>
  - <span data-ttu-id="880c2-312">www.contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="880c2-312">www.contoso.com/b</span></span>
  - <span data-ttu-id="880c2-313">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="880c2-313">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="880c2-314">**Разрешить не сопоставляемые** и несопоставленные **блоки**:</span><span class="sxs-lookup"><span data-stu-id="880c2-314">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="880c2-315">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="880c2-315">123contoso.com</span></span>
  - <span data-ttu-id="880c2-316">contoso.org</span><span class="sxs-lookup"><span data-stu-id="880c2-316">contoso.org</span></span>

#### <a name="scenario-ip-address"></a><span data-ttu-id="880c2-317">Сценарий: IP-адрес</span><span class="sxs-lookup"><span data-stu-id="880c2-317">Scenario: IP address</span></span>

<span data-ttu-id="880c2-318">**Запись**: `1.2.3.4`</span><span class="sxs-lookup"><span data-stu-id="880c2-318">**Entry**: `1.2.3.4`</span></span>

- <span data-ttu-id="880c2-319">**Разрешить ПОИСКПОЗ** и **блокировать ПОИСКПОЗ**: 1.2.3.4</span><span class="sxs-lookup"><span data-stu-id="880c2-319">**Allow match** and **Block match**: 1.2.3.4</span></span>

- <span data-ttu-id="880c2-320">**Разрешить не сопоставляемые** и несопоставленные **блоки**:</span><span class="sxs-lookup"><span data-stu-id="880c2-320">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="880c2-321">1.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="880c2-321">1.2.3.4/a</span></span>
  - <span data-ttu-id="880c2-322">11.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="880c2-322">11.2.3.4/a</span></span>

#### <a name="ip-address-with-right-wildcard"></a><span data-ttu-id="880c2-323">IP-адрес с подстановкой по правому краю</span><span class="sxs-lookup"><span data-stu-id="880c2-323">IP address with right wildcard</span></span>

<span data-ttu-id="880c2-324">**Запись**: `1.2.3.4/*`</span><span class="sxs-lookup"><span data-stu-id="880c2-324">**Entry**: `1.2.3.4/*`</span></span>

- <span data-ttu-id="880c2-325">**Разрешить согласование** и **согласование блокировок**:</span><span class="sxs-lookup"><span data-stu-id="880c2-325">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="880c2-326">1.2.3.4/b</span><span class="sxs-lookup"><span data-stu-id="880c2-326">1.2.3.4/b</span></span>
  - <span data-ttu-id="880c2-327">1.2.3.4/баааа</span><span class="sxs-lookup"><span data-stu-id="880c2-327">1.2.3.4/baaaa</span></span>

### <a name="examples-of-invalid-entries"></a><span data-ttu-id="880c2-328">Примеры недопустимых записей</span><span class="sxs-lookup"><span data-stu-id="880c2-328">Examples of invalid entries</span></span>

<span data-ttu-id="880c2-329">Следующие записи недопустимы:</span><span class="sxs-lookup"><span data-stu-id="880c2-329">The following entries are invalid:</span></span>

- <span data-ttu-id="880c2-330">**Отсутствующие или недопустимые значения домена**:</span><span class="sxs-lookup"><span data-stu-id="880c2-330">**Missing or invalid domain values**:</span></span>

  - <span data-ttu-id="880c2-331">компанией</span><span class="sxs-lookup"><span data-stu-id="880c2-331">contoso</span></span>
  - <span data-ttu-id="880c2-332">\*компанией.\*</span><span class="sxs-lookup"><span data-stu-id="880c2-332">\*.contoso.\*</span></span>
  - <span data-ttu-id="880c2-333">\*. com</span><span class="sxs-lookup"><span data-stu-id="880c2-333">\*.com</span></span>
  - <span data-ttu-id="880c2-334">\*. PDF</span><span class="sxs-lookup"><span data-stu-id="880c2-334">\*.pdf</span></span>

- <span data-ttu-id="880c2-335">**Подстановочный знак для текста или без пробелов**:</span><span class="sxs-lookup"><span data-stu-id="880c2-335">**Wildcard on text or without spacing characters**:</span></span>

  - <span data-ttu-id="880c2-336">\*contoso.com</span><span class="sxs-lookup"><span data-stu-id="880c2-336">\*contoso.com</span></span>
  - <span data-ttu-id="880c2-337">contoso.com\*</span><span class="sxs-lookup"><span data-stu-id="880c2-337">contoso.com\*</span></span>
  - <span data-ttu-id="880c2-338">\*1.2.3.4</span><span class="sxs-lookup"><span data-stu-id="880c2-338">\*1.2.3.4</span></span>
  - <span data-ttu-id="880c2-339">1.2.3.4\*</span><span class="sxs-lookup"><span data-stu-id="880c2-339">1.2.3.4\*</span></span>
  - <span data-ttu-id="880c2-340">contoso.com/a\*</span><span class="sxs-lookup"><span data-stu-id="880c2-340">contoso.com/a\*</span></span>
  - <span data-ttu-id="880c2-341">contoso.com/ab\*</span><span class="sxs-lookup"><span data-stu-id="880c2-341">contoso.com/ab\*</span></span>

- <span data-ttu-id="880c2-342">**IP-адреса с портами**:</span><span class="sxs-lookup"><span data-stu-id="880c2-342">**IP addresses with ports**:</span></span>

  - <span data-ttu-id="880c2-343">contoso.com:443</span><span class="sxs-lookup"><span data-stu-id="880c2-343">contoso.com:443</span></span>
  - <span data-ttu-id="880c2-344">abc.contoso.com:25</span><span class="sxs-lookup"><span data-stu-id="880c2-344">abc.contoso.com:25</span></span>

- <span data-ttu-id="880c2-345">**Подстановочные знаки, не являющиеся описательными**:</span><span class="sxs-lookup"><span data-stu-id="880c2-345">**Non-descriptive wildcards**:</span></span>

  - \*
  - <span data-ttu-id="880c2-346">\*.\*</span><span class="sxs-lookup"><span data-stu-id="880c2-346">\*.\*</span></span>

- <span data-ttu-id="880c2-347">**Посрединные подстановочные знаки**:</span><span class="sxs-lookup"><span data-stu-id="880c2-347">**Middle wildcards**:</span></span>

  - <span data-ttu-id="880c2-348">Конто \* so.com</span><span class="sxs-lookup"><span data-stu-id="880c2-348">conto\*so.com</span></span>
  - <span data-ttu-id="880c2-349">Конто ~ so. com</span><span class="sxs-lookup"><span data-stu-id="880c2-349">conto~so.com</span></span>

- <span data-ttu-id="880c2-350">**Знаки подстановки двойной замены**</span><span class="sxs-lookup"><span data-stu-id="880c2-350">**Double wildcards**</span></span>

  - <span data-ttu-id="880c2-351">contoso.com/\*\*</span><span class="sxs-lookup"><span data-stu-id="880c2-351">contoso.com/\*\*</span></span>
  - <span data-ttu-id="880c2-352">contoso.com/\*/\*</span><span class="sxs-lookup"><span data-stu-id="880c2-352">contoso.com/\*/\*</span></span>
