---
title: Управление вашими разрешателем и блоками в списке "Разрешить или заблокировать клиента"
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
description: Администраторы могут узнать, как настроить разрешаемые и блоки в списке разрешаемых и заблокированных клиентов на портале безопасности.
ms.openlocfilehash: c789b09224d00f5bb41ae29d6d2a6efa64d23a8d
ms.sourcegitcommit: 495b66b77d6dbe6d69e5b06b304089e4e476e568
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49799717"
---
# <a name="managing-allows-and-blocks-in-the-tenant-allowblock-list"></a><span data-ttu-id="80f09-103">Управление разрешением и блоками в списке "Разрешить или заблокировать клиента"</span><span class="sxs-lookup"><span data-stu-id="80f09-103">Managing allows and blocks in the Tenant Allow/Block List</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


> [!NOTE]
> <span data-ttu-id="80f09-104">Функции, описанные в этой статье, доступны в предварительной версии, могут изменяться и доступны не во всех организациях.</span><span class="sxs-lookup"><span data-stu-id="80f09-104">The features described in this article are in Preview, are subject to change, and are not available in all organizations.</span></span>

<span data-ttu-id="80f09-105">В организациях Microsoft 365 с почтовыми ящиками в организациях Exchange Online или автономных организациях Exchange Online Protection (EOP) без почтовых ящиков Exchange Online вы можете не согласиться с решением о фильтрации EOP.</span><span class="sxs-lookup"><span data-stu-id="80f09-105">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, you might disagree with the EOP filtering verdict.</span></span> <span data-ttu-id="80f09-106">Например, хорошее сообщение может быть помечено как плохое (ложное срабатыващение), или сообщение может быть разрешено (ложный отрицательный результат).</span><span class="sxs-lookup"><span data-stu-id="80f09-106">For example, a good message might be marked as bad (a false positive), or a bad message might be allowed through (a false negative).</span></span>

<span data-ttu-id="80f09-107">Список "Разрешить или заблокировать клиента" в Центре безопасности & соответствия требованиям позволяет вручную переопределять решения фильтров Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="80f09-107">The Tenant Allow/Block List in the Security & Compliance Center gives you a way to manually override the Microsoft 365 filtering verdicts.</span></span> <span data-ttu-id="80f09-108">Список "Разрешить/заблокировать" клиента используется во время потока почты и во время нажатия пользователем.</span><span class="sxs-lookup"><span data-stu-id="80f09-108">The Tenant Allow/Block List is used during mail flow and at the time of user clicks.</span></span> <span data-ttu-id="80f09-109">Вы можете указать URL-адреса, которые необходимо разрешить или заблокировать, в списке "Разрешить или заблокировать клиента".</span><span class="sxs-lookup"><span data-stu-id="80f09-109">You can specify URLs to allow or block in the Tenant Allow/Block List.</span></span>

<span data-ttu-id="80f09-110">В этом разделе описывается настройка записей в списке разрешения и блокировки клиентов в Центре безопасности и соответствия требованиям & или в PowerShell (Exchange Online PowerShell для организаций Microsoft 365 с почтовыми ящиками в Exchange Online; автономный EOP PowerShell для организаций без почтовых ящиков Exchange Online).</span><span class="sxs-lookup"><span data-stu-id="80f09-110">This topic describes how to configure entries in the Tenant Allow/Block List in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="80f09-111">Что нужно знать перед началом работы</span><span class="sxs-lookup"><span data-stu-id="80f09-111">What do you need to know before you begin?</span></span>

- <span data-ttu-id="80f09-112">Откройте Центр безопасности и соответствия требованиям на сайте <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="80f09-112">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="80f09-113">Чтобы перейти непосредственно на **страницу "Список заблокированных** и разрешаний клиентов", используйте <https://protection.office.com/tenantAllowBlockList> .</span><span class="sxs-lookup"><span data-stu-id="80f09-113">To go directly to the **Tenant Allow/Block List** page, use <https://protection.office.com/tenantAllowBlockList>.</span></span>

- <span data-ttu-id="80f09-114">Доступные значения URL-адресов описаны в синтаксисах [URL-адресов](#url-syntax-for-the-tenant-allowblock-list) для раздела "Список допустимого и заблокированного клиента" далее в этой статье.</span><span class="sxs-lookup"><span data-stu-id="80f09-114">The available URL values are described in the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this article.</span></span>

- <span data-ttu-id="80f09-115">Список "Разрешить/заблокировать" клиента позволяет использовать не более 500 записей для URL-адресов.</span><span class="sxs-lookup"><span data-stu-id="80f09-115">The Tenant Allow/Block List allows a maximum of 500 entries for URLs.</span></span>

- <span data-ttu-id="80f09-116">Запись должна быть активна в течение 15 минут.</span><span class="sxs-lookup"><span data-stu-id="80f09-116">An entry should be active within 15 minutes.</span></span>

- <span data-ttu-id="80f09-117">Блок-записи имеют приоритет над допустимой записью.</span><span class="sxs-lookup"><span data-stu-id="80f09-117">Block entries take precedence over allow entries.</span></span>

- <span data-ttu-id="80f09-118">По умолчанию срок действия записей в списке "Разрешить или заблокировать клиента" истекает через 30 дней.</span><span class="sxs-lookup"><span data-stu-id="80f09-118">By default, entries in the Tenant Allow/Block List will expire after 30 days.</span></span> <span data-ttu-id="80f09-119">Вы можете указать дату или установить для них срок действия без срока действия.</span><span class="sxs-lookup"><span data-stu-id="80f09-119">You can specify a date or set them to never expire.</span></span>

- <span data-ttu-id="80f09-120">Сведения о том, как подключиться к Exchange Online PowerShell, см. в статье [Подключение к Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="80f09-120">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="80f09-121">Чтобы подключиться к автономному EOP PowerShell, см. раздел [Подключение к PowerShell Exchange Online Protection](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="80f09-121">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="80f09-122">Для выполнения процедур, описанных в этой статье, вам должны быть назначены разрешения в Центре безопасности и соответствия требованиям:</span><span class="sxs-lookup"><span data-stu-id="80f09-122">You need to be assigned permissions in the Security & Compliance Center before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="80f09-123">Чтобы добавить и удалить значения из списка "Разрешить или заблокировать клиента",  необходимо быть членом группы ролей "Управление организацией" или "Администратор безопасности". </span><span class="sxs-lookup"><span data-stu-id="80f09-123">To add and remove values from the Tenant Allow/Block List, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="80f09-124">Для доступа только для чтения к списку разрешаний и блокировок  клиентов необходимо быть членом группы ролей **"Глобальное** чтение" или "Читатель безопасности".</span><span class="sxs-lookup"><span data-stu-id="80f09-124">For read-only access to the Tenant Allow/Block List, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="80f09-125">Дополнительные сведения см. в статье [Разрешения в Центре безопасности и соответствия требованиям](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="80f09-125">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

  <span data-ttu-id="80f09-126">**Примечания**.</span><span class="sxs-lookup"><span data-stu-id="80f09-126">**Notes**:</span></span>

  - <span data-ttu-id="80f09-127">Добавление пользователей в соответствующую роль Azure Active Directory в Центре безопасности Microsoft 365 предоставляет пользователям необходимые разрешения в Центре безопасности и соответствия требованиям _и_ разрешения для других функций в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="80f09-127">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="80f09-128">Дополнительные сведения см. в статье [О ролях администраторов](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span><span class="sxs-lookup"><span data-stu-id="80f09-128">For more information, see [About admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span></span>
  - <span data-ttu-id="80f09-129">Группа ролей **Управление организацией с правами только на просмотр** в [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) также предоставляет доступ только для чтения к этой функции.</span><span class="sxs-lookup"><span data-stu-id="80f09-129">The **View-Only Organization Management** role group in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

## <a name="use-the-security--compliance-center-to-create-url-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="80f09-130">Использование Центра безопасности & соответствия требованиям для создания URL-адресов в списке "Разрешить или заблокировать клиента"</span><span class="sxs-lookup"><span data-stu-id="80f09-130">Use the Security & Compliance Center to create URL entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="80f09-131">Подробные сведения о синтаксисах для [](#url-syntax-for-the-tenant-allowblock-list) записей URL-адресов см. в разделе "Синтаксис URL-адресов для списка допустимого и заблокированного клиента" далее в этой статье.</span><span class="sxs-lookup"><span data-stu-id="80f09-131">For details about the syntax for URL entries, see the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this article.</span></span>

1. <span data-ttu-id="80f09-132">В Центре безопасности & соответствия требованиям  перейдите в список "Политики управления угрозами" в списке \>  \> **"Разрешить/заблокировать клиента".**</span><span class="sxs-lookup"><span data-stu-id="80f09-132">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="80f09-133">На странице **"Список заблокированных** и разрешаний клиентов" убедитесь, что вкладка **"URL-адреса"** выбрана, и нажмите кнопку **"Добавить".**</span><span class="sxs-lookup"><span data-stu-id="80f09-133">On the **Tenant Allow/Block List** page, verify that the **URLs** tab is selected, and then click **Add**</span></span>

3. <span data-ttu-id="80f09-134">В **окне "Добавление новых** URL-адресов" настройте следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="80f09-134">In the **Add new URLs** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="80f09-135">**Добавление URL-адресов с поддиаными** знаками: введите один URL-адрес в строку до 20.</span><span class="sxs-lookup"><span data-stu-id="80f09-135">**Add URLs with wildcards**: Enter one URL per line, up to a maximum of 20.</span></span>

   - <span data-ttu-id="80f09-136">**Block/Allow**: Select whether you want to **Allow** or **Block** the specified URLs.</span><span class="sxs-lookup"><span data-stu-id="80f09-136">**Block/Allow**: Select whether you want to **Allow** or **Block** the specified URLs.</span></span>

   - <span data-ttu-id="80f09-137">**Срок действия не истекает:** сделайте одно из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="80f09-137">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="80f09-138">Убедитесь, что параметр отключен (выключен) и используйте поле "Срок действия" для указания даты окончания срока ![ ](../../media/scc-toggle-off.png) действия записей. </span><span class="sxs-lookup"><span data-stu-id="80f09-138">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entries.</span></span>

     <span data-ttu-id="80f09-139">или</span><span class="sxs-lookup"><span data-stu-id="80f09-139">or</span></span>

     - <span data-ttu-id="80f09-140">Переместите его вправо, чтобы настроить срок действия записей:</span><span class="sxs-lookup"><span data-stu-id="80f09-140">Move the toggle to the right to configure the entries to never expire:</span></span> ![Включенный переключатель](../../media/scc-toggle-on.png)<span data-ttu-id="80f09-142">.</span><span class="sxs-lookup"><span data-stu-id="80f09-142">.</span></span>

   - <span data-ttu-id="80f09-143">**Необязательное примечание.** Введите описательное текст для записей.</span><span class="sxs-lookup"><span data-stu-id="80f09-143">**Optional note**: Enter descriptive text for the entries.</span></span>

4. <span data-ttu-id="80f09-144">По завершению нажмите кнопку **"Добавить".**</span><span class="sxs-lookup"><span data-stu-id="80f09-144">When you're finished, click **Add**.</span></span>

## <a name="use-the-security--compliance-center-to-view-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="80f09-145">Использование Центра безопасности & соответствия требованиям для просмотра записей в списке "Разрешить или заблокировать клиента"</span><span class="sxs-lookup"><span data-stu-id="80f09-145">Use the Security & Compliance Center to view entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="80f09-146">В Центре безопасности & соответствия требованиям  перейдите в список "Политики управления угрозами" в списке \>  \> **"Разрешить/заблокировать клиента".**</span><span class="sxs-lookup"><span data-stu-id="80f09-146">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="80f09-147">Выберите вкладку **"URL-адреса".**</span><span class="sxs-lookup"><span data-stu-id="80f09-147">Select the **URLs** tab.</span></span>

<span data-ttu-id="80f09-148">Щелкните следующие заголовки столбцов, чтобы отсортировать их по возрастанию или убыванию:</span><span class="sxs-lookup"><span data-stu-id="80f09-148">Click on the following column headings to sort in ascending or descending order:</span></span>

- <span data-ttu-id="80f09-149">**Значение**</span><span class="sxs-lookup"><span data-stu-id="80f09-149">**Value**</span></span>
- <span data-ttu-id="80f09-150">**Action**: **Block** or **Allow**.</span><span class="sxs-lookup"><span data-stu-id="80f09-150">**Action**: **Block** or **Allow**.</span></span>
- <span data-ttu-id="80f09-151">**Дата последнего обновления**</span><span class="sxs-lookup"><span data-stu-id="80f09-151">**Last updated date**</span></span>
- <span data-ttu-id="80f09-152">**Дата окончания срока действия**</span><span class="sxs-lookup"><span data-stu-id="80f09-152">**Expiration date**</span></span>
- <span data-ttu-id="80f09-153">**Примечание**</span><span class="sxs-lookup"><span data-stu-id="80f09-153">**Note**</span></span>

<span data-ttu-id="80f09-154">Щелкните **"Группа"** для группировки записей по **действию** **(блокировка** или **разрешение)** или **"Нет".**</span><span class="sxs-lookup"><span data-stu-id="80f09-154">Click **Group** to group the entries by **Action** (**Block** or **Allow**) or **None**.</span></span>

<span data-ttu-id="80f09-155">Нажмите **кнопку**"Поиск", введите все или часть значения, а затем нажмите ввод, чтобы найти определенное значение.</span><span class="sxs-lookup"><span data-stu-id="80f09-155">Click **Search**, enter all or part of a value, and then press ENTER to find a specific value.</span></span> <span data-ttu-id="80f09-156">По завершению нажмите кнопку **"Очистить поиск"** ![ и нажмите значок "Очистить поиск". ](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif)</span><span class="sxs-lookup"><span data-stu-id="80f09-156">When you're finished, click **Clear search** ![Clear search icon](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif).</span></span>

<span data-ttu-id="80f09-157">Щелкните **"Фильтр"**.</span><span class="sxs-lookup"><span data-stu-id="80f09-157">Click **Filter**.</span></span> <span data-ttu-id="80f09-158">Во появляется **во** flyout фильтра, настройте любой из следующих параметров:</span><span class="sxs-lookup"><span data-stu-id="80f09-158">In the **Filter** flyout that appears, configure any of the following settings:</span></span>

- <span data-ttu-id="80f09-159">**Действие:** выберите **"Разрешить",** **"Заблокировать"** или "И то, и другое".</span><span class="sxs-lookup"><span data-stu-id="80f09-159">**Action**: Select **Allow**, **Block** or both.</span></span>

- <span data-ttu-id="80f09-160">**Никогда не истекает:** выключите: ![ отключите ](../../media/scc-toggle-off.png) или включите: ![ включите. ](../../media/scc-toggle-on.png)</span><span class="sxs-lookup"><span data-stu-id="80f09-160">**Never expire**: Select off: ![Toggle off](../../media/scc-toggle-off.png) or on: ![Toggle on](../../media/scc-toggle-on.png).</span></span>

- <span data-ttu-id="80f09-161">**Last updated**: Select a start date (**From),** an end date (**To**) or both.</span><span class="sxs-lookup"><span data-stu-id="80f09-161">**Last updated**: Select a start date (**From**), an end date (**To**) or both.</span></span>

- <span data-ttu-id="80f09-162">**Дата окончания** срока действия: выберите даты начала **(от),** даты окончания (**To)** или и того, и другого.</span><span class="sxs-lookup"><span data-stu-id="80f09-162">**Expiration date**: Select a start date (**From**), an end date (**To**) or both.</span></span>

<span data-ttu-id="80f09-163">По завершению нажмите кнопку **"Применить".**</span><span class="sxs-lookup"><span data-stu-id="80f09-163">When you're finished, click **Apply**.</span></span>

<span data-ttu-id="80f09-164">Чтобы очистить существующие фильтры, щелкните **"Фильтр",** а затем щелкните  **"Очистить фильтры".**</span><span class="sxs-lookup"><span data-stu-id="80f09-164">To clear existing filters, click **Filter**, and in the **Filter** flyout that appears, click **Clear filters**.</span></span>

## <a name="use-the-security--compliance-center-to-modify-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="80f09-165">Использование Центра безопасности & соответствия требованиям для изменения записей в списке "Разрешить или заблокировать клиента"</span><span class="sxs-lookup"><span data-stu-id="80f09-165">Use the Security & Compliance Center to modify entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="80f09-166">Вы не можете изменить значение URL-адреса.</span><span class="sxs-lookup"><span data-stu-id="80f09-166">You can't modify the URL value itself.</span></span> <span data-ttu-id="80f09-167">Вместо этого необходимо удалить запись и повторно создать ее.</span><span class="sxs-lookup"><span data-stu-id="80f09-167">Instead, you need to delete the entry and recreate it.</span></span>

1. <span data-ttu-id="80f09-168">В Центре безопасности & соответствия требованиям  перейдите в список "Политики управления угрозами" в списке \>  \> **"Разрешить/заблокировать клиента".**</span><span class="sxs-lookup"><span data-stu-id="80f09-168">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="80f09-169">Выберите вкладку **"URL-адреса".**</span><span class="sxs-lookup"><span data-stu-id="80f09-169">Select the **URLs** tab.</span></span>

3. <span data-ttu-id="80f09-170">Выберите запись, которую нужно изменить,  и нажмите значок ![ ](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) редактирования.</span><span class="sxs-lookup"><span data-stu-id="80f09-170">Select the entry that you want to modify, and then click **Edit** ![Edit icon](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png).</span></span>

4. <span data-ttu-id="80f09-171">Во появляется во flyout настройте следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="80f09-171">In the flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="80f09-172">**Block/Allow**: Select **Allow** or **Block**.</span><span class="sxs-lookup"><span data-stu-id="80f09-172">**Block/Allow**: Select **Allow** or **Block**.</span></span>

   - <span data-ttu-id="80f09-173">**Срок действия не истекает:** сделайте одно из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="80f09-173">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="80f09-174">Убедитесь, что параметр отключен (выключен) и используйте поле "Срок действия" для указания даты окончания ![ ](../../media/scc-toggle-off.png) срока действия записи. </span><span class="sxs-lookup"><span data-stu-id="80f09-174">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entry.</span></span>

     <span data-ttu-id="80f09-175">или</span><span class="sxs-lookup"><span data-stu-id="80f09-175">or</span></span>

     - <span data-ttu-id="80f09-176">Переместите его вправо, чтобы настроить срок действия записи:</span><span class="sxs-lookup"><span data-stu-id="80f09-176">Move the toggle to the right to configure the entry to never expire:</span></span> ![Включенный переключатель](../../media/scc-toggle-on.png)<span data-ttu-id="80f09-178">.</span><span class="sxs-lookup"><span data-stu-id="80f09-178">.</span></span>

   - <span data-ttu-id="80f09-179">**Необязательное примечание.** Введите описательное текст для записи.</span><span class="sxs-lookup"><span data-stu-id="80f09-179">**Optional note**: Enter descriptive text for the entry.</span></span>

5. <span data-ttu-id="80f09-180">Когда закончите, нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="80f09-180">When you're finished, click **Save**.</span></span>

## <a name="use-the-security--compliance-center-to-remove-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="80f09-181">Использование Центра безопасности & соответствия требованиям для удаления записей из списка "Разрешить или заблокировать клиента"</span><span class="sxs-lookup"><span data-stu-id="80f09-181">Use the Security & Compliance Center to remove entries from the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="80f09-182">В Центре безопасности & соответствия требованиям  перейдите в список "Политики управления угрозами" в списке \>  \> **"Разрешить/заблокировать клиента".**</span><span class="sxs-lookup"><span data-stu-id="80f09-182">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="80f09-183">Выберите вкладку **"URL-адреса".**</span><span class="sxs-lookup"><span data-stu-id="80f09-183">Select the **URLs** tab.</span></span>

3. <span data-ttu-id="80f09-184">Выберите запись, которую нужно удалить, и нажмите кнопку **"Удалить** ![ значок удаления". ](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png)</span><span class="sxs-lookup"><span data-stu-id="80f09-184">Select the entry that you want to remove, and then click **Delete** ![Delete icon](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png).</span></span>

4. <span data-ttu-id="80f09-185">В появится диалоговое окно предупреждения, нажмите кнопку **"Удалить".**</span><span class="sxs-lookup"><span data-stu-id="80f09-185">In the warning dialog that appears, click **Delete**.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-the-tenant-allowblock-list"></a><span data-ttu-id="80f09-186">Использование Exchange Online PowerShell или автономный EOP PowerShell для настройки списка "Разрешить или заблокировать клиента"</span><span class="sxs-lookup"><span data-stu-id="80f09-186">Use Exchange Online PowerShell or standalone EOP PowerShell to configure the Tenant Allow/Block List</span></span>

### <a name="use-powershell-to-add-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="80f09-187">Добавление записей в список "Разрешить или заблокировать" с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="80f09-187">Use PowerShell to add entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="80f09-188">Чтобы добавить записи в список "Клиенты: разрешить или заблокировать", используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="80f09-188">To add entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
New-TenantAllowBlockListItems -ListType Url -Action <Allow | Block> -Entries <String[]> [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

<span data-ttu-id="80f09-189">В этом примере добавляется запись блока URL-адресов для contoso.com и всех поддоменов (например, contoso.com, www.contoso.com и xyz.abc.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="80f09-189">This example adds a URL block entry for contoso.com and all subdomains (for example, contoso.com, www.contoso.com, and xyz.abc.contoso.com).</span></span> <span data-ttu-id="80f09-190">Так как мы не использовали параметры ExpirationDate или NoExpiration, срок действия записи истекает через 30 дней.</span><span class="sxs-lookup"><span data-stu-id="80f09-190">Because we didn't use the ExpirationDate or NoExpiration parameters, the entry expires after 30 days.</span></span>

```powershell
New-TenantAllowBlockListItem -ListType Url -Action Block -Entries ~contoso.com
```

<span data-ttu-id="80f09-191">Подробные сведения о синтаксисе и параметрах см. в описании [New-TenantAllowBlockListItems.](https://docs.microsoft.com/powershell/module/exchange/new-tenantallowblocklistitems)</span><span class="sxs-lookup"><span data-stu-id="80f09-191">For detailed syntax and parameter information, see [New-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/new-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-view-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="80f09-192">Использование PowerShell для просмотра записей в списке "Разрешить или заблокировать клиента"</span><span class="sxs-lookup"><span data-stu-id="80f09-192">Use PowerShell to view entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="80f09-193">Чтобы просмотреть записи в списке "Разрешить или заблокировать клиента", используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="80f09-193">To view entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType Url [-Entry <URLValue>] [-Action <Allow | Block>] [-ExpirationDate <DateTime>] [-NoExpiration]
```

<span data-ttu-id="80f09-194">В этом примере возвращаются все заблокированные URL-адреса.</span><span class="sxs-lookup"><span data-stu-id="80f09-194">This example returns all blocked URLs.</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType Url -Action Block
```

<span data-ttu-id="80f09-195">Подробные сведения о синтаксисе и параметрах см. в описании [Get-TenantAllowBlockListItems.](https://docs.microsoft.com/powershell/module/exchange/get-tenantallowblocklistitems)</span><span class="sxs-lookup"><span data-stu-id="80f09-195">For detailed syntax and parameter information, see [Get-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/get-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-modify-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="80f09-196">Использование PowerShell для изменения записей в списке "Разрешить или заблокировать клиента"</span><span class="sxs-lookup"><span data-stu-id="80f09-196">Use PowerShell to modify entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="80f09-197">Вы не можете изменить значение URL-адреса.</span><span class="sxs-lookup"><span data-stu-id="80f09-197">You can't modify the URL value itself.</span></span> <span data-ttu-id="80f09-198">Вместо этого необходимо удалить запись и повторно создать ее.</span><span class="sxs-lookup"><span data-stu-id="80f09-198">Instead, you need to delete the entry and recreate it.</span></span>

<span data-ttu-id="80f09-199">Чтобы изменить записи в списке допустимой и заблокированной записей клиента, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="80f09-199">To modify entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType Url -Ids <"Id1","Id2",..."IdN"> [-Action <Allow | Block>] [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

<span data-ttu-id="80f09-200">В этом примере изменяется дата окончания срока действия указанной записи.</span><span class="sxs-lookup"><span data-stu-id="80f09-200">This example changes the expiration date of the specified entry.</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -ExpirationDate (Get-Date "5/30/2020 9:30 AM").ToUniversalTime()
```

<span data-ttu-id="80f09-201">Подробные сведения о синтаксисе и параметрах см. в описании [Set-TenantAllowBlockListItems.](https://docs.microsoft.com/powershell/module/exchange/set-tenantallowblocklistitems)</span><span class="sxs-lookup"><span data-stu-id="80f09-201">For detailed syntax and parameter information, see [Set-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/set-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-remove-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="80f09-202">Использование PowerShell для удаления записей из списка "Разрешить или заблокировать клиента"</span><span class="sxs-lookup"><span data-stu-id="80f09-202">Use PowerShell to remove entries from the Tenant Allow/Block List</span></span>

<span data-ttu-id="80f09-203">Чтобы удалить записи из списка "Клиенты: разрешить или заблокировать", используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="80f09-203">To remove entries from the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType Url -Ids <"Id1","Id2",..."IdN">
```

<span data-ttu-id="80f09-204">В этом примере из списка допустимого или заблокированного клиента удаляется указанная запись URL-адреса.</span><span class="sxs-lookup"><span data-stu-id="80f09-204">This example removes the specified URL entry from the Tenant Allow/Block List.</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSPAAAA0"
```

<span data-ttu-id="80f09-205">Подробные сведения о синтаксисе и параметрах см. в описании [remove-TenantAllowBlockListItems.](https://docs.microsoft.com/powershell/module/exchange/remove-tenantallowblocklistitems)</span><span class="sxs-lookup"><span data-stu-id="80f09-205">For detailed syntax and parameter information, see [Remove-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/remove-tenantallowblocklistitems).</span></span>

## <a name="url-syntax-for-the-tenant-allowblock-list"></a><span data-ttu-id="80f09-206">Синтаксис URL-адресов для списка допустимого и заблокированного клиента</span><span class="sxs-lookup"><span data-stu-id="80f09-206">URL syntax for the Tenant Allow/Block List</span></span>

- <span data-ttu-id="80f09-207">Ip4v- и IPv6-адреса разрешены, а порты TCP/UDP — нет.</span><span class="sxs-lookup"><span data-stu-id="80f09-207">IP4v and IPv6 addresses are allowed, but TCP/UDP ports are not.</span></span>

- <span data-ttu-id="80f09-208">Расширения имен файлов запрещены (например, test.pdf).</span><span class="sxs-lookup"><span data-stu-id="80f09-208">Filename extensions are not allowed (for example, test.pdf).</span></span>

- <span data-ttu-id="80f09-209">Юникод не поддерживается, но это punycode.</span><span class="sxs-lookup"><span data-stu-id="80f09-209">Unicode is not supported, but Punycode is.</span></span>

- <span data-ttu-id="80f09-210">Имена хостов разрешены, если истинны все следующие утверждения:</span><span class="sxs-lookup"><span data-stu-id="80f09-210">Hostnames are allowed if all of the following statements are true:</span></span>

  - <span data-ttu-id="80f09-211">Имя хоста содержит период.</span><span class="sxs-lookup"><span data-stu-id="80f09-211">The hostname contains a period.</span></span>
  - <span data-ttu-id="80f09-212">Слева от периода находится хотя бы один символ.</span><span class="sxs-lookup"><span data-stu-id="80f09-212">There is at least one character to the left of the period.</span></span>
  - <span data-ttu-id="80f09-213">Справа от периода есть по крайней мере два символа.</span><span class="sxs-lookup"><span data-stu-id="80f09-213">There are at least two characters to the right of the period.</span></span>

  <span data-ttu-id="80f09-214">Например, `t.co` разрешено или `.com` `contoso.` запрещено.</span><span class="sxs-lookup"><span data-stu-id="80f09-214">For example, `t.co` is allowed; `.com` or `contoso.` are not allowed.</span></span>

- <span data-ttu-id="80f09-215">Подпазки не подразумеваются.</span><span class="sxs-lookup"><span data-stu-id="80f09-215">Subpaths are not implied.</span></span>

  <span data-ttu-id="80f09-216">Например, `contoso.com` не включает `contoso.com/a` .</span><span class="sxs-lookup"><span data-stu-id="80f09-216">For example, `contoso.com` does not include `contoso.com/a`.</span></span>

- <span data-ttu-id="80f09-217">В следующих сценариях допускаются поддиаными знаками (\*):</span><span class="sxs-lookup"><span data-stu-id="80f09-217">Wildcards (\*) are allowed in the following scenarios:</span></span>

  - <span data-ttu-id="80f09-218">Чтобы указать поддомен, необходимо следовать за левый поддиакон.</span><span class="sxs-lookup"><span data-stu-id="80f09-218">A left wildcard must be followed by a period to specify a subdomain.</span></span>

    <span data-ttu-id="80f09-219">Например, `*.contoso.com` разрешено; `*contoso.com` запрещено.</span><span class="sxs-lookup"><span data-stu-id="80f09-219">For example, `*.contoso.com` is allowed; `*contoso.com` is not allowed.</span></span>

  - <span data-ttu-id="80f09-220">Для указания пути правый поддиаптер должен следовать косой черты (/).</span><span class="sxs-lookup"><span data-stu-id="80f09-220">A right wildcard must follow a forward slash (/) to specify a path.</span></span>

    <span data-ttu-id="80f09-221">Например, `contoso.com/*` разрешено или `contoso.com*` `contoso.com/ab*` запрещено.</span><span class="sxs-lookup"><span data-stu-id="80f09-221">For example, `contoso.com/*` is allowed; `contoso.com*` or `contoso.com/ab*` are not allowed.</span></span>

  - <span data-ttu-id="80f09-222">Поддиапатический знак не подразумевает все подпазки.</span><span class="sxs-lookup"><span data-stu-id="80f09-222">All subpaths are not implied by a right wildcard.</span></span>

    <span data-ttu-id="80f09-223">Например, `contoso.com/*` не включает `contoso.com/a` .</span><span class="sxs-lookup"><span data-stu-id="80f09-223">For example, `contoso.com/*` does not include `contoso.com/a`.</span></span>

  - <span data-ttu-id="80f09-224">`*.com*` является недопустимым (не является разрешаемым доменом, а правый поддиапный знак не следует косой черте).</span><span class="sxs-lookup"><span data-stu-id="80f09-224">`*.com*` is invalid (not a resolvable domain and the right wildcard does not follow a forward slash).</span></span>

  - <span data-ttu-id="80f09-225">Поддиапные знаки не разрешены в IP-адресах.</span><span class="sxs-lookup"><span data-stu-id="80f09-225">Wildcards are not allowed in IP addresses.</span></span>

- <span data-ttu-id="80f09-226">Символ тильды (~) доступен в следующих сценариях:</span><span class="sxs-lookup"><span data-stu-id="80f09-226">The tilde (~) character is available in the following scenarios:</span></span>

  - <span data-ttu-id="80f09-227">Левая тильда подразумевает домен и все поддомены.</span><span class="sxs-lookup"><span data-stu-id="80f09-227">A left tilde implies a domain and all subdomains.</span></span>

    <span data-ttu-id="80f09-228">Например, `~contoso.com` включает `contoso.com` и `*.contoso.com` .</span><span class="sxs-lookup"><span data-stu-id="80f09-228">For example `~contoso.com` includes `contoso.com` and `*.contoso.com`.</span></span>

- <span data-ttu-id="80f09-229">Url-адреса, содержащие протоколы (например, , или ) не удастся, так как `http://` `https://` `ftp://` url-записи применяются к всем протоколам.</span><span class="sxs-lookup"><span data-stu-id="80f09-229">URL entries that contain protocols (for example, `http://`, `https://`, or `ftp://`) will fail, because URL entries apply to all protocols.</span></span>

- <span data-ttu-id="80f09-230">Имя пользователя или пароль не поддерживаются и не требуются.</span><span class="sxs-lookup"><span data-stu-id="80f09-230">A username or password aren't supported or required.</span></span>

- <span data-ttu-id="80f09-231">Кавычка (' или ") являются недопустимыми символами.</span><span class="sxs-lookup"><span data-stu-id="80f09-231">Quotes (' or ") are invalid characters.</span></span>

- <span data-ttu-id="80f09-232">URL-адрес должен включать все перенаправления по возможности.</span><span class="sxs-lookup"><span data-stu-id="80f09-232">A URL should include all redirects where possible.</span></span>

### <a name="url-entry-scenarios"></a><span data-ttu-id="80f09-233">Сценарии ввода URL-адреса</span><span class="sxs-lookup"><span data-stu-id="80f09-233">URL entry scenarios</span></span>

<span data-ttu-id="80f09-234">Допустимые URL-адреса и их результаты описаны в следующих разделах.</span><span class="sxs-lookup"><span data-stu-id="80f09-234">Valid URL entries and their results are described in the following sections.</span></span>

#### <a name="scenario-no-wildcards"></a><span data-ttu-id="80f09-235">Сценарий: поддиаными знаками не является</span><span class="sxs-lookup"><span data-stu-id="80f09-235">Scenario: No wildcards</span></span>

<span data-ttu-id="80f09-236">**Запись:**`contoso.com`</span><span class="sxs-lookup"><span data-stu-id="80f09-236">**Entry**: `contoso.com`</span></span>

- <span data-ttu-id="80f09-237">**Разрешить соответствие**: contoso.com</span><span class="sxs-lookup"><span data-stu-id="80f09-237">**Allow match**: contoso.com</span></span>

- <span data-ttu-id="80f09-238">**Allow not matched**:</span><span class="sxs-lookup"><span data-stu-id="80f09-238">**Allow not matched**:</span></span>

  - <span data-ttu-id="80f09-239">abc-contoso.com</span><span class="sxs-lookup"><span data-stu-id="80f09-239">abc-contoso.com</span></span>
  - <span data-ttu-id="80f09-240">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="80f09-240">contoso.com/a</span></span>
  - <span data-ttu-id="80f09-241">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="80f09-241">payroll.contoso.com</span></span>
  - <span data-ttu-id="80f09-242">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="80f09-242">test.com/contoso.com</span></span>
  - <span data-ttu-id="80f09-243">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="80f09-243">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="80f09-244">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="80f09-244">www.contoso.com</span></span>
  - <span data-ttu-id="80f09-245">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="80f09-245">www.contoso.com/q=a@contoso.com</span></span>

- <span data-ttu-id="80f09-246">**Блокировка совпадений:**</span><span class="sxs-lookup"><span data-stu-id="80f09-246">**Block match**:</span></span>

  - <span data-ttu-id="80f09-247">contoso.com</span><span class="sxs-lookup"><span data-stu-id="80f09-247">contoso.com</span></span>
  - <span data-ttu-id="80f09-248">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="80f09-248">contoso.com/a</span></span>
  - <span data-ttu-id="80f09-249">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="80f09-249">payroll.contoso.com</span></span>
  - <span data-ttu-id="80f09-250">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="80f09-250">test.com/contoso.com</span></span>
  - <span data-ttu-id="80f09-251">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="80f09-251">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="80f09-252">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="80f09-252">www.contoso.com</span></span>
  - <span data-ttu-id="80f09-253">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="80f09-253">www.contoso.com/q=a@contoso.com</span></span>

- <span data-ttu-id="80f09-254">**Block not matched**: abc-contoso.com</span><span class="sxs-lookup"><span data-stu-id="80f09-254">**Block not matched**: abc-contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain"></a><span data-ttu-id="80f09-255">Сценарий: левый поддомен (поддомен)</span><span class="sxs-lookup"><span data-stu-id="80f09-255">Scenario: Left wildcard (subdomain)</span></span>

<span data-ttu-id="80f09-256">**Запись:**`*.contoso.com`</span><span class="sxs-lookup"><span data-stu-id="80f09-256">**Entry**: `*.contoso.com`</span></span>

- <span data-ttu-id="80f09-257">**Разрешить соответствие и** **блокировку совпадений:**</span><span class="sxs-lookup"><span data-stu-id="80f09-257">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="80f09-258">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="80f09-258">www.contoso.com</span></span>
  - <span data-ttu-id="80f09-259">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="80f09-259">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="80f09-260">**Allow not matched** and **Block not matched**:</span><span class="sxs-lookup"><span data-stu-id="80f09-260">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="80f09-261">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="80f09-261">123contoso.com</span></span>
  - <span data-ttu-id="80f09-262">contoso.com</span><span class="sxs-lookup"><span data-stu-id="80f09-262">contoso.com</span></span>
  - <span data-ttu-id="80f09-263">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="80f09-263">test.com/contoso.com</span></span>
  - <span data-ttu-id="80f09-264">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="80f09-264">www.contoso.com/abc</span></span>

#### <a name="scenario-right-wildcard-at-top-of-path"></a><span data-ttu-id="80f09-265">Сценарий: правый под wildcard в верхней части пути</span><span class="sxs-lookup"><span data-stu-id="80f09-265">Scenario: Right wildcard at top of path</span></span>

<span data-ttu-id="80f09-266">**Запись:**`contoso.com/a/*`</span><span class="sxs-lookup"><span data-stu-id="80f09-266">**Entry**: `contoso.com/a/*`</span></span>

- <span data-ttu-id="80f09-267">**Разрешить соответствие и** **блокировку совпадений:**</span><span class="sxs-lookup"><span data-stu-id="80f09-267">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="80f09-268">contoso.com/a/b</span><span class="sxs-lookup"><span data-stu-id="80f09-268">contoso.com/a/b</span></span>
  - <span data-ttu-id="80f09-269">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="80f09-269">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="80f09-270">contoso.com/a/?q=joe@t.com</span><span class="sxs-lookup"><span data-stu-id="80f09-270">contoso.com/a/?q=joe@t.com</span></span>

- <span data-ttu-id="80f09-271">**Allow not matched** and **Block not matched**:</span><span class="sxs-lookup"><span data-stu-id="80f09-271">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="80f09-272">contoso.com</span><span class="sxs-lookup"><span data-stu-id="80f09-272">contoso.com</span></span>
  - <span data-ttu-id="80f09-273">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="80f09-273">contoso.com/a</span></span>
  - <span data-ttu-id="80f09-274">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="80f09-274">www.contoso.com</span></span>
  - <span data-ttu-id="80f09-275">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="80f09-275">www.contoso.com/q=a@contoso.com</span></span>

#### <a name="scenario-left-tilde"></a><span data-ttu-id="80f09-276">Сценарий: левая тильда</span><span class="sxs-lookup"><span data-stu-id="80f09-276">Scenario: Left tilde</span></span>

<span data-ttu-id="80f09-277">**Запись:**`~contoso.com`</span><span class="sxs-lookup"><span data-stu-id="80f09-277">**Entry**: `~contoso.com`</span></span>

- <span data-ttu-id="80f09-278">**Разрешить соответствие и** **блокировку совпадений:**</span><span class="sxs-lookup"><span data-stu-id="80f09-278">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="80f09-279">contoso.com</span><span class="sxs-lookup"><span data-stu-id="80f09-279">contoso.com</span></span>
  - <span data-ttu-id="80f09-280">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="80f09-280">www.contoso.com</span></span>
  - <span data-ttu-id="80f09-281">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="80f09-281">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="80f09-282">**Allow not matched** and **Block not matched**:</span><span class="sxs-lookup"><span data-stu-id="80f09-282">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="80f09-283">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="80f09-283">123contoso.com</span></span>
  - <span data-ttu-id="80f09-284">contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="80f09-284">contoso.com/abc</span></span>
  - <span data-ttu-id="80f09-285">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="80f09-285">www.contoso.com/abc</span></span>

#### <a name="scenario-right-wildcard-suffix"></a><span data-ttu-id="80f09-286">Сценарий: правый суффикс подстановки</span><span class="sxs-lookup"><span data-stu-id="80f09-286">Scenario: Right wildcard suffix</span></span>

<span data-ttu-id="80f09-287">**Запись:**`contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="80f09-287">**Entry**: `contoso.com/*`</span></span>

- <span data-ttu-id="80f09-288">**Разрешить соответствие и** **блокировку совпадений:**</span><span class="sxs-lookup"><span data-stu-id="80f09-288">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="80f09-289">contoso.com/?q=whatever@fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="80f09-289">contoso.com/?q=whatever@fabrikam.com</span></span>
  - <span data-ttu-id="80f09-290">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="80f09-290">contoso.com/a</span></span>
  - <span data-ttu-id="80f09-291">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="80f09-291">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="80f09-292">contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="80f09-292">contoso.com/ab</span></span>
  - <span data-ttu-id="80f09-293">contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="80f09-293">contoso.com/b</span></span>
  - <span data-ttu-id="80f09-294">contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="80f09-294">contoso.com/b/a/c</span></span>
  - <span data-ttu-id="80f09-295">contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="80f09-295">contoso.com/ba</span></span>

- <span data-ttu-id="80f09-296">**Allow not matched** and **Block not matched**: contoso.com</span><span class="sxs-lookup"><span data-stu-id="80f09-296">**Allow not matched** and **Block not matched**: contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain-and-right-wildcard-suffix"></a><span data-ttu-id="80f09-297">Сценарий: левый поддомен и правый суффикс подстановки</span><span class="sxs-lookup"><span data-stu-id="80f09-297">Scenario: Left wildcard subdomain and right wildcard suffix</span></span>

<span data-ttu-id="80f09-298">**Запись:**`*.contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="80f09-298">**Entry**: `*.contoso.com/*`</span></span>

- <span data-ttu-id="80f09-299">**Разрешить соответствие и** **блокировку совпадений:**</span><span class="sxs-lookup"><span data-stu-id="80f09-299">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="80f09-300">abc.contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="80f09-300">abc.contoso.com/ab</span></span>
  - <span data-ttu-id="80f09-301">abc.xyz.contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="80f09-301">abc.xyz.contoso.com/a/b/c</span></span>
  - <span data-ttu-id="80f09-302">www.contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="80f09-302">www.contoso.com/a</span></span>
  - <span data-ttu-id="80f09-303">www.contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="80f09-303">www.contoso.com/b/a/c</span></span>
  - <span data-ttu-id="80f09-304">xyz.contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="80f09-304">xyz.contoso.com/ba</span></span>

- <span data-ttu-id="80f09-305">**Allow not matched** and **Block not matched**: contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="80f09-305">**Allow not matched** and **Block not matched**: contoso.com/b</span></span>

#### <a name="scenario-left-and-right-tilde"></a><span data-ttu-id="80f09-306">Сценарий: левая и правая тильда</span><span class="sxs-lookup"><span data-stu-id="80f09-306">Scenario: Left and right tilde</span></span>

<span data-ttu-id="80f09-307">**Запись:**`~contoso.com~`</span><span class="sxs-lookup"><span data-stu-id="80f09-307">**Entry**: `~contoso.com~`</span></span>

- <span data-ttu-id="80f09-308">**Разрешить соответствие и** **блокировку совпадений:**</span><span class="sxs-lookup"><span data-stu-id="80f09-308">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="80f09-309">contoso.com</span><span class="sxs-lookup"><span data-stu-id="80f09-309">contoso.com</span></span>
  - <span data-ttu-id="80f09-310">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="80f09-310">contoso.com/a</span></span>
  - <span data-ttu-id="80f09-311">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="80f09-311">www.contoso.com</span></span>
  - <span data-ttu-id="80f09-312">www.contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="80f09-312">www.contoso.com/b</span></span>
  - <span data-ttu-id="80f09-313">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="80f09-313">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="80f09-314">**Allow not matched** and **Block not matched**:</span><span class="sxs-lookup"><span data-stu-id="80f09-314">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="80f09-315">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="80f09-315">123contoso.com</span></span>
  - <span data-ttu-id="80f09-316">contoso.org</span><span class="sxs-lookup"><span data-stu-id="80f09-316">contoso.org</span></span>

#### <a name="scenario-ip-address"></a><span data-ttu-id="80f09-317">Сценарий: IP-адрес</span><span class="sxs-lookup"><span data-stu-id="80f09-317">Scenario: IP address</span></span>

<span data-ttu-id="80f09-318">**Запись:**`1.2.3.4`</span><span class="sxs-lookup"><span data-stu-id="80f09-318">**Entry**: `1.2.3.4`</span></span>

- <span data-ttu-id="80f09-319">**Разрешить соответствие** и **блокировку**: 1.2.3.4</span><span class="sxs-lookup"><span data-stu-id="80f09-319">**Allow match** and **Block match**: 1.2.3.4</span></span>

- <span data-ttu-id="80f09-320">**Allow not matched** and **Block not matched**:</span><span class="sxs-lookup"><span data-stu-id="80f09-320">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="80f09-321">1.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="80f09-321">1.2.3.4/a</span></span>
  - <span data-ttu-id="80f09-322">11.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="80f09-322">11.2.3.4/a</span></span>

#### <a name="ip-address-with-right-wildcard"></a><span data-ttu-id="80f09-323">IP-адрес с правильным поддиапным знаком</span><span class="sxs-lookup"><span data-stu-id="80f09-323">IP address with right wildcard</span></span>

<span data-ttu-id="80f09-324">**Запись:**`1.2.3.4/*`</span><span class="sxs-lookup"><span data-stu-id="80f09-324">**Entry**: `1.2.3.4/*`</span></span>

- <span data-ttu-id="80f09-325">**Разрешить соответствие и** **блокировку совпадений:**</span><span class="sxs-lookup"><span data-stu-id="80f09-325">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="80f09-326">1.2.3.4/b</span><span class="sxs-lookup"><span data-stu-id="80f09-326">1.2.3.4/b</span></span>
  - <span data-ttu-id="80f09-327">1.2.3.4/baaaa</span><span class="sxs-lookup"><span data-stu-id="80f09-327">1.2.3.4/baaaa</span></span>

### <a name="examples-of-invalid-entries"></a><span data-ttu-id="80f09-328">Примеры недопустимых записей</span><span class="sxs-lookup"><span data-stu-id="80f09-328">Examples of invalid entries</span></span>

<span data-ttu-id="80f09-329">Недопустимы следующие записи:</span><span class="sxs-lookup"><span data-stu-id="80f09-329">The following entries are invalid:</span></span>

- <span data-ttu-id="80f09-330">**Отсутствуют или недопустимые значения домена:**</span><span class="sxs-lookup"><span data-stu-id="80f09-330">**Missing or invalid domain values**:</span></span>

  - <span data-ttu-id="80f09-331">contoso</span><span class="sxs-lookup"><span data-stu-id="80f09-331">contoso</span></span>
  - <span data-ttu-id="80f09-332">\*.contoso.\*</span><span class="sxs-lookup"><span data-stu-id="80f09-332">\*.contoso.\*</span></span>
  - <span data-ttu-id="80f09-333">\*.com</span><span class="sxs-lookup"><span data-stu-id="80f09-333">\*.com</span></span>
  - <span data-ttu-id="80f09-334">\*PDF</span><span class="sxs-lookup"><span data-stu-id="80f09-334">\*.pdf</span></span>

- <span data-ttu-id="80f09-335">**Поддиапные знаки для текста или без знаков интервала:**</span><span class="sxs-lookup"><span data-stu-id="80f09-335">**Wildcard on text or without spacing characters**:</span></span>

  - <span data-ttu-id="80f09-336">\*contoso.com</span><span class="sxs-lookup"><span data-stu-id="80f09-336">\*contoso.com</span></span>
  - <span data-ttu-id="80f09-337">contoso.com\*</span><span class="sxs-lookup"><span data-stu-id="80f09-337">contoso.com\*</span></span>
  - <span data-ttu-id="80f09-338">\*1.2.3.4</span><span class="sxs-lookup"><span data-stu-id="80f09-338">\*1.2.3.4</span></span>
  - <span data-ttu-id="80f09-339">1.2.3.4\*</span><span class="sxs-lookup"><span data-stu-id="80f09-339">1.2.3.4\*</span></span>
  - <span data-ttu-id="80f09-340">contoso.com/a\*</span><span class="sxs-lookup"><span data-stu-id="80f09-340">contoso.com/a\*</span></span>
  - <span data-ttu-id="80f09-341">contoso.com/ab\*</span><span class="sxs-lookup"><span data-stu-id="80f09-341">contoso.com/ab\*</span></span>

- <span data-ttu-id="80f09-342">**IP-адреса с портами:**</span><span class="sxs-lookup"><span data-stu-id="80f09-342">**IP addresses with ports**:</span></span>

  - <span data-ttu-id="80f09-343">contoso.com:443</span><span class="sxs-lookup"><span data-stu-id="80f09-343">contoso.com:443</span></span>
  - <span data-ttu-id="80f09-344">abc.contoso.com:25</span><span class="sxs-lookup"><span data-stu-id="80f09-344">abc.contoso.com:25</span></span>

- <span data-ttu-id="80f09-345">**Неописательные поддиапники:**</span><span class="sxs-lookup"><span data-stu-id="80f09-345">**Non-descriptive wildcards**:</span></span>

  - \*
  - <span data-ttu-id="80f09-346">\*.\*</span><span class="sxs-lookup"><span data-stu-id="80f09-346">\*.\*</span></span>

- <span data-ttu-id="80f09-347">**Средние подикаки:**</span><span class="sxs-lookup"><span data-stu-id="80f09-347">**Middle wildcards**:</span></span>

  - <span data-ttu-id="80f09-348">conto \* so.com</span><span class="sxs-lookup"><span data-stu-id="80f09-348">conto\*so.com</span></span>
  - <span data-ttu-id="80f09-349">conto~so.com</span><span class="sxs-lookup"><span data-stu-id="80f09-349">conto~so.com</span></span>

- <span data-ttu-id="80f09-350">**Double wildcards**</span><span class="sxs-lookup"><span data-stu-id="80f09-350">**Double wildcards**</span></span>

  - <span data-ttu-id="80f09-351">contoso.com/\*\*</span><span class="sxs-lookup"><span data-stu-id="80f09-351">contoso.com/\*\*</span></span>
  - <span data-ttu-id="80f09-352">contoso.com/\*/\*</span><span class="sxs-lookup"><span data-stu-id="80f09-352">contoso.com/\*/\*</span></span>
