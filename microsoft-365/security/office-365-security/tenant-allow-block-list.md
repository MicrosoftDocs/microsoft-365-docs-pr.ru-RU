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
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: Администраторы могут узнать, как настроить разрешаемые и блоки в списке разрешаемых и заблокированных клиентов на портале безопасности.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 250b6223ffe663e0cd950069a3c3c7827b4aa57b
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/18/2021
ms.locfileid: "50290169"
---
# <a name="manage-the-tenant-allowblock-list"></a><span data-ttu-id="40b88-103">Управление списком разрешенных и запрещенных клиентов</span><span class="sxs-lookup"><span data-stu-id="40b88-103">Manage the Tenant Allow/Block List</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="40b88-104">**Область применения**</span><span class="sxs-lookup"><span data-stu-id="40b88-104">**Applies to**</span></span>
- [<span data-ttu-id="40b88-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="40b88-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="40b88-106">Microsoft Defender для Office 365 (план 1 и план 2)</span><span class="sxs-lookup"><span data-stu-id="40b88-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="40b88-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="40b88-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

> [!NOTE]
>
> <span data-ttu-id="40b88-108">Функции, описанные в этой статье, доступны в предварительной версии, могут изменяться и доступны не во всех организациях.</span><span class="sxs-lookup"><span data-stu-id="40b88-108">The features described in this article are in Preview, are subject to change, and are not available in all organizations.</span></span>
>
> <span data-ttu-id="40b88-109">В настоящее время нельзя **настроить разрешенные** элементы в списке разрешенных и заблокированных клиентов.</span><span class="sxs-lookup"><span data-stu-id="40b88-109">You can't **configure** allowed items in the Tenant Allow/Block List at this time.</span></span>

<span data-ttu-id="40b88-110">В организациях Microsoft 365 с почтовыми ящиками в организациях Exchange Online или автономных организациях Exchange Online Protection (EOP) без почтовых ящиков Exchange Online вы можете не согласиться с решением о фильтрации EOP.</span><span class="sxs-lookup"><span data-stu-id="40b88-110">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, you might disagree with the EOP filtering verdict.</span></span> <span data-ttu-id="40b88-111">Например, хорошее сообщение может быть помечено как плохое (ложное срабатыващение), или сообщение может быть разрешено (ложный отрицательный результат).</span><span class="sxs-lookup"><span data-stu-id="40b88-111">For example, a good message might be marked as bad (a false positive), or a bad message might be allowed through (a false negative).</span></span>

<span data-ttu-id="40b88-112">Список "Разрешить или заблокировать клиента" в Центре безопасности & соответствия требованиям позволяет вручную переопределять решения фильтров Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="40b88-112">The Tenant Allow/Block List in the Security & Compliance Center gives you a way to manually override the Microsoft 365 filtering verdicts.</span></span> <span data-ttu-id="40b88-113">Список "Разрешить/заблокировать" клиента используется во время потока почты и во время нажатия пользователем.</span><span class="sxs-lookup"><span data-stu-id="40b88-113">The Tenant Allow/Block List is used during mail flow and at the time of user clicks.</span></span> <span data-ttu-id="40b88-114">Вы можете указать URL-адреса или файлы, которые необходимо всегда блокировать.</span><span class="sxs-lookup"><span data-stu-id="40b88-114">You can specify URLs or files to always block.</span></span>

<span data-ttu-id="40b88-115">В этой статье описывается настройка записей в списке разрешения и блокировки клиентов в Центре безопасности & и соответствия требованиям или в PowerShell (Exchange Online PowerShell для организаций Microsoft 365 с почтовыми ящиками в Exchange Online; автономный EOP PowerShell для организаций без почтовых ящиков Exchange Online).</span><span class="sxs-lookup"><span data-stu-id="40b88-115">This article describes how to configure entries in the Tenant Allow/Block List in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="40b88-116">Что нужно знать перед началом работы</span><span class="sxs-lookup"><span data-stu-id="40b88-116">What do you need to know before you begin?</span></span>

- <span data-ttu-id="40b88-117">Откройте Центр безопасности и соответствия требованиям по ссылке <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="40b88-117">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="40b88-118">Чтобы перейти непосредственно на **страницу "Список заблокированных** и разрешаний клиентов", используйте <https://protection.office.com/tenantAllowBlockList> .</span><span class="sxs-lookup"><span data-stu-id="40b88-118">To go directly to the **Tenant Allow/Block List** page, use <https://protection.office.com/tenantAllowBlockList>.</span></span>

- <span data-ttu-id="40b88-119">Вы указываете файлы, используя значение hash SHA256 файла.</span><span class="sxs-lookup"><span data-stu-id="40b88-119">You specify files by using the SHA256 hash value of the file.</span></span> <span data-ttu-id="40b88-120">Чтобы найти значение hash SHA256 файла в Windows, запустите следующую команду в командной подсказке:</span><span class="sxs-lookup"><span data-stu-id="40b88-120">To find the SHA256 hash value of a file in Windows, run the following command in a Command Prompt:</span></span>

  ```dos
  certutil.exe -hashfile "<Path>\<Filename>" SHA256
  ```

  <span data-ttu-id="40b88-121">Пример значения: `768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3a` .</span><span class="sxs-lookup"><span data-stu-id="40b88-121">An example value is `768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3a`.</span></span> <span data-ttu-id="40b88-122">Значения perceptual hash (pHash) не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="40b88-122">Perceptual hash (pHash) values are not supported.</span></span>

- <span data-ttu-id="40b88-123">Доступные значения URL-адресов описаны в синтаксисах [URL-адресов](#url-syntax-for-the-tenant-allowblock-list) для раздела "Список допустимого и заблокированного клиента" далее в этой статье.</span><span class="sxs-lookup"><span data-stu-id="40b88-123">The available URL values are described in the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this article.</span></span>

- <span data-ttu-id="40b88-124">Список "Разрешить/заблокировать" клиента позволяет использовать не более 500 записей для URL-адресов и 500 записей для хеш-файлов.</span><span class="sxs-lookup"><span data-stu-id="40b88-124">The Tenant Allow/Block List allows a maximum of 500 entries for URLs, and 500 entries for file hashes.</span></span>

- <span data-ttu-id="40b88-125">Запись должна быть активна в течение 15 минут.</span><span class="sxs-lookup"><span data-stu-id="40b88-125">An entry should be active within 15 minutes.</span></span>

- <span data-ttu-id="40b88-126">По умолчанию срок действия записей в списке "Разрешить или заблокировать клиента" истекает через 30 дней.</span><span class="sxs-lookup"><span data-stu-id="40b88-126">By default, entries in the Tenant Allow/Block List will expire after 30 days.</span></span> <span data-ttu-id="40b88-127">Вы можете указать дату или установить для них срок действия без срока действия.</span><span class="sxs-lookup"><span data-stu-id="40b88-127">You can specify a date or set them to never expire.</span></span>

- <span data-ttu-id="40b88-128">Сведения о том, как подключиться к Exchange Online PowerShell, см. в статье [Подключение к Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="40b88-128">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="40b88-129">Чтобы подключиться к автономному EOP PowerShell, см. раздел [Подключение к PowerShell Exchange Online Protection](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="40b88-129">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="40b88-130">Для выполнения процедур, описанных в этой статье, вам должны быть назначены разрешения в Центре безопасности и соответствия требованиям:</span><span class="sxs-lookup"><span data-stu-id="40b88-130">You need to be assigned permissions in the Security & Compliance Center before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="40b88-131">Чтобы добавить и удалить значения из списка "Разрешить или заблокировать клиента", необходимо быть членом группы ролей "Управление организацией" или "Администратор **безопасности".** </span><span class="sxs-lookup"><span data-stu-id="40b88-131">To add and remove values from the Tenant Allow/Block List, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="40b88-132">Для доступа только для чтения к списку разрешаний и блокировок  клиентов необходимо быть членом группы ролей **"Глобальное** чтение" или "Читатель безопасности".</span><span class="sxs-lookup"><span data-stu-id="40b88-132">For read-only access to the Tenant Allow/Block List, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="40b88-133">Дополнительные сведения см. в статье [Разрешения в Центре безопасности и соответствия требованиям](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="40b88-133">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

  <span data-ttu-id="40b88-134">**Примечания**.</span><span class="sxs-lookup"><span data-stu-id="40b88-134">**Notes**:</span></span>

  - <span data-ttu-id="40b88-135">Добавление пользователей в соответствующую роль Azure Active Directory в Центре безопасности Microsoft 365 предоставляет пользователям необходимые разрешения в Центре безопасности и соответствия требованиям _и_ разрешения для других функций в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="40b88-135">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="40b88-136">Дополнительные сведения см. в статье [О ролях администраторов](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="40b88-136">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  - <span data-ttu-id="40b88-137">Группа ролей **Управление организацией с правами только на просмотр** в [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) также предоставляет доступ только для чтения к этой функции.</span><span class="sxs-lookup"><span data-stu-id="40b88-137">The **View-Only Organization Management** role group in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

## <a name="use-the-security--compliance-center-to-create-url-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="40b88-138">Использование Центра безопасности & соответствия требованиям для создания записей URL-адресов в списке "Разрешить или заблокировать клиента"</span><span class="sxs-lookup"><span data-stu-id="40b88-138">Use the Security & Compliance Center to create URL entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="40b88-139">Подробные сведения о синтаксисах для [](#url-syntax-for-the-tenant-allowblock-list) записей URL-адресов см. в разделе "Синтаксис URL-адресов для списка допустимого и заблокированного клиента" далее в этой статье.</span><span class="sxs-lookup"><span data-stu-id="40b88-139">For details about the syntax for URL entries, see the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this article.</span></span>

1. <span data-ttu-id="40b88-140">В Центре безопасности & соответствия требованиям  перейдите в список "Политики управления угрозами" в списке \>  \> **"Разрешить/заблокировать клиента".**</span><span class="sxs-lookup"><span data-stu-id="40b88-140">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="40b88-141">**Убедитесь,** что вкладка "URL-адреса" выбрана на странице "Разрешить или заблокировать список клиентов" и нажмите кнопку  **"Блокировать".**</span><span class="sxs-lookup"><span data-stu-id="40b88-141">On the **Tenant Allow/Block List** page, verify that the **URLs** tab is selected, and then click **Block**</span></span>

3. <span data-ttu-id="40b88-142">Во появляется **во flyout** блокировки URL-адресов, настройте следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="40b88-142">In the **Block URLs** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="40b88-143">**Добавьте URL-адреса для блокировки:** введите один URL-адрес в строке не более 20.</span><span class="sxs-lookup"><span data-stu-id="40b88-143">**Add URLs to block**: Enter one URL per line, up to a maximum of 20.</span></span>

   - <span data-ttu-id="40b88-144">**Срок действия не истекает:** сделайте одно из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="40b88-144">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="40b88-145">Убедитесь, что параметр отключен (выключен) и используйте поле "Срок действия" для указания даты окончания срока ![ ](../../media/scc-toggle-off.png) действия записей. </span><span class="sxs-lookup"><span data-stu-id="40b88-145">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entries.</span></span>

     <span data-ttu-id="40b88-146">или</span><span class="sxs-lookup"><span data-stu-id="40b88-146">or</span></span>

     - <span data-ttu-id="40b88-147">Переместите его вправо, чтобы настроить срок действия записей:</span><span class="sxs-lookup"><span data-stu-id="40b88-147">Move the toggle to the right to configure the entries to never expire:</span></span> ![Включенный переключатель](../../media/scc-toggle-on.png)<span data-ttu-id="40b88-149">.</span><span class="sxs-lookup"><span data-stu-id="40b88-149">.</span></span>

   - <span data-ttu-id="40b88-150">**Необязательное примечание.** Введите описательное текст для записей.</span><span class="sxs-lookup"><span data-stu-id="40b88-150">**Optional note**: Enter descriptive text for the entries.</span></span>

4. <span data-ttu-id="40b88-151">Когда вы закончите, нажмите **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="40b88-151">When you're finished, click **Add**.</span></span>

## <a name="use-the-security--compliance-center-to-create-file-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="40b88-152">Использование Центра безопасности & соответствия требованиям для создания записей файлов в списке "Разрешить или заблокировать клиента"</span><span class="sxs-lookup"><span data-stu-id="40b88-152">Use the Security & Compliance Center to create file entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="40b88-153">В Центре безопасности & соответствия требованиям  перейдите в список "Политики управления угрозами" в списке \>  \> **"Разрешить/заблокировать клиента".**</span><span class="sxs-lookup"><span data-stu-id="40b88-153">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="40b88-154">На странице **"Список заблокированных и разрешаний** клиентов" выберите вкладку **"Файлы"** и нажмите кнопку **"Блокировать".**</span><span class="sxs-lookup"><span data-stu-id="40b88-154">On the **Tenant Allow/Block List** page, select **Files** tab, and then click **Block**.</span></span>

3. <span data-ttu-id="40b88-155">В поле **"Добавление файлов для блокировки"** настройте следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="40b88-155">In the **Add files to block** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="40b88-156">**Добавление хеша файла:** введите одно значение хеша SHA256 в строку до 20.</span><span class="sxs-lookup"><span data-stu-id="40b88-156">**Add file hashes**: Enter one SHA256 hash value per line, up to a maximum of 20.</span></span>

   - <span data-ttu-id="40b88-157">**Срок действия не истекает:** сделайте одно из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="40b88-157">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="40b88-158">Убедитесь, что параметр отключен (выключен) и используйте поле "Срок действия" для указания даты окончания срока ![ ](../../media/scc-toggle-off.png) действия записей. </span><span class="sxs-lookup"><span data-stu-id="40b88-158">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entries.</span></span>

     <span data-ttu-id="40b88-159">или</span><span class="sxs-lookup"><span data-stu-id="40b88-159">or</span></span>

     - <span data-ttu-id="40b88-160">Переместите его вправо, чтобы настроить срок действия записей:</span><span class="sxs-lookup"><span data-stu-id="40b88-160">Move the toggle to the right to configure the entries to never expire:</span></span> ![Включенный переключатель](../../media/scc-toggle-on.png)<span data-ttu-id="40b88-162">.</span><span class="sxs-lookup"><span data-stu-id="40b88-162">.</span></span>

   - <span data-ttu-id="40b88-163">**Необязательное примечание.** Введите описательное текст для записей.</span><span class="sxs-lookup"><span data-stu-id="40b88-163">**Optional note**: Enter descriptive text for the entries.</span></span>

4. <span data-ttu-id="40b88-164">Когда вы закончите, нажмите **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="40b88-164">When you're finished, click **Add**.</span></span>

## <a name="use-the-security--compliance-center-to-view-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="40b88-165">Просмотр запис & ей в списке "Разрешить или заблокировать" с помощью Центра безопасности и соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="40b88-165">Use the Security & Compliance Center to view entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="40b88-166">В Центре безопасности & соответствия требованиям  перейдите в список "Политики управления угрозами" в списке \>  \> **"Разрешить/заблокировать клиента".**</span><span class="sxs-lookup"><span data-stu-id="40b88-166">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="40b88-167">Выберите **вкладку "URL-адреса"** или вкладку **"Файлы".**</span><span class="sxs-lookup"><span data-stu-id="40b88-167">Select the **URLs** tab or the **Files** tab.</span></span>

<span data-ttu-id="40b88-168">Щелкните следующие заголовки столбцов, чтобы отсортировать их по возрастанию или убыванию:</span><span class="sxs-lookup"><span data-stu-id="40b88-168">Click on the following column headings to sort in ascending or descending order:</span></span>

- <span data-ttu-id="40b88-169">**Значение:** URL-адрес или hash файла.</span><span class="sxs-lookup"><span data-stu-id="40b88-169">**Value**: The URL or the file hash.</span></span>
- <span data-ttu-id="40b88-170">**Дата последнего обновления**</span><span class="sxs-lookup"><span data-stu-id="40b88-170">**Last updated date**</span></span>
- <span data-ttu-id="40b88-171">**Дата окончания срока действия**</span><span class="sxs-lookup"><span data-stu-id="40b88-171">**Expiration date**</span></span>
- <span data-ttu-id="40b88-172">**Примечание**</span><span class="sxs-lookup"><span data-stu-id="40b88-172">**Note**</span></span>

<span data-ttu-id="40b88-173">Нажмите **кнопку**"Поиск", введите все или часть значения, а затем нажмите ввод, чтобы найти определенное значение.</span><span class="sxs-lookup"><span data-stu-id="40b88-173">Click **Search**, enter all or part of a value, and then press ENTER to find a specific value.</span></span> <span data-ttu-id="40b88-174">По завершению нажмите кнопку **"Очистить значок** ![ "Очистить поиск". ](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif)</span><span class="sxs-lookup"><span data-stu-id="40b88-174">When you're finished, click **Clear search** ![Clear search icon](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif).</span></span>

<span data-ttu-id="40b88-175">Щелкните **"Фильтр"**.</span><span class="sxs-lookup"><span data-stu-id="40b88-175">Click **Filter**.</span></span> <span data-ttu-id="40b88-176">Во появляется **во** flyout фильтра, настройте любой из следующих параметров:</span><span class="sxs-lookup"><span data-stu-id="40b88-176">In the **Filter** flyout that appears, configure any of the following settings:</span></span>

- <span data-ttu-id="40b88-177">**Никогда не истекает:** выключите: ![ отключите ](../../media/scc-toggle-off.png) или включите: ![ включите. ](../../media/scc-toggle-on.png)</span><span class="sxs-lookup"><span data-stu-id="40b88-177">**Never expire**: Select off: ![Toggle off](../../media/scc-toggle-off.png) or on: ![Toggle on](../../media/scc-toggle-on.png).</span></span>

- <span data-ttu-id="40b88-178">**Last updated**: Select a start date (**From),** an end date (**To**) or both.</span><span class="sxs-lookup"><span data-stu-id="40b88-178">**Last updated**: Select a start date (**From**), an end date (**To**) or both.</span></span>

- <span data-ttu-id="40b88-179">**Дата окончания** срока действия: выберите даты начала **(от),** даты окончания (**To)** или и того, и другого.</span><span class="sxs-lookup"><span data-stu-id="40b88-179">**Expiration date**: Select a start date (**From**), an end date (**To**) or both.</span></span>

<span data-ttu-id="40b88-180">По завершению нажмите кнопку **"Применить".**</span><span class="sxs-lookup"><span data-stu-id="40b88-180">When you're finished, click **Apply**.</span></span>

<span data-ttu-id="40b88-181">Чтобы очистить существующие фильтры, щелкните **"Фильтр",** а затем в окле "Фильтр" щелкните **"Очистить фильтры".** </span><span class="sxs-lookup"><span data-stu-id="40b88-181">To clear existing filters, click **Filter**, and in the **Filter** flyout that appears, click **Clear filters**.</span></span>

## <a name="use-the-security--compliance-center-to-modify-block-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="40b88-182">Использование Центра безопасности & соответствия требованиям для изменения записей блокировки в списке "Разрешить или заблокировать клиента"</span><span class="sxs-lookup"><span data-stu-id="40b88-182">Use the Security & Compliance Center to modify block entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="40b88-183">В записи нельзя изменить существующий заблокированный URL-адрес или значения файлов.</span><span class="sxs-lookup"><span data-stu-id="40b88-183">You can't modify the existing blocked URL or file values within an entry.</span></span> <span data-ttu-id="40b88-184">Чтобы изменить эти значения, необходимо удалить и повторно создать запись.</span><span class="sxs-lookup"><span data-stu-id="40b88-184">To modify these values, you need to delete and recreate the entry.</span></span>

1. <span data-ttu-id="40b88-185">В Центре безопасности & соответствия требованиям  перейдите в список "Политики управления угрозами" в списке \>  \> **"Разрешить/заблокировать клиента".**</span><span class="sxs-lookup"><span data-stu-id="40b88-185">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="40b88-186">Выберите **вкладку "URL-адреса"** или вкладку **"Файлы".**</span><span class="sxs-lookup"><span data-stu-id="40b88-186">Select the **URLs** tab or the **Files** tab.</span></span>

3. <span data-ttu-id="40b88-187">Выберите блок записи, которую нужно изменить, и нажмите значок  ![ ](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) редактирования.</span><span class="sxs-lookup"><span data-stu-id="40b88-187">Select the block entry that you want to modify, and then click **Edit** ![Edit icon](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png).</span></span>

4. <span data-ttu-id="40b88-188">Во появляются во flyout, настройте следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="40b88-188">In the flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="40b88-189">**Срок действия не истекает:** сделайте одно из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="40b88-189">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="40b88-190">Убедитесь, что параметр отключен (выключен) и используйте поле "Срок действия" для указания даты окончания ![ ](../../media/scc-toggle-off.png) срока действия записи. </span><span class="sxs-lookup"><span data-stu-id="40b88-190">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entry.</span></span>

     <span data-ttu-id="40b88-191">или</span><span class="sxs-lookup"><span data-stu-id="40b88-191">or</span></span>

     - <span data-ttu-id="40b88-192">Переместите его вправо, чтобы настроить срок действия записи:</span><span class="sxs-lookup"><span data-stu-id="40b88-192">Move the toggle to the right to configure the entry to never expire:</span></span> ![Включенный переключатель](../../media/scc-toggle-on.png)<span data-ttu-id="40b88-194">.</span><span class="sxs-lookup"><span data-stu-id="40b88-194">.</span></span>

   - <span data-ttu-id="40b88-195">**Необязательное примечание.** Введите описательное текст для записи.</span><span class="sxs-lookup"><span data-stu-id="40b88-195">**Optional note**: Enter descriptive text for the entry.</span></span>

5. <span data-ttu-id="40b88-196">По завершении нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="40b88-196">When you're finished, click **Save**.</span></span>

## <a name="use-the-security--compliance-center-to-remove-block-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="40b88-197">Использование Центра безопасности & соответствия требованиям для удаления записей блокировки из списка "Разрешить или заблокировать клиента"</span><span class="sxs-lookup"><span data-stu-id="40b88-197">Use the Security & Compliance Center to remove block entries from the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="40b88-198">В Центре безопасности & соответствия требованиям  перейдите в список "Политики управления угрозами" в списке \>  \> **"Разрешить/заблокировать клиента".**</span><span class="sxs-lookup"><span data-stu-id="40b88-198">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="40b88-199">Выберите **вкладку "URL-адреса"** или вкладку **"Файлы".**</span><span class="sxs-lookup"><span data-stu-id="40b88-199">Select the **URLs** tab or the **Files** tab.</span></span>

3. <span data-ttu-id="40b88-200">Выберите блок записи, которую нужно удалить, и нажмите значок **"Удалить** ![ ](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png) удалить".</span><span class="sxs-lookup"><span data-stu-id="40b88-200">Select the block entry that you want to remove, and then click **Delete** ![Delete icon](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png).</span></span>

4. <span data-ttu-id="40b88-201">В появится диалоговое окно предупреждения, нажмите кнопку **"Удалить".**</span><span class="sxs-lookup"><span data-stu-id="40b88-201">In the warning dialog that appears, click **Delete**.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-the-tenant-allowblock-list"></a><span data-ttu-id="40b88-202">Использование Exchange Online PowerShell или автономный EOP PowerShell для настройки списка "Разрешить или заблокировать клиента"</span><span class="sxs-lookup"><span data-stu-id="40b88-202">Use Exchange Online PowerShell or standalone EOP PowerShell to configure the Tenant Allow/Block List</span></span>

### <a name="use-powershell-to-add-block-entries-to-the-tenant-allowblock-list"></a><span data-ttu-id="40b88-203">Добавление записей блокировки в список "Разрешить или заблокировать" с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="40b88-203">Use PowerShell to add block entries to the Tenant Allow/Block List</span></span>

<span data-ttu-id="40b88-204">Чтобы добавить блоковые записи в список "Разрешить или заблокировать клиента", используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="40b88-204">To add block entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
New-TenantAllowBlockListItems -ListType <Url | FileHash> -Block -Entries <String[]> [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

<span data-ttu-id="40b88-205">В этом примере добавляется запись URL-адреса блока для contoso.com и всех поддоменов (например, contoso.com, www.contoso.com и xyz.abc.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="40b88-205">This example adds a block URL entry for contoso.com and all subdomains (for example, contoso.com, www.contoso.com, and xyz.abc.contoso.com).</span></span> <span data-ttu-id="40b88-206">Так как мы не использовали параметры ExpirationDate или NoExpiration, срок действия записи истекает через 30 дней.</span><span class="sxs-lookup"><span data-stu-id="40b88-206">Because we didn't use the ExpirationDate or NoExpiration parameters, the entry expires after 30 days.</span></span>

```powershell
New-TenantAllowBlockListItem -ListType Url -Block -Entries ~contoso.com
```

<span data-ttu-id="40b88-207">В этом примере добавляется запись заблокированного файла для указанных файлов, срок действия которых не истекает.</span><span class="sxs-lookup"><span data-stu-id="40b88-207">This example adds a block file entry for the specified files that never expires.</span></span>

```powershell
New-TenantAllowBlockListItem -ListType FileHash -Block -Entries "768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3","2c0a35409ff0873cfa28b70b8224e9aca2362241c1f0ed6f622fef8d4722fd9a" -NoExpiration
```

<span data-ttu-id="40b88-208">Подробные сведения о синтаксисе и параметрах см. в описании [New-TenantAllowBlockListItems.](https://docs.microsoft.com/powershell/module/exchange/new-tenantallowblocklistitems)</span><span class="sxs-lookup"><span data-stu-id="40b88-208">For detailed syntax and parameter information, see [New-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/new-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-view-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="40b88-209">Использование PowerShell для просмотра записей в списке "Разрешить или заблокировать клиента"</span><span class="sxs-lookup"><span data-stu-id="40b88-209">Use PowerShell to view entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="40b88-210">Чтобы просмотреть записи в списке "Разрешить или заблокировать клиента", используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="40b88-210">To view entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType <Url | FileHash> [-Entry <URLValue | FileHashValue>] [-Block] [-ExpirationDate <DateTime>] [-NoExpiration]
```

<span data-ttu-id="40b88-211">В этом примере возвращаются все заблокированные URL-адреса.</span><span class="sxs-lookup"><span data-stu-id="40b88-211">This example returns all blocked URLs.</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType Url -Block
```

<span data-ttu-id="40b88-212">В этом примере возвращаются сведения об указанном значении hash файла.</span><span class="sxs-lookup"><span data-stu-id="40b88-212">This example returns information for the specified file hash value.</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType FileHash -Entry "9f86d081884c7d659a2feaa0c55ad015a3bf4f1b2b0b822cd15d6c15b0f00a08"
```

<span data-ttu-id="40b88-213">Подробные сведения о синтаксисе и параметрах см. в описании [Get-TenantAllowBlockListItems.](https://docs.microsoft.com/powershell/module/exchange/get-tenantallowblocklistitems)</span><span class="sxs-lookup"><span data-stu-id="40b88-213">For detailed syntax and parameter information, see [Get-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/get-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-modify-block-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="40b88-214">Использование PowerShell для изменения записей блокировки в списке "Разрешить или заблокировать клиента"</span><span class="sxs-lookup"><span data-stu-id="40b88-214">Use PowerShell to modify block entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="40b88-215">Нельзя изменить существующий URL-адрес или значения файлов в блоке записи.</span><span class="sxs-lookup"><span data-stu-id="40b88-215">You can't modify the existing URL or file values within a block entry.</span></span> <span data-ttu-id="40b88-216">Чтобы изменить эти значения, необходимо удалить и повторно создать запись.</span><span class="sxs-lookup"><span data-stu-id="40b88-216">To modify these values, you need to delete and recreate the entry.</span></span>

<span data-ttu-id="40b88-217">Чтобы изменить записи блокировки в списке "Разрешить или заблокировать клиента", используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="40b88-217">To modify block entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType <Url | FileHash> -Ids <"Id1","Id2",..."IdN"> [-Block] [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

<span data-ttu-id="40b88-218">В этом примере изменяется срок действия указанной записи блока.</span><span class="sxs-lookup"><span data-stu-id="40b88-218">This example changes the expiration date of the specified block entry.</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -ExpirationDate (Get-Date "5/30/2020 9:30 AM").ToUniversalTime()
```

<span data-ttu-id="40b88-219">Подробные сведения о синтаксисе и параметрах см. в описании [Set-TenantAllowBlockListItems.](https://docs.microsoft.com/powershell/module/exchange/set-tenantallowblocklistitems)</span><span class="sxs-lookup"><span data-stu-id="40b88-219">For detailed syntax and parameter information, see [Set-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/set-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-remove-block-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="40b88-220">Использование PowerShell для удаления записей блокировки из списка "Разрешить или заблокировать клиента"</span><span class="sxs-lookup"><span data-stu-id="40b88-220">Use PowerShell to remove block entries from the Tenant Allow/Block List</span></span>

<span data-ttu-id="40b88-221">Чтобы удалить блоковые записи из списка "Разрешить или заблокировать клиента", используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="40b88-221">To remove block entries from the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType <Url | FileHash> -Ids <"Id1","Id2",..."IdN">
```

<span data-ttu-id="40b88-222">В этом примере из списка "Разрешить/заблокировать" удаляется указанная запись URL-адреса блокировки.</span><span class="sxs-lookup"><span data-stu-id="40b88-222">This example removes the specified block URL entry from the Tenant Allow/Block List.</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSPAAAA0"
```

<span data-ttu-id="40b88-223">Подробные сведения о синтаксисе и параметрах см. в описании [remove-TenantAllowBlockListItems.](https://docs.microsoft.com/powershell/module/exchange/remove-tenantallowblocklistitems)</span><span class="sxs-lookup"><span data-stu-id="40b88-223">For detailed syntax and parameter information, see [Remove-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/remove-tenantallowblocklistitems).</span></span>

## <a name="url-syntax-for-the-tenant-allowblock-list"></a><span data-ttu-id="40b88-224">Синтаксис URL-адресов для списка допустимого или заблокированного клиента</span><span class="sxs-lookup"><span data-stu-id="40b88-224">URL syntax for the Tenant Allow/Block List</span></span>

- <span data-ttu-id="40b88-225">Ip4v- и IPv6-адреса разрешены, а порты TCP/UDP — нет.</span><span class="sxs-lookup"><span data-stu-id="40b88-225">IP4v and IPv6 addresses are allowed, but TCP/UDP ports are not.</span></span>

- <span data-ttu-id="40b88-226">Расширения имен файлов запрещены (например, test.pdf).</span><span class="sxs-lookup"><span data-stu-id="40b88-226">Filename extensions are not allowed (for example, test.pdf).</span></span>

- <span data-ttu-id="40b88-227">Юникод не поддерживается, но это punycode.</span><span class="sxs-lookup"><span data-stu-id="40b88-227">Unicode is not supported, but Punycode is.</span></span>

- <span data-ttu-id="40b88-228">Имена хостов разрешены, если истинны все следующие утверждения:</span><span class="sxs-lookup"><span data-stu-id="40b88-228">Hostnames are allowed if all of the following statements are true:</span></span>
  - <span data-ttu-id="40b88-229">Имя хоста содержит период.</span><span class="sxs-lookup"><span data-stu-id="40b88-229">The hostname contains a period.</span></span>
  - <span data-ttu-id="40b88-230">Слева от периода находится по крайней мере один символ.</span><span class="sxs-lookup"><span data-stu-id="40b88-230">There is at least one character to the left of the period.</span></span>
  - <span data-ttu-id="40b88-231">Справа от периода есть по крайней мере два символа.</span><span class="sxs-lookup"><span data-stu-id="40b88-231">There are at least two characters to the right of the period.</span></span>

  <span data-ttu-id="40b88-232">Например, `t.co` разрешено или `.com` `contoso.` запрещено.</span><span class="sxs-lookup"><span data-stu-id="40b88-232">For example, `t.co` is allowed; `.com` or `contoso.` are not allowed.</span></span>

- <span data-ttu-id="40b88-233">Подпазки не подразумеваются.</span><span class="sxs-lookup"><span data-stu-id="40b88-233">Subpaths are not implied.</span></span>

  <span data-ttu-id="40b88-234">Например, `contoso.com` не включает `contoso.com/a` .</span><span class="sxs-lookup"><span data-stu-id="40b88-234">For example, `contoso.com` does not include `contoso.com/a`.</span></span>

- <span data-ttu-id="40b88-235">В следующих сценариях допускаются поддиаными знаками (\*):</span><span class="sxs-lookup"><span data-stu-id="40b88-235">Wildcards (\*) are allowed in the following scenarios:</span></span>

  - <span data-ttu-id="40b88-236">Чтобы указать поддомен, необходимо следовать за левый поддиакон.</span><span class="sxs-lookup"><span data-stu-id="40b88-236">A left wildcard must be followed by a period to specify a subdomain.</span></span>

    <span data-ttu-id="40b88-237">Например, `*.contoso.com` разрешено; `*contoso.com` запрещено.</span><span class="sxs-lookup"><span data-stu-id="40b88-237">For example, `*.contoso.com` is allowed; `*contoso.com` is not allowed.</span></span>

  - <span data-ttu-id="40b88-238">Для указания пути правый поддиаптер должен следовать косой черты (/).</span><span class="sxs-lookup"><span data-stu-id="40b88-238">A right wildcard must follow a forward slash (/) to specify a path.</span></span>

    <span data-ttu-id="40b88-239">Например, `contoso.com/*` разрешено или `contoso.com*` `contoso.com/ab*` запрещено.</span><span class="sxs-lookup"><span data-stu-id="40b88-239">For example, `contoso.com/*` is allowed; `contoso.com*` or `contoso.com/ab*` are not allowed.</span></span>

  - <span data-ttu-id="40b88-240">Поддиапатический знак не подразумевает все подпазки.</span><span class="sxs-lookup"><span data-stu-id="40b88-240">All subpaths are not implied by a right wildcard.</span></span>

    <span data-ttu-id="40b88-241">Например, `contoso.com/*` не включает `contoso.com/a` .</span><span class="sxs-lookup"><span data-stu-id="40b88-241">For example, `contoso.com/*` does not include `contoso.com/a`.</span></span>

  - <span data-ttu-id="40b88-242">`*.com*` является недопустимым (не является разрешаемым доменом, а правый поддиапный знак не следует косой черте).</span><span class="sxs-lookup"><span data-stu-id="40b88-242">`*.com*` is invalid (not a resolvable domain and the right wildcard does not follow a forward slash).</span></span>

  - <span data-ttu-id="40b88-243">Поддиапные знаки не разрешены в IP-адресах.</span><span class="sxs-lookup"><span data-stu-id="40b88-243">Wildcards are not allowed in IP addresses.</span></span>

- <span data-ttu-id="40b88-244">Символ тильды (~) доступен в следующих сценариях:</span><span class="sxs-lookup"><span data-stu-id="40b88-244">The tilde (~) character is available in the following scenarios:</span></span>

  - <span data-ttu-id="40b88-245">Левая тильда подразумевает домен и все поддомены.</span><span class="sxs-lookup"><span data-stu-id="40b88-245">A left tilde implies a domain and all subdomains.</span></span>

    <span data-ttu-id="40b88-246">Например, `~contoso.com` включает `contoso.com` и `*.contoso.com` .</span><span class="sxs-lookup"><span data-stu-id="40b88-246">For example `~contoso.com` includes `contoso.com` and `*.contoso.com`.</span></span>

- <span data-ttu-id="40b88-247">Url-адреса, содержащие протоколы (например, , или ) не удастся, так как `http://` `https://` `ftp://` url-записи применяются к всем протоколам.</span><span class="sxs-lookup"><span data-stu-id="40b88-247">URL entries that contain protocols (for example, `http://`, `https://`, or `ftp://`) will fail, because URL entries apply to all protocols.</span></span>

- <span data-ttu-id="40b88-248">Имя пользователя или пароль не поддерживаются и не требуются.</span><span class="sxs-lookup"><span data-stu-id="40b88-248">A username or password aren't supported or required.</span></span>

- <span data-ttu-id="40b88-249">Кавычка (' или ") являются недопустимыми символами.</span><span class="sxs-lookup"><span data-stu-id="40b88-249">Quotes (' or ") are invalid characters.</span></span>

- <span data-ttu-id="40b88-250">URL-адрес должен включать все перенаправления по возможности.</span><span class="sxs-lookup"><span data-stu-id="40b88-250">A URL should include all redirects where possible.</span></span>

### <a name="url-entry-scenarios"></a><span data-ttu-id="40b88-251">Сценарии ввода URL-адреса</span><span class="sxs-lookup"><span data-stu-id="40b88-251">URL entry scenarios</span></span>

<span data-ttu-id="40b88-252">Допустимые url-адреса и их результаты описаны в следующих разделах.</span><span class="sxs-lookup"><span data-stu-id="40b88-252">Valid URL entries and their results are described in the following sections.</span></span>

#### <a name="scenario-no-wildcards"></a><span data-ttu-id="40b88-253">Сценарий: поддиаными знаками не является</span><span class="sxs-lookup"><span data-stu-id="40b88-253">Scenario: No wildcards</span></span>

<span data-ttu-id="40b88-254">**Запись:**`contoso.com`</span><span class="sxs-lookup"><span data-stu-id="40b88-254">**Entry**: `contoso.com`</span></span>

- <span data-ttu-id="40b88-255">**Разрешить соответствие**: contoso.com</span><span class="sxs-lookup"><span data-stu-id="40b88-255">**Allow match**: contoso.com</span></span>

- <span data-ttu-id="40b88-256">**Allow not matched**:</span><span class="sxs-lookup"><span data-stu-id="40b88-256">**Allow not matched**:</span></span>

  - <span data-ttu-id="40b88-257">abc-contoso.com</span><span class="sxs-lookup"><span data-stu-id="40b88-257">abc-contoso.com</span></span>
  - <span data-ttu-id="40b88-258">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="40b88-258">contoso.com/a</span></span>
  - <span data-ttu-id="40b88-259">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="40b88-259">payroll.contoso.com</span></span>
  - <span data-ttu-id="40b88-260">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="40b88-260">test.com/contoso.com</span></span>
  - <span data-ttu-id="40b88-261">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="40b88-261">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="40b88-262">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="40b88-262">www.contoso.com</span></span>
  - <span data-ttu-id="40b88-263">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="40b88-263">www.contoso.com/q=a@contoso.com</span></span>

- <span data-ttu-id="40b88-264">**Блокировка совпадения:**</span><span class="sxs-lookup"><span data-stu-id="40b88-264">**Block match**:</span></span>

  - <span data-ttu-id="40b88-265">contoso.com</span><span class="sxs-lookup"><span data-stu-id="40b88-265">contoso.com</span></span>
  - <span data-ttu-id="40b88-266">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="40b88-266">contoso.com/a</span></span>
  - <span data-ttu-id="40b88-267">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="40b88-267">payroll.contoso.com</span></span>
  - <span data-ttu-id="40b88-268">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="40b88-268">test.com/contoso.com</span></span>
  - <span data-ttu-id="40b88-269">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="40b88-269">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="40b88-270">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="40b88-270">www.contoso.com</span></span>
  - <span data-ttu-id="40b88-271">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="40b88-271">www.contoso.com/q=a@contoso.com</span></span>

- <span data-ttu-id="40b88-272">**Block not matched**: abc-contoso.com</span><span class="sxs-lookup"><span data-stu-id="40b88-272">**Block not matched**: abc-contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain"></a><span data-ttu-id="40b88-273">Сценарий: левый поддомен (поддомен)</span><span class="sxs-lookup"><span data-stu-id="40b88-273">Scenario: Left wildcard (subdomain)</span></span>

<span data-ttu-id="40b88-274">**Запись:**`*.contoso.com`</span><span class="sxs-lookup"><span data-stu-id="40b88-274">**Entry**: `*.contoso.com`</span></span>

- <span data-ttu-id="40b88-275">**Разрешить соответствие и** **блокировку совпадений:**</span><span class="sxs-lookup"><span data-stu-id="40b88-275">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="40b88-276">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="40b88-276">www.contoso.com</span></span>
  - <span data-ttu-id="40b88-277">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="40b88-277">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="40b88-278">**Allow not matched** and **Block not matched**:</span><span class="sxs-lookup"><span data-stu-id="40b88-278">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="40b88-279">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="40b88-279">123contoso.com</span></span>
  - <span data-ttu-id="40b88-280">contoso.com</span><span class="sxs-lookup"><span data-stu-id="40b88-280">contoso.com</span></span>
  - <span data-ttu-id="40b88-281">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="40b88-281">test.com/contoso.com</span></span>
  - <span data-ttu-id="40b88-282">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="40b88-282">www.contoso.com/abc</span></span>

#### <a name="scenario-right-wildcard-at-top-of-path"></a><span data-ttu-id="40b88-283">Сценарий: правый под wildcard в верхней части пути</span><span class="sxs-lookup"><span data-stu-id="40b88-283">Scenario: Right wildcard at top of path</span></span>

<span data-ttu-id="40b88-284">**Запись:**`contoso.com/a/*`</span><span class="sxs-lookup"><span data-stu-id="40b88-284">**Entry**: `contoso.com/a/*`</span></span>

- <span data-ttu-id="40b88-285">**Разрешить соответствие и** **блокировку совпадений:**</span><span class="sxs-lookup"><span data-stu-id="40b88-285">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="40b88-286">contoso.com/a/b</span><span class="sxs-lookup"><span data-stu-id="40b88-286">contoso.com/a/b</span></span>
  - <span data-ttu-id="40b88-287">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="40b88-287">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="40b88-288">contoso.com/a/?q=joe@t.com</span><span class="sxs-lookup"><span data-stu-id="40b88-288">contoso.com/a/?q=joe@t.com</span></span>

- <span data-ttu-id="40b88-289">**Allow not matched** and **Block not matched**:</span><span class="sxs-lookup"><span data-stu-id="40b88-289">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="40b88-290">contoso.com</span><span class="sxs-lookup"><span data-stu-id="40b88-290">contoso.com</span></span>
  - <span data-ttu-id="40b88-291">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="40b88-291">contoso.com/a</span></span>
  - <span data-ttu-id="40b88-292">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="40b88-292">www.contoso.com</span></span>
  - <span data-ttu-id="40b88-293">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="40b88-293">www.contoso.com/q=a@contoso.com</span></span>

#### <a name="scenario-left-tilde"></a><span data-ttu-id="40b88-294">Сценарий: левая тильда</span><span class="sxs-lookup"><span data-stu-id="40b88-294">Scenario: Left tilde</span></span>

<span data-ttu-id="40b88-295">**Запись:**`~contoso.com`</span><span class="sxs-lookup"><span data-stu-id="40b88-295">**Entry**: `~contoso.com`</span></span>

- <span data-ttu-id="40b88-296">**Разрешить соответствие и** **блокировку совпадений:**</span><span class="sxs-lookup"><span data-stu-id="40b88-296">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="40b88-297">contoso.com</span><span class="sxs-lookup"><span data-stu-id="40b88-297">contoso.com</span></span>
  - <span data-ttu-id="40b88-298">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="40b88-298">www.contoso.com</span></span>
  - <span data-ttu-id="40b88-299">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="40b88-299">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="40b88-300">**Allow not matched** and **Block not matched**:</span><span class="sxs-lookup"><span data-stu-id="40b88-300">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="40b88-301">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="40b88-301">123contoso.com</span></span>
  - <span data-ttu-id="40b88-302">contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="40b88-302">contoso.com/abc</span></span>
  - <span data-ttu-id="40b88-303">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="40b88-303">www.contoso.com/abc</span></span>

#### <a name="scenario-right-wildcard-suffix"></a><span data-ttu-id="40b88-304">Сценарий: правый суффикс с подстановными знаками</span><span class="sxs-lookup"><span data-stu-id="40b88-304">Scenario: Right wildcard suffix</span></span>

<span data-ttu-id="40b88-305">**Запись:**`contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="40b88-305">**Entry**: `contoso.com/*`</span></span>

- <span data-ttu-id="40b88-306">**Разрешить соответствие и** **блокировку совпадений:**</span><span class="sxs-lookup"><span data-stu-id="40b88-306">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="40b88-307">contoso.com/?q=whatever@fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="40b88-307">contoso.com/?q=whatever@fabrikam.com</span></span>
  - <span data-ttu-id="40b88-308">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="40b88-308">contoso.com/a</span></span>
  - <span data-ttu-id="40b88-309">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="40b88-309">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="40b88-310">contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="40b88-310">contoso.com/ab</span></span>
  - <span data-ttu-id="40b88-311">contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="40b88-311">contoso.com/b</span></span>
  - <span data-ttu-id="40b88-312">contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="40b88-312">contoso.com/b/a/c</span></span>
  - <span data-ttu-id="40b88-313">contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="40b88-313">contoso.com/ba</span></span>

- <span data-ttu-id="40b88-314">**Allow not matched** and **Block not matched**: contoso.com</span><span class="sxs-lookup"><span data-stu-id="40b88-314">**Allow not matched** and **Block not matched**: contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain-and-right-wildcard-suffix"></a><span data-ttu-id="40b88-315">Сценарий: левый поддомен и правый суффикс подстановки</span><span class="sxs-lookup"><span data-stu-id="40b88-315">Scenario: Left wildcard subdomain and right wildcard suffix</span></span>

<span data-ttu-id="40b88-316">**Запись:**`*.contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="40b88-316">**Entry**: `*.contoso.com/*`</span></span>

- <span data-ttu-id="40b88-317">**Разрешить соответствие и** **блокировку совпадений:**</span><span class="sxs-lookup"><span data-stu-id="40b88-317">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="40b88-318">abc.contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="40b88-318">abc.contoso.com/ab</span></span>
  - <span data-ttu-id="40b88-319">abc.xyz.contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="40b88-319">abc.xyz.contoso.com/a/b/c</span></span>
  - <span data-ttu-id="40b88-320">www.contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="40b88-320">www.contoso.com/a</span></span>
  - <span data-ttu-id="40b88-321">www.contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="40b88-321">www.contoso.com/b/a/c</span></span>
  - <span data-ttu-id="40b88-322">xyz.contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="40b88-322">xyz.contoso.com/ba</span></span>

- <span data-ttu-id="40b88-323">**Allow not matched** and **Block not matched**: contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="40b88-323">**Allow not matched** and **Block not matched**: contoso.com/b</span></span>

#### <a name="scenario-left-and-right-tilde"></a><span data-ttu-id="40b88-324">Сценарий: левая и правая тильда</span><span class="sxs-lookup"><span data-stu-id="40b88-324">Scenario: Left and right tilde</span></span>

<span data-ttu-id="40b88-325">**Запись:**`~contoso.com~`</span><span class="sxs-lookup"><span data-stu-id="40b88-325">**Entry**: `~contoso.com~`</span></span>

- <span data-ttu-id="40b88-326">**Разрешить соответствие и** **блокировку совпадений:**</span><span class="sxs-lookup"><span data-stu-id="40b88-326">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="40b88-327">contoso.com</span><span class="sxs-lookup"><span data-stu-id="40b88-327">contoso.com</span></span>
  - <span data-ttu-id="40b88-328">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="40b88-328">contoso.com/a</span></span>
  - <span data-ttu-id="40b88-329">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="40b88-329">www.contoso.com</span></span>
  - <span data-ttu-id="40b88-330">www.contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="40b88-330">www.contoso.com/b</span></span>
  - <span data-ttu-id="40b88-331">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="40b88-331">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="40b88-332">**Allow not matched** and **Block not matched**:</span><span class="sxs-lookup"><span data-stu-id="40b88-332">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="40b88-333">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="40b88-333">123contoso.com</span></span>
  - <span data-ttu-id="40b88-334">contoso.org</span><span class="sxs-lookup"><span data-stu-id="40b88-334">contoso.org</span></span>

#### <a name="scenario-ip-address"></a><span data-ttu-id="40b88-335">Сценарий: IP-адрес</span><span class="sxs-lookup"><span data-stu-id="40b88-335">Scenario: IP address</span></span>

<span data-ttu-id="40b88-336">**Запись:**`1.2.3.4`</span><span class="sxs-lookup"><span data-stu-id="40b88-336">**Entry**: `1.2.3.4`</span></span>

- <span data-ttu-id="40b88-337">**Разрешить соответствие** и **блокировку**: 1.2.3.4</span><span class="sxs-lookup"><span data-stu-id="40b88-337">**Allow match** and **Block match**: 1.2.3.4</span></span>

- <span data-ttu-id="40b88-338">**Allow not matched** and **Block not matched**:</span><span class="sxs-lookup"><span data-stu-id="40b88-338">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="40b88-339">1.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="40b88-339">1.2.3.4/a</span></span>
  - <span data-ttu-id="40b88-340">11.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="40b88-340">11.2.3.4/a</span></span>

#### <a name="ip-address-with-right-wildcard"></a><span data-ttu-id="40b88-341">IP-адрес с правильным поддиапным знаком</span><span class="sxs-lookup"><span data-stu-id="40b88-341">IP address with right wildcard</span></span>

<span data-ttu-id="40b88-342">**Запись:**`1.2.3.4/*`</span><span class="sxs-lookup"><span data-stu-id="40b88-342">**Entry**: `1.2.3.4/*`</span></span>

- <span data-ttu-id="40b88-343">**Разрешить соответствие и** **блокировку совпадений:**</span><span class="sxs-lookup"><span data-stu-id="40b88-343">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="40b88-344">1.2.3.4/b</span><span class="sxs-lookup"><span data-stu-id="40b88-344">1.2.3.4/b</span></span>
  - <span data-ttu-id="40b88-345">1.2.3.4/baaaa</span><span class="sxs-lookup"><span data-stu-id="40b88-345">1.2.3.4/baaaa</span></span>

### <a name="examples-of-invalid-entries"></a><span data-ttu-id="40b88-346">Примеры недопустимых записей</span><span class="sxs-lookup"><span data-stu-id="40b88-346">Examples of invalid entries</span></span>

<span data-ttu-id="40b88-347">Недопустимы следующие записи:</span><span class="sxs-lookup"><span data-stu-id="40b88-347">The following entries are invalid:</span></span>

- <span data-ttu-id="40b88-348">**Отсутствуют или недопустимые значения домена:**</span><span class="sxs-lookup"><span data-stu-id="40b88-348">**Missing or invalid domain values**:</span></span>

  - <span data-ttu-id="40b88-349">contoso</span><span class="sxs-lookup"><span data-stu-id="40b88-349">contoso</span></span>
  - <span data-ttu-id="40b88-350">\*.contoso.\*</span><span class="sxs-lookup"><span data-stu-id="40b88-350">\*.contoso.\*</span></span>
  - <span data-ttu-id="40b88-351">\*.com</span><span class="sxs-lookup"><span data-stu-id="40b88-351">\*.com</span></span>
  - <span data-ttu-id="40b88-352">\*PDF</span><span class="sxs-lookup"><span data-stu-id="40b88-352">\*.pdf</span></span>

- <span data-ttu-id="40b88-353">**Поддиапные знаки для текста или без знаков интервала:**</span><span class="sxs-lookup"><span data-stu-id="40b88-353">**Wildcard on text or without spacing characters**:</span></span>

  - <span data-ttu-id="40b88-354">\*contoso.com</span><span class="sxs-lookup"><span data-stu-id="40b88-354">\*contoso.com</span></span>
  - <span data-ttu-id="40b88-355">contoso.com\*</span><span class="sxs-lookup"><span data-stu-id="40b88-355">contoso.com\*</span></span>
  - <span data-ttu-id="40b88-356">\*1.2.3.4</span><span class="sxs-lookup"><span data-stu-id="40b88-356">\*1.2.3.4</span></span>
  - <span data-ttu-id="40b88-357">1.2.3.4\*</span><span class="sxs-lookup"><span data-stu-id="40b88-357">1.2.3.4\*</span></span>
  - <span data-ttu-id="40b88-358">contoso.com/a\*</span><span class="sxs-lookup"><span data-stu-id="40b88-358">contoso.com/a\*</span></span>
  - <span data-ttu-id="40b88-359">contoso.com/ab\*</span><span class="sxs-lookup"><span data-stu-id="40b88-359">contoso.com/ab\*</span></span>

- <span data-ttu-id="40b88-360">**IP-адреса с портами:**</span><span class="sxs-lookup"><span data-stu-id="40b88-360">**IP addresses with ports**:</span></span>

  - <span data-ttu-id="40b88-361">contoso.com:443</span><span class="sxs-lookup"><span data-stu-id="40b88-361">contoso.com:443</span></span>
  - <span data-ttu-id="40b88-362">abc.contoso.com:25</span><span class="sxs-lookup"><span data-stu-id="40b88-362">abc.contoso.com:25</span></span>

- <span data-ttu-id="40b88-363">**Неописательные поддиапники:**</span><span class="sxs-lookup"><span data-stu-id="40b88-363">**Non-descriptive wildcards**:</span></span>

  - \*
  - <span data-ttu-id="40b88-364">\*.\*</span><span class="sxs-lookup"><span data-stu-id="40b88-364">\*.\*</span></span>

- <span data-ttu-id="40b88-365">**Поддиакаограммы среднего звена:**</span><span class="sxs-lookup"><span data-stu-id="40b88-365">**Middle wildcards**:</span></span>

  - <span data-ttu-id="40b88-366">conto \* so.com</span><span class="sxs-lookup"><span data-stu-id="40b88-366">conto\*so.com</span></span>
  - <span data-ttu-id="40b88-367">conto~so.com</span><span class="sxs-lookup"><span data-stu-id="40b88-367">conto~so.com</span></span>

- <span data-ttu-id="40b88-368">**Double wildcards**</span><span class="sxs-lookup"><span data-stu-id="40b88-368">**Double wildcards**</span></span>

  - <span data-ttu-id="40b88-369">contoso.com/\*\*</span><span class="sxs-lookup"><span data-stu-id="40b88-369">contoso.com/\*\*</span></span>
  - <span data-ttu-id="40b88-370">contoso.com/\*/\*</span><span class="sxs-lookup"><span data-stu-id="40b88-370">contoso.com/\*/\*</span></span>
