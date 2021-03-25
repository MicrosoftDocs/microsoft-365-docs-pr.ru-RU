---
title: Управление вашими допусками и блоками в списке разрешить или блокировать клиента
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
description: Администраторы могут научиться настраивать разрешит и блокирует в списке разрешить или заблокировать клиента на портале безопасности.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 55116ddac8fa25b63e50b7fba73f668855e2858d
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/25/2021
ms.locfileid: "51206438"
---
# <a name="manage-the-tenant-allowblock-list"></a><span data-ttu-id="c3728-103">Управление списком разрешенных и запрещенных клиентов</span><span class="sxs-lookup"><span data-stu-id="c3728-103">Manage the Tenant Allow/Block List</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="c3728-104">**Область применения**</span><span class="sxs-lookup"><span data-stu-id="c3728-104">**Applies to**</span></span>
- [<span data-ttu-id="c3728-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="c3728-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="c3728-106">Microsoft Defender для Office 365 (план 1 и план 2)</span><span class="sxs-lookup"><span data-stu-id="c3728-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="c3728-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c3728-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

> [!NOTE]
>
> <span data-ttu-id="c3728-108">Функции, описанные в этой статье, находятся в предварительном просмотре, могут изменяться и недоступны во всех организациях.</span><span class="sxs-lookup"><span data-stu-id="c3728-108">The features described in this article are in Preview, are subject to change, and are not available in all organizations.</span></span>
>
> <span data-ttu-id="c3728-109">В настоящее время нельзя **настроить разрешенные** элементы в списке разрешить или заблокировать клиента.</span><span class="sxs-lookup"><span data-stu-id="c3728-109">You can't **configure** allowed items in the Tenant Allow/Block List at this time.</span></span>

<span data-ttu-id="c3728-110">В организациях Microsoft 365 с почтовыми ящиками в Exchange Online или автономных организациях Exchange Online Protection (EOP) без почтовых ящиков Exchange Online вы можете не согласиться с вердиктом по фильтрации EOP.</span><span class="sxs-lookup"><span data-stu-id="c3728-110">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, you might disagree with the EOP filtering verdict.</span></span> <span data-ttu-id="c3728-111">Например, хорошее сообщение может быть помечено как плохое (ложное положительное) или плохое сообщение может быть разрешено (ложное отрицательное).</span><span class="sxs-lookup"><span data-stu-id="c3728-111">For example, a good message might be marked as bad (a false positive), or a bad message might be allowed through (a false negative).</span></span>

<span data-ttu-id="c3728-112">Список разрешить или заблокировать клиента в Центре & безопасности позволяет вручную переопредировать решения по фильтрации Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c3728-112">The Tenant Allow/Block List in the Security & Compliance Center gives you a way to manually override the Microsoft 365 filtering verdicts.</span></span> <span data-ttu-id="c3728-113">Список разрешить/заблокировать клиента используется во время потока почты и во время щелчков пользователя.</span><span class="sxs-lookup"><span data-stu-id="c3728-113">The Tenant Allow/Block List is used during mail flow and at the time of user clicks.</span></span> <span data-ttu-id="c3728-114">Вы можете указать URL-адреса или файлы, чтобы всегда блокировать.</span><span class="sxs-lookup"><span data-stu-id="c3728-114">You can specify URLs or files to always block.</span></span>

<span data-ttu-id="c3728-115">В этой статье описывается настройка записей в Списке разрешения клиента или блока в Центре обеспечения безопасности & или в PowerShell (Exchange Online PowerShell для организаций Microsoft 365 с почтовыми ящиками в Exchange Online; автономный EOP PowerShell для организаций без почтовых ящиков Exchange Online).</span><span class="sxs-lookup"><span data-stu-id="c3728-115">This article describes how to configure entries in the Tenant Allow/Block List in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="c3728-116">Что нужно знать перед началом работы</span><span class="sxs-lookup"><span data-stu-id="c3728-116">What do you need to know before you begin?</span></span>

- <span data-ttu-id="c3728-117">Откройте Центр безопасности и соответствия требованиям на сайте <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="c3728-117">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="c3728-118">Чтобы перейти непосредственно на **страницу Разрешить или заблокировать** список клиента, используйте <https://protection.office.com/tenantAllowBlockList> .</span><span class="sxs-lookup"><span data-stu-id="c3728-118">To go directly to the **Tenant Allow/Block List** page, use <https://protection.office.com/tenantAllowBlockList>.</span></span>

- <span data-ttu-id="c3728-119">Вы указываете файлы, используя значение hash SHA256 для файла.</span><span class="sxs-lookup"><span data-stu-id="c3728-119">You specify files by using the SHA256 hash value of the file.</span></span> <span data-ttu-id="c3728-120">Чтобы найти значение hash SHA256 для файла в Windows, запустите следующую команду в командной подсказке:</span><span class="sxs-lookup"><span data-stu-id="c3728-120">To find the SHA256 hash value of a file in Windows, run the following command in a Command Prompt:</span></span>

  ```console
  certutil.exe -hashfile "<Path>\<Filename>" SHA256
  ```

  <span data-ttu-id="c3728-121">Например, значение `768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3a` .</span><span class="sxs-lookup"><span data-stu-id="c3728-121">An example value is `768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3a`.</span></span> <span data-ttu-id="c3728-122">Перцептивные значения hash (pHash) не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="c3728-122">Perceptual hash (pHash) values are not supported.</span></span>

- <span data-ttu-id="c3728-123">Доступные значения URL-адресов описаны в синтаксисе [URL-адресов](#url-syntax-for-the-tenant-allowblock-list) для раздела "Разрешить или заблокировать список клиента" в этой статье.</span><span class="sxs-lookup"><span data-stu-id="c3728-123">The available URL values are described in the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this article.</span></span>

- <span data-ttu-id="c3728-124">Список разрешить или блокировать клиента позволяет не более 500 записей для URL-адресов и 500 записей для хеш-файлов.</span><span class="sxs-lookup"><span data-stu-id="c3728-124">The Tenant Allow/Block List allows a maximum of 500 entries for URLs, and 500 entries for file hashes.</span></span>

- <span data-ttu-id="c3728-125">Максимальное количество символов для каждой записи:</span><span class="sxs-lookup"><span data-stu-id="c3728-125">The maximum number of characters for each entry is:</span></span>
  - <span data-ttu-id="c3728-126">Хеши файла = 64</span><span class="sxs-lookup"><span data-stu-id="c3728-126">File hashes = 64</span></span>
  - <span data-ttu-id="c3728-127">URL-адрес = 250</span><span class="sxs-lookup"><span data-stu-id="c3728-127">URL = 250</span></span>

- <span data-ttu-id="c3728-128">Запись должна быть активна в течение 30 минут.</span><span class="sxs-lookup"><span data-stu-id="c3728-128">An entry should be active within 30 minutes.</span></span>

- <span data-ttu-id="c3728-129">По умолчанию срок действия записей в списке разрешить или блокировать клиента истекает через 30 дней.</span><span class="sxs-lookup"><span data-stu-id="c3728-129">By default, entries in the Tenant Allow/Block List will expire after 30 days.</span></span> <span data-ttu-id="c3728-130">Вы можете указать дату или установить, чтобы срок их действия никогда не истек.</span><span class="sxs-lookup"><span data-stu-id="c3728-130">You can specify a date or set them to never expire.</span></span>

- <span data-ttu-id="c3728-131">Сведения о том, как подключиться к Exchange Online PowerShell, см. в статье [Подключение к Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="c3728-131">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="c3728-132">Чтобы подключиться к автономному EOP PowerShell, см. раздел [Подключение к PowerShell Exchange Online Protection](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="c3728-132">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="c3728-133">Для выполнения процедур, описанных в этой статье, вам должны быть назначены разрешения в **Exchange Online**:</span><span class="sxs-lookup"><span data-stu-id="c3728-133">You need to be assigned permissions in **Exchange Online** before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="c3728-134">Чтобы добавить и удалить значения из списка "Разрешить или заблокировать клиента", необходимо быть членом группы ролей администратора организации или **администратора** безопасности. </span><span class="sxs-lookup"><span data-stu-id="c3728-134">To add and remove values from the Tenant Allow/Block List, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="c3728-135">Чтобы получить доступ только для чтения к списку разрешить или заблокировать клиента, необходимо быть членом групп ролей **Global Reader** или **Security Reader.**</span><span class="sxs-lookup"><span data-stu-id="c3728-135">For read-only access to the Tenant Allow/Block List, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="c3728-136">Дополнительные сведения см. в статье [Разрешения в Exchange Online](/exchange/permissions-exo/permissions-exo).</span><span class="sxs-lookup"><span data-stu-id="c3728-136">For more information, see [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  > [!NOTE]
  > 
  > - <span data-ttu-id="c3728-137">Добавление пользователей в соответствующую роль Azure Active Directory в Центре безопасности Microsoft 365 предоставляет пользователям необходимые разрешения _и_ разрешения для других функций в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c3728-137">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="c3728-138">Дополнительные сведения см. в статье [О ролях администраторов](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="c3728-138">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  > - <span data-ttu-id="c3728-139">Группа ролей **Управление организацией с правами только на просмотр** в [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) также предоставляет доступ только для чтения к этой функции.</span><span class="sxs-lookup"><span data-stu-id="c3728-139">The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

## <a name="use-the-security--compliance-center-to-create-url-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="c3728-140">Используйте Центр & безопасности для создания записей URL-адресов в списке разрешить или блокировать клиента</span><span class="sxs-lookup"><span data-stu-id="c3728-140">Use the Security & Compliance Center to create URL entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="c3728-141">Подробные сведения о синтаксисе записей URL-адресов см. в разделе [Синтаксис](#url-syntax-for-the-tenant-allowblock-list) URL-адресов для раздела Разрешить или заблокировать список клиента в этой статье.</span><span class="sxs-lookup"><span data-stu-id="c3728-141">For details about the syntax for URL entries, see the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this article.</span></span>

1. <span data-ttu-id="c3728-142">В Центре обеспечения & безопасности перейдите в **список** "Разрешить и заблокировать" политики управления \>  \> **угрозами.**</span><span class="sxs-lookup"><span data-stu-id="c3728-142">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="c3728-143">На странице **Разрешить или заблокировать** список клиента убедитесь, что выбрана вкладка URL-адресов, а затем нажмите **кнопку Блок** </span><span class="sxs-lookup"><span data-stu-id="c3728-143">On the **Tenant Allow/Block List** page, verify that the **URLs** tab is selected, and then click **Block**</span></span>

3. <span data-ttu-id="c3728-144">В **вылете** url-адресов блока, который отображается, настройте следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="c3728-144">In the **Block URLs** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="c3728-145">**Добавление URL-адресов для блокировки:** введите один URL-адрес на строку, не более 20.</span><span class="sxs-lookup"><span data-stu-id="c3728-145">**Add URLs to block**: Enter one URL per line, up to a maximum of 20.</span></span>

   - <span data-ttu-id="c3728-146">**Никогда не истекает** срок действия: Сделайте один из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="c3728-146">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="c3728-147">Проверьте отключение параметра (Отключение) и используйте истекает в поле, чтобы указать дату истечения ![ ](../../media/scc-toggle-off.png) срока действия записей. </span><span class="sxs-lookup"><span data-stu-id="c3728-147">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entries.</span></span>

       <span data-ttu-id="c3728-148">или</span><span class="sxs-lookup"><span data-stu-id="c3728-148">or</span></span>

     - <span data-ttu-id="c3728-149">Переместите окантовку вправо, чтобы настроить записи, чтобы никогда не истекал срок действия:</span><span class="sxs-lookup"><span data-stu-id="c3728-149">Move the toggle to the right to configure the entries to never expire:</span></span> ![Включенный переключатель](../../media/scc-toggle-on.png)<span data-ttu-id="c3728-151">.</span><span class="sxs-lookup"><span data-stu-id="c3728-151">.</span></span>

   - <span data-ttu-id="c3728-152">**Необязательный** примечание. Введите описательный текст для записей.</span><span class="sxs-lookup"><span data-stu-id="c3728-152">**Optional note**: Enter descriptive text for the entries.</span></span>

4. <span data-ttu-id="c3728-153">Когда вы закончите, нажмите **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="c3728-153">When you're finished, click **Add**.</span></span>

## <a name="use-the-security--compliance-center-to-create-file-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="c3728-154">Используйте Центр & безопасности для создания записей файлов в списке разрешить или заблокировать клиента</span><span class="sxs-lookup"><span data-stu-id="c3728-154">Use the Security & Compliance Center to create file entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="c3728-155">В Центре обеспечения & безопасности перейдите в **список** "Разрешить и заблокировать" политики управления \>  \> **угрозами.**</span><span class="sxs-lookup"><span data-stu-id="c3728-155">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="c3728-156">На странице **Разрешить или блокировать** список клиента выберите вкладку **Файлы** и нажмите **кнопку Блок**.</span><span class="sxs-lookup"><span data-stu-id="c3728-156">On the **Tenant Allow/Block List** page, select **Files** tab, and then click **Block**.</span></span>

3. <span data-ttu-id="c3728-157">В **добавлении файлов для блокировки** вылетов, которые появляются, настройте следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="c3728-157">In the **Add files to block** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="c3728-158">**Добавление хеша файла:** введите одно хеш-значение SHA256 за строку, не более 20.</span><span class="sxs-lookup"><span data-stu-id="c3728-158">**Add file hashes**: Enter one SHA256 hash value per line, up to a maximum of 20.</span></span>

   - <span data-ttu-id="c3728-159">**Никогда не истекает** срок действия: Сделайте один из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="c3728-159">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="c3728-160">Проверьте отключение параметра (Отключение) и используйте истекает в поле, чтобы указать дату истечения ![ ](../../media/scc-toggle-off.png) срока действия записей. </span><span class="sxs-lookup"><span data-stu-id="c3728-160">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entries.</span></span>

     <span data-ttu-id="c3728-161">или</span><span class="sxs-lookup"><span data-stu-id="c3728-161">or</span></span>

     - <span data-ttu-id="c3728-162">Переместите окантовку вправо, чтобы настроить записи, чтобы никогда не истекал срок действия:</span><span class="sxs-lookup"><span data-stu-id="c3728-162">Move the toggle to the right to configure the entries to never expire:</span></span> ![Включенный переключатель](../../media/scc-toggle-on.png)<span data-ttu-id="c3728-164">.</span><span class="sxs-lookup"><span data-stu-id="c3728-164">.</span></span>

   - <span data-ttu-id="c3728-165">**Необязательный** примечание. Введите описательный текст для записей.</span><span class="sxs-lookup"><span data-stu-id="c3728-165">**Optional note**: Enter descriptive text for the entries.</span></span>

4. <span data-ttu-id="c3728-166">Когда вы закончите, нажмите **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="c3728-166">When you're finished, click **Add**.</span></span>

## <a name="use-the-security--compliance-center-to-view-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="c3728-167">Используйте Центр & безопасности для просмотра записей в списке разрешить или заблокировать клиента</span><span class="sxs-lookup"><span data-stu-id="c3728-167">Use the Security & Compliance Center to view entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="c3728-168">В Центре обеспечения & безопасности перейдите в **список** "Разрешить и заблокировать" политики управления \>  \> **угрозами.**</span><span class="sxs-lookup"><span data-stu-id="c3728-168">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="c3728-169">Выберите **вкладку URL-адреса** или **вкладку Files.**</span><span class="sxs-lookup"><span data-stu-id="c3728-169">Select the **URLs** tab or the **Files** tab.</span></span>

<span data-ttu-id="c3728-170">Нажмите на следующие заголовки столбца, чтобы отсортироваться в порядке по возрастанию или убыванию:</span><span class="sxs-lookup"><span data-stu-id="c3728-170">Click on the following column headings to sort in ascending or descending order:</span></span>

- <span data-ttu-id="c3728-171">**Значение:** URL-адрес или hash файла.</span><span class="sxs-lookup"><span data-stu-id="c3728-171">**Value**: The URL or the file hash.</span></span>
- <span data-ttu-id="c3728-172">**Последняя обновленная дата**</span><span class="sxs-lookup"><span data-stu-id="c3728-172">**Last updated date**</span></span>
- <span data-ttu-id="c3728-173">**Срок действия**</span><span class="sxs-lookup"><span data-stu-id="c3728-173">**Expiration date**</span></span>
- <span data-ttu-id="c3728-174">**Примечание**</span><span class="sxs-lookup"><span data-stu-id="c3728-174">**Note**</span></span>

<span data-ttu-id="c3728-175">Щелкните **Поиск,** введите все или часть значения, а затем нажмите КНОПКУ ВВОДА, чтобы найти определенное значение.</span><span class="sxs-lookup"><span data-stu-id="c3728-175">Click **Search**, enter all or part of a value, and then press ENTER to find a specific value.</span></span> <span data-ttu-id="c3728-176">По завершению щелкните **значок Clear Search** Clear search ![ ](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif) .</span><span class="sxs-lookup"><span data-stu-id="c3728-176">When you're finished, click **Clear search** ![Clear search icon](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif).</span></span>

<span data-ttu-id="c3728-177">Щелкните **Фильтр**.</span><span class="sxs-lookup"><span data-stu-id="c3728-177">Click **Filter**.</span></span> <span data-ttu-id="c3728-178">В **вылете Filter,** который отображается, настройте любой из следующих параметров:</span><span class="sxs-lookup"><span data-stu-id="c3728-178">In the **Filter** flyout that appears, configure any of the following settings:</span></span>

- <span data-ttu-id="c3728-179">**Никогда не истекает:** Выберите отключение: ![ отключите или ](../../media/scc-toggle-off.png) включите. ![ ](../../media/scc-toggle-on.png)</span><span class="sxs-lookup"><span data-stu-id="c3728-179">**Never expire**: Select off: ![Toggle off](../../media/scc-toggle-off.png) or on: ![Toggle on](../../media/scc-toggle-on.png).</span></span>

- <span data-ttu-id="c3728-180">**Последнее обновление:** Выберите дату начала **(Из**), даты окончания **(To)** или обоих.</span><span class="sxs-lookup"><span data-stu-id="c3728-180">**Last updated**: Select a start date (**From**), an end date (**To**) or both.</span></span>

- <span data-ttu-id="c3728-181">**Срок действия:** Выберите дату начала **(От),** даты окончания **(к)** или и то, и другое.</span><span class="sxs-lookup"><span data-stu-id="c3728-181">**Expiration date**: Select a start date (**From**), an end date (**To**) or both.</span></span>

<span data-ttu-id="c3728-182">По завершению нажмите кнопку **Применить**.</span><span class="sxs-lookup"><span data-stu-id="c3728-182">When you're finished, click **Apply**.</span></span>

<span data-ttu-id="c3728-183">Чтобы очистить существующие фильтры, **щелкните Фильтр,** а в вылете **Фильтр,** который появится, щелкните **Очистить фильтры**.</span><span class="sxs-lookup"><span data-stu-id="c3728-183">To clear existing filters, click **Filter**, and in the **Filter** flyout that appears, click **Clear filters**.</span></span>

## <a name="use-the-security--compliance-center-to-modify-block-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="c3728-184">Используйте Центр & безопасности для изменения записей блоков в списке разрешить или заблокировать клиента</span><span class="sxs-lookup"><span data-stu-id="c3728-184">Use the Security & Compliance Center to modify block entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="c3728-185">Вы не можете изменить существующие заблокированные URL-адрес или значения файлов в записи.</span><span class="sxs-lookup"><span data-stu-id="c3728-185">You can't modify the existing blocked URL or file values within an entry.</span></span> <span data-ttu-id="c3728-186">Чтобы изменить эти значения, необходимо удалить и воссоздать запись.</span><span class="sxs-lookup"><span data-stu-id="c3728-186">To modify these values, you need to delete and recreate the entry.</span></span>

1. <span data-ttu-id="c3728-187">В Центре обеспечения & безопасности перейдите в **список** "Разрешить и заблокировать" политики управления \>  \> **угрозами.**</span><span class="sxs-lookup"><span data-stu-id="c3728-187">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="c3728-188">Выберите **вкладку URL-адреса** или **вкладку Files.**</span><span class="sxs-lookup"><span data-stu-id="c3728-188">Select the **URLs** tab or the **Files** tab.</span></span>

3. <span data-ttu-id="c3728-189">Выберите блок-запись, которую необходимо изменить, а затем нажмите **кнопку Изменить значок Редактирование** ![ ](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) .</span><span class="sxs-lookup"><span data-stu-id="c3728-189">Select the block entry that you want to modify, and then click **Edit** ![Edit icon](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png).</span></span>

4. <span data-ttu-id="c3728-190">В вылете, который отображается, настройте следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="c3728-190">In the flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="c3728-191">**Никогда не истекает** срок действия: Сделайте один из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="c3728-191">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="c3728-192">Убедитесь, что параметр отключен (отключается) и используйте истекает в поле, чтобы указать дату истечения ![ ](../../media/scc-toggle-off.png) срока действия записи. </span><span class="sxs-lookup"><span data-stu-id="c3728-192">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entry.</span></span>

       <span data-ttu-id="c3728-193">или</span><span class="sxs-lookup"><span data-stu-id="c3728-193">or</span></span>

     - <span data-ttu-id="c3728-194">Перемещение точки вправо, чтобы настроить запись, чтобы не истек срок действия:</span><span class="sxs-lookup"><span data-stu-id="c3728-194">Move the toggle to the right to configure the entry to never expire:</span></span> ![Включенный переключатель](../../media/scc-toggle-on.png)<span data-ttu-id="c3728-196">.</span><span class="sxs-lookup"><span data-stu-id="c3728-196">.</span></span>

   - <span data-ttu-id="c3728-197">**Необязательный примечание.** Введите описательный текст для записи.</span><span class="sxs-lookup"><span data-stu-id="c3728-197">**Optional note**: Enter descriptive text for the entry.</span></span>

5. <span data-ttu-id="c3728-198">Когда закончите, нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="c3728-198">When you're finished, click **Save**.</span></span>

## <a name="use-the-security--compliance-center-to-remove-block-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="c3728-199">Используйте Центр & безопасности для удаления блоковых записей из списка разрешить или заблокировать клиента</span><span class="sxs-lookup"><span data-stu-id="c3728-199">Use the Security & Compliance Center to remove block entries from the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="c3728-200">В Центре обеспечения & безопасности перейдите в **список** "Разрешить и заблокировать" политики управления \>  \> **угрозами.**</span><span class="sxs-lookup"><span data-stu-id="c3728-200">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="c3728-201">Выберите **вкладку URL-адреса** или **вкладку Files.**</span><span class="sxs-lookup"><span data-stu-id="c3728-201">Select the **URLs** tab or the **Files** tab.</span></span>

3. <span data-ttu-id="c3728-202">Выберите блок-запись, которую необходимо удалить, а затем нажмите **кнопку Удалить значок Удалить** ![ ](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png) .</span><span class="sxs-lookup"><span data-stu-id="c3728-202">Select the block entry that you want to remove, and then click **Delete** ![Delete icon](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png).</span></span>

4. <span data-ttu-id="c3728-203">В диалоговом октаге предупреждения нажмите кнопку **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="c3728-203">In the warning dialog that appears, click **Delete**.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-the-tenant-allowblock-list"></a><span data-ttu-id="c3728-204">Используйте Exchange Online PowerShell или автономный EOP PowerShell для настройки списка разрешить/заблокировать клиента</span><span class="sxs-lookup"><span data-stu-id="c3728-204">Use Exchange Online PowerShell or standalone EOP PowerShell to configure the Tenant Allow/Block List</span></span>

### <a name="use-powershell-to-add-block-entries-to-the-tenant-allowblock-list"></a><span data-ttu-id="c3728-205">Использование PowerShell для добавления записей блоков в список разрешить или заблокировать клиента</span><span class="sxs-lookup"><span data-stu-id="c3728-205">Use PowerShell to add block entries to the Tenant Allow/Block List</span></span>

<span data-ttu-id="c3728-206">Чтобы добавить блоковые записи в список разрешить или блокировать клиента, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="c3728-206">To add block entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
New-TenantAllowBlockListItems -ListType <Url | FileHash> -Block -Entries <String[]> [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

<span data-ttu-id="c3728-207">В этом примере добавляется запись URL-адреса contoso.com всех поддоменов (например, contoso.com, www.contoso.com и xyz.abc.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="c3728-207">This example adds a block URL entry for contoso.com and all subdomains (for example, contoso.com, www.contoso.com, and xyz.abc.contoso.com).</span></span> <span data-ttu-id="c3728-208">Поскольку мы не использовали параметры ExpireDate или NoExpiration, срок действия записи истекает через 30 дней.</span><span class="sxs-lookup"><span data-stu-id="c3728-208">Because we didn't use the ExpirationDate or NoExpiration parameters, the entry expires after 30 days.</span></span>

```powershell
New-TenantAllowBlockListItems -ListType Url -Block -Entries ~contoso.com
```

<span data-ttu-id="c3728-209">В этом примере добавляется запись заблокированного файла для указанных файлов, срок действия которых никогда не истекает.</span><span class="sxs-lookup"><span data-stu-id="c3728-209">This example adds a block file entry for the specified files that never expires.</span></span>

```powershell
New-TenantAllowBlockListItems -ListType FileHash -Block -Entries "768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3","2c0a35409ff0873cfa28b70b8224e9aca2362241c1f0ed6f622fef8d4722fd9a" -NoExpiration
```

<span data-ttu-id="c3728-210">Подробные сведения о синтаксисе и параметрах см. в [обзоре New-TenantAllowBlockListItems.](/powershell/module/exchange/new-tenantallowblocklistitems)</span><span class="sxs-lookup"><span data-stu-id="c3728-210">For detailed syntax and parameter information, see [New-TenantAllowBlockListItems](/powershell/module/exchange/new-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-view-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="c3728-211">Использование PowerShell для просмотра записей в списке разрешить или заблокировать клиента</span><span class="sxs-lookup"><span data-stu-id="c3728-211">Use PowerShell to view entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="c3728-212">Чтобы просмотреть записи в списке разрешить или блокировать клиента, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="c3728-212">To view entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType <Url | FileHash> [-Entry <URLValue | FileHashValue>] [-Block] [-ExpirationDate <DateTime>] [-NoExpiration]
```

<span data-ttu-id="c3728-213">В этом примере возвращаются все заблокированные URL-адреса.</span><span class="sxs-lookup"><span data-stu-id="c3728-213">This example returns all blocked URLs.</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType Url -Block
```

<span data-ttu-id="c3728-214">В этом примере возвращается информация для указанного значения hash файла.</span><span class="sxs-lookup"><span data-stu-id="c3728-214">This example returns information for the specified file hash value.</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType FileHash -Entry "9f86d081884c7d659a2feaa0c55ad015a3bf4f1b2b0b822cd15d6c15b0f00a08"
```

<span data-ttu-id="c3728-215">Подробные сведения о синтаксисе и параметрах см. в [обзоре Get-TenantAllowBlockListItems.](/powershell/module/exchange/get-tenantallowblocklistitems)</span><span class="sxs-lookup"><span data-stu-id="c3728-215">For detailed syntax and parameter information, see [Get-TenantAllowBlockListItems](/powershell/module/exchange/get-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-modify-block-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="c3728-216">Использование PowerShell для изменения записей блоков в списке разрешить или заблокировать клиента</span><span class="sxs-lookup"><span data-stu-id="c3728-216">Use PowerShell to modify block entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="c3728-217">Вы не можете изменить существующие значения URL-адресов или файлов в блок-записи.</span><span class="sxs-lookup"><span data-stu-id="c3728-217">You can't modify the existing URL or file values within a block entry.</span></span> <span data-ttu-id="c3728-218">Чтобы изменить эти значения, необходимо удалить и воссоздать запись.</span><span class="sxs-lookup"><span data-stu-id="c3728-218">To modify these values, you need to delete and recreate the entry.</span></span>

<span data-ttu-id="c3728-219">Чтобы изменить записи блокировки в списке разрешить или блокировать клиента, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="c3728-219">To modify block entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType <Url | FileHash> -Ids <"Id1","Id2",..."IdN"> [-Block] [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

<span data-ttu-id="c3728-220">В этом примере изменяется срок действия указанной блок-записи.</span><span class="sxs-lookup"><span data-stu-id="c3728-220">This example changes the expiration date of the specified block entry.</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -ExpirationDate (Get-Date "5/30/2020 9:30 AM").ToUniversalTime()
```

<span data-ttu-id="c3728-221">Подробные сведения о синтаксисе и параметрах см. в [ссылке Set-TenantAllowBlockListItems.](/powershell/module/exchange/set-tenantallowblocklistitems)</span><span class="sxs-lookup"><span data-stu-id="c3728-221">For detailed syntax and parameter information, see [Set-TenantAllowBlockListItems](/powershell/module/exchange/set-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-remove-block-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="c3728-222">Использование PowerShell для удаления записей блокировки из списка разрешить или заблокировать клиента</span><span class="sxs-lookup"><span data-stu-id="c3728-222">Use PowerShell to remove block entries from the Tenant Allow/Block List</span></span>

<span data-ttu-id="c3728-223">Чтобы удалить блоковые записи из списка "Разрешить или блокировать клиента", используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="c3728-223">To remove block entries from the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType <Url | FileHash> -Ids <"Id1","Id2",..."IdN">
```

<span data-ttu-id="c3728-224">В этом примере удаляется указанная запись URL-адреса блокировки из списка разрешить или блокировать клиента.</span><span class="sxs-lookup"><span data-stu-id="c3728-224">This example removes the specified block URL entry from the Tenant Allow/Block List.</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSPAAAA0"
```

<span data-ttu-id="c3728-225">Подробные сведения о синтаксисе и параметрах см. в [ссылке Remove-TenantAllowBlockListItems.](/powershell/module/exchange/remove-tenantallowblocklistitems)</span><span class="sxs-lookup"><span data-stu-id="c3728-225">For detailed syntax and parameter information, see [Remove-TenantAllowBlockListItems](/powershell/module/exchange/remove-tenantallowblocklistitems).</span></span>

## <a name="url-syntax-for-the-tenant-allowblock-list"></a><span data-ttu-id="c3728-226">Синтаксис URL-адреса для списка разрешить или блокировать клиента</span><span class="sxs-lookup"><span data-stu-id="c3728-226">URL syntax for the Tenant Allow/Block List</span></span>

- <span data-ttu-id="c3728-227">Ip4v и IPv6-адреса разрешены, но порты TCP/UDP — нет.</span><span class="sxs-lookup"><span data-stu-id="c3728-227">IP4v and IPv6 addresses are allowed, but TCP/UDP ports are not.</span></span>

- <span data-ttu-id="c3728-228">Расширения filename не разрешены (например, test.pdf).</span><span class="sxs-lookup"><span data-stu-id="c3728-228">Filename extensions are not allowed (for example, test.pdf).</span></span>

- <span data-ttu-id="c3728-229">Юникод не поддерживается, но Punycode есть.</span><span class="sxs-lookup"><span data-stu-id="c3728-229">Unicode is not supported, but Punycode is.</span></span>

- <span data-ttu-id="c3728-230">Имена хост-кодов разрешены, если все следующие утверждения верны:</span><span class="sxs-lookup"><span data-stu-id="c3728-230">Hostnames are allowed if all of the following statements are true:</span></span>
  - <span data-ttu-id="c3728-231">Имя хост-пользователя содержит период.</span><span class="sxs-lookup"><span data-stu-id="c3728-231">The hostname contains a period.</span></span>
  - <span data-ttu-id="c3728-232">Существует по крайней мере один символ слева от периода.</span><span class="sxs-lookup"><span data-stu-id="c3728-232">There is at least one character to the left of the period.</span></span>
  - <span data-ttu-id="c3728-233">Справа от периода имеется по крайней мере два символа.</span><span class="sxs-lookup"><span data-stu-id="c3728-233">There are at least two characters to the right of the period.</span></span>

  <span data-ttu-id="c3728-234">Например, `t.co` разрешено или `.com` `contoso.` запрещено.</span><span class="sxs-lookup"><span data-stu-id="c3728-234">For example, `t.co` is allowed; `.com` or `contoso.` are not allowed.</span></span>

- <span data-ttu-id="c3728-235">Subpaths не подразумеваются.</span><span class="sxs-lookup"><span data-stu-id="c3728-235">Subpaths are not implied.</span></span>

  <span data-ttu-id="c3728-236">Например, `contoso.com` не включает `contoso.com/a` .</span><span class="sxs-lookup"><span data-stu-id="c3728-236">For example, `contoso.com` does not include `contoso.com/a`.</span></span>

- <span data-ttu-id="c3728-237">Поддиальды (\*) разрешены в следующих сценариях:</span><span class="sxs-lookup"><span data-stu-id="c3728-237">Wildcards (\*) are allowed in the following scenarios:</span></span>

  - <span data-ttu-id="c3728-238">За левой подгруппой должен следовать период, чтобы указать поддомен.</span><span class="sxs-lookup"><span data-stu-id="c3728-238">A left wildcard must be followed by a period to specify a subdomain.</span></span>

    <span data-ttu-id="c3728-239">Например, `*.contoso.com` разрешено; `*contoso.com` запрещено.</span><span class="sxs-lookup"><span data-stu-id="c3728-239">For example, `*.contoso.com` is allowed; `*contoso.com` is not allowed.</span></span>

  - <span data-ttu-id="c3728-240">Правая подмайка должна следовать за полосой вперед (/), чтобы указать путь.</span><span class="sxs-lookup"><span data-stu-id="c3728-240">A right wildcard must follow a forward slash (/) to specify a path.</span></span>

    <span data-ttu-id="c3728-241">Например, `contoso.com/*` разрешено или `contoso.com*` `contoso.com/ab*` запрещено.</span><span class="sxs-lookup"><span data-stu-id="c3728-241">For example, `contoso.com/*` is allowed; `contoso.com*` or `contoso.com/ab*` are not allowed.</span></span>

  - <span data-ttu-id="c3728-242">Все подпаты не подразумеваются правой подгруппой.</span><span class="sxs-lookup"><span data-stu-id="c3728-242">All subpaths are not implied by a right wildcard.</span></span>

    <span data-ttu-id="c3728-243">Например, `contoso.com/*` не включает `contoso.com/a` .</span><span class="sxs-lookup"><span data-stu-id="c3728-243">For example, `contoso.com/*` does not include `contoso.com/a`.</span></span>

  - <span data-ttu-id="c3728-244">`*.com*` является недействительным (не разрешимый домен, а правая подкратная карточка не следует передовую черту).</span><span class="sxs-lookup"><span data-stu-id="c3728-244">`*.com*` is invalid (not a resolvable domain and the right wildcard does not follow a forward slash).</span></span>

  - <span data-ttu-id="c3728-245">В IP-адресах запрещено использовать поддиальдные знаки.</span><span class="sxs-lookup"><span data-stu-id="c3728-245">Wildcards are not allowed in IP addresses.</span></span>

- <span data-ttu-id="c3728-246">Символ tilde (~) доступен в следующих сценариях:</span><span class="sxs-lookup"><span data-stu-id="c3728-246">The tilde (~) character is available in the following scenarios:</span></span>

  - <span data-ttu-id="c3728-247">Левая тильда подразумевает домен и все поддомены.</span><span class="sxs-lookup"><span data-stu-id="c3728-247">A left tilde implies a domain and all subdomains.</span></span>

    <span data-ttu-id="c3728-248">Например, `~contoso.com` включает `contoso.com` и `*.contoso.com` .</span><span class="sxs-lookup"><span data-stu-id="c3728-248">For example `~contoso.com` includes `contoso.com` and `*.contoso.com`.</span></span>

- <span data-ttu-id="c3728-249">Записи URL-адресов, содержащие протоколы (например, или ) не будут работать, так как URL-записи применяются `http://` `https://` к всем `ftp://` протоколам.</span><span class="sxs-lookup"><span data-stu-id="c3728-249">URL entries that contain protocols (for example, `http://`, `https://`, or `ftp://`) will fail, because URL entries apply to all protocols.</span></span>

- <span data-ttu-id="c3728-250">Имя пользователя или пароль не поддерживаются или не требуются.</span><span class="sxs-lookup"><span data-stu-id="c3728-250">A username or password aren't supported or required.</span></span>

- <span data-ttu-id="c3728-251">Кавычка (' или ") являются недействительными символами.</span><span class="sxs-lookup"><span data-stu-id="c3728-251">Quotes (' or ") are invalid characters.</span></span>

- <span data-ttu-id="c3728-252">URL-адрес должен включать все перенаправления, где это возможно.</span><span class="sxs-lookup"><span data-stu-id="c3728-252">A URL should include all redirects where possible.</span></span>

### <a name="url-entry-scenarios"></a><span data-ttu-id="c3728-253">Сценарии ввода URL-адресов</span><span class="sxs-lookup"><span data-stu-id="c3728-253">URL entry scenarios</span></span>

<span data-ttu-id="c3728-254">Допустимые записи URL-адресов и их результаты описаны в следующих разделах.</span><span class="sxs-lookup"><span data-stu-id="c3728-254">Valid URL entries and their results are described in the following sections.</span></span>

#### <a name="scenario-no-wildcards"></a><span data-ttu-id="c3728-255">Сценарий: нет поддиальдов</span><span class="sxs-lookup"><span data-stu-id="c3728-255">Scenario: No wildcards</span></span>

<span data-ttu-id="c3728-256">**Запись:**`contoso.com`</span><span class="sxs-lookup"><span data-stu-id="c3728-256">**Entry**: `contoso.com`</span></span>

- <span data-ttu-id="c3728-257">**Разрешить совпадение:** contoso.com</span><span class="sxs-lookup"><span data-stu-id="c3728-257">**Allow match**: contoso.com</span></span>

- <span data-ttu-id="c3728-258">**Разрешить не совпадать:**</span><span class="sxs-lookup"><span data-stu-id="c3728-258">**Allow not matched**:</span></span>

  - <span data-ttu-id="c3728-259">abc-contoso.com</span><span class="sxs-lookup"><span data-stu-id="c3728-259">abc-contoso.com</span></span>
  - <span data-ttu-id="c3728-260">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="c3728-260">contoso.com/a</span></span>
  - <span data-ttu-id="c3728-261">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="c3728-261">payroll.contoso.com</span></span>
  - <span data-ttu-id="c3728-262">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="c3728-262">test.com/contoso.com</span></span>
  - <span data-ttu-id="c3728-263">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="c3728-263">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="c3728-264">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="c3728-264">www.contoso.com</span></span>
  - <span data-ttu-id="c3728-265">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="c3728-265">www.contoso.com/q=a@contoso.com</span></span>

- <span data-ttu-id="c3728-266">**Совпадение блоков:**</span><span class="sxs-lookup"><span data-stu-id="c3728-266">**Block match**:</span></span>

  - <span data-ttu-id="c3728-267">contoso.com</span><span class="sxs-lookup"><span data-stu-id="c3728-267">contoso.com</span></span>
  - <span data-ttu-id="c3728-268">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="c3728-268">contoso.com/a</span></span>
  - <span data-ttu-id="c3728-269">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="c3728-269">payroll.contoso.com</span></span>
  - <span data-ttu-id="c3728-270">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="c3728-270">test.com/contoso.com</span></span>
  - <span data-ttu-id="c3728-271">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="c3728-271">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="c3728-272">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="c3728-272">www.contoso.com</span></span>
  - <span data-ttu-id="c3728-273">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="c3728-273">www.contoso.com/q=a@contoso.com</span></span>

- <span data-ttu-id="c3728-274">**Блок не соответствует**: abc-contoso.com</span><span class="sxs-lookup"><span data-stu-id="c3728-274">**Block not matched**: abc-contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain"></a><span data-ttu-id="c3728-275">Сценарий: левая подгруппа (subdomain)</span><span class="sxs-lookup"><span data-stu-id="c3728-275">Scenario: Left wildcard (subdomain)</span></span>

<span data-ttu-id="c3728-276">**Запись:**`*.contoso.com`</span><span class="sxs-lookup"><span data-stu-id="c3728-276">**Entry**: `*.contoso.com`</span></span>

- <span data-ttu-id="c3728-277">**Разрешить совпадение** **и блокировку:**</span><span class="sxs-lookup"><span data-stu-id="c3728-277">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="c3728-278">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="c3728-278">www.contoso.com</span></span>
  - <span data-ttu-id="c3728-279">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="c3728-279">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="c3728-280">**Разрешить не совпадать и** **блок не совпадает:**</span><span class="sxs-lookup"><span data-stu-id="c3728-280">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="c3728-281">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="c3728-281">123contoso.com</span></span>
  - <span data-ttu-id="c3728-282">contoso.com</span><span class="sxs-lookup"><span data-stu-id="c3728-282">contoso.com</span></span>
  - <span data-ttu-id="c3728-283">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="c3728-283">test.com/contoso.com</span></span>
  - <span data-ttu-id="c3728-284">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="c3728-284">www.contoso.com/abc</span></span>

#### <a name="scenario-right-wildcard-at-top-of-path"></a><span data-ttu-id="c3728-285">Сценарий: правая под диктовка в верхней части пути</span><span class="sxs-lookup"><span data-stu-id="c3728-285">Scenario: Right wildcard at top of path</span></span>

<span data-ttu-id="c3728-286">**Запись:**`contoso.com/a/*`</span><span class="sxs-lookup"><span data-stu-id="c3728-286">**Entry**: `contoso.com/a/*`</span></span>

- <span data-ttu-id="c3728-287">**Разрешить совпадение** **и блокировку:**</span><span class="sxs-lookup"><span data-stu-id="c3728-287">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="c3728-288">contoso.com/a/b</span><span class="sxs-lookup"><span data-stu-id="c3728-288">contoso.com/a/b</span></span>
  - <span data-ttu-id="c3728-289">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="c3728-289">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="c3728-290">contoso.com/a/?q=joe@t.com</span><span class="sxs-lookup"><span data-stu-id="c3728-290">contoso.com/a/?q=joe@t.com</span></span>

- <span data-ttu-id="c3728-291">**Разрешить не совпадать и** **блок не совпадает:**</span><span class="sxs-lookup"><span data-stu-id="c3728-291">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="c3728-292">contoso.com</span><span class="sxs-lookup"><span data-stu-id="c3728-292">contoso.com</span></span>
  - <span data-ttu-id="c3728-293">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="c3728-293">contoso.com/a</span></span>
  - <span data-ttu-id="c3728-294">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="c3728-294">www.contoso.com</span></span>
  - <span data-ttu-id="c3728-295">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="c3728-295">www.contoso.com/q=a@contoso.com</span></span>

#### <a name="scenario-left-tilde"></a><span data-ttu-id="c3728-296">Сценарий: левая тильда</span><span class="sxs-lookup"><span data-stu-id="c3728-296">Scenario: Left tilde</span></span>

<span data-ttu-id="c3728-297">**Запись:**`~contoso.com`</span><span class="sxs-lookup"><span data-stu-id="c3728-297">**Entry**: `~contoso.com`</span></span>

- <span data-ttu-id="c3728-298">**Разрешить совпадение** **и блокировку:**</span><span class="sxs-lookup"><span data-stu-id="c3728-298">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="c3728-299">contoso.com</span><span class="sxs-lookup"><span data-stu-id="c3728-299">contoso.com</span></span>
  - <span data-ttu-id="c3728-300">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="c3728-300">www.contoso.com</span></span>
  - <span data-ttu-id="c3728-301">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="c3728-301">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="c3728-302">**Разрешить не совпадать и** **блок не совпадает:**</span><span class="sxs-lookup"><span data-stu-id="c3728-302">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="c3728-303">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="c3728-303">123contoso.com</span></span>
  - <span data-ttu-id="c3728-304">contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="c3728-304">contoso.com/abc</span></span>
  - <span data-ttu-id="c3728-305">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="c3728-305">www.contoso.com/abc</span></span>

#### <a name="scenario-right-wildcard-suffix"></a><span data-ttu-id="c3728-306">Сценарий: суффикс правой подстановки</span><span class="sxs-lookup"><span data-stu-id="c3728-306">Scenario: Right wildcard suffix</span></span>

<span data-ttu-id="c3728-307">**Запись:**`contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="c3728-307">**Entry**: `contoso.com/*`</span></span>

- <span data-ttu-id="c3728-308">**Разрешить совпадение** **и блокировку:**</span><span class="sxs-lookup"><span data-stu-id="c3728-308">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="c3728-309">contoso.com/?q=whatever@fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="c3728-309">contoso.com/?q=whatever@fabrikam.com</span></span>
  - <span data-ttu-id="c3728-310">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="c3728-310">contoso.com/a</span></span>
  - <span data-ttu-id="c3728-311">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="c3728-311">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="c3728-312">contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="c3728-312">contoso.com/ab</span></span>
  - <span data-ttu-id="c3728-313">contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="c3728-313">contoso.com/b</span></span>
  - <span data-ttu-id="c3728-314">contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="c3728-314">contoso.com/b/a/c</span></span>
  - <span data-ttu-id="c3728-315">contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="c3728-315">contoso.com/ba</span></span>

- <span data-ttu-id="c3728-316">**Разрешить не совпадать** и **блок не совпадает**: contoso.com</span><span class="sxs-lookup"><span data-stu-id="c3728-316">**Allow not matched** and **Block not matched**: contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain-and-right-wildcard-suffix"></a><span data-ttu-id="c3728-317">Сценарий. Поддомайн левой подстановки и суффикс правой подстановки</span><span class="sxs-lookup"><span data-stu-id="c3728-317">Scenario: Left wildcard subdomain and right wildcard suffix</span></span>

<span data-ttu-id="c3728-318">**Запись:**`*.contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="c3728-318">**Entry**: `*.contoso.com/*`</span></span>

- <span data-ttu-id="c3728-319">**Разрешить совпадение** **и блокировку:**</span><span class="sxs-lookup"><span data-stu-id="c3728-319">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="c3728-320">abc.contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="c3728-320">abc.contoso.com/ab</span></span>
  - <span data-ttu-id="c3728-321">abc.xyz.contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="c3728-321">abc.xyz.contoso.com/a/b/c</span></span>
  - <span data-ttu-id="c3728-322">www.contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="c3728-322">www.contoso.com/a</span></span>
  - <span data-ttu-id="c3728-323">www.contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="c3728-323">www.contoso.com/b/a/c</span></span>
  - <span data-ttu-id="c3728-324">xyz.contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="c3728-324">xyz.contoso.com/ba</span></span>

- <span data-ttu-id="c3728-325">**Разрешить не совпадать** и **блок не соответствует**: contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="c3728-325">**Allow not matched** and **Block not matched**: contoso.com/b</span></span>

#### <a name="scenario-left-and-right-tilde"></a><span data-ttu-id="c3728-326">Сценарий: левая и правая тильда</span><span class="sxs-lookup"><span data-stu-id="c3728-326">Scenario: Left and right tilde</span></span>

<span data-ttu-id="c3728-327">**Запись:**`~contoso.com~`</span><span class="sxs-lookup"><span data-stu-id="c3728-327">**Entry**: `~contoso.com~`</span></span>

- <span data-ttu-id="c3728-328">**Разрешить совпадение** **и блокировку:**</span><span class="sxs-lookup"><span data-stu-id="c3728-328">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="c3728-329">contoso.com</span><span class="sxs-lookup"><span data-stu-id="c3728-329">contoso.com</span></span>
  - <span data-ttu-id="c3728-330">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="c3728-330">contoso.com/a</span></span>
  - <span data-ttu-id="c3728-331">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="c3728-331">www.contoso.com</span></span>
  - <span data-ttu-id="c3728-332">www.contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="c3728-332">www.contoso.com/b</span></span>
  - <span data-ttu-id="c3728-333">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="c3728-333">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="c3728-334">**Разрешить не совпадать и** **блок не совпадает:**</span><span class="sxs-lookup"><span data-stu-id="c3728-334">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="c3728-335">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="c3728-335">123contoso.com</span></span>
  - <span data-ttu-id="c3728-336">contoso.org</span><span class="sxs-lookup"><span data-stu-id="c3728-336">contoso.org</span></span>

#### <a name="scenario-ip-address"></a><span data-ttu-id="c3728-337">Сценарий: IP-адрес</span><span class="sxs-lookup"><span data-stu-id="c3728-337">Scenario: IP address</span></span>

<span data-ttu-id="c3728-338">**Запись:**`1.2.3.4`</span><span class="sxs-lookup"><span data-stu-id="c3728-338">**Entry**: `1.2.3.4`</span></span>

- <span data-ttu-id="c3728-339">**Разрешить совпадение** **и блокировку:** 1.2.3.4</span><span class="sxs-lookup"><span data-stu-id="c3728-339">**Allow match** and **Block match**: 1.2.3.4</span></span>

- <span data-ttu-id="c3728-340">**Разрешить не совпадать и** **блок не совпадает:**</span><span class="sxs-lookup"><span data-stu-id="c3728-340">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="c3728-341">1.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="c3728-341">1.2.3.4/a</span></span>
  - <span data-ttu-id="c3728-342">11.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="c3728-342">11.2.3.4/a</span></span>

#### <a name="ip-address-with-right-wildcard"></a><span data-ttu-id="c3728-343">IP-адрес с правой подголой карточкой</span><span class="sxs-lookup"><span data-stu-id="c3728-343">IP address with right wildcard</span></span>

<span data-ttu-id="c3728-344">**Запись:**`1.2.3.4/*`</span><span class="sxs-lookup"><span data-stu-id="c3728-344">**Entry**: `1.2.3.4/*`</span></span>

- <span data-ttu-id="c3728-345">**Разрешить совпадение** **и блокировку:**</span><span class="sxs-lookup"><span data-stu-id="c3728-345">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="c3728-346">1.2.3.4/b</span><span class="sxs-lookup"><span data-stu-id="c3728-346">1.2.3.4/b</span></span>
  - <span data-ttu-id="c3728-347">1.2.3.4/baaaa</span><span class="sxs-lookup"><span data-stu-id="c3728-347">1.2.3.4/baaaa</span></span>

### <a name="examples-of-invalid-entries"></a><span data-ttu-id="c3728-348">Примеры недействительных записей</span><span class="sxs-lookup"><span data-stu-id="c3728-348">Examples of invalid entries</span></span>

<span data-ttu-id="c3728-349">Следующие записи являются недействительными:</span><span class="sxs-lookup"><span data-stu-id="c3728-349">The following entries are invalid:</span></span>

- <span data-ttu-id="c3728-350">**Отсутствующие или недействительные значения домена:**</span><span class="sxs-lookup"><span data-stu-id="c3728-350">**Missing or invalid domain values**:</span></span>

  - <span data-ttu-id="c3728-351">contoso</span><span class="sxs-lookup"><span data-stu-id="c3728-351">contoso</span></span>
  - <span data-ttu-id="c3728-352">\*.contoso.\*</span><span class="sxs-lookup"><span data-stu-id="c3728-352">\*.contoso.\*</span></span>
  - <span data-ttu-id="c3728-353">\*.com</span><span class="sxs-lookup"><span data-stu-id="c3728-353">\*.com</span></span>
  - <span data-ttu-id="c3728-354">\*PDF</span><span class="sxs-lookup"><span data-stu-id="c3728-354">\*.pdf</span></span>

- <span data-ttu-id="c3728-355">**Под диктовка текста или без интервалов символов:**</span><span class="sxs-lookup"><span data-stu-id="c3728-355">**Wildcard on text or without spacing characters**:</span></span>

  - <span data-ttu-id="c3728-356">\*contoso.com</span><span class="sxs-lookup"><span data-stu-id="c3728-356">\*contoso.com</span></span>
  - <span data-ttu-id="c3728-357">contoso.com\*</span><span class="sxs-lookup"><span data-stu-id="c3728-357">contoso.com\*</span></span>
  - <span data-ttu-id="c3728-358">\*1.2.3.4</span><span class="sxs-lookup"><span data-stu-id="c3728-358">\*1.2.3.4</span></span>
  - <span data-ttu-id="c3728-359">1.2.3.4\*</span><span class="sxs-lookup"><span data-stu-id="c3728-359">1.2.3.4\*</span></span>
  - <span data-ttu-id="c3728-360">contoso.com/a\*</span><span class="sxs-lookup"><span data-stu-id="c3728-360">contoso.com/a\*</span></span>
  - <span data-ttu-id="c3728-361">contoso.com/ab\*</span><span class="sxs-lookup"><span data-stu-id="c3728-361">contoso.com/ab\*</span></span>

- <span data-ttu-id="c3728-362">**IP-адреса с портами:**</span><span class="sxs-lookup"><span data-stu-id="c3728-362">**IP addresses with ports**:</span></span>

  - <span data-ttu-id="c3728-363">contoso.com:443</span><span class="sxs-lookup"><span data-stu-id="c3728-363">contoso.com:443</span></span>
  - <span data-ttu-id="c3728-364">abc.contoso.com:25</span><span class="sxs-lookup"><span data-stu-id="c3728-364">abc.contoso.com:25</span></span>

- <span data-ttu-id="c3728-365">**Неописуемые подражательные знаки:**</span><span class="sxs-lookup"><span data-stu-id="c3728-365">**Non-descriptive wildcards**:</span></span>

  - \*
  - <span data-ttu-id="c3728-366">\*.\*</span><span class="sxs-lookup"><span data-stu-id="c3728-366">\*.\*</span></span>

- <span data-ttu-id="c3728-367">**Средние подкарды:**</span><span class="sxs-lookup"><span data-stu-id="c3728-367">**Middle wildcards**:</span></span>

  - <span data-ttu-id="c3728-368">conto \* so.com</span><span class="sxs-lookup"><span data-stu-id="c3728-368">conto\*so.com</span></span>
  - <span data-ttu-id="c3728-369">conto~so.com</span><span class="sxs-lookup"><span data-stu-id="c3728-369">conto~so.com</span></span>

- <span data-ttu-id="c3728-370">**Двойные подкарды**</span><span class="sxs-lookup"><span data-stu-id="c3728-370">**Double wildcards**</span></span>

  - <span data-ttu-id="c3728-371">contoso.com/\*\*</span><span class="sxs-lookup"><span data-stu-id="c3728-371">contoso.com/\*\*</span></span>
  - <span data-ttu-id="c3728-372">contoso.com/\*/\*</span><span class="sxs-lookup"><span data-stu-id="c3728-372">contoso.com/\*/\*</span></span>